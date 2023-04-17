+++
lang="pl-PL"
title="Jak zainfekować sieć OT przez Internet?"
date="2020-01-16"
author="Michał Stępień"
image="/blog/Seqred_Czwartki_OT_zabezpieczenie_infrastruktury.jpg"
tags=['automatyka przemysłowa', 'czwartki OT', 'infrastruktura krytyczna']
+++

W raporcie Globalnych Ryzyk 2020 Światowego Forum Ekonomicznego cyberataki oraz przełamanie kluczowych zabezpieczeń infrastruktury oraz sieci zostały zaklasyfikowane w TOP 10 globalnych ryzyk. Świadomość zagrożeń użytkowników końcowych ciągle rośnie, a co za tym idzie atakujący poszukują nowych metod instalacji malware’u. W artykule przedstawimy atak z przełomu 2013 i 2014 roku, który spowodował nieświadome udostępnianie przez użytkowników informacji o infrastrukturze ICS, możliwe scenariusze ataku oraz metody zabezpieczeń sieci przemysłowych.


## Malware pochodzący z Internetu infekuje sieć korporacyjną{ .article-section }

Jest przełom 2013 i 2014 roku. Na przejętych stronach Internetowych producenta routerów VPN firmy Ewon zostaje podmieniona zawartość plików aplikacji klienckiej. Zanim producent urządzeń sieciowych usunie złośliwe dane z serwera, około 250 unikalnych użytkowników pobierze i wielu z nich zainstaluje „poprawione” przez grupę Dragonfly oprogramowanie (atak typu _watering hole_), żeby później nieświadomie udostępniać informacje o wykorzystywanych aplikacjach oraz infrastrukturze ICS.

Działania atakujących w powyższym przypadku były sprofilowane na konkretną grupę użytkowników, osób związanych z przemysłem. Hakerzy do ataku wykorzystywali dwa główne warianty malware’u umożlwiające zdalny dostęp i klasyfikowane jako RAT (_remote-access-trojan_): Havex (Oldrea) oraz Kragany, dzięki którym mogli między innymi pobierać oraz wysyłać dane i uruchamiać pliki wykonywalne na komputerze ofiary. Oprogramowanie posiadało funkcje takie jak: katalogowanie dokumentów, pozyskiwanie haseł oraz robienie zrzutów ekranu.

Znając możliwości złośliwego oprogramowania, aby lepiej się przed nimi chronić, warto jest poznać możliwe źródła instalacji z Internetu oraz narażone komponenty.

## Czynniki zagrożeń dla sieci przemysłowych{ .article-section }


Sieci korporacyjne wykorzystują standardowe komponenty takie jak: systemy operacyjne, serwery www oraz bazy danych. Przeglądarki oraz klienci poczty elektronicznej (e-mail) na ogół mają połączenie z Internetem. Nowe podatności tych komponentów są odkrywane niemal codziennie. Atakujący może je wykorzystać w celu dostania się do sieci korporacyjnej oraz instalacji malware’u. Alternatywnie, malware może zostać wprowadzony do sieci korporacyjnej przy wykorzystaniu zainfekowanych nośników wymiennych. W obu przypadkach, krytyczne lub wrażliwe informacje mogą zostać pozyskane przez czynnik zagrażający. Ponadto utrzymanie właściwego bezpieczeństwa IT jest utrudnione przez rosnące wykorzystanie sieci i protokołów Ethernet w środowisku ICS oraz ich połączenie z serwerami wchodzących np. w skład systemów ERP lub MES. Wzajemne relacje powodują, że często infiltracja sieci ICS jest możliwa bezpośrednio z sieci biurowej czy korporacyjnej lub w następnej fazie ataku.

Dostęp z sieci ICS lub sieci zbliżonej do ICS do innych sieci – zwłaszcza Internetu – może skutkować atakami profilowanymi lub nieukierunkowanymi. Poniżej prezentujemy scenariusze zagrożeń.

> ## Scenariusze zagrożeń, które warto omówić podczas okresowych szkoleń dla pracowników i dostawców zewnętrznych{ .article-section }

**Scenariusz 1.**  
Wykorzystanie znanych luk w zabezpieczeniach lub tzw. exploitów typu zero-day. Te ostatnie oznaczają nieznane wcześniej ataki, czyli takie, które nie są jeszcze wykrywalne przez programy antywirusowe lub przez inne rozwiązania bazujące na sygnaturach.

**Scenariusz 2.**  
Manipulowanie zewnętrznymi stronami internetowymi, np. w celu przeprowadzenia ataku typu _drive-by-download_. Czasem wystarczą odwiedziny strony, by infrastruktura ofiary została zainfekowana. Jednym z przykładów takich wektorów ataku może być przeglądanie Internetu na urządzeniach wchodzących w skład sterowni (np. serwery SCADA) lub na innych urządzeniach sterujących (np. panelach operatorskich).

**Scenariusz 3.**  
Przeprowadzanie ataków na strony internetowe przedsiębiorstwa (np. SQL Injection, cross-site scripting itp.).

**Scenariusz 4.**  
Zainfekowanie komponentów złośliwym oprogramowaniem, które może rozprzestrzeniać się w sieci w sposób niekontrolowany (np. robakami) oraz atakować przypadkowe systemy ograniczając ich funkcjonalność lub dostępność poprzez nieplanowane wykorzystanie dodatkowych zasobów.

**Scenariusz 5.**  
Instalacja prywatnego sprzętu, który może być zainfekowany lub posiada podatności, które mogą być wykorzystane do przeprowadzenia ataku. Zaskakujące może wydawać się scenariusz z wykorzystaniem routera WLAN w celu korzystania z sieci bezprzewodowej na smartfonach, komputerach do gier oraz konsolach.

Duża część prezentowanych scenariuszy może okazać się problematyczna w kontekście regulacji RODO. Wyciek danych wrażliwych powinien zostać każdorazowo zgłoszony odpowiednim jednostkom. Niewłaściwa obsługa incydentów lub niedopatrzenie ze strony ofiary, może doprowadzić do nałożenia wysokich kar na przedsiębiorstwo.

## Ryzyko ataku można zmniejszyć poprzez:{ .article-section }

**1.** maksymalną izolację różnych sieci ([segmentację](https://seqred.pl/segmentacja-sieci/)) przez zapory (firewall) oraz zastosowanie rozwiązań VPN do wybranych segmentów, które w dużej mierze ograniczają możliwe ścieżki ataku (np. prowadzące z sieci biurowej, do sieci OT). Ponadto należy izolować niezabezpieczone / nieaktualizowane systemy tworząc tzw. bezpieczne wyspy _(secure islands_),

**2.** stosowanie konwencjonalnych zabezpieczeń brzegowych (np. zapory, oprogramowanie antywirusowe) lub w ICS (np. _whitelisting_ aplikacji lub w niektórych przypadkach zapory),

**3.** ograniczenie dostępnych informacji w przedsiębiorstwie (np. przechowywanych na serwerach plików lub w bazach danych) w celu utrudnienia wycieku krytycznych informacji (zasada niezbędnej wiedzy),

**4.** regularne i terminowe łatanie systemów operacyjnych i aplikacji w biurze i backend’zie sieci oraz w stosownych przypadkach, w sieciach ICS,

**5.** monitorowanie oraz analizę logów systemowych w celu wykrycia nietypowych połączeń lub prób ich nawiązania,

**6.** optymalne utwardzanie wszystkich komponentów IT (usług, komputerów) używanych w środowisku biurowym i ICS.

Czy zastosowanie wszystkich powyższych reguł wyeliminuje całkowicie możliwość infiltracji złośliwego oprogramowania do sieci ICS? Niestety nie, ale według raportu opublikowanego w 2019 r. przez Federalny Urząd ds. Bezpieczeństwa Informacji pozwoli zredukować to ryzyko.

Na koniec warto wskazać na istniejące rozwiązania bezpieczeństwa, które mają m.in. wspomagać monitorowanie komunikacji oraz detekcję zagrożeń w sieciach ICS. Niektórymi z takich rozwiązań są **Forge firmy Honeywell, (dawniej ICSShield)** oraz produkty firmy **Nozomi Networks.**

**Źródła:**  
[ISS Source: ICS Alert USB Malware Attack](https://www.allianz-fuer-cybersicherheit.de/ACS/DE/_/downloads/BSI-CS/BSI-CS_005.pdf?__blob=publicationFile&v=12)  
[Symanec: Dragonfly – Western Energy Companies Under Sabotage Threat](//www.symantec.com/connect/blogs/dragonfly-western-energy-companies-under-sabotage-threat)  
[Netresec: Full Disclosure of Havex Trojans](//www.netresec.com/?page=Blog&month=2014-10&post=Full-Disclosure-of-Havex-Trojans)  
[World Economic Forum: The Global Risks Report 2020](https://www.weforum.org/reports/the-global-risks-report-2020)