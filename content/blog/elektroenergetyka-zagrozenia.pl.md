+++
lang="pl-PL"
title="Elektroenergetyka XXI wieku - ewolucja zagrożeń"
date="2019-10-14"
author="Krzysztof Graj"
image="/blog/Elektroenergetyka_zagrozenia.jpg"
tags=['automatyka przemysłowa', 'bezpieczeństwo OT', 'infrastruktura krytyczna']
+++

Do niedawna zagrożenia fizyczne i naturalne stanowiły największe, jeśli
nie jedyne niebezpieczeństwo dla prawidłowego funkcjonowania systemów
energetycznych. Wraz z pojawieniem się inteligentnych sieci i
zautomatyzowanych urządzeń, energetyka stała się wrażliwym celem
cyberataków zakłócających prawidłowe działanie systemów generacji i
dystrybucji prądu.

Rok 2010 był dla polskich energetyków szczególnie trudny, ponieważ
warunki pogodowe powodowały oblodzenia linii elektroenergetycznych,
które padały jedna za drugą. Pierwsza poważna awaria wydarzyła się w
styczniu tego roku w rejonie województwa świętokrzyskiego - wówczas
dostaw prądu pozbawionych było ponad 25 tysięcy gospodarstw. Po raz
kolejny aura dała o sobie znać na końcu grudnia tego samego roku, kiedy
- ponownie z powodu oblodzenia linii elektroenergetycznych - awaria
dotknęła niemal całej północnej Polski. Szczególnie podatne na zerwania
okazały się przewody odgromowe, które często były pierwszym kamykiem
lawiny zdarzeń.

W tamtym czasie zagrożenia świata realnego stanowiły większe
niebezpieczeństwo, niż ataki w cyberprzestrzeni. Od ataku na wirówki do
wzbogacania uranu w Natanz w Iranie minęło wówczas zaledwie kilka
miesięcy i świat dopiero budził w sobie świadomość tego, z jaką mocą
cyberataki mogą wpłynąć na gospodarkę.

## Niezawodność sieci, czyli uzależnienie od AI{ .article-section }

Dla większości gałęzi przemysłu przyszłość rysuje się bardzo podobnie --
jest to maksymalizacja automatyzacji procesów i zarządzania zdarzeniami,
czyli wprowadzenie algorytmów i elementów sztucznej inteligencji, w celu
wyeliminowania błędów ludzkich. Tworzone i wdrażane obecnie algorytmy,
nie tylko potrafią reagować na zaistniały problem, ale również posiadają
wiedzę o zdarzeniach, jakie miały miejsce w przeszłości i na tej
podstawie potrafią analizować bieżące trendy zachowań i poziomy
parametrów poszczególnych elementów. Pozwala to na sterowanie procesami
w sposób zapobiegający rozwojowi niebezpiecznych sytuacji. Każdy nowy
przypadek jest poddawany bieżącej analizie, aby mógł zasilić bazę danych
algorytmu i tym samym go udoskonalać.

Taki sam proces realizowany jest też obecnie w elektroenergetyce, co
powoduje, iż ta branża także musi kierować się w stronę integracji
wszystkich elementów systemu w jeden dynamiczny i jednocześnie
harmonijny organizm.

## Energetyczny cyberorganizm{ .article-section }

Czujniki i elementy automatyki przemysłowej umieszczone na stacjach
transformatorowych, w krytycznych punktach sieci przesyłowych oraz w
elektrowniach są ze sobą coraz bardziej zintegrowane i od siebie
zależne. Do tego dochodzi kontrola punktów odbioru (inteligentne
liczniki) oraz algorytmy optymalizujące przepływy mocy w sieci. Taki
proces wymaga umiejętnej konfiguracji sieci danych łączącej wszystkie te
elementy i sterowniki (szczegóły w artykule: [Segmentacja sieci w ochronie systemów przemysłowych](https://seqred.pl/segmentacja-sieci-ot/)) oraz niezwykłej
dbałości o zabezpieczenie całej sieci przed atakami cybernetycznymi.

Najsłabszym ogniwem tego ekosystemu niestety nadal pozostaje człowiek co
uwydatnia się na niemal wszystkich poziomach zabezpieczenia sieci i
działających w niej elementów. Najbardziej popularne są nadal **ataki
phishingowe** polegające na rozsyłaniu emaili z niebezpiecznym
załącznikiem, którego otwarcie daje atakującym dostęp do sieci, w której
znajduje się zainfekowany komputer lub powoduje różnego rodzaju szkody w
sieci IT. Atak taki jest jednak ryzykowny i najczęściej nie daje
atakującym długotrwałego dostępu do systemów ofiary ataku.

Bardziej skuteczne mogą okazać się ataki, w których dostęp do systemów
zarządzania siecią elektroenergetyczną następuje stopniowo na przykład
poczynając od firmowej sieci WiFi lub dostępów wykorzystywanych przez
serwisantów, którzy zajmują się utrzymaniem elementów stacji
transformatorowych bądź elektrowni.

## Hakerzy wchodzą tylnimi drzwiami{ .article-section }

Każda szczelina w pozornie jednolitej strukturze zabezpieczeń może być
tą, która będzie początkiem pasma problemów prowadzących do pozbawienia
odbiorców dostaw energii elektrycznej czy degradacji parametrów
jakościowych sieci energetycznej, poprzez wyłączenie lub też nawet
trwałe uszkodzenie urządzeń. Im dłuższy jest czas nieuprawnionego
dostępu do sieci IT i systemów sterowania siecią elektroenergetyczną,
tym więcej czasu atakujący mają na przygotowanie bardziej wymyślnych
form działania i tym większym zaskoczeniem może okazać się atak.

Najlepszym przykładem jest **malware Stuxnet** stworzony wspólnie przez
Izrael i USA, w celu uszkodzenia irańskich wirówek do wzbogacania uranu.
Złośliwe oprogramowanie powodowało, że odczyty parametrów pracy urządzeń
pozostawały na właściwym poziomie, gdy jednocześnie urządzenia były
wysterowane do wartości skrajnych powodujących ich uszkodzenie.
Nietrudno jest sobie wyobrazić atak, w którym administrator systemu
zarządzania siecią elektroenergetyczną otrzymuje prawidłowe wskazania
pracy urządzeń, a jednocześnie w tym samym czasie następują takie
odchylenia parametrów sieci, które powodują uszkodzenia transformatorów.
Przy odpowiednim przygotowaniu ataku część sterowników stacji
transformatorowej nie zareaguje, ponieważ również one będą otrzymywały
prawidłowe wskazania wartości prądu, napięcia, synchronizacji bądź
temperatury, pomimo że rzeczywistość będzie zupełnie odmienna. Byłaby to
skomplikowana operacja, ale czy na pewno niemożliwa?

## O krok przed atakującymi{ .article-section }

W celu zapewnienia bezpieczeństwa systemów energetycznych tak ważne są
następujące działania:

**Etap planowania, budowy i rozwoju systemu:**

-   zakup odpowiednich elementów infrastruktury sieciowej wraz z
    komponentami systemu cyberbezpieczeństwa,
-   kontrola łańcucha dostaw sprzętu i oprogramowania w celu
    zabezpieczenia się przed wprowadzeniem do sieci elementów
    posiadających podatności [(Cybersecurity Bill of
    Materials)](https://seqred.pl/cbom/) lub elementów celowo
    zmodyfikowanych w celu pozyskania nieuprawnionych dostępów do
    infrastruktury,
-   [segmentacja sieci IT,](https://seqred.pl/segmentacja-sieci-ot/)
-   minimalizacja ilości uruchamianych serwisów, protokołów oraz
    wystawianych portów.

**Szkolenia:**

-   rozwój kompetencji i świadomości zagrożeń we własnej organizacji
    poprzez przeprowadzanie regularnych szkoleń dla pracowników z
    zakresu cyberbezpieczeństwa [(szkolenia Security
    Awareness),](https://seqred.pl/cyberbezpieczenstwo-systemow-przemyslowych/)
-   szkolenia z zakresu bezpieczeństwa informacji, uświadamiające
    konsekwencje publikowania lub przekazywania danych potencjalnie
    wrażliwych, których wykorzystanie może wspomagać proces ataku
    cybernetycznego na naszą firmę.

**Utrzymanie sieci i systemów:**

-   korzystanie z usługi typu [Threat
    Intelligence](https://seqred.pl/threat-intelligence/) -- bieżące
    śledzenie informacji na temat nowych form zagrożeń, planowanych
    atakach oraz przygotowywanych programach typu malware,
-   regularny update reguł na firewall'ach oraz upgrade oprogramowania,
-   monitoring, kontrola i inwentaryzacja urządzeń, oprogramowania oraz
    narzędzi wprowadzanych do sieci,
-   testy sieci IT i jej zabezpieczeń poprzez regularnie przeprowadzane
    pentesty oraz operacje RedTeam,
-   procedury przyznawania, odbierania i modyfikacji dostępów do sieci
    dla własnych pracowników oraz klientów, dostawców i serwisantów
    zewnętrznych,
-   prowadzenie polityki zmiany haseł na wszystkich poziomach dostępu,
-   kontrola danych udostępnianych publicznie przez firmę (OSINT).

Jest to w rzeczywistości nieustanna praca, dzięki której systemy i
procedury dotyczące cyberbezpieczeństwa będą choćby o krok wyprzedzały
możliwości atakujących.