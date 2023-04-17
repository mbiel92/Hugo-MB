+++
lang="pl-PL"
title="Powłamaniowa analiza incydentów bezpieczeństwa – Model Diamentowy"
date="2020-08-27"
author="Sylwia Sławińska"
image="/blog/Model_Diamentowy.jpg"
tags=['analiza incydentów bezpieczeństwa']

+++

Nie wszystkim incydentom bezpieczeństwa można było zapobiec. Tylko w 2019 roku do CSIRT GOV Polska zgłoszone zostało ich blisko 12,5 tys. Przeprowadzone ataki hakerskie mogą mieć negatywne skutki dla funkcjonowania całego przedsiębiorstwa. Często od szybkości i efektywności ich wykrycia oraz poddania analizie całego zdarzenia zależy zakres i skala szkód oraz ich konsekwencje.

Do analizy incydentów bezpieczeństwa można wykorzystać Model Diamentowy, który pozwala na określenie w jaki sposób incydent się rozpoczął, jak przebiegał oraz jakie są jego skutki. Model ten oprócz analizy pojedynczego zdarzenia umożliwia powiązanie różnych ataków między sobą dzięki wyodrębnieniu podobnych technik ataku oraz określeniu wykorzystanego złośliwego oprogramowania.

#### **Z artykułu dowiesz się:**

*   co to jest Model Diamentowy?
*   z jakich elementów się składa?
*   jak wykorzystać Model Diamentowy w praktyce?
*   jak wygląda analiza ataku w Modelu Diamentowym?
*   jakie są podobieństwa i różnice między Modelem Diamentowym, a Cyber Kill Chain?

**Przeczytaj także:**

*   [Cyber Kill Chain oraz jak wykorzystać go do powstrzymania zaawansowanych ataków:](https://seqred.pl/cyber-kill-chain-co-to-jest-i-jak-wykorzystac-go-do-powstrzymania-zaawansowanych-atakow)
*   [MITRE ATT&CK – analiza przeprowadzonych ataków w celu skuteczniejszej ochrony](https://seqred.pl/mitre-attck-analiza-atakow-w-celu-skuteczniejszej-ochrony/)


> Co to jest Model Diamentowy?
> ----------------------------

Model Diamentowy to podejście do analizy incydentów bezpieczeństwa. Zakłada on, że zdarzenie jest podstawowym elementem każdej aktywności włamaniowej.

Model Diamentowy swoją nazwę i kształt zawdzięcza czterem głównym połączonym ze sobą elementom, które składają się na zdarzenie:

*   **napastnik** – może być to osoba bezpośrednio wykonująca atak, lub podmiot, który odnosi korzyści z przeprowadzonego ataku,np. grupy zorganizowane (electrum, dymalloy, magnalium, chrysene), APT, hacktywiści,
*   **infrastruktura** – zasoby niezbędne do przeprowadzenia ataku, np. konfiguracja urządzeń, serwery, urządzenia mobilne, zasoby programowe, środowiska chmurowe,
*   **możliwości** – narzędzia i techniki, podatności ofiary oraz informacje, które mogą być wykorzystane do przeprowadzenia ataku, np. wiedza o przebiegach procesów, umiejętności związane z tworzeniem złośliwego oprogramowania, dostęp do zaawansowanej infrastruktury,
*   **ofiara**, którą może być osoba, organizacja lub posiadane przez nią zasoby, np. prywatna firm, instytucja rządowa, infrastruktura krytyczna, łańcuchy dostaw.

Analiza incydentów obejmuje złożenie elementów diamentu z wykorzystaniem informacji zebranych na temat każdego wraz z uwzględnieniem meta-cech zdarzenia, w celu zrozumienia pełnego kontekstu.

[![](/blog/Model-Diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa-1.jpg)](https://seqred.pl/wp-content/uploads/2020/08/Model-Diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa-1.jpg)

W najprostszej formie Model Diamentowy opisuje jak **przeciwnik** wykorzystuje daną **możliwość** za pomocą określonej **infrastruktury** przeciwko **ofierze**.

Model Diamentowy pozwala na łączenie zdarzeń w wątki aktywności oraz zdarzeń i wątków w określone grupy aktywności. Tak pogłębiona analiza pozwala na stworzenie kompleksowego modelu aktywności włamaniowej.

Pełne zrozumienie złośliwej aktywności, na którą składają się zarówno zdarzenia, jak i wątki zdarzeń pomaga w zrozumieniu przebiegu włamań – nie jako pojedynczych zdarzeń, ale jako stopniowo następujących po sobie etapów.

> Model Diamentowy w praktyce
> ---------------------------

Umieszczenie podstawowych elementów zdarzenia: ofiary, infrastruktury, przeciwnika i możliwości na wierzchołkach diamentu pozwala na śledzenie działań napastnika w ramach każdego zdarzenia. Każdy z tych elementów może być punktem zwrotnym, który obrońcy mogą wykorzystać podczas analizy, aby połączyć cechy jednego ataku z innymi. Przykładowo znany atak typy zero-day, który wymaga unikalnego sposobu wdrożenia zmieniłby możliwości atakującego; można to wykorzystać w celu zbadania innych ataków, które wykorzystywały podobne metody lub ten sam atak zero-day.

Wykorzystując Model Diamentowy przykładowe zdarzenie możemy przedstawić w poniższy sposób:

[![](/blog/Model-Diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa-1a-1.jpg)](https://seqred.pl/wp-content/uploads/2020/08/Model-Diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa-1a-1.jpg)

**1.** Ofiara odkrywa złośliwe oprogramowanie,

**2.** Malware zawiera charakterystyczne fragmenty kodu, co pozwala na identyfikację napastnika,

**3.** Zidentyfikowany napastnik zawsze atakuje elementy infrastruktury krytycznej danego typu,

**4.** Malware napastnika wykorzystuje konkretną podatność,

**5.** Podatność ta znajduje się w systemie ofiary.

Poruszanie się po modelu w opisany powyżej sposób pozwala na analizę dowolnego zdarzenia. Łączenie ze sobą określonych zdarzeń, prowadzi do poznania struktury ataku. Oznacza to, że Model Diamentowy jest dynamiczną konstrukcją, która może się dowolnie rozrastać, w zależności od zachowań napastnika.

> Szczegółówa analiza ataku w Modelu Diamentowym
> ----------------------------------------------

Cyberatak nie jest pojedynczym zdarzeniem. Specjaliści z branży cyberbezpieczeństwa są zgodni, że cała działalność związana z atakami powinna być traktowana jako łańcuch zdarzeń. Przykładowo, atakujący musi zidentyfikować ofiarę, następnie odkryć jej podatności, wykorzystać je, aby ustanowić zdalny dostęp, a na koniec przeprowadzić zamierzone działania. Model Diamentowy może wykorzystywać dowolny, składający się z etapów, model działania przeciwnika (np. Cyber Kill Chain). Istotne jest, aby zachować uporządkowaną kolejność zdarzeń, dlatego Faza – jedna z meta-cech Modelu Diamentowego została wprowadzona w celu przypisania zdarzenia do konkretnego etapu ataku.

Poniższy wykres przestawia przebieg ataku na sieć energetyczną na Ukrainie w 2015, który miał miejsce w 2015 roku. Zgodnie z oficjalnymi analizami, łącznie 30 stacji o różnej mocy zostało odłączonych na trzy godziny z powodu zewnętrznej ingerencji w sieć SCADA. Atak ten, doprowadził do przerwania procesu wytwarzania energii, uniemożliwił zdalną konfigurację sterowników, nadpisał dane na stacjach roboczych, RTU oraz HMI i zatrzymał pracę (atak typu denial-of-service) centrali telefonicznej w celu odmówienia konsumentom aktualnych informacji na temat przerwy w dostawie prądu.

Zdarzenia w przedstawionym poniżej modelu są przedstawione za pomocą diamentów, liczby pozwalają na śledzenie kolejności występowania zdarzeń, a strzałki identyfikują związki przyczynowe między zdarzeniami. Dzięki połączeniom między zdarzeniami (diamentami) można określić, czy dane zdarzenie jest wymagane, czy opcjonalne (czy istnieje więcej niż jedna ścieżka ze zdarzenia). Pomocne podczas analizy jest także rozróżnienie, które zdarzenia są uznawane za pewne, a które za hipotetyczne.

Poszczególne zdarzenia połączone zgodnie z kolejnością zdarzeń. Linie ciągłe pokazują rzeczywiste zdarzenia, podczas kiedy linia przerywana obrazuje zdarzenia hipotetyczne.

**

Scenariusz przebiegu ataku na sieć energetyczną na Ukrainie w 2015

**

[![](/blog/Model-Diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa-2.jpg)](/blog/Model-Diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa-2.jpg)

**1.** Wykonanie działań OSINT

**2.** Dostarczenie złośliwego oprogramowania BlackEnergy3 za pomocą wiadomości e-mail typu spear phishing z załączonymi dokumentami

**3.** Otwarcie złośliwego załącznika wykorzystującego narzędzie pozwalające na nieautoryzowane wykonanie kodu

**4.** Instalacja wirusa – BlackEnergy3

**5.** Uzyskanie kontroli zdalnej

**6.** Przechwycenie danych uwierzytelniających do VPN dla stanowisk roboczych

**7.** Wykorzystanie danych uwierzytelniających VPN do dostępu do sieci ICS

**8.** Rozpoznanie zasbów w sieci ICS

**9.** Uzyskanie dostępu do serwerów dyspozytorskich ICS i stacji roboczych

**10.** Instalacja oprogramowania KillDisk na kluczowych stacjach roboczych/serwerach i jednostkach RTU

**11.** Modyfikacja sterowników dla urządzeń Serial-to-Ethernet, aby nie reagowały na zdalną kontrolę

**12.** Doprowadzenie do awarii zasilania przy użyciu zainfekowanych interfejsów HMI

**13.** Wymazanie danych ze stacji roboczych, serwerów, RTU oraz HMI za pomocą KillDisk

**14.** Blokada kont administratorów systemu

**15.** Zebranie numerów telefonów do centrum telefonicznego elektrowni

**16.** Wykorzytanie aplikacji do wykonywania licznych połączeń do centrum telefonicznego

**17.** Doprowadzenie do telefonicznej odmowy usługi (TDoS)

> Model Diamentowy vs. Cyber Kill Chain
> -------------------------------------

Model Diamentowy analizy incydentów i Cyber Kill Chain są względem siebie komplementarne.

Cyber kill chain jest jedną z kilku metod pozwalających na zrozumienie przebiegu cyberataków. Na przestrzeni ostatnich lat pojawiły się kolejne, bardziej szczegółowe modele przedstawiające możliwe scenariusze wrogich działań.

Cyber Kill Chain pozwala namierzyć przeciwnika oraz identyfikuje środki obrony mające na celu powstrzymanie ataku. Model Diamentowy został zaprojektowany tak, aby umożliwić śledzenie i łączenie ze sobą wykrytych podczas analizy zdarzeń, w celu pogłębienia wiedzy na temat dokonanego ataku.

Podstawowa różnica między tymi modelami polega na tym, że Cyber Kill Chain stosuje liniowe podejście narracyjne do analizy cyberataku. Każdy kolejny krok prowadzi do następnego.

Model Diamentowy pozwala natomiast na wielokierunkową i dogłębną analizę zdarzeń. Jest dynamiczny, podlega ciągłym zmianom, ponieważ atakujący dość często zmieniają swoją infrastrukturę i możliwości. Każdy element Modelu Diamentowego: ofiara, infrastruktura, przeciwnik, możliwości może być punktem zwrotnym, który analitycy mogą wykorzystać, aby połączyć cechy jednego ataku z innymi.

**Przeczytaj więcej o:** [Cyber Kill Chain oraz jak wykorzystać go do powstrzymania zaawansowanych ataków](https://seqred.pl/cyber-kill-chain-co-to-jest-i-jak-wykorzystac-go-do-powstrzymania-zaawansowanych-atakow)
