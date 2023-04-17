+++
lang="pl-PL"
title="Bezpieczeństwo: działy OT i IT - razem, czy oddzielnie?"
date="2020-04-02"
author="Michał Stępień"
image="/blog/Porownanie_OT_IT.jpeg"
tags=['czwartki OT']

+++

Cyberbezpieczeństwa w fabrykach, organizacjach, przedsiębiorstwach nie
można rozpatrywać oddzielnie dla działów IT oraz OT. Historycznie
pracownicy działów OT postrzegali warstwę IT jako zło konieczne,
niektórzy z nich nawet „chronili w zamkniętych szafach" swoją
infrastrukturę przed pracownikami działu IT. Instalacje aktualizacji np.
systemów operacyjnych mogły wiązać się z zakłóceniem monitoringu pracy
procesu poprzez unieruchomienie np. systemów SCADA.

Różnice oraz podobieństwa między systemami IT oraz OT nie dla wszystkich
są oczywiste. Kompleksowe zestawienie publikuje **Sarah Fluchs** w swoim
artykule **["Why OT has different needs than
IT"](https://medium.com/@fluchsfriction/why-ot-has-different-needs-than-it-18ba9baa36e7)**
i prezentuje różnice pomiędzy środowiskiem IT oraz OT z uwzględnieniem
różnych perspektyw m.in. warunków pracy, stosowanych technologii,
podejścia projektowego, dynamiki zmian oraz wymagań organizacyjnych.

W poniższym artykule omówię pokazane w tabeli zagadnienia wraz z
przykładami, które pozwolą na lepsze zrozumienie, dlaczego odmienne jest
postrzeganie systemów przez zespoły IT oraz OT.


![](/blog/Porownanie_OT_IT.jpg)

Źródło: [Sarah Fluchs "Why OT has different needs than IT"](https://medium.com/@fluchsfriction/why-ot-has-different-needs-than-it-18ba9baa36e7)


## Różnice między działami OT i IT

### 1. Warunki pracy

Serwery w sieci IT pracują zwykle w biurach lub w serwerowniach, które
są klimatyzowane. Ze względu na warunki pracy, zwykle mają dedykowane
zasilanie nie narzucające ograniczeń związanych z ilością doprowadzanej
energii do strefy np. zagrożonej wybuchem. W przypadku sieci OT szafy
obiektowe niejednokrotnie znajdują się na obiekcie w miejscach, w
których może występować duże zapylenie, czy wilgotność. Personel
niejednokrotnie prowadzi prace dezynfekcyjne z wykorzystaniem piany lub
gorącej wody, obudowy niejednokrotnie poddawane są działaniu tych
substancji. W przypadku zastosowań produkcyjnych, niejednokrotnie
pojawiają się wymagania związane ze stopniem ochrony np. IP55 dla szaf
sterowniczych. Oprócz wymagań dotyczących obudowy, specjalne wymagania
stawiane są urządzeniom wewnątrz szafy.

### 2. Stosowane technologie

Technologie biznesowe stosowane w sieciach IT niejednokrotnie są
dostępne „z półki" np. systemy SAP i wymagają dostosowania w zakresie
niezbędnych funkcjonalności do charakteru organizacji. W przypadku
systemów sterowania OT zwykle są programowane pod konkretne potrzeby i
właściwości typowe dla specyfiki procesu. Sterowniki oraz inne
komponenty inteligentne na korzystają z protokołów typowych dla
producentów urządzeń (choć są wyjątki). Ułatwieniem dla
automatyków-programistów jest wspólna platforma wykorzystywana do
programowania np. paneli operatorskich, sterowników programowalnych oraz
np. napędów, stąd ze względu na optymalizację czasu wdrożenia
preferowane są rozwiązania pochodzące od jednego dostawcy.

### 3. Podejście do projektowania

Analiza systemów IT związana jest z postrzeganiem systemu z punktu
widzenia „sieci" oraz działających „aplikacji", w przypadku OT system
rozpatrywany jako widok urządzeń (np. pomp, zbiorników, zaworów,
reaktorów itp.), których funkcjonowanie związane jest z wysterowaniem
konkretnych komponentów, odczytem sygnałów pomiarowych (np. temperatury,
objętości, przepływu). Projektowanie systemów IT odbywa się z
uwzględnieniem analizy bezpieczeństwa m.in. kanałów komunikacyjnych oraz
konfiguracji. Podejście projektantów systemów OT było na ogół odmienne
-- stawiano wymagania funkcjonalne, co do niezawodności oraz
bezpieczeństwa fizycznego „safety" raczej niż informacji „security".

### 4. Priorytety działania, cele bezpieczeństwa

Priorytety działania systemów IT obejmują zwykle wydajność,
funkcjonalność, bezpieczeństwo, dla systemów OT są to ciągłość produkcji
lub świadczenia usług, unikanie zdarzeń niebezpiecznych oraz kontrola
przekroczeń wartości granicznych.

Cele bezpieczeństwa stawione systemom IT obejmuje w kolejności m.in.
poufność, integralność i dostępność do danych. W przypadku systemów ICS
są to dostępność, niezawodność oraz determinizm funkcji. Powinna być
zapewniona także integralność danych, transmisja danych w czasie
rzeczywistym, bez opóźnień lub zakłóceń. W sieciach IT wymagania dotyczą
ponadto ochrony danych.

### 5. Dynamika zmian

Projektowany czas życia systemu IT to zwykle 3-5 lat, po tym czasie
będzie on przestarzały i będzie wskazana jego wymiana. Dla urządzeń OT
okres ten wynosi około 20 lat. Po tym czasie można przeprowadzić jego
modernizację w przypadku:

-   rekomendacji opartej na wynikach analizy ryzyka przeprowadzonej dla
    instalacji,
-   pozytywnego wyniku opłacalności inwestycyjnej projektu,
-   ograniczonej dostępności części zamiennych.

Modernizacja powinna być dokonana bez zbędnych przestojów.

Pod względem zmienności systemy IT cechują się większymi wymaganiami w
zakresie zarządzania użytkownikami, czy ich uprawnieniami. Grupy
użytkowników OT, w przypadku systemów procesowych, są na ogół bardziej
statyczne.

Sieci OT zwykle mają charakter statyczny, nie ewoluują w krótkim
horyzoncie czasowym. Architektura sieci IT zaś cechuje się dużą
zmiennością, skalowalnością.

### 6. Podejście organizacyjne

W przypadku systemów IT w dużych organizacjach zwykle istnieje
dedykowany zespół odpowiedzialny za fragment procesu (np. inne osoby
odpowiadają za bazy danych, inne za komunikację, jeszcze inne za bieżące
prace konserwacyjne). W przypadku OT pracownicy działów utrzymania ruchu
zwykle odpowiadają za całość procesu (m.in. komunikację między
urządzeniami, parametryzowanie urządzeń, wymianę wadliwych komponentów,
utrzymanie aktualności dokumentacji, bieżące prace konserwacyjne).

## Działy bezpieczeństwa IT i OT - razem, czy oddzielnie?

Współpraca między działami IT oraz OT jest ważna, dlatego, że odmienne
spojrzenia na systemy, a co za tym idzie dostrzeganie różnych zagrożeń
dla bezpieczeństwa systemów, mogą przyczynić się do uwzględnienia
potrzeb obu grup na etapie formułowania założeń projektowych, wdrażania
oraz późniejszego utrzymania systemów automatyki. Często przeszkodą w
realizacji tego celu pozostaje zagadnienie związane z niezrozumieniem
tych dwóch różnych perspektyw w kontekście systemów automatyki oraz
odmienne słownictwo branżowe stosowane w tych działach.