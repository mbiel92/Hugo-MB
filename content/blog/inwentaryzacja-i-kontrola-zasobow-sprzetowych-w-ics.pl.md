+++
lang="pl-PL"
title="Inwentaryzacja i kontrola zasobów sprzętowych w ICS"
date="2020-05-07"
author="Józef Sulwiński, Michał Stępień"
image="/blog/Inwentaryzacja_kontrola_sprzetowa_systemow_ICS.png"
tags=['czwartki OT']
+++

W celu zapewnienia prawidłowej ochrony cybernetycznej dla środowisk OT,
konieczne jest uzyskanie odpowiedzi na pytania: co powinniśmy lub chcemy
chronić oraz w jaki sposób powinniśmy to robić. Aby zaadresować te
zagadnienia, niezbędne jest poznanie elementów komponentów środowiska
OT.

## Dlaczego inwentaryzacja zasobów sprzętowych jest tak ważna dla bezpieczeństwa systemów automatyki przemysłowej

Cykl życia systemów OT jest znacznie dłuższy niż systemów IT i może
wynosić nawet kilka dekad. Podczas tak długiego okresu w złożonych
instalacjach przemysłowych mogą zachodzić zmiany i modernizacje systemów
sterowania, które nie były w należyty sposób udokumentowane. Z naszych
doświadczeń wynika, że często informacja na temat aktualnej architektury
i konfiguracji środowiska dostępna jest jedynie w głowach kluczowych
pracowników.

W zapewnieniu właściwej ochrony cybernetycznej urządzeń w ICS ważną rolę
odgrywają mechanizmy identyfikacji komponentów rozwiązań, monitoringu
komunikacji oraz wykorzystania zasobów systemów teleinformatycznych. Jak
pokazuje doświadczenie, posiadanie bieżących informacji o
funkcjonujących urządzeniach oraz specyfice ich pracy jest podstawowym
elementem budowania aktywnej ochrony.

Poniżej przedstawiamy listę wyzwań, które są związane z inwentaryzacją
sprzętową środowiska OT, i mogą się pojawić na drodze do wprowadzania
programu zapewnienia cyberbezpieczeństwa systemów automatyki.

### Wyzwania związane z programem poprawy cyberbezpieczeństwa w środowisku OT

**1.** inwentaryzacja zasobów sprzętowych -
właściwy wybór środków technicznych i organizacyjnych umożliwiających
przeprowadzenie spisu lub weryfikacji spisu ze stanem bieżącym w
określonym czasie,

**2.** zapewnienie aktualności inwentaryzacji
zasobów sprzętowych,

**3.** wprowadzanie warunkowej blokady
dostępu do sieci OT nieautoryzowanym urządzeniom, np. stacje robocze
zewnętrznych integratorów maszyn i instalacji technologicznych.

**W tym artykule odpowiemy na pytania dotyczące inwentaryzacji zasobów
sprzętowych:**

-   jaka jest rola inwentaryzacji w kontekście bezpieczeństwa OT?
-   jakie są metody inwentaryzacji?
-   jakie systemy mogą wspierać inwentaryzację?

Przedstawimy również przykładowy rezultat identyfikacji urządzeń OT z
wykorzystaniem rozwiązania Guardian firmy Nozomi Networks.

### Rola inwentaryzacji w kontekście bezpieczeństwa OT

Istotnym składnikiem bezpieczeństwa OT jest zbudowanie zdolności do
zarządzania podatnościami komponentów rozwiązań. Wiedza na temat
podatności identyfikowanych dla rozwiązań OT jest powszechnie dostępna
(np. na stronie [Common Vulnerabilities and
Exposures](https://cve.mitre.org/)). Dla skutecznego zarządzania
bezpieczeństwem kluczowa jest zdolność do oceny, czy opublikowana
podatność dotyczy sprzętu i oprogramowania w wersjach, które
wykorzystujemy. Bez kompletnej wiedzy o komponentach automatyki
przemysłowej działających w naszych instalacjach nie możemy tego ocenić.
Posiadanie kompletnej i aktualnej informacji o architekturze i
konfiguracji rozwiązań OT stanowi podstawę do jakichkolwiek działań
związanych z eliminacją podatności.

## Sposoby inwentaryzacji zasobów w środowisku OT

-   inwentaryzacja manualna (spis z natury),
-   inwentaryzacja automatyczna -- pasywna,
-   inwentaryzacja automatyczna -- aktywna (selektywna).

Poniżej postaramy się przybliżyć każdą z tych metod.

### Metoda manualna

Podejście do inwentaryzacji zasobów sprzętowych ICS zazwyczaj rozpoczyna
się od wykorzystania metody manualnej, czyli spisu z natury. Jest to
jedyna metoda, która umożliwia objęcie inwentaryzacją wszystkich
urządzeń automatyki, nie ograniczając się jedynie do środowiska sieci
Ethernet, czy szerzej IP. Warto przy tej okazji zaznajomić się z
diagramami P&ID (Piping and instrumentation diagram). O ile służby
utrzymania ruchu potrafią interpretować te diagramy, o tyle dla
specjalistów ds. cyberbezpieczeństwa mogą w pierwszej chwili wydawać się
nie lada wyzwaniem.

### Inwentaryzacja automatyczna pasywna

Metoda ta wykorzystuje agregację oraz analizę danych komunikacji
sieciowej między komponentami rozwiązań OT i zakłada, że rozwiązanie
monitorujące nie inicjuje bezpośredniej komunikacji z urządzeniami w
sieci.

Inwentaryzacja pasywna zazwyczaj pozwala na wyodrębnienie podstawowych
informacji, takich jak:

-   adresy IP oraz fizyczne adresy komunikujących się urządzeń,
-   numery portów,
-   wykorzystywane protokoły komunikacyjne (także te przemysłowe),
-   nagłówki pakietów zawierających metadane nt. urządzeń
    uczestniczących w komunikacji (jeżeli dostępne).

Metoda ta jest mało inwazyjna, a jej ograniczeniem jest zdolność
identyfikacji jedynie tych urządzeń, które w czasie analizy ruchu
sieciowego komunikowały się między sobą -- może nie wykryć urządzeń
uśpionych lub komunikujących się z niską, względem czasu prowadzenia
analizy, częstotliwością. Pomimo braku bezpośredniej interakcji z
monitorowanymi systemami, niektórzy dostawcy systemów sterowania nie
pozwalają na uruchomienie takiego oprogramowania w środowisku
produkcyjnym ze względu na obawy przed potencjalnie niekorzystnym
wpływem na parametry jakościowe komunikacji w sieci.

Zastosowanie pasywnej inwentaryzacji pozwala na uzyskanie informacji
niezbędnych do stworzenia podstawowego modelu ruchu. Zebrane dane mogą
posłużyć do procesu uczenia oprogramowania stosowanego do monitoringu
ruchu sieciowego oraz detekcji zdarzeń (rozwiązań IDS).

**Wiodącymi na rynku rozwiązaniami służącymi do automatyzacji
inwentaryzacji z użyciem metod pasywnych są: Guardian firmy Nozomi
Networks, TenableOT, CyberX. Seqred opracował również własne rozwiązanie
do tego celu, które w wybranych scenariuszach zastosowań stanowić może
prostszą do wdrożenia i tańszą alternatywę.**

#### **Przykładowy rezultat identyfikacji urządzeń OT z wykorzystaniem Guardian firmy Nozomi Networks**

Poniżej przedstawiamy przykłady urządzeń oraz protokołów przemysłowych
zidentyfikowanych w ramach monitoringu z użyciem rozwiązania Guardian.
Narzędzie zidentyfikowało urządzenia sieciowe oraz stacje robocze
komunikujące się m.in. z wykorzystaniem protokołów przemysłowych
**ModbusTCP** oraz **IEC 60870-5:104.**

![](/blog/Identyfikacja-urzadzen-OT-Guardian-Nozomi-Networks.jpg)

Pełną listę protokołów rozpoznawanych przez rozwiązanie Nozomi Networks
można znaleźć [na stronach
producenta.](https://www.nozominetworks.com/downloads/US/Nozomi-Networks-Protocol-Support-List.pdf)

Wyniki pasywnej identyfikacji urządzeń zazwyczaj wymagają weryfikacji i
uzupełnienia, np. na podstawie selektywnego spisu z natury lub przez
analizę danych agregowanych w logach wybranych urządzeń.

### Inwentaryzacja automatyczna - aktywna (selektywna)

Metoda inwentaryzacji aktywnej bazuje na formułowaniu aktywnych zapytań
do pojedynczych urządzeń OT (w tym sterowników, stacji operatorskich
oraz inżynierskich). W jej wyniku otrzymujemy pełniejsze, niż w metodzie
pasywnej, informacje o komponentach, takie jak:

-   rodzaj oraz model sprzętu,
-   wersja firmware'u i software'u,
-   skonfigurowane oraz aktywne usługi,
-   informacje diagnostyczne,
-   dane o wydajności,
-   niekiedy także dane o historycznych zdarzeniach w postaci logów.

Narzędzia do automatycznej inwentaryzacji aktywnej często wykorzystują
funkcje interfejsów urządzeń lub protokołów dedykowane pierwotnie do
parametryzacji przez oprogramowanie inżynierskie. Z tego powodu ich
wpływ na działanie instalacji jest przewidywalny. W ten sposób
producenci narzędzi do inwentaryzacji aktywnej adresują ryzyko
potencjalnych zakłóceń i niepożądanego wpływu na proces.

**Wiodące dostępne narzędzia wspierające automatyczną inwentaryzację
aktywną to: Forge firmy Honeywell, Guardian firmy Nozomi Networks,
TenableOT.**

#### **Przykładowy wynik aktywnej identyfikacji urządzeń OT z wykorzystaniem narzędzia Guardian firmy Nozomi Networks**

W celu prezentacji rozwiązania, przeprowadzono selektywne aktywne
skanowanie w środowisku testowym. Pozyskano informacje o przemysłowym
sterowniku PLC. Ustalono m.in. model urządzenia, numer seryjny, nazwy
producenta oraz wersje firmware'u.

![](/blog/Guardian-Nozomi-Networks-Aktywna-identyfikacja-urzadzen-OT-.jpg)

Zastosowanie aktywnej inwentaryzacji pozwala na uzyskanie informacji
niezbędnych do pozyskania listy urządzeń wraz z wersjami zainstalowanego
oprogramowania i znacząco rozszerza wiedzę o urządzeniach pozyskaną w
ramach automatycznej inwentaryzacji pasywnej.

W kolejnym odcinku przeanalizujemy, którą z metod inwentaryzacji
najlepiej zastosować w do określonych potrzeb środowiska ICS.
Zaprezentujemy także zagadnienia związane z aktualnością listy zasobów
OT oraz prowadzeniem rejestru urządzeń automatyki.


## Którą z metod inwentaryzacji zastosować do określonych potrzeb środowiska ICS?

Podstawowym kryterium wyboru optymalnej dla danego środowiska metody
inwentaryzacji powinien być cel gromadzenia danych.

Jeśli zebrane dane będą wykorzystane do budowy systemu wykrywania i
zapobiegania włamaniom (IDS/IPS) w oparciu o model ruchu zalecana jest
**automatyczna pasywna metoda inwentaryzacji.**

**Metody aktywne, szczególnie selektywną,** warto rozważyć, jeśli celem
jest pozyskanie danych na potrzeby prowadzenia programu zarządzania
podatnościami. Dzięki nim uzyskamy informacje o wersjach, w jakich
występują urządzenia w naszej infrastrukturze oraz o występujących
lukach bezpieczeństwa.

Przy wyborze metody inwentaryzacji dodatkowo należy uwzględnić aspekty
związane z:

**a.** bezpieczeństwem przeprowadzenia
inwentaryzacji, w tym zapewnieniem warunków bezpieczniejszego stosowania
metod selektywnych,

**b.** możliwością automatyzacji oraz
zapewnienia aktualności informacji w zmieniającym się środowisku.

### Bezpieczeństwo przeprowadzenia inwentaryzacji

Jednym z kluczowych czynników determinujących wybór metody
inwentaryzacji jest jej oddziaływanie na bezpieczeństwo ludzi,
instalacji oraz ciągłości procesu. Metoda manualna zwykle zaliczana jest
do metod nieinwazyjnych, czyli takich, które nie mają wpływu na proces
(np. przeglądanie dokumentacji). Inaczej wygląda to w przypadku
automatycznych metod inwentaryzacji:

**a. metoda automatyczna pasywna** jest
zazwyczaj mniej inwazyjna od metod aktywnych. Czasami wymaga
rekonfiguracji urządzeń sieciowych np. w celu skopiowania ruchu
(ustawienia mirror portu). Istnieje tutaj zagrożenie dla ciągłości
procesu związane z m.in. z potencjalnym wyczerpaniem zasobów
przeznaczonych do obsługi standardowej komunikacji między urządzeniami
(np. sterownikami, a systemem SCADA) na switchu lub routerze
przemysłowym,

**b. metoda automatyczna selektywna aktywna**
jest bardziej inwazyjna, ponieważ oprócz standardowego monitoringu
ruchu, oprogramowanie wykonuje zapytania do urządzeń sieciowych (np.
sterowników) m.in. w celu ustalenia wersji oprogramowania lub pozyskania
danych diagnostycznych.

Metoda selektywna dostarcza bardziej szczegółowych danych, ale ze
względu na wysyłanie komunikatów do urządzeń automatyki, przy jej
stosowaniu należy zachować szczególne środki ostrożności.

**Warunki, które powinny zostać spełnione, aby poprawić bezpieczeństwo
korzystania z metody automatycznej selektywnej aktywnej:**

-   skanowanie powinno zostać przeprowadzane punktowo (dla wybranych
    adresów IP),
-   należy oszacować wielkość ruchu sieciowego, który zostanie
    wygenerowany przez aktywne działania oraz zweryfikować wynikające z
    niego obciążenie względem standardowych parametrów pracy sieci.

**Dodatkowe warunki organizacyjne i techniczne, które należy uwzględnić
przed rozpoczęciem inwentaryzacji:**

-   uzgodnienie ze służbami utrzymania ruchu i/lub dostawcą zakresu
    działań aktywnych,
-   wcześniejsze przeprowadzenie inwentaryzacji manualnej środowiska OT,
-   oszacowanie ryzyka negatywnego wpływu działań aktywnych na elementy
    środowiska OT w oparciu o wyniki inwentaryzacji manualnej.

Metoda aktywna związana jest z możliwym występowaniem ograniczeń ze
strony środowiska ICS, które zazwyczaj nie występują dla środowiska IT.
Przy analizie ryzyka negatywnego wpływu skanowania na systemy automatyki
warto uwzględnić **ryzyka techniczne.** Zaliczamy do nich:

-   brak mechanizmów kontroli zasobów bazujących na funkcji jakości
    usług (QoS). Ruch wygenerowany w wyniku skanowania może doprowadzić
    do ograniczenia dostępnego pasma dla bieżącej komunikacji pomiędzy
    urządzeniami produkcyjnymi,
-   brak możliwości obsłużenia dodatkowych zapytań kierowanych np. do
    sterowników przemysłowych. Przestarzałe urządzenia mają znacznie
    ograniczoną pamięć RAM, co uniemożliwia obsługę nadmiarowej
    komunikacji (wydzielenie dodatkowego bufora),
-   ograniczenie ilości równoczesnych połączeń (sprzętowych lub
    programowych). Skanowanie może wykorzystać dostępne zasoby do
    nawiązania nowych połączeń, a istniejące urządzenia OT, które np.
    inicjują komunikację okazjonalnie, utracą tę możliwość,
-   błędna implementacja obsługi protokołu IP oraz ograniczona zdolność
    obsługi zapytań może doprowadzić do restartu urządzenia w przypadku
    otrzymania komunikatu, który spowoduje nieoczekiwanie, błędne
    wykonanie funkcji.

W celu uniknięcia niektórych ryzyk technicznych związanych ze
skanowaniem, zwłaszcza zatrzymania procesu na skutek błędnych
mechanizmów obsługi komunikacji, proponowane jest przeprowadzenie testów
komponentów automatyki w wyizolowanym środowisku (test próbki). W wyniku
takiej analizy przeprowadzonej przez Seqred zidentyfikowaliśmy błąd,
który pozwalał na zdalny reset urządzenia automatyki.

[Przeczytaj więcej testowaniu urządzeń metodą
fuzzowania](https://seqred.pl/fuzzowanie_afl)

Innym podejściem jest weryfikacja informacji o podatnościach (lukach
bezpieczeństwa) urządzeń prezentowanych w ogólnodostępnych źródłach (np.
cvedetails.com). Warto sprawdzić opublikowane dane pod kątem możliwego
unieruchomienia urządzenia w trakcie przeprowadzania aktywnej
inwentaryzacji. Pomóc w tym może prowadzenie rejestru urządzeń
automatyki.

### Prowadzenie rejestru urządzeń automatyki - zmniejszenie ryzyka przypadkowego zatrzymania urządzeń podczas skanowania

Stosowanie automatycznych metod inwentaryzacji pasywnej oraz aktywnej
poprzedzone jest manualną identyfikacją systemów. Otrzymane wyniki można
przedstawić np. w formie listy. Poniżej przedstawiono przykłady, jak
może wyglądać lista urządzeń.

**Lista 1: Wzór rejestru wspierającego identyfikację znanych podatności
urządzeń automatyki**

![](/blog/rejestr-urzadzen-OT-wspierajacy-identyfikacje-podatnosci.jpg)

Informacje o tym, jakie urządzenia i w jakich wersjach znajdują się w
infrastrukturze można próbować pozyskać od integratora systemu lub
działu utrzymania ruchu. Oprócz podstawowych informacji rejestr powinien
zawierać adnotację o osobach odpowiedzialnych za aktualizację (np. w
celu informowania o nowoodkrytych podatnościach) oraz o tym, czy została
przeprowadzona kontrola bezpieczeństwa (np. pod kątem bezpieczeństwa
konfiguracji).

**Lista 2: Wzór rejestru wspierającego zarządzanie komponentami sieciowymi**

![](/blog/rejestr-urzadzen-OT-wspierajacych-zarzadzanie-komponentami-sieciowymi.jpg)

Dla metody manualnej podstawowe informacje można pozyskać z dokumentacji
urządzenia lub wizji lokalnej (np. odczytując adresy fizyczne z obudowy
urządzenia). Oprócz typowych pól, warto uwzględnić informacje o tym, czy
urządzenie zostało dopuszczone do pracy w naszej sieci OT (np. po
uprzednim sprawdzeniu poprawności konfiguracji).

Dobre praktyki wskazują, że rejestr powinien zawierać co najmniej spis
wszystkich instalacji technologicznych, w które zaangażowane są
elektroniczne programowalne układy sterowania lub regulacji. Dodatkowo
należy uwzględnić komponenty inteligentne, takie jak: stacje robocze,
stacje inżynierskie, napędy, zarządzalne switche oraz routery. Warto
zwrócić uwagę, że w procesie inwentaryzacji nie należy ograniczać się
jedynie do urządzeń posiadających łącze Ethernet czy Wi-fi.
Inwentaryzacji powinny być poddane również urządzenia z innymi typami
interfejsów komunikacyjnych, np. RS232/RS422/RS485 czy USB, gdyż mogą
one stanowić potencjalny punkt dostępu do sieci OT przez niepożądane
osoby.

Tak przygotowany rejestr manualny, może stanowić wprowadzenie do
automatycznych metod pozyskiwania informacji o systemach automatyki.
Niestety ze względu na zmieniające się środowisko ICS oraz regularnie
odkrywane nowe luki bezpieczeństwa urządzeń, lista szybko ulega
przedawnieniu. Warto zadbać o jej uzupełnianie oraz weryfikację wraz z
cykliczną aktualizacją urządzeń przez służby IT oraz OT. Dla systemów
ICS wskazane jest wówczas wykorzystanie automatycznych metod
inwentaryzacji zasobów.

### Automatyzacja oraz zapewnienie aktualności wyników inwentaryzacji w zmieniającym się środowisku

Ze względu na modernizacje, rozbudowy czy modyfikacje środowiska OT
utrzymywanie aktualności rejestru bez wsparcia specjalizowanych
systemów, jest nieefektywne. Wykorzystywanie wyłącznie ręcznych metod
inwentaryzacji zasobów jest czasochłonne oraz podatne na błędy ludzkie.
Otrzymana lista może nie zawierać wszystkich komunikujących się
urządzeń, zwłaszcza takich, które nie widnieją na schematach
architektury sieciowej i znajdują się w niedostępnych miejscach
(utrudnione jest przeprowadzenie wizji lokalnej).

Zagadnienie jest jeszcze bardziej złożone, gdy przedsiębiorstwo prowadzi
działalność w różnych lokalizacjach lub gdy służby odpowiedzialne za
utrzymanie ruchu dedykowane są dla konkretnego wydziału i nie komunikują
się pomiędzy sobą.

Podłączenie zewnętrznych urządzeń do sieci OT przez partnerów
zewnętrznych takich, jak integratorzy czy pracownicy tymczasowi,
pozostaje niezauważone przez manualne, wykonywane jednorazowo
inwentaryzacje (np. w przypadku prowadzenia rejestru tylko własnych
zasobów).

[Przeczytaj: jak bezpiecznie korzystać z nośników wymiennych w sieciach ICS](https://seqred.pl/bezpieczne_usb/)

Aby zapewnić aktualność rejestru oraz konfiguracji w zmiennym środowisku
OT istnieją rozwiązania umożliwiające automatyczną i ciągłą detekcję
urządzeń oraz wspierające proces zarządzania.

#### **Przykładowy rezultat automatycznej inwentaryzacji zasobów z wykorzystaniem Guardian firmy Nozomi Networks**

Narzędzie Guardian firmy Nozomi Networks pozwala na eksport listy
urządzeń i wspiera prowadzenie rejestrów urządzeń automatyki. W
podstawowej funkcjonalności umożliwia stworzenie modelu ruchu w trybie
uczenia, który zostanie wykorzystany do alarmowania o nietypowych
zdarzeniach sieciowych, np. pojawieniu się nowych, niezidentyfikowanych
hostów w sieci (np. komputer integratora). Poniższy zrzut ekranu
przedstawia podstawowe informacje na temat urządzeń uzyskane w wyniku
pasywnego monitoringu oraz selektywnego aktywnego skanowania środowiska
ICS.

## Inwentaryzacja oprogramowania urządzeń automatyki ICS - rejestr konfiguracji z Tenable OT

W środowisku ICS oprócz urządzeń realizujących funkcje stało programowe,
takie jak dedykowane sterowniki sprzętowe, istnieją komponenty
posiadające możliwości przeprogramowania. Do takich urządzeń zaliczamy
systemy DCS, sterowniki PLC oraz systemy SCADA. W celu ochrony systemów
przemysłowych, wyżej wymienione komponenty powinny być zabezpieczone
przez dostępem osób nieuprawnionych, wszelkie zdalne działania związane
z konfiguracją lub parametryzacją powinny być monitorowane, a
niedozwolona aktywność zablokowana.

Jednym z dostępnych na rynku rozwiązań dedykowanych dla środowiska ICS,
które wspiera proces zarządzania oprogramowaniem komponentów
przemysłowych jest Tenable OT. W niniejszym artykule chcemy przedstawić
w szczególności funkcjonalności tego rozwiązania pozwalające na:

**a.** **monitorowanie bezpieczeństwa i stałości kodu źródłowego** w celu weryfikacji, czy program urządzenia
nie został zmodyfikowany i wykonywane przez sterowniki funkcje są zgodne
z oczekiwaniami integratora lub technologa,

**b.** **detekcję zdarzeń związanych z odczytem lub zmianą konfiguracji,** np. z pobraniem oprogramowania ze
sterownika, wymuszeniem/ forsowaniem wyjść fizycznych,

**c** **detekcję znanych podatności firmware'u** w celu zabezpieczenia urządzeń przed wykorzystaniem
publicznie znanych podatności przez atakujących np. do zatrzymania
instalacji.

### Monitorowanie bezpieczeństwa i stałości kodu źródłowego

Jednym z efektów działań hakerów zainteresowanych środowiskiem
przemysłowym może być przeprowadzona w trudny do zauważenia sposób
modyfikacja programu sterowania w celu wyrządzenia fizycznych szkód (np.
jak miało to miejsce 10 lat temu w przypadku ataku Stuxnet) lub
doprowadzenie do zatrzymania systemów automatyki ICS. Jednym z
podstawowych detekcyjnych mechanizmów kontrolnych jest zastosowanie
oprogramowania monitorującego, którego zadaniem jest wykrywanie oraz
podwiadamianie o wykryciu nieautoryzowanych działań w systemach IT, czy
w przypadku Tenable OT, w systemach ICS. Oprócz monitoringu ruch
sieciowego wewnątrz sieci OT, pozwala to również na analizę wykonywania
funkcji logicznych przez urządzenia automatyki (np. sterowniki PLC).
Omawiane oprogramowanie, oprócz działań czysto detekcyjnych, wspiera
również działania korekcyjne, np. lokalizuje zmienione fragmenty
programu oraz prezentuje historię modyfikacji kodu źródłowego.

 

#### **Lokalizacja zmian logiki sterowania urządzeń OT w TenableOT**

[[![](/blog/Tenable-OT-lokalizacja-zmian-logiki-sterowania-urzadzen-OT.jpg)

Powyższy przykład pokazuje różnice w obrębie programu źródłowego
realizowane przez sterownik programowalny. W stosunku do poprzedniej
konfiguracji w bloku programowym została usunięta zmienna (Flap), a w
innym miejscu dodane (N7, MSG_Read_Data).

### Rejestr zdarzeń dostępu do konfiguracji

Posiadanie aktualnej wiedzy o działaniach takich, jak: odczyt
konfiguracji sterowników, wejście w tryb monitorowania stanu urządzeń,
porównanie bloków funkcyjnych pozwala na podjęcie działań chroniących
konfigurację zanim atakujący zmodyfikują program sterowania i wyrządzą
szkody fizyczne. W świecie IT standardem jest wyposażanie rozwiązań
bezpieczeństwa w mechanizmy rejestracji oraz analizy dzienników
systemowych czy śladów audytowych (ang. Audit trails). Omawiane
rozwiązanie Tenable OT przenosi, tę bez wątpienia najlepszą praktykę, do
świata OT.

Raport działania programu wygenerowany w TenableOT zawiera kompleksowe
informacje o dostępie do konfiguracji w tym zadań odczytu lub
modyfikacji. Wyniki obejmują m.in. zagregowaną listę zidentyfikowanych
czynności wraz z godziną zarejestrowania ostatniego zdarzenia, ilość
wystąpień danego typu ze wskazaniem rodziny sterowników, których ono
dotyczyło. Zaprezentowany poniżej raport zawiera informacje o aktywacji
wymuszania stanów wejść / wyjść (Force) niezależnie od realizacji logiki
sterowania, co może wskazywać na testowanie urządzeń podczas wdrożenia
czy diagnostyki lub próbę ataku.

#### **Rejestr zdarzeń dostępu do konfiguracji urządzeń automatyki w TenableOT**

![](/blog/Tenable-OT-rejestr-zdarzen-dostepu-do-konfiguracji-urzadzen-automatyki.jpg)

Oprócz działań reaktywnych na zdarzenia cybernetyczne, osoby
odpowiedzialne za bezpieczeństwo systemów automatyki mogą podjąć kroki
pozwalające na utrudnieniu atakującym dostępu do urządzeń poprzez
usuwanie znanych luk bezpieczeństwa w oprogramowaniu komponentów ICS.

### Identyfikacja znanych podatności firmware'u

Działania pozwalające na redukcję ryzyka ataków cybernetycznych poprzez
aktualizowanie oprogramowania urządzeń automatyki przemysłowej wymagają
posiadania listy luk bezpieczeństwa, które występują w infrastrukturze.
Oprócz metod manualnych, istnieją sposoby automatyczne wspierające
proces takiej inwentaryzacji. Oprogramowanie TenableOT umożliwia
wykonanie selektywnych zapytań do urządzeń, a co za tym idzie pozwala na
identyfikację wersji oprogramowania oraz porównanie zgromadzonej wiedzy
z bazą informacji o znanych lukach bezpieczeństwa. Użytkownicy
oprogramowania informowani są m.in. o rodzaju podatności, skali
zagrożenia oraz wersji firmware'u urządzeń ICS, których ono dotyczy.

#### **Identyfikacja znanych podatności w TenableOT**

![](/blog/Tenable-OT-Identyfikacja-znanych-podatnosci.jpg)

Oprogramowanie wyposażone w mechanizmy detekcji znanych luk pomaga w
prowadzeniu rejestru na potrzeby zarządzania aktualizacjami komponentów
ICS, w tym gromadzeniu wiedzy w celu niezwłocznej instalacji poprawek na
urządzeniach OT.

**Źródła:**\
[Stuxnet - Modus Operandi](https://www.sans.org/cyber-security-summit/archives/file/summit-archive-1493844778.pdf)

**W kolejnych odcinkach powiemy więcej na temat metod poprawy bezpieczeństwa związanych z zarządzaniem podatnościami oraz opublikujemy przykładowe kolejne wyniki działania oprogramowania, które umożliwia detekcję luk bezpieczeństwa urządzeń ICS.**

Zapraszamy do lektury nowego cyklu artykułów na temat środków kontroli
stosowanych w systemach ICS. Poruszać będziemy następujące tematy:

**1.** inwentaryzacja i kontrola zasobów
sprzętowych dla środowiska ICS\
**2.** inwentaryzacja i kontrola zasobów
oprogramowania w środowisku przemysłowym\
**3.** metody zarządzania lukami w
zabezpieczeniach (podatnościami)\
**4.** kontrolowane korzystanie z uprawnień
administracyjnych\
**5.** bezpieczna konfiguracji sprzętu oraz
oprogramowania na urządzeniach mobilnych, laptopach, stacjach roboczych
i serwerach\
**6.** utrzymanie, monitorowanie i analiza
dzienników zdarzeń (logów)