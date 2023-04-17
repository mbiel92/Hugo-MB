+++
lang="pl-PL"
title="Ataki na dostępność typu (D)DoS. Jak zabezpieczyć infrastrukturę przemysłową?"
date="2020-02-27"
author="Michał Stępień"
image="/blog/Zdalny_dostep_do_ICS.jpg"
tags=['czwartki OT']
+++

4 wrzesień 2019, Północnoamerykańska Korporacja Niezawodności Energii
Elektrycznej (NERC) publikuje raport o zdarzeniu cybernetycznym
dotyczącym infrastruktury elektroenergetycznej, które wydarzyło się 5
marca 2019. Wykorzystanie podatności w interfejsie webowym producenta
firewalli, pozwoliło atakującym na zresetowanie urządzenia bez
uwierzytelnienia. Efektem było zakłócenie dostępności usługi (DoS) w
centrum sterowania o niskim wpływie i wielu zdalnych lokalizacjach o
niskim wpływie. Nieoczekiwane ponowne uruchomienie sprzętu powodowało
cykliczne, krótsze niż pięciominutowe przerwy w komunikacji między
urządzeniami polowymi na podstacjach oraz między tymi lokalizacjami a
centrum kontroli. Problem rozwiązano we wszystkich lokalizacjach łącznie
po upływie ponad 8 godzin.


## Co to są ataki typu DoS?{ .article-section }

Zakłócenia dostępności (typu DoS) stanowią rozległą grupę ataków, obejmującą m.in.:
- **ataki wolumetryczne** (np. ataki na kanał komunikacyjny),
- **na protokoły** (np. prowadzące do wysycenia tablicy dostępnych połączeń na urządzeniach sieciowych), oraz
- **na warstwę aplikacji** (np. zablokowanie dostępności do bazy danych przez wysyłanie ogromnej liczby zapytań).

W środowiskach przemysłowych takie ataki mogą być realizowane np.
poprzez wykorzystanie znanych podatności komponentów sieciowych (np. w
sieciach przewodowych) lub też poprzez oddziaływanie na komunikacją
bezprzewodową (sieci WLAN), łączność mobilna (GSM, UMTS, LTE).

## 4 scenariusze zagrożeń atakami DoS:{ .article-section }

**Scenariusz 1.**
wykorzystanie komunikatów sieciowych, które wykorzystując lukę w
implementacji, pozwolą na zdalną eksploitację podatności urządzeń,

**Scenariusz 2.**
zakłócenie komunikacji bezprzewodowej w określonym paśmie częstotliwości
w celu uniemożliwienia normalnego ruchu,

**Scenariusz 3.**
wykorzystanie fałszywych stacji bazowych, w celu umożliwienia połączenia
klienta do nieprawidłowej sieci bezprzewodowej,

**Scenariusz 4.**
wysyłanie spreparowanych pakietów, które powodują, przerwanie
istniejących połączeń sieciowych.

## W jaki sposób zapobiegać atakom typu DoS na systemy automatyki?{ .article-section }

**1.** stosowanie dobrych praktyk w zakresie monitorowania, wykrywania podatności oraz odpowiednich metod zarządzania
aktualizacjami,

**2.** zmniejszenie powierzchni ataku poprzez udostępnianie do Internetu tylko niezbędnych urządzeń,

**3.** wykorzystanie komunikacji VPN podczas łączenia się z urządzeniami z zewnątrz,

**4.** wykorzystanie list kontroli dostępu (ACL) w celu filtrowania ruchu jeszcze przed obsłużeniem go przez zaporę (firewall),

**5.** obrona warstwowa. Przejęcie przez
atakujących zestawu: routera monitorującego (screening router),
terminatora sieci VPN oraz zapory może być bardziej skomplikowane niż
uzyskanie kontroli nad pojedynczym urządzeniem, np. zaporą (przy
założeniu poprawnej konfiguracji urządzeń)

**6.** ścisła konfiguracja i utwardzenie
konfiguracji punktów dostępu do sieci i kanałów komunikacji, a dla
krytycznych aplikacji wykorzystanie dedykowanych połączeń kablowych,

**7.** segmentacja sieci. Ograniczenie
komunikacji pionowej tylko do niezbędnego, wymaganego minimum,

**8.** ciągłe monitorowanie i prawidłowe
zarządzanie podatnościami w celu wykrycia luk w urządzeniach oraz
zastosowania aktualizacji (jeśli możliwe),

**9.** instalacja systemów klasy IDS
(Intrusion Detection Systems) w celu wykrywania ataków i wyzwalania
alarmów za pośrednictwem alternatywnych kanałów.

**10.** stosowanie połączeń redundantnych
przy użyciu różnych protokołów i/lub kanałów komunikacji w celu
zwiększenia dostępności.

Istnieje całe spektrum środków technicznych oraz organizacyjnych
wspierających obronę przed atakami. Stosowanie dobrych praktyk oraz
wszystkich zaleceń może okazać się wyzwaniem. Zachęcamy do kontaktu w
sprawie możliwości przeprowadzenia analizy ryzyk dla Państwa
przedsiębiorstwa w celu identyfikacji krytycznych urządzeń, procesów
szczególnie narażonych na ryzyko konkretnych ataków cybernetycznych na
Państwa organizację.

Zastosowanie odpowiednich środków technicznych pozwalających zmniejszyć
ryzyko ataku może okazać się wyzwaniem. Zachęcamy do kontaktu m.in. w
sprawie możliwości prezentacji systemów pozwalających na monitorowanie
podatności systemów automatyki oraz pomocy przy przeprowadzeniu procesu
segmentacji sieci w Państwa przedsiębiorstwie.

**Źródła:**

-   NERC -- Risks Posed by Firewall Firmware Vulnerabilities(https://www.nerc.com/pa/rrm/ea/Lessons%20Learned%20Document%20Library/20190901_Risks_Posed_by_Firewall_Firmware_Vulnerabilities.pdf)
-   NERC Issues Lessons Learned Report Regarding March 5, 2019 Cybersecurity Incident](https://www.troutmansandersenergyreport.com/2019/09/nerc-issues-lessons-learned-report-regarding-march-5-2019-cybersecurity-incident/)
-   Industrial Control System Security Top 10 Bedrohungen und Gegenmaßnahmen 2019(https://www.allianz-fuer-cybersicherheit.de/ACS/DE/_/downloads/BSI-CS/BSI-CS_005.pdf?__blob=publicationFile&v=12)
