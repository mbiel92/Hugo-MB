+++
lang="pl-PL"
title="Tagowanie pamięci"
date="2019-02-25"
author="@tals0n0r"
image="/blog/procesory.jpg"
tags=['procesory']
+++

> ### W czwartym kwartale 2018 roku ARM przedstawił nową wersję architektury procesorów pod zbiorczą nazwą ARMv8.5-A. Jedno z wprowadzonych usprawnień to Memory Tagging Extension (MTE): tagowanie pamięci ze wsparciem sprzętowym. Jaki jest cel wprowadzenia MTE?

Większość błędów bezpieczeństwa w kernelu linux, bibliotekach czy aplikacjach napisanych w C/C++ związanych jest z niepoprawnym dostępem do pamięci. Najczęstsze z nich to przepełnienie bufora na stosie lub stercie (stack or heap buffer overflow), dostęp do zwolnionej pamięci (use-after-free) i użycie niezainicjowanej pamięci (uninitizalized memory). Przypomnijmy, na czym polegają wspomniane błędy i jakie mogą powodować konsekwencje.


Przepełnienie bufora to sytuacja, w której program w trakcie swojego wykonywania odwołuje się do pamięci poza wyznaczonym obszarem (na stosie lub stercie). Znakomita większość podatności bezpieczeństwa to **liniowe przepełnienia bufora** lub bezpośredni dostęp poza obszar bufora (out-of-bounds access):  
[– Heartbleed](http://heartbleed.com)  
[– Total Meltdown](https://nvd.nist.gov/vuln/detail/CVE-2018-1038)  
[– GHOSTBug](https://nvd.nist.gov/vuln/detail/CVE-2015-0235)  
[– Venom](https://venom.crowdstrike.com/)

Ostatnie błędy znalezione w Chrome::  
[– CVE-2018-6153](https://www.cvedetails.com/cve/CVE-2018-6153/)  
[– CVE-2018-6120](https://www.cvedetails.com/cve/CVE-2018-6120/)

Błędy odnalezione w kernelu linuxowym:  
[– CVE-2018-14633](https://www.cvedetails.com/cve/CVE-2018-14633/)  
[– CVE-2018-12233](https://www.cvedetails.com/cve/CVE-2018-12233/)

**Błędy typu use-after-free,** gdy program odwołuje się do fragmentu pamięci, który został poprzednio zwolniony:  
[– CVE-2018-16065](https://www.cvedetails.com/cve/CVE-2018-16065/)  
[– CVE-2018-17182](https://www.cvedetails.com/cve/CVE-2018-17182/)  
[– CVE-2018-10879](https://www.cvedetails.com/cve/CVE-2018-10879/)

**Błędy niezainicjalizowanej pamięci,** które mogą prowadzić do ujawnienia fragmentu pamięci:  
[– CVE-2017-5103](https://www.cvedetails.com/cve/CVE-2017-5103/)  
[– CVE-2017-5102](https://www.cvedetails.com/cve/CVE-2017-5102/)  
[– Red Hut Bugzilla](https://bugzilla.redhat.com/show_bug.cgi?id=1584043)

> ## Narzędzia do odnajdywania błędów dostępu do pamięci{ .article-section }

Na rynku dostępnych jest kilka open-sourcowych narzędzi do przeprowadzenia skutecznej analizy pod kątem błędnego dostępu do pamięci. Najstarszym i najbardziej znanym jest **Valgrind** i jego moduł **Memcheck**, który został upubliczniony w lutym 2002 roku. Drugi, **AdressSanitizer (ASAN)**, został zaprezentowany ze wsparciem w kompilatorach LLVM 3.1 i GCC 4.8 w 2011 przez Google. ASAN jest w stanie odnaleźć błędy typu stack i heap buffer overflow, use-after-free, use-after-return, czy use-after-scope. Kolejnym narzędziem z tej rodziny jest **Memory Sanitizer (MSan)**, który odnajduje błędy związane z niezainicjalizowaną pamięcią. Dla audytowania kernela linuxowego zostały wprowadzone odpowiednio **kmemcheck** i **kasan**.

Użycie wspomnianych sanitizerów ma jednak kilka zauważalnych wad: narzędzia te utrzymują kopie fragmentów pamięci, czerwone strefy (red zones) i kwarantanny dookoła fragmentów stosu, sterty i obiektów globalnych. Taka forma testowania znacząco zwiększa zużycie pamięci i obciążenie procesora, dlatego narzędzia te są używane jedynie w fazie testów oraz jako wsparcie podczas przeprowadzania audytu kodu źródłowego pod kątem bezpieczeństwa, fuzzowania, czy ogólnie security hardeningu, a nigdy nie są używane w finalnych produktach.

> ## Tagowanie pamięci{ .article-section }

Innym podejściem do zapobiegania błędom dostępu do pamięci jest tagowanie pamięci (znane również jako kolorowanie pamięci). Zgodnie z tym podejściem, weryfikowany fragment pamięci zostaje wyrównany do rozmiaru TG (tag-granularity – granulacja tagu) i pokolorwany tagiem o rozmiarze TS (tag size – rozmiar tagu). Bity tagu w rozmiarze TS są umieszczane w nieużywanej części wskaźnika. W architekturze Aarch64 stanowi to do ośmiu najbardziej znaczących bitów 64-bitowego wskaźnika (dzięki TBI, top-byte-ignore). W trakcie alokacji pamięci, wylosowany tag zostaje oznaczony na całym obszarze zaalokawanej pamięci i powiązany z odpowiadającym mu wskaźnikiem. Podczas operacji ładowania i zapisu do wcześniej zaalokowanego fragmentu pamięci, tagi dla pamięci i wskaźnika są walidowane. Jeśli tagi różnią się zgłaszany jest wyjątek. Taki zabieg pozwala na odnalezienie większości błędów, takich jak stak and heap buffer overflow i use-after-free.

Przeanalizujmy alokację pamięci w rozmiarze 20 bajtów, gdy TS (tag-size) jest równy 4 bity, a TG (tag-granularity) 16 bajtów (obraz 1).

![](/blog/Memory_tagging_1-1.jpg)

Należy zaalokować 20 bajtów: alokator pamięci wyrównuje ten rozmiar do 32 bajtów ze względu na 16-bajtowe TG. Następnie alokator losuje tag (zaznaczony na zielono) i zapisuje w 4 (TS) najbardziej znaczących bitach wskaźnika oraz taguje pamięć, na którą wskazuje. Podczas dereferencji wskaźnika p na pozycji 32, wartość taga nie będzie zgodna pomiędzy wskaźnikiem p, a pamięcią z offsetu 32 i taki dostęp zostanie wyłapany (obraz 2). Zaznaczmy, że z powodu 16-bajtowego rozmiaru TG, dereferencja spod pozycji np. 20 nie zostanie wykryta, ponieważ tag wskaźnika i pamięci będą takie same.

![](/blog/Memory_tagging_2a-1.jpg)

Podobny zabieg zostanie przeprowadzony podczas dealokacji pamięci. W trakcie zwalniania fragmentu sterty, pamięć zostanie ponownie otagowana (analogicznie jak w przykładzie 3, pokolorowana na czerwono). Jeśli pozostanie wskaźnik (zielony) wskazujący na tę pamięć (czerwona po zwolnieniu) i nastąpi próba dereferencji, taki dostęp zostanie wykryty (obraz 3).

![](/blog/Memory_tagging_3a-1.jpg)

Tagowanie pamięci otrzymało wsparcie w kompilatorze Clang/LLVM i zostało nazwane **HWSAN** (hardware-assisted address sanitizer). Działa ono na architekturze Aarch64 dzięki TBI z rozmiarem tagów równym 4 bity i wyrównaniem do 16-bajtów. Walidacja tagów odbywa się jednak programowo: cały czas pozostaje spory narzut na zużycie procesora i rozmiar pliku wykonywalnego (do 2 razy). Pozytywnie za to spadło zużycie pamięci, które względem standardowych rozwiązań jest bardzo niskie, około 6 proc.

Aby rozwiązać problemy związane z niepoprawnym dostępem do pamięci i niską wydajnością dostępnych narzędzi, ARM zdecydował się na wprowadzenie sprzętowego wsparcia dla tagowania pamięci, Memory Tagging Extension. Implementacja będzie pozwalała na tagowanie pamięci z rozmiarem tagu 4 bitów i granulacją tagu w rozmiarze 16 bajtów. Jednocześnie zestaw instrukcji został powiększony o 15 nowych:

![](/blog/Memory_tagging-1.jpg)

> ## Co dalej?{ .article-section }

Pozostaje chwilę poczekać. Wsparcie dla tagowania pamięci dla procesorów ARM zostało wprowadzone do [GCC 9](https://gcc.gnu.org/git/?p=gcc.git;a=commit;h=3a861b7b9e2c3652dcbe8b44434650429199df56) i [LLVM](https://reviews.llvm.org/D52490), jednak należy wprowadzić jeszcze sporo optymalizacji. Oddzielnym problemem jest dostępność nowych procesorów ARMv8.5A: okres od prezentacji architektury do momentu produkcji gotowych układów przez producentów, takich jak Qualcomm czy Samsung to około 2 lata. Miejmy nadzieję, że układy SoC z nową architekturą szybko pojawią się na rynku: zaprezentowane rozszerzenie Memory Tagging Extension znacznie zmniejszy ilość potencjalnych błędów związanych z dostępem do pamięci w aplikacjach pisanych w C/C++.

[  
](https://reviews.llvm.org/D52490)

[**Referencje**  
](https://reviews.llvm.org/D52490)[– Arm A-Profile Architecture Developments 2018: Armv8.5-A](https://community.arm.com/processors/b/blog/posts/arm-a-profile-architecture-2018-developments-armv85a)  
– “Memory Tagging and how it improves C/C++ memory safety” by Kostya Serebryany: [pdf](https://arxiv.org/pdf/1802.09517.pdf) [video](https://www.youtube.com/watch?v=lLEcbXidK2o)  
[– Wikipedia](https://en.wikichip.org/wiki/arm/mte)


