+++
lang="pl-PL"
title="Cyber Kill Chain - co to jest i jak wykorzystać go do powstrzymania zaawansowanych atakó"
date="2020-08-05"
author="Sylwia Sławińska"
image="/blog/Cyber-kill-chain-grafika-edycja-ost.png"
tags=['analiza incydentów bezpieczeństwa']

+++

Z roku na rok notowana jest coraz większa liczba cyber ataków. Szacuje
się, że ich liczba z wykorzystaniem
[ransomware](https://seqred.pl/ransomware-co-to-jest-jak-sie-zabezpieczyc-jak-usunac/)
wzrasta o 350% rocznie¹. Pandemia Covid19 spowodowała również
zwiększenie liczby złośliwych maili o 600%². Jednym z podstawowych
elementów ochrony przed potencjalnymi atakami, jest zrozumienie anatomii
ataku i strategii stosowanych przez cyberprzestępców.

Specjaliści z dziedziny cyberbezpieczeństwa stworzyli kilka modeli
przedstawiających anatomię ataku. Opisali w nich poszczególne etapy oraz
metody i techniki wykorzystywane przez atakujących. W poniższym artykule
przedstawimy model Cyber Kill Chain -- jego etapy oraz sposoby mitygacji
działań napastników w każdym z tych etapów.

#### **Z tego artykułu dowiesz się:**

-   co to jest Cyber Kill Chain?
-   jaka jest jego geneza?
-   jakie wyróżnia etapy ataku cybernetycznego?
-   jak można się zabezpieczyć przed każdą z faz ataku?
-   jak wykorzystać model w praktyce?
-   wady Cyber Kill Chain.

W kolejnych artykułach przedstawione zostaną: Model Diamentowy, Mitre
[email protected](/cdn-cgi/l/email-protection) oraz model kill chain dla ICS, omówimy ich
zastosowanie oraz porównanie wad i zalet wszystkich opisanych modeli.

## Co to jest Cyber Kill Chain?

**Cyber Kill Chain** ilustruje strukturę skutecznego cyberataku.
Rozdziela on i systematyzuje działania atakujących na poszczególne etapy
zaczynając od zebrania informacji o celu, przez przygotowanie narzędzi i
dostarczenie złośliwego oprogramowania, aż po realizację celu ataku.
Pomaga zrozumieć i lepiej przygotować się na kierowane ataki takie jak:
kradzież danych, ataki z użyciem złośliwego oprogramowania, czy
zaawansowane ataki typu APTs (advanced persistent attacks). Zrozumienie
modelu kill chain pozwala zespołom ds. bezpieczeństwa IT wdrożyć
strategie i technologie mające na celu przerwanie łańcucha, a tym samym
uniemożliwienie realizacji ataku.

## Cyber Kill Chain -- wojskowe podejście do struktury ataków

Termin kill chain był pierwotnie używany jako pojęcie wojskowe związane
ze strukturą ataku. Jednym z wojskowych modeli kill chain jest "F2T2EA",
który obejmuje następujące fazy:

**1.** **Znajdź** -- zidentyfikowanie celu,

**2.** **Ustal** -- ustalenie lokalizacji celu,

**3.** **Trasa** -- monitorowanie ruchu celu,

**4.** **Cel** -- wybór odpowiedniej broni
lub środka do użycia na celu,

**5.** **Wykonanie** -- zastosowanie broni do
realizacji celu,

**6.** **Dokonanie oceny** -- ocena efektów
ataku.

Jest to zintegrowany i kompleksowy proces, który został opisany jako
łańcuch, ze względu na skojarzenie jego etapów z ogniwami łańcucha --
przerwanie dowolnego ogniwa powoduje przerwanie całego procesu. Jest to
skuteczna metoda obrony lub działania prewencyjnego.

## Etapy Cyber Kill Chain

Lockheed Martin w 2011 r. zaadaptował koncepcję wojskowego kill chainu
do bezpieczeństwa informacji, wykorzystując go jako metodę modelowania
włamań do sieci komputerowej. Skonstruował łańcuch składający się z
następujących etapów ataku:

![](/blog/Cyber-kill-chain-grafika-edycja-ost.png)

## Obrona przed cyberatakami z wykorzystaniem modelu Cyber Kill Chain

### Rozpoznanie

Atakujący zbiera informacje o celu. Może użyć metod manualnych lub
automatycznych skanerów służących do mapowania struktury organizacji,
znalezienia słabych punktów i luk pozwalających na ich wykorzystanie.
Próbuje zidentyfikować i zbadać istniejące systemy bezpieczeństwa takie
jak: firewalle, systemy zapobiegania włamaniom i mechanizmy
uwierzytelniania. Jako źródło informacji może wykorzystać OSINT.

**Cel obrony:** identyfikacja prób skanowania lub wyszukiwania
informacji.

**Metody obrony:**

-   okresowa analiza widoczności informacji dotyczących firmy i
    pracowników w sieci Internet i publicznie dostępnych rejestrach (np.
    [Shodan](https://seqred.pl/shodan-rekonesans-infrastruktury-it-ot/))
    i podejmowanie działań korygujących (usuwanie niepożądanych treści),
-   sprawdzanie logów pod kątem osób odwiedzających stronę internetową,
-   wykorzystanie narzędzi do rozpoznawania działań typowych dla fazy
    rekonesansu, takich jak np. skanowanie sieci lub domeny.

### Uzbrajanie

Atakujący wykorzystują informacje zdobyte na etapie rekonesansu, aby
przygotować złośliwe oprogramowanie oraz sposoby wykorzystania słabych
punktów. Zatrzymanie działań napastnika w tym etapie jest praktycznie
niemożliwe, ponieważ wszystkie czynności wykonywane są po jego stronie.
Wskazane jest, aby zidentyfikować słabe i mocne strony posiadanych
urządzeń i systemów, aby jak najlepiej przygotować się na prawdopodobny
atak. Identyfikacja słabych stron pozwala na ustalenie, którym aspektom
obrony należy poświęcić szczególną uwagę, ponieważ mogą stanowić
potencjalne wejście do systemów przez atakującego.

**Cel obrony:** identyfikacja własnych podatności oraz metod
zabezpieczenia kluczowych zasobów.

**Metody obrony:**

-   identyfikacja i utrzymanie aktualnej informacji o posiadanych i
    chronionych zasobach,
-   identyfikacja istniejących podatności we własnej organizacji oraz
    hardening kluczowych zasobów,
-   monitorowanie oraz analiza nowych podatności oraz instalowanie
    aktualizacji zawierających łatki bezpieczeństwa,
-   przeprowadzenie oceny podatności w celu priorytetyzacji wykrytych
    luk,
-   wykorzystanie threat intelligence w celu rozpoznania oraz
    przygotowania do możliwych nadchodzących zagrożeń.

### Dostarczanie

Atakujący podejmuje próbę dostarczenia przygotowanego złośliwego
oprogramowania do systemów organizacji lub wykorzystania
zidentyfikowanych słabych punktów. Popularnym sposobem jego dostarczenia
jest wysyłanie linków lub załączników z wykorzystaniem technik
phishingowych.

**Cel obrony:** wykrycie oraz uniemożliwienie pobrania złośliwego kodu.

**Metody obrony:**

-   zwiększenie poziomu świadomości zagrożeń poprzez edukację
    pracowników i współpracowników,
-   wdrożenie dodatkowych środków bezpieczeństwa, w tym firewalli,
    programów antywirusowych, sandboxów i innych narzędzi ochrony
    punktów końcowych,
-   wykorzystanie mechanizmów antyspamowych,
-   monitorowanie ruchu sieciowego w celu identyfikacji i aktywnego
    blokowania zagrożenia na podstawie pochodzenia oraz zawartości
    pakietów.

### Wykorzystanie

Wykorzystanie zidentyfikowanej podatności w systemie ofiary w celu
wykonania złośliwego kodu dostarczonego przez atakującego.

**Cel obrony:** uniemożliwienie wykonania złośliwego oprogramowania.

**Metody obrony:**

-   wykorzystanie SIEM (Security Information and Event Management) --
    oprogramowania do zarządzania informacjami oraz zdarzeniami
    bezpieczeństwa do badania logów i wykonania analiz w celu
    identyfikacji podejrzanych działań,
-   wykorzystanie narzędzi chroniących punkty końcowe, takich jak EDR
    (endpoint detection & response),
-   edukacja użytkowników w celu rozpoznawania złośliwego oprogramowania
    i odpowiedniego reagowania,
-   wykorzystanie rozwiązań typu threat intelligence, zasilających bazę
    wiedzy urządzeń chroniących typu program antywirusowy, IPS lub IDS.

### Instalacja

Instalacja złośliwego oprogramowania w systemie ofiary w celu uzyskania
zdalnego dostępu do środowiska.

**Cel obrony:** wykrycie napastnika, uniemożliwienie wykonywania
operacji.

**Metody obrony:**

-   HIPS (Host-based Intrusion Prevention System -- system do wykrywania
    i blokowania ataków w czasie rzeczywistym na urządzeniach końcowych)
    w celu ostrzegania lub blokowania próby instalacji na wspólnych
    ścieżkach,
-   okresowa kontrola zmian konfiguracji systemu w stosunku do
    konfiguracji wzorcowej (baseline),
-   sprawdzanie certyfikatów wszystkich podpisanych plików
    wykonywalnych,
-   separacja i segregacja uprawnień w celu uniemożliwienia instalacji,
-   dwuczynnikowe uwierzytelnianie.

### Dowodzenie i kontrola (C2)

Atakujący używa konsoli poleceń, aby móc zdalnie wykonywać komendy na
atakowanym komputerze w celu utrzymania i rozwijania ataku.

**Cel obrony:** wykrycie oraz przerwanie komunikacji między celem a
napastnikiem.

**Metody obrony:**

-   wymaganie korzystania z wewnętrznych serwerów proxy dla wszystkich
    rodzajów ruchu (m.in. http, DNS),
-   DNS sinkhole (serwer DNS zwracający niepoprawne nazwy domenowe) oraz
    zatrucie serwera nazw,
-   pasywne monitorowanie ruchu sieciowego oraz archiwizacja metadanych
    dotyczących konwersacji pomiędzy komponentami sieci,
-   monitorowanie sieci za pomocą NIDS (network Intrusion Detection
    System -- sieciowy system do wykrywania ataków w czasie
    rzeczywistym) w celu wykrycia niecodziennych aktywności.

### Realizacja celu

W końcowym etapie atakujący realizuje cele, którymi mogą być: wyciek
(naruszenie poufności danych), modyfikacja danych (naruszenie
integralności danych) lub zaszyfrowanie systemu (naruszenie dostępności
danych).

**Cel obrony:** powstrzymanie działań napastnika.

**Metody obrony:**

-   monitorowanie aktywności bazy danych,
-   natychmiastowa reakcja ekspertów na alerty,
-   wdrożony systematyczny proces reagowania na incydenty
    bezpieczeństwa,
-   wdrożony proces komunikacji kryzysowej,
-   przetwarzanie wrażliwych danych w wyseparowanych sieciach
    teleinformatycznych lub na wydzielonych stanowiskach,
-   stosowanie metod szyfrowania przetwarzanych danych (np. szyfrowanie
    nośników danych, szyfrowanie poczty e-mail),
-   systematyczne tworzenie kopii zapasowych na nośnikach off-line.

## Metody przerwania ataków

Aby przerwać Cyber Kill Chain zdefiniowane zostały następujące typy
działań obronnych:

**1.** -- określenie,
kiedy i jak napastnik przeprowadza rekonesans przeciwko organizacji lub
sieci,

**2.** **Odmowa (deny)** -- powstrzymanie
ataku poprzez uniemożliwienie ujawnienia informacji lub
nieautoryzowanego dostępu,

**3.** **Zakłócenie (disrupt)** -- zmiana lub
zatrzymanie przepływu informacji lub wycieku danych do atakującego,

**4.** **Degradacja (degrade)** --
ograniczenie skuteczności lub efektywności ataku,

**5.** **Zmylenie (deceive)** -- zakłócenie
ataku za pomocą niewłaściwego ukierunkowania atakującego lub
dezinformacji,

**6.** **Ograniczenie (contain)** --
ograniczenie zakresu ataku do poszczególnych segmentów sieci lub
organizacji.

## Macierz kontroli Cyber Kill Chain

Znajomość etapów kill chain, działań obronnych oraz czynności i
rozwiązań, które mogą zostać użyte przeciwko napastnikom, pozwala na
utworzenie Macierzy kontroli Cyber Kill Chain. Jej celem jest
identyfikacja mechanizmów kontrolnych, które organizacja wdrożyła jako
zabezpieczenia dla poszczególnych etapów ataku oraz określenie, w jaki
sposób mogą one przyczynić się do zakłócenia, zatrzymania lub eliminacji
cyberataku.

Przykładowa Macierz kontroli Cyber Kill Chain:

![](/blog/tabelka-cyber-kill-chain-ost.png)

Prezentowaną macierz można wykorzystać jako szablon w celu identyfikacji
posiadanych zasobów oraz przypisania im ról w ochronie systemów. Dzięki
niej łatwiejsza jest identyfikacja, na jakich etapach posiadane
zabezpieczenia pozwolą na obronę przed atakiem, a w których miejscach
należy zastosować dodatkowe środki ochrony.

## Wady klasycznego modelu Cyber Kill Chain

Model Cyber Kill Chain Lockheeda Martina jako narzędzie oceny zagrożeń
nie jest modelem idealnym. Głównym zarzutem, jest, że metodyka ta ma na
celu wzmocnienie tradycyjnych strategii obronnych opartych na
bezpieczeństwie sieci oraz zapobieganiu złośliwemu oprogramowaniu, które
nie są jedynymi wektorami ataków. Tradycyjny kill chain w
cyberprzestrzeni nie nadaje się do modelowania wewnętrznego zagrożenia,
np. pochodzącego od pracowników danej firmy, stąd potrzeba opracowania
oddzielnej strategii do postępowania z napastnikami z wewnątrz
organizacji. Dodatkowo za wadę uznaje się, że pierwsze etapy mają
miejsce poza bronioną siecią, co utrudnia identyfikację lub obronę przed
działaniami napastników w tych etapach.

## Zastosowanie Cyber Kill Chain

W ciągu 9 lat od stworzenia Cyber Kill Chain technologia oraz metody
przeprowadzania ataków istotnie ewoluowały -- pojawiły się nowe wektory
ataków oraz sposoby ich wykorzystania. Obecnie napastnicy pomijają
poszczególne etapy tego modelu, dodają nowe kroki lub je powtarzają.
Cyber Kill Chain jest nadal szeroko stosowany.\
Wykorzystanie go pozwala na określenie poziomu zabezpieczeń oraz
uniemożliwienie potencjalnemu napastnikowi przeprowadzenie ataku lub
istotne zmniejszenie jego skutków.

Cyber Kill Chain jest jedną z kilku metod pozwalających na zrozumienie
przebiegu cyberataków. Na przestrzeni ostatnich lat pojawiły się
kolejne, bardziej szczegółowe modele przedstawiające możliwe scenariusze
wrogich działań.

W kolejnych artykułach przedstawimy model diamentowy, Mitre
[\[email protected\]](/cdn-cgi/l/email-protection){.__cf_email__
cfemail="73320707331018"} oraz model kill chain dla ICS, omówimy ich
zastosowanie oraz porównanie wad i zalet wszystkich opisanych modeli.

**Źródła:**

**1.** [Cyber Security Statistics for
2019](https://www.cyberdefensemagazine.com/cyber-security-statistics-for-2019)

**2.** [ONZ: podczas pandemii liczba
złośliwych e-maili wzrosła o 600
proc.](https://www.cyberdefence24.pl/onz-podczas-pandemii-liczba-zlosliwych-e-maili-wzrosla-o-600-proc)

**3.** [Gaining the Advantage -- Applying
Cyber Kill Chain® Methodology to Network
Defense](https://www.lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/Gaining_the_Advantage_Cyber_Kill_Chain.pdf)

**4.** [How the Cyber Kill Chain can help you
protect against
attacks](https://sbscyber.com/resources/how-the-cyber-kill-chain-can-help-you-protect-against-attacks)

## Masz pytania dotyczące wykorzystania modelu Cyber Kill Chain? 

[Napisz do nas](/kontakt)