+++
lang="pl-PL"
title="MITRE ATT&CK – analiza przeprowadzonych ataków w celu skuteczniejszej ochrony"
date="2021-01-20"
author="Sylwia Sławińska"
image="/blog/Mitre_Attack.jpg"
tags=['analiza incydentów bezpieczeństwa']

+++

Aby pokonać wroga należy myśleć jak on – to przesłanka metodologii stojącej za stworzeniem modelu Mitre ATT&CK. Mitre ATT&CK to pierwsza baza wiedzy, która tak szczegółowo prezentuje anatomię ataku oraz wyróżnia taktyki i techniki wykorzystywane przez napastników w rzeczywistych atakach.

Dzięki znajomości tych działań możliwe jest stworzenie modelu zachowań napastników oraz określenie indywidualnych cech grup APT (Advanced Persistent Threats), w tym określenie jakich technik używają najczęściej, jakie branże atakują lub jakie podatności najczęściej wykorzystują. Korzystając z tej wiedzy specjaliści z branży bezpieczeństwa są w stanie przygotować adekwatne do zagrożeń środki techniczne oraz proceduralne niezbędne do przeciwdziałania atakom.

Po opublikowaniu modelu Mitre ATT&CK w 2015 roku, został on szybko przyjęty przez środowisko, ponieważ w odróżnieniu od [Cyber Kill Chain,](https://seqred.pl/cyber-kill-chain-co-to-jest-i-jak-wykorzystac-go-do-powstrzymania-zaawansowanych-atakow/) czy [Modelu Diamentowego,](https://seqred.pl/model-diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa/) nie bazuje on jedynie na ogólnych etapach ataku, ale zawiera spis technik wykorzystywanych do zainfekowania systemów, np. enumeracja połączeń sieciowych, czy zmiany stanu programu.

Wiedza ekspercka zawarta w modelu Mitre przyniosła mu ogromną popularność oraz spowodowała jego powszechne wykorzystanie, zarówno przez jednostki rządowe, sektor prywatny, firmy rozwijające produkty cyberbezpieczeństwa oraz podmioty zainteresowane cyberbezpieczeństwem.

#### **Z tego artykułu dowiesz się:**

*   co to jest Mitre ATT&CK?
*   poznasz 14 taktyk Mitre ATT&CK?
*   poznasz modele Enterprise, Mobile oraz ICS
*   dowiesz się, jak wykorzystać model Mitre ATT&CK
*   oraz jak wkomponować model Mitre w procesy bezpieczeństwa w firmie
*   poznasz ograniczenia modeli Mitre

[![Mitre Attack](/blog/Mitre_Attack.jpg "Mitre Attack")](/blog/Mitre_Attack.jpg "Mitre Attack")

> Co to jest Mitre ATT&CK?
> ------------------------

Mitre ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge) – to dostępna na całym świecie baza wiedzy na temat taktyk i technik stosowanych przez hakerów, oparta na rzeczywistych obserwacjach, wykorzystywana jako podstawa do opracowywania konkretnych modeli zagrożeń. Mitre ATT&CK została stworzona przez organizację Mitre wspierającą amerykańskie agencje rządowe.

Model Mitre składa się z 14 taktyk oraz przypisanych im technik ataku. Kolumny (taktyki) od lewej do prawej stanowią kolejne fazy ataku. Daną taktykę można realizować za pomocą różnych technik, ale w zależności od zamiarów napastnika nie wszystkie opisane w modelu taktyki muszą zostać wykorzystane.

Zbiór technik stosowanych podczas ataku nazywany jest profilem zachowania – procedurą, którą napastnik wykonywał, aby osiągnąć swój ostateczny cel atakując system.
![Mittre Attack techniki i taktyki](/blog/Mitre_Attak_wykres1-1.jpg "Mittre Attack techniki i taktyki")

> 14 taktyk Mitre Att&ck
> ----------------------

Model Mitre opisuje 14 taktyk:

**1\.** **Reconnaissance / Rekonesans** – gromadzenie informacji niezbędnych do zaplanowania przyszłych operacji,  
**2\.** **Resource development / Przygotowanie zasobów** – przygotowanie niezbędnych do przeprowadzenia ataku zasobów, narzędzi, itp.  
**3\.** **Initial access / Uzyskanie dostępu** – początkowy dostęp do sieci lub systemu ofiary,  
**4\.** **Execution / Wykonanie** – wykonanie złośliwego kodu,  
**5\. Persistence / Trwały dostęp** – sposoby na pozostanie w sieci, nawet po wyłączeniu komputera,  
**6\. Privilege escalation / Eskalacja uprawnień** – próba uzyskania wyższych uprawnień, np. administratora,  
**7\. Defense evasion / Maskowanie** – praktyki mające na celu uniknięcie wyrycia,  
**8\. Credential access / Pozyskanie danych logowania** – pozyskiwanie loginów, haseł, PIN-ów, itp.,  
**9\. Discovery / Rozpoznanie środowiska** – rozpoznanie środowiska ofiary, sprawdzenie do jakich zasobów można uzyskać dostęp,  
**10\. Lateral movement / Przemieszczanie** – przemieszczanie się po sieci ofiary z zainfekowanego urządzenia na kolejne,  
**11\. Collection / Gromadzenie** – gromadzenie dowolnego rodzaju danych,  
**12\. Command and control / Zdalna kontrola** – ustanowienie zdalnej kontroli nad zainfekowanym systemem,  
**13\. Exfiltration / Eksfiltracja** – pozyskiwanie danych w sposób trudny do wykrycia, np. za pomocą szyfrowanych tuneli,  
**14\. Impact / Impakt** – efekty działań atakującego na systemie ofiary, np. w przypadku ransomeware’u efektem działań będzie zaszyfrowanie danych.

> Enterprise, Mobile oraz ICS – modele opracowane przez Mitre
> -----------------------------------------------------------

Pierwszym opracowanym przez Mitre modelem był model Enterprise, który pokrywał największą powierzchnię cyberataków. W związku z coraz większą liczbą ataków na urządzenia mobilne, po wydaniu przez NIST listy zagrożeń dla urządzeń mobilnych, Mitre opracowało Model Mobile. Trzeci i najmłodszy to Model ICS, nakierowany na bezpieczeństwo systemów przemysłowych.

### Model Enterprise

Model opisuje działania, jakie atakujący może podjąć, aby doprowadzić do kompromitacji sieci korporacyjnej. Matryca zawiera informacje dla następujących platform: Windows, MacOS, Linux, PRE, AWS, GCP, Azure, Azure AD, Office 365, SaaS, Network.

Aktualna wersja modelu składa się z:

*   14 taktyk,
*   177 technik,
*   348 podtechnik.

### Model Mobile

Wraz ze wzrostem popularności urządzeń mobilnych stały się one wektorem ataku pozwalającym np. na wejście do sieci korporacyjnej, czy wykradanie danych. W 2016 roku NIST opublikował dokument prezentujący zagrożenia dla urządzeń mobilnych oraz ich infrastruktury.

Model Mitre ATT&CK for Mobile bazuje na Katalogu Zagrożeń Mobilnych NIST, dostarczając taktyki i technik stosowane w celu uzyskania dostępu do urządzeń mobilnych.

Aktualna wersja modelu składa się z:

*   14 taktyk,
*   86 technik.

### Model ICS

Systemy przemysłowe coraz częściej wykorzystują rozwiązania z zakresu IT, aby umożliwić łączność systemów przemysłowych z systemami korporacyjnymi lub umożliwić zdalny dostęp do nich. Należy pamiętać, że sieć korporacyjna może zostać wykorzystana jako wektor wejściowy do sieci ICS.

Mitre ATT&CK dla ICS to baza wiedzy przydatna do analizy działań, jakie atakujący może podjąć w sieciach przemysłowych (ICS) obejmujących systemy sterowania nadrzędnego i akwizycji danych (SCADA) oraz inne konfiguracje systemów regulacji i sterowania.

Aktualna wersja modelu składa się z:

*   11 taktyk,
*   81 technik.

> Jak wykorzystać model MITRE ATT&CK?
> -----------------------------------

Korzystając z modelu Mitre możemy zobrazować, w jaki sposób został przeprowadzony konkretny atak, który może stanowić ryzyko dla organizacji, a przed którym należy się zabezpieczyć. Analiza ataku pozwala na określenie, które elementy systemu są mniej lub bardziej narażone na atak oraz które urządzenia lub oprogramowanie może być kluczowe do jego przerwania lub zakłócenia.

Pomimo, że model Mitre podzielony jest na konkretne taktyki, które kojarzą się z etapami modelu [Cyber Kill Chain,](https://seqred.pl/cyber-kill-chain-co-to-jest-i-jak-wykorzystac-go-do-powstrzymania-zaawansowanych-atakow/) to korzystanie z Mitre nie wymaga zachowywania kolejności operacji, zgodnych z kolejnością pól w matrycy.

[![Mittre Attack wykres 2](/blog/Mitre-Attack-wykres-2-1.jpg "Mittre Attack wykres 2")](/blog/Mitre-Attack-wykres-2-1.jpg "Mittre Attack wykres 2")

Powyższa grafika przedstawia schemat ataku Stuxnet na irański program nuklearny w 2010 roku zobrazowany za pomocą modelu Mitre Att&ck for ICS. Pomarańczowe pola oznaczają techniki wykorzystane do przeprowadzenia ataku.

Stuxnet jest bardzo złożonym złośliwym oprogramowaniem, które wykorzystuje wiele skomplikowanych czynników, takich jak luki zero-day, dedykowany rootkit dla systemów Windows oraz metody infekcji sieci. Wszystkie techniki zaprezentowane w modelu są opisane przez organizację Mitre wraz ze sposobami ich mitygacji, co umożliwia przygotowanie konkretnych środków zaradczych. Przykładowo w fazie Initial Access atakujący użyli przenośnego nośnika do zainfekowania systemu. Zapewnienie bezpieczeństwa nośników przenośnych, np. z wykorzystaniem SMX Secure Media Exchange poprzez brak wektora wejściowego mogłoby uniemożliwić atak.

Analiza konkretnego ataku, np. Stuxnet pozwala na zabezpieczenie się przed tego typu zagrożeniem. Model Mitre umożliwia także analizę działań oraz technik stosowanych przez zorganizowane grupy, co pozwala na szerszą ocenę sytuacji, a tym samym planowanie oraz podejmowanie strategicznych decyzji w zakresie cyberbezpieczeństwa.

### Wykorzystanie Modelu Mitre do analizy działań grup APT

Model Mitre w swojej bazie zawiera szczegółowe informacje na temat technik wykorzystywanych przez znane grupy APT . Framework Mitre Att&ck pozwala porównać działania dowolnie wybranych grup APT, w szczególności podobieństwa i różnice w przeprowadzanych atakach oraz stosowanych technikach.

![Mittre Attack wykres 3](/blog/Mitre-Attack-wykres-3-2.jpg "Mittre Attack wykres 3")

Powyższy rysunek przedstawia porównanie grup APT28 oraz APT41:

*   kolorem żółtym oznaczone zostały techniki wykorzystywane przez grupę APT 41,
*   czerwonym: techniki wykorzystywane przez grupę APT 28,
*   zielonym: techniki wykorzystywane przez obie grupy.

**APT 41 – znana również jako Barium lub Winnti**  
Grupa powiązana z Chinami, działająca od 2012 roku, zaobserwowana w 14 krajach. Zaangażowana w gromadzenie strategicznych informacji wywiadowczych od organizacji z wielu sektorów oraz w ataki o podłożu finansowym.

**APT28 – Strontium, Sofacy lub Fancy Bear**  
APT28 jest grupą przypisaną do rządu Rosji, która działa co najmniej od 2004 roku. Grupa ta została powiązana z włamaniami lub próbami włamań do systemów parlamentu Niemiec, Białego Domu, Komisji Europejskiej, Banku Światowego, NATO oraz innych instytucji. W 2016 roku to prawdopodobnie APT28 próbując zakłócić wybory prezydenckie w USA skompromitowało kampanię Hillary Clinton, Demokratyczny Komitet Narodowy i Komitet Kampanii Kongresu Demokratycznego.

> Jak wkomponować model Mitre ATT&CK w procesy bezpieczeństwa w firmie?
> ---------------------------------------------------------------------

Włączenie modelu Mitre w procesy bezpieczeństwa firmy może przynieść wymierne korzyści, przede wszystkim umożliwia ono planowanie i podejmowanie działań oparte na rzeczywistych danych. Poniżej przedstawiamy 5 kroków, w jaki sposób można praktycznie wykorzystać tę wiedzę.

### **Krok 1  
Biblioteka referencyjna**

ATT&CK Framework nie tylko dokumentuje znane techniki ataków, ale także działania napastników, którzy z nich korzystali. Dostęp do bazy danych wspomaga zespół [Red Team](https://seqred.pl/red-team/) oraz zespoły badawcze w rozpoznaniu konkretnych zagadnień i zapewnia kierownictwu jasne zrozumienie przyszłych zadań z zakresu bezpieczeństwa. Dzięki niemu możliwe jest uzyskanie odpowiedzi na pytania:

*   którzy atakujący celują w konkretną branżę?
*   jakie techniki są powszechnie stosowane przez tych atakujących?
*   jakich narzędzi używają napastnicy do realizacji poszczególnych technik?
*   czy jest możliwe wykrycie tych techniki?
*   jakie środki zapobiegawcze łagodzą te techniki?

### **Krok 2  
Określenie możliwości obronnych**

Wiedza o tym, jak instytucja może zostać zaatakowana, jest równie ważna, jak znajomość jej możliwości obronnych. Mapowanie zabezpieczonych obszarów w modelu ATT&CK nie tylko daje jasny pogląd na to, przed czym można się bronić, ale stanowi także pierwszy krok w poprawianiu możliwości wykrywania i reagowania na incydenty.

### **Krok 3  
Opracowanie strategii obrony**

Specjaliści bezpieczeństwa muszą przenieść nacisk z “co mamy” na “co powinniśmy mieć”. W wielu przypadkach za osiągniecie akceptowalnego poziom bezpieczeństwa uważa się zabezpieczenie przed jak największą liczbą technik w matrycy. Zamiast wyczerpywać zasoby organizacji na obronę przed ponad 200 technikami, lepsze będzie skupienie się na technikach, które zostały wykorzystane do ataków na firmy z tej samej branży. Takie działanie pozwoli na efektywne wypełnienie luk w obronie.

### **Krok 4  
Szkolenie personelu – zwiększenie świadomości technik oraz taktyk**

Modele ATT&CK zmieniły globalne podejście do cyberbezpieczeństwa. Szkolenie personelu z korzystania z ww. modeli pozwala na wdrożenie taktyk i technik do organizacji pracy i codziennych czynności. Każdy SOC powinien dążyć do kultury opartej w większym stopniu na dokonywaniu systematycznych analiz oraz priorytetowym traktowaniu informacji na temat najbardziej prawdopodobnych zagrożeń.

### **Krok 5  
Symulacje ataków – ocena efektywności zabezpieczeń**

Najlepszym sposobem wykorzystania ATT&CK Framework jest testowanie rozwiązań obronnych i sprawdzanie wskaźników oceniających ich skuteczność. Przydatne okazują się symulacje ataku, które mogą przyjmować różne formy, np. [testy penetracyjne](https://seqred.pl/testy-penetracyjne/) czy operacje [Red Team.](https://seqred.pl/red-team/)

> Ograniczenia modeli Mitre ATT&CK
> --------------------------------

Biorąc pod uwagę konstrukcję modeli Mitre ATT&CK oraz komponenty, z jakich składa się wyrafinowane złośliwe oprogramowanie – w niektórych przypadkach techniki wykorzystywane przez atakujących mogą nakładać się na siebie. Przykładowo malware, który warstwowo korzysta z innych technologii, np. złośliwego skryptu, może zawierać polecenia dla konsoli CMD, które dalej zawierają złośliwy kod PowerShell. Trudno jednoznacznie określić, czy taki przypadek powinien być określony jako Command Shell, czy PowerShell.

> Podsumowanie
> ------------

Baza wiedzy Mitre jest regularnie rozbudowywana i aktualizowana. Należy pamiętać, że nie ma złych rozwiązań bezpieczeństwa, są jedynie niewłaściwie zastosowane lub nieumiejętnie skonfigurowane. O tym, w jaki sposób należy je dobierać, decydują zagrożenia przed którymi chcemy się ochronić, a które powinny wynikać z analizy ryzyk, jakie grożą organizacji oraz ogólnego krajobrazu zagrożeń danej branży. Wdrożenie rozwiązań nie jest jeszcze gwarancją ich efektywności. Aby upewnić się o skuteczności działania środków ochronnych należy je przetestować. Najskuteczniejsze są testy przeprowadzane w najbardziej zbliżonych do rzeczywistych warunków, w jakich urządzenia będą działać. Przy tego typu zadaniach najlepiej sprawdzają się [testy penetracyjne](https://seqred.pl/testy-penetracyjne/) oraz operacje [Red / Blue Team.](https://seqred.pl/red-team/) Podczas ich realizacji specjaliści cyberbezpieczeństwa symulują realne zagrożenia sprawdzając, w jaki sposób wdrożone zabezpieczenia są w stanie im się przeciwdziałać. Wynikiem jest szczegółowy raport, który przedstawia klientowi jaki jest rzeczywisty poziom zabezpieczeń, jakie występują zagrożenia oraz rekomendacje, jak należy się zabezpieczyć.

Sprawdź, jak wykorzystać Model Mitre ATT&CK do zabezpieczenia swojej firmy
--------------------------------------------------------------------------

[Skontaktuj się z nami](https://seqred.pl/kontakt/)

**Źródła:**

*   [CYCRAFT “Mitre ATT&CK vs. Cyber Kill Chain vs. Diamond Model”](https://medium.com/cycraft/cycraft-classroom-mitre-att-ck-vs-cyber-kill-chain-vs-diamond-model-1cc8fa49a20f)

**Zainteresował Cię ten temat? Przeczytaj także:**

*   [Cyber Kill Chain – co to jest i jak wykorzystać go do powstrzymania zaawansowanych ataków](https://seqred.pl/cyber-kill-chain-co-to-jest-i-jak-wykorzystac-go-do-powstrzymania-zaawansowanych-atakow/)
*   [Powłamaniowa analiza incydentów bezpieczeństwa – Model Diamentowy](https://seqred.pl/model-diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa/)