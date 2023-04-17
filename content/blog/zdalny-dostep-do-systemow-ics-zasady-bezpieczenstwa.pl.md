+++
lang="pl-PL"
title="Zdalny dostęp do systemów ICS – zasady bezpieczeństwa"
date="2020-07-22"
author="Michał Stępień, Łukasz Dudkowski"
image="/blog/Bezpieczny-zdalny-dostep-ICS.jpg"
tags=['Czwartki OT']
+++

Podstawowym sposobem działania w sytuacji wymuszonej przez Covid-19 było umożliwienie pracy zdalnej z systemami sterowania. Nagła i dynamiczna sytuacja utrudniała wybór oraz wdrożenie bezpiecznego rozwiązania. Według raportu Cionet, Deliotte, VMware aż 2/3 firm wprowadziło rozwiązania VPN, natomiast tylko 1/3 firm dodatkowo wprowadziło zmiany w architekturze systemów IT. Daje to podstawy to stwierdzenia, że przy wprowadzeniu rozwiązań do pracy zdalnej mogły nie zostać uwzględnione aspekty związane z cyberbezpieczeństwem.


Sytuacja pandemiczna przyniosła właścicielom instalacji przemysłowych wyzwania związane z:

*   ograniczeniem dostępu do pracowników,
*   koniecznością pracy zdalnej z systemami automatyki,
*   utrudnieniami w dostępie do systemów dla partnerów, czy zewnętrznych ekspertów.

Rozwiązaniem jest zdalny dostęp, który umożliwia prowadzenie zleconych prac serwisowych, ale niesie ze sobą także ryzyka dla bezpieczeństwa i ciągłości działania systemów ICS.

Na rynku istnieją rozwiązania dedykowane do zapewnienia bezpiecznego dostępu do systemów automatyki przemysłowej, takie jak Secure Remote Access firmy Honeywell, które na etapie projektowania, wdrożenia i użytkowania zapewniają wysoki poziom bezpieczeństwa oraz niezbędne funkcjonalności ułatwiające bezpieczną pracę i zarządzanie dostępem do sieci ICS.

Firmy często korzystają jednak z mniej zaawansowanych metod zdalnego dostępu, takich jak udostępnienie protokołu RDP, czy VNC bezpośrednio do Internetu, co stanowi realne ryzyko ataku hakerskiego na naszą infrastrukturę.

Wybierając lub weryfikując posiadane rozwiązanie zdalnego dostępu dedykowane do systemów automatyki musimy pamiętać, że jego wdrożenie to zazwyczaj dodatkowa powierzchnia ataku na system i należy przestrzegać wielu zasad związanych z cyberbezpieczeństwem.

W ramach serii wpisów przedstawimy listę siedemnastu rekomendacji, których należy przestrzegać projektując lub decydując o wyborze rozwiązania do zdalnego dostępu.  
Mamy nadzieję, że porady pomogą również uszczelnić lub przemodelować obecnie stosowane rozwiązania.

> Segmentacja sieci – podstawa bezpiecznej architektury przedsiębiorstwa
> ----------------------------------------------------------------------

Przedstawienie pierwszych dwóch zasad wymaga przywołania podstaw segmentacji sieci przedsiębiorstwa. Prawidłowo wdrożona segmentacja sieci pozwala na ograniczenie powierzchni ataku dostępnej dla atakujących po przełamaniu wstępnych zabezpieczeń (np. uzyskanie dostępu do podsieci). Poszczególne segmenty sieci oddzielone są za pomocą aktywnych urządzeń sieciowych (np. firewall), na których implementuje się odpowiednie reguły zezwalające tylko na niezbędny ruch sieciowy. Pomiędzy warstwami mogą istnieć strefy (DMZ), które odseparowane są od sieci chronionych (np. OT) oraz korporacyjnych, a urządzenia, które się w nich znajdują zostają wyodrębnione w wyniku analizy funkcjonalnej oraz analizy ryzyka.

[Przeczytaj więcej o segmentacji sieci](https://seqred.pl/segmentacja-sieci-ot/)

> Zasada 1: Unikaj kaskadowego przenoszenia ryzyka
> ------------------------------------------------

[![](/blog/bezpieeczny_zdalny_dostep.jpg)](/blog/bezpieeczny_zdalny_dostep.jpg)

Schemat pokazuje powszechnie stosowaną architekturę, której zastosowanie wiąże się ze sporym ryzykiem ze względu na umożliwienie wejścia do strefy DMZ i stacji inżynierskiej, a następnie z tego poziomu do urządzeń ICS przy użyciu jednego protokołu.

Na schemacie wskazano niewielki wycinek architektury sieci – fragment systemu, w którym zdalny dostęp do sieci OT został zapewniony z wykorzystaniem stacji pośredniczącej (serwera terminali).

Powyższa architektura może umożliwiać wykorzystanie luk np. w zabezpieczeniach RDP, z których przykładowo korzysta złośliwe oprogramowanie Dharma. Propagacja w środowisku sieciowym może doprowadzić do uzyskania nieautoryzowanego dostępu do serwera terminali, a następnie do sieci OT. Jeśli niezbędne jest takie połączenie np. z sieci korporacyjnej do serwera w DMZ, a następnie do urządzenia w sieci OT, to zastosowanie różnych usług, protokołów powoduje konieczność wykorzystania przez atakujących więcej niż jednej podatności. Taka architektura zwiększa pracochłonność zadania oraz może zredukować powierzchnię ataku.

> Zasada 2: Unikaj połączeń przychodzących, white-listuj oraz monitoruj połączenia wychodzące. Akceptuj połączenia po stronie chronionej
> --------------------------------------------------------------------------------------------------------------------------------------

Dobrą praktyką jest ustawienie reguł na aktywnych urządzeniach (np. firewall) lub zastosowanie rozwiązania typu Forge firmy Honeywell zapewniającego zdalny dostęp w taki sposób, aby połączenie było inicjowane ze strony chronionej (sieci OT).

Otwieranie portów wejściowych z sieci korporacyjnej oraz OT na stałe powoduje ryzyko, w którym dostępna na określonym porcie usługa np. ze znanymi luki bezpieczeństwa jest eksponowana dla strony atakującej. Wykorzystanie znanej podatności może doprowadzić do przejęcia kontroli nad urządzeniem. Wykorzystanie mechanizmu, w którym usługa ze strony chronionej – ICS nawiązuje komunikację ze stroną mniej zaufaną (DMZ) ogranicza powierzchnię ataku. Tak inicjowana komunikacja powoduje, że komunikaty przechodzące przez FW oraz ustanowiona sesja dostępna jest tylko tymczasowo, co znacznie utrudnia (ale nie uniemożliwia) zadanie atakującym.

Nie wolno stosować praktyki, która umożliwia nawiązanie połączenia z zewnątrz, zwłaszcza w kontekście możliwości wystawienia urządzeń do Internetu (nie tylko bezpośredniego).

[Przeczytaj więcej o atakach na systemy przemysłowe przez luki bezpieczeństwa zdalnego dostępu](https://seqred.pl/atak-przez-zdalny-dostep-ics/)

> Zasada 3: Korzystaj z uwierzytelniania dwuskładnikowego
> -------------------------------------------------------

Atakujący, w swoich działaniach ukierunkowanych na uzyskanie nieautoryzowanego dostępu do sieci, oprócz próby użycia typowych haseł oraz loginów wykorzystują m.in. wiedzę pozyskaną ze źródeł otwartych (OSINT), w tym dane pozyskane z wycieków. Dzięki nim znajdują oni loginy oraz hasła logowania, które często wykorzystywane są przez użytkowników zarówno do uwierzytelnienia do ich prywatnej poczty oraz do systemów korporacyjnych. Próba zalogowania pozyskanymi poświadczeniami (lub ich kombinacjami) do urządzeń wystawionych bezpośrednio do Internetu lub pośrednio do rozwiązań umożliwiających zdalny dostęp m.in. z wykorzystaniem RDP, może zapewnić atakującym dostęp do komponentów w sieci OT.

Skuteczną ochronę może stanowić wykorzystanie dwuskładnikowego uwierzytelniania, które od użytkownika podejmującego próbę logowania wymaga np. posiadania odpowiedniego tokena lub klucza sprzętowego, jak ma to miejsce np. w przypadku urządzeń Yubico. Powoduje to dodanie kolejnego stopnia zabezpieczeń jednocześnie wymuszając fizyczną akceptację dostępu np. do systemu operacyjnego lub aplikacji po stronie chronionej. Dzięki temu zalogowanie do stacji inżynierskiej lub uruchomienie aplikacji pozwalającej na modyfikację programu sterownika PLC wymaga potwierdzenia np. ze strony służb utrzymania ruchu w fabryce (poprzez naciśnięcie przycisku na fizycznym kluczu dostępu).

[Przeczytaj więcej o białym wywiadzie (OSINT)](https://seqred.pl/osint-bialy-wywiad/)

> Zasada 4: Ograniczaj ryzyko nieautoryzowanego dostępu
> -----------------------------------------------------

Zalecane jest wprowadzenie oraz stosowanie właściwych procedur uzyskiwania zaufanego dostępu do zasobów wyłącznie na czas serwisowy, po przeprowadzeniu czynności sprawdzających i akceptacji „po bezpiecznej stronie”. Przykładem takiego scenariusza może być inicjacja połączenia ze strony chronionej na zewnątrz segmentu sieci przez osobę posiadającą odpowiednie uprawnienia, np. inżyniera serwisu technicznego. W praktyce odbywa się to np. poprzez wygenerowanie odpowiedniego linku przekazywanego stronie wykonującej prace na odległość. Nawiązanie połączenia musi być potwierdzone po stronie chronionej. Wyzwanie może stanowić potwierdzanie połączenia w systemach przemysłowych, np. w instalacjach podwodnych, niezamieszkanych obszarach lub instalacjach bezzałogowych. W takich systemach możliwe jest wdrożenie procesu zatwierdzania połączeń z wykorzystaniem pomocniczych środków technicznych np. odbiorników fal radiowych.

> Zasada 5: Monitoruj i identyfikuj niedozwolony ruch
> ---------------------------------------------------

W celu ochrony systemów OT należy kontrolować, czy i jakie dane z sieci OT mogą być wysyłane z/do sieci OT. Nie należy dopuszczać możliwości połączenia tunelowego typu end-to-end pomiędzy serwerem z sieci przemysłowej ICS oraz serwerem po niezaufanej stronie (zarówno w sieci korporacyjnej, jak i dostawcy Internetu). Szyfrowany kanał komunikacji utrudnia, jeśli nie uniemożliwia, inspekcję ruchu, może więc ominąć środki kontrolne pozwalające na detekcję naruszeń bezpieczeństwa. Przykładową praktyką jest przerwanie połączenia tunelowego na firewall’u, inspekcja ruchu oraz reorganizacja tunelu do węzła leżącego po stronie chronionej.

Ograniczaj nieautoryzowaną działalność
--------------------------------------

> Zasada 6: Konfiguruj zdalnych użytkowników oraz dostępne usług
> --------------------------------------------------------------

Systemy dostępu do sieci OT oferują możliwość konfigurowania zdalnych użytkowników oraz dostępnych usług. W bardziej rozbudowanych systemach osoba nadzorująca ma możliwość podglądu wykonywanych działań z poziomu narzędzia, a sesje oraz logi operacji mogą być nagrywane oraz odtwarzane.

> Zasada 7: Zarządzaj sesjami
> ---------------------------

Systemy dedykowane do sieci OT oferują funkcjonalności zarządzania sesjami. Takie rozwiązanie oferuje np. platforma Forge firmy Honeywell, która umożliwia obsługę otwartych połączeń, a w momencie wykrycia nieprawidłowości możliwość zakończenia połączenia. Czynność ta nie powinna odbywać się automatycznie, lecz być świadomą decyzją inżyniera, czy operatora, ponieważ nieoczekiwane przerwanie połączenia podczas prowadzenia krytycznych procesów, może doprowadzić do utraty kontroli lub nawet zniszczenia instalacji.

> Zasada 8: Ogranicz zdalny dostęp do komponentów OT
> --------------------------------------------------

Zdalny dostęp do węzłów urządzeń automatyki powinien zostać ograniczony do minimum z uwzględnieniem administracyjnych oraz technicznych środków kontroli. Operacje zdalne na systemach, które realizują kluczowe funkcje bezpieczeństwa nie powinny być dostępne z zewnątrz, ponieważ niesie to ryzyko wpływania na krytyczne funkcje systemu.

**Kolejne zasady – już wkrótce!**

*   ograniczenie ryzyka nieautoryzowanego dostępu,
*   ograniczenie nieautoryzowanej działalności,
*   ograniczenie ryzyka uzyskania poufnych danych,
*   ograniczenie ryzyka włamania,
*   ograniczenie ryzyka infekcji złośliwym oprogramowaniem.

Stay tuned!

**Źródła:**

*   Zasady przygotowane na podstawie artykułu [Sinclair Koelemij “Remote access”](https://otcybersecurity.blog/2020/06/13/remote-access/amp/)
*   [Raport Cionet, Deliotte, VMware “Odmrażanie pracy”](https://cdn2.hubspot.net/hubfs/4295993/PL_Digital-Excellence/CIONET%20Odmra%C5%BCanie%20Pracy%20wnioski%20z%20badania%20maj%202020.pdf)