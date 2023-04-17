+++
lang="pl-PL"
title="Czy systemy BMS mogą stanowić wektor ataku na systemy ICS?"
date="2020-04-09"
author="Łukasz Dudkowski"
image="/blog/Seqred_Czy_systemy_BMS_moga_stanowic_wektor_ataku_dla_systemow_ICS.jpg"
+++

W wielu przedsiębiorstwach, w których funkcjonują zaawansowane systemy
przemysłowe wdrażane i użykowane są także systemy budynkowe. Ich
bezpieczeństwo często uznawane jest za mniej istotne niż systemów ICS,
ponieważ nie realizują one głównego celu firmy. W ostatnich latach
systemy BMS (Building Management Systems) zarządzające prawidłowym
funkcjonowaniem budynków stały się częstym celem ataków hakerskich.
Oznacza to, że atak na system BMS, w przypadku jego połączenia z
systemem ICS, może być skuteczną ścieżką ataku na system automatyki
przemysłowej przedsiębiorstwa.

**Z tego artykułu dowiesz się:**

-   jak systemy BMS wspierają pracę przedsiębiorstwa,
-   jak zagrożenia systemów budynkowych wpływają na bezpieczeństwo
    systemów ICS,
-   jak ograniczyć negatywne skutki dla systemów ICS spowodowane
    kompromitacją systemów budynkowych.

**Przeczytaj także:**

-   [Jak zabezpieczyć obiekty Smart Building przed
    cyberatakami](https://seqred.pl/smart_building/)
-   [O zagrożeniach cyberbezpieczeństwa dla obiektów Smart Building z
    przykładami ataków oraz konsekwencjach związanych z brakiem
    odpowiednich
    zabezpieczeń](https://seqred.pl/cyberbezpieczenstwo_smart_building/)

## Systemy budynkowe - wsparcie dla prawidłowego funkcjonowania przedsiębiorstwa

Prawidłowe i bezpieczne użytkowanie systemów budynkowych może mieć wpływ
na funkcjonowanie wielu obszarów przedsiębiorstwa, za które
odpowiedzialne są systemy ICS, np.:

-   funkcjonowanie hali magazynowej wymaga wydajnego systemu kontroli
    temperatury, wilgotności i odpowiedniej ilości cykli wymiany
    powietrza,
-   zakład produkcyjny korzysta z systemów kontroli bezpieczeństwa oraz
    przepływu osób z wykorzystaniem: kontroli dostępu, systemu
    sygnalizacji włamania i napadu, czy nadzoru terenu wewnętrznego oraz
    zewnętrznego z wykorzystaniem systemu CCTV,
-   część biurowa przedsiębiorstwa, wykorzystywana przez inżynierów,
    projektantów czy zarząd wymaga zapewnienia komfortowych warunków
    pracy wykorzystując systemy pozwalające na kontrolę klimatyzacji,
    jasności oświetlenia czy wdrożenia systemu rezerwacji sal
    konferencyjnych,
-   za wstępne przygotowanie powietrza na potrzeby „strefy
    czystej"/„Clean room" często także odpowiada system budynkowy.

Powyższe przykłady pokazują, że zazwyczaj obok systemów przemysłowych
użytkowane są odpowiednie systemy budynkowe, które mogą wówczas pełnić
rolę systemów:

-   **wspomagających funkcjonowanie obiektu:** zapewnienie komfortu i
    bezpieczeństwa pracowników,
-   **biorących pośredni udział w procesie produkcyjnym, czy
    technologicznym:** wstępne przygotowanie powietrza (HVAC), czy
    przekazanie pojedynczych mierzonych parametrów,
-   **zapewniających bezpieczeństwo fizyczne dla systemu przemysłowego i
    ochrony obiektu** (system kontroli dostępu, telewizja dozorowa
    CCTV).

## Niższy priorytet bezpieczeństwa systemów budynkowych w przedsiębiorstwach produkcyjnych

Zdarza się, że systemy budynkowe w obiektach przemysłowych traktowane są
z mniejszą uwagą niż systemy odpowiadające za realizację głównego celu
danego obiektu. Wynika to z położenia nacisku na bezpieczeństwo systemów
i urządzeń ICS mających strategiczne znaczenie dla prowadzonej
działalności. Należy zwrócić uwagę, że systemy budynkowe, które w co raz
to nowocześniejszej odsłonie występują w zmodernizowanych obiektach
przemysłowych również wymagają kompleksowych działań w zakresie
cyberbezpieczeństwa.

Oprócz wypracowania wymogów cyberbezpieczeństwa dla systemów ICS, należy
z odpowiednią higieną użytkować systemy budynkowe. Ich odpowiednie
zabezpieczenie może mieć także wpływ na bezpieczeństwo głównego procesu,
tym bardziej, że systemy budynkowe coraz częściej narażone są na
cyberataki.

## Zagrożenia pochodzące od systemów BMS

Do analizy ryzyka w obszarze cyberbezpieczeństwa systemów przemysłowych
należy uwzględnić zagrożenia pochodzące od systemów BMS. Jest to
istotne, ponieważ systemy budynkowe stały się popularnym celem ataków
hakerskich. Ilość oraz różnorodność zagrożeń dla systemów Smart Building
w ostatnim czasie bardzo wzrosła.

Z raportu firmy Kasperski na temat zagrożeń cyberbezpieczeństwa systemów
Smart Building z 19 września 2019 wynika, że 4 na 10 komputerów
używanych do zarządzania systemami budynkowymi padło ofiarą ataku
malware w pierwszej połowie 2019 r. Do prób infekcji dochodziło
najczęściej za pośrednictwem Internetu, urządzeń przenośnych oraz
e-maili.

Jeśli chcesz dowiedzieć się więcej na temat rodzajów zagrożeń oraz
potencjalnych skutków ataków dla systemów BMS przeczytaj artykuł
["Inteligentne Budynki -- blisko 40 proc. systemów zaatakowanych przez
malware"](https://seqred.pl/smart_building_raport/). Więcej informacji
na temat systemów wykorzystywanych przez inteligentne budynki wraz z
przykładami ataków hakerskich znajdziesz w artykule ["Smart Building --
cyberbezpieczeństwo musi być
priorytetem"](https://seqred.pl/cyberbezpieczenstwo_smart_building/).

## Zagrożenia dla systemów ICS jakie mogą nieść współistniejące systemy budynkowe

Wpływ ataku na system budynkowy może rzutować na system ICS na wielu
płaszczyznach:

### **1. dodatkowy wektor ataku**

W przypadku nieprawidłowo wykonanej separacji/segmentacji sieci może to
być dodatkowy wektor ataku, który pozwoli dostać się do architektury
systemu ICS.

### **2. zmiana przebiegu procesu w systemie docelowym** 

W przypadku używania zmiennych z systemu budynkowego: przykładowo
pomiaru temperatury, przepływu wody (np. zbieranej na potrzeby
monitoringu mediów), czy temperatury powietrza i przekazywania ich do
procesu systemu ICS, nieautoryzowana manipulacja w systemie pierwotnym
może rzutować na realizację procesu w systemie docelowym.

### **3. zainfekowanie malware**

Zainfekowanie stacji roboczej wykorzystywanej do systemu BMS może
doprowadzić do przeniesienia malware na stację roboczą systemu ICS (np.
przy używaniu tych samych urządzeń pamięci masowej).

### **4. zatrzymanie produkcji/ utraty jakości produkowanych wyrobów**

Manipulacja pracą urządzeń sterowanych przez system budynkowy jak np.
skrajna zmiana temperatury/ wilgotności na hali produkcyjnej może
doprowadzić w specyficznym przypadku do zatrzymania produkcji/ utraty
jakości produkowanych wyrobów.

### **5. uzyskanie fizycznego dostępu do systemu ICS**

Uzyskanie nieautoryzowanego dostępu do systemów bezpieczeństwa
fizycznego kontrolowanego przez systemy budynkowe (CCTV, SKD, SSWiN),
może pozwolić na nielegalne wtargnięcie na teren zakładu przemysłowego,
a w dalszej kolejności na uzyskanie fizycznego dostępu do systemu ICS.

## Jak ograniczyć negatywne skutki dla systemów ICS spowodowane kompromitacją systemów budynkowych?

W celu zminimalizowania wpływu skutków dla systemu ICS warto rozpatrzeć
przede wszystkim następujące działania:

**1.** Zinwentaryzuj architekturę rozwiązania
Smart Building z uwzględnieniem separacji od systemu ICS lub
prawidłowego zabezpieczenia (DMZ, firewall itp.) punktów styku pomiędzy
systemami o ile są konieczne.

**2.** Wykonuj testy bezpieczeństwa rozwiązań
budynkowych z uwzględnieniem możliwość eskalacji zasięgu ataku na system
ICS.

**3.** W analizie ryzyka dla systemu ICS
uwzględniaj również zagrożenia wynikające z ataku na systemy BMS.

**4.** W planach „zachowania ciągłości
produkcji" uwzględnij scenariusze wynikające z wpływu nieprawidłowo
działających instalacji budynkowych.

**5.** Dla serwerów, stacji roboczych, mediów
przenośnych w obszarze systemów budynkowych, tam, gdzie to możliwe
zastosuj analogiczne rozwiązania bezpieczeństwa jak wdrożone dla systemu
ICS.

**Źródła:**

[Kaspersky "Threat landscape for smart buildings. Q1 2019 in brief"](https://ics-cert.kaspersky.com/reports/2019/09/19/threat-landscape-for-smart-buildings-h1-2019-in-brief/)