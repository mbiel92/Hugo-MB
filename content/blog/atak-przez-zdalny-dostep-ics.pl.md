+++
lang="pl-PL"
title="Ataki na systemy przemysłowe przez luki bezpieczeństwa zdalnego dostępu"
date="2020-03-12"
author="Michał Stępień"
image="/blog/Zdalny_dostep_do_ICS.jpg"
tags=['czwartki OT']
+++

## Co kryje się w urządzeniach umożliwiających zdalny dostęp do ICS?{ .article-section }

W 2017 odkryto login i hash hasła ukrytego użytkownika oraz klucze
prywatne w firmware urządzeń Westermo zapewniających zdalny dostęp do
sieci ICS. Jedna z podatności została oceniona na 10 w skali CVSS v3.
Przykład ataku na infrastrukturę OT z wykorzystaniem zdalnego dostępu
oraz słabych haseł został upubliczniony w 2014 przez Departament of
Homeland Security.


## Zdalny dostęp do sieci OT{ .article-section }

Zdalny dostęp do sieci OT odgrywa ważną rolę w monitorowaniu systemów
ICS ze strony zewnętrznych serwisantów. Powszechny problem stanowi słabe
zabezpieczenie urządzeń poprzez stosowanie domyślnych haseł czy
zakodowanych na stałe, ukrytych kont logowania, haseł oraz kluczy.
Wyzwanie w środowisku ICS stanowi także ograniczenie widoczności po
zalogowaniu do sieci do konkretnych urządzeń, zamiast nielimitowanego
dostępu do całej podsieci, w której mogą znajdować się także inne
komponenty. Ponadto brak uwierzytelnienia oraz autoryzacji, a także płaskie
struktury sieciowe stwarzają zagrożenie dla systemów ze strony
atakujących.

Integracja maszyn oraz linii technologicznych przez zewnętrznych
partnerów często związana jest z zapisami umowy i przyznaniem dostawcom
prawa wyłączności do konserwacji oraz modyfikacji programowania w
okresie gwarancyjnym. Nieautoryzowane zmiany dokonywane przez działy
utrzymania ruchu wiążą się z utratą gwarancji na instalację. Klienci
często udostępniają producentom zdalny dostęp do urządzeń w celu
skrócenia czasu przestoju instalacji w przypadku awarii. Stwarza to
dodatkowe wyzwania zespołom odpowiedzialnym za zapewnienie
bezpieczeństwa i wymaga od nich zaangażowania oraz sformułowania
wytycznych jeszcze na etapie specyfikowania zamówień.

## Scenariusze zagrożeń{ .article-section }

#### Bezpośredni atak na punkt dostępu zdalnego, na przykład poprzez:{ .fw-bold .py-3 }

**Scenariusz 1.** wykorzystanie metod typu brute-force w celu uzyskania dostępu do punktów dostępu zabezpieczonych hasłem,

**Scenariusz 2.** ponowne wykorzystanie przechwyconego tokenu w celu uzyskania dostępu np. do konsoli zarządzania,

**Scenariusz 3.** ataki typowe dla sieci web, takie jak: wstrzyknięcie lub CSRF na punkty wykorzystywane do zdalnego dostępu w celach serwisowych.

#### Ataki pośrednie przez systemy dostawców usług, dla których utworzono zdalny dostęp:{ .fw-bold .py-3 }

**Scenariusz 4.**
użycie oprogramowania typu RAT (trojanów) w celu uzyskania
bezpośredniego dostępu do stacji inżynierskiej,

**Scenariusz 5.**
kradzież haseł, certyfikatów lub innych poświadczeń lub wykorzystanie
innych technik do pozyskania szczegółów logowania np. przekupienie lub
szantażowanie osób mających dostęp do takich danych,

**Scenariusz 6.**
kradzież sprzętu np. notebooków z skonfigurowanym oprogramowaniem do
zdalnego dostępu.

## W jaki sposób zapobiegać atakom na sieci ICS?{ .article-section }

**1.** dezaktywacja, blokada lub usunięcie domyślnych użytkowników / haseł. Zasady specyfikowane są w warunkach dostawy, a ich spełnienie weryfikowane oraz potwierdzone w protokole odbioru,

**2.** korzystanie z wystarczająco bezpiecznych procedur uwierzytelniania, np. wstępnie współdzielone klucze (pre-shared key), certyfikaty, tokeny sprzętowe, hasła jednorazowe i uwierzytelnianie wieloskładnikowe,

**3.** ochrona kanału transmisji przez szyfrowanie z wykorzystaniem bezpiecznych algorytmów szyfrujących,

**4.** segmentacja sieci, w celu zminimalizowania „zasięgu" zdalnego dostępu,

**5.** konfiguracja punktów dostępu do zdalnej konserwacji w strefie zdemilitaryzowanej (DMZ). W ten sposób dostawcy usług najpierw łączą się z DMZ, a nie bezpośrednio z siecią ICS. Tam uzyskują wymagany dostęp tylko do systemu docelowego.

**6.** zdalny dostęp powinien być zawsze kierowany przez firewall (zaporę ogniową), która pozwala i monitoruje dostęp do systemu docelowego. Odpowiednie reguły pozwalają na ujawnienie tylko tych adresów IP, portów i systemów, które są niezbędne do wykonania prac serwisowych

**7.** zapewnienie zdalnego dostępu pracownikom wyłącznie na czas prowadzenia konkretnego zadania serwisowego.

**8.** rejestrowanie sesji dostępu zdalnego w celu zapewnienia identyfikowalności. Należy zastosować dodatkowe procesy, aby zapewnić, że zarejestrowane dane zostaną ocenione i zarchiwizowane.

**9.** korzystanie ze spersonalizowanych środków dostępu, tzn. nie można współdzielić kont funkcjonalnych, co oznacza, przypisanie loginu do pojedynczego użytkownika.

**10.** cykliczny audyt systemów oraz środków dostępu.

Do monitorowania zdalnego dostępu służą m.in. rozwiązania firmy Honeywell oparte na platformie Forge.

**Źródła:**

- [Industrial Control System Security Top 10 Bedrohungen und Gegenmaßnahmen 2019](https://www.allianz-fuer-cybersicherheit.de/ACS/DE/_/downloads/BSI-CS/BSI-CS_005.pdf?__blob=publicationFile&v=12)
- [CISA: ICS Advisory (ICSA-17-236-01)](https://www.us-cert.gov/ics/advisories/ICSA-17-236-01)
- [ICS Cert Monitor](https://www.us-cert.gov/sites/default/files/Monitors/ICS-CERT_Monitor_Jan-April2014.pdf)