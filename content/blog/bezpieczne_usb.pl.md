+++
lang="pl-PL"
title="Jak bezpiecznie korzystać z nośników wymiennych w sieciach ICS?"
date="2020-01-09"
author="Józef Sulwiński, Michał Stępień"
image="/blog/Bezpieczne_USB.jpg"
tags=['automatyka przemysłowa', 'czwartki OT', 'infrastruktura krytyczna']

+++

Właśnie mija 10 lat od wydania alertu przez Cybersecurity and
Infrastructure Security Agency (CISA) wskazującego zagrożenia związane
ze stosowaniem nośników USB jako jednego ze źródeł zagrożeń dla systemów
sterowania. Pomimo upływu lat, zagrożenia te cały czas istnieją i jak
pokazuje przykład ataku znanego jako Operacja Copperfield, cały czas
powinniśmy się ich obawiać. Warto zwrócić uwagę, że Federalny Urząd ds.
Bezpieczeństwa Informacji w opublikowanym w 2019 raporcie wymienia je
jako jedno z głównych zagrożeń dla systemów ICS.


## Nośniki USB jako jedno ze źródeł zagrożeń dla systemów sterowania{ .article-section }

11 grudnia 2017 r. o godz. 01:21 pracownik nocnej zmiany w jednym z
zakładów przemysłowych na Bliskim Wschodzie podłączył napęd USB do
współdzielonej stacji roboczej, z której na co dzień korzystają
dziesiątki pracowników firmy. Pracownik oglądał film La La Land, który
podczas przerwy pobrał na swój dysk USB. Nie wiedział, że jego działania
zapoczątkowały sekwencję wydarzeń, które mogły mieć katastrofalne skutki
dla jego organizacji. Wraz z uruchomieniem filmu rozpoczął się dobrze
przygotowany atak, znany jako Operacja Copperfield.

Nośniki danych, takie jak dyski USB, dyski zewnętrzne, karty pamięci są
szeroko stosowane. Pracownicy korzystają z nich zarówno w biurze, jak i
w sieciach ICS. Często zabierają je do domu, aby kontynuować prace nad
projektami lub po prostu skopiować najnowsze filmy czy muzykę. Dostawcy
zewnętrzni często przynoszą własne komputery (BYOD), na których
przechowywane są dane konfiguracyjne oraz oprogramowanie serwisowe,
które nierzadko jest wykorzystywane przy różnych instalacjach, u różnych
klientów. **Niestety pracownicy oraz dostawcy zewnętrzni często nie są
świadomi skutków powodowanych przez złośliwe oprogramowanie. Pomimo
wysokiej wiedzy dotyczącej aspektów BHP i bezpieczeństwa fizycznego cały
czas można zaobserwować niską świadomość zagrożeń cybernetycznych.**

## 3 scenariusze zagrożeń, które warto omówić podczas okresowych szkoleń dla pracowników i dostawców zewnętrznych{ .article-section }

**Scenariusz 1.**\
Nośniki USB mogły zostać zainfekowane w sieci biurowej lub w środowisku
prywatnym. W następstwie tego złośliwe oprogramowanie może zostać
przeniesione za pomocą tych nośników do sieci, w której funkcjonują
rozwiązania ICS (nawet jeżeli jest ona odizolowana).

**Scenariusz 2.**\
Komputery przenośne używane do konserwacji mogły zostać zainfekowane
podczas uzyskiwania dostępu do Internetu, sieci biurowej lub w
infrastrukturze dostawcy zewnętrznego. W przypadku użycia takiego
urządzenia w sieci ICS, narażamy nasze krytyczne systemy i komponenty
automatyki na zainfekowanie złośliwym kodem.

**Scenariusz 3.**\
Przenoszone pliki projektów lub aplikacje serwisowe mogą byś odpowiednio
spreparowane i zawierać złośliwy kod prowadzący do infekcji lub wycieku
danych.

## Metody zabezpieczeń przed zagrożeniami związanymi z nośnikami wymiennymi{ .article-section }

**[1.]** wprowadzenie mechanizmów whitelistingu
nośników wymiennych (tylko zarejestrowane nośniki są dopuszczane do
użytku),

**[2.]** każdorazowe sprawdzanie nośników
wymiennych pod kątem złośliwego oprogramowania na izolowanej stacji
roboczej lub w kiosku, na których znajduje się inny system operacyjny
niż komputery obsługi technicznej,

**[3.]}** wyraźne, unikalne oznaczanie nośników
wymiennych dedykowanych do użytku prywatnego (nie wolno używać ich w
sieciach chronionych),

**[4.]** wyraźne, unikalnie oznaczanie nośników
wymiennych dedykowanych wyłącznie do sieci OT,

**[5.]** instalowanie fizycznych barier
uniemożliwiających nieautoryzowane wykorzystanie wbudowanych w
urządzenia portów USB (zaklejenie, instalacja blokad USB lub odlutowanie
obwodów),

**[6.]** wdrożenie mechanizmów pełnego
szyfrowania nośników danych.

## Wymagania i mechanizmy kontrolne dla dostawców zewnętrznych wykorzystujących urządzenia przenośne w naszej sieci{ .article-section }

Dla dostawców zewnętrzych warto wprowadzić poniższe wymagania i
mechanizmy kontrolne:

**1.**
za pośrednictwem i przy użyciu wyżej wymienionych mechanizmów
kontrolnych,

**2.** 
wdrożenie mechanizmów kwarantanny
sieciowej dla połączeń dostawców usług zewnętrznych,

**3.** 
obowiązkowe skanowanie antywirusowe
wszystkich zewnętrznych urządzeń przed podłączeniem ich do sieci,

**4.**
zapewnienie przez właściciela danego
zasobu pełnego szyfrowania komputerów przenośnych wykorzystywanych w
celach serwisowych.

Czy wspomniane na wstępie zagrożenie jest na tyle poważne, że wymaga
wprowadzenia aż tylu rozwiązań zabezpieczających? Niestety tak. Jak
pokazuje doświadczenie, nośniki wymienne oraz komputery przenośne są
wykorzystywane do przenoszenia złośliwego oprogramowania nawet do
galwanicznie wyizolowanych sieci. To była podstawowa forma
rozpowszechniania się robaka STUXNET.

Przeczytaj więcej o [Secure Media
Exchange](https://seqred.pl/smx-secure-media-exchange/)

Na koniec warto wskazać na pojawiające się rozwiązania bezpieczeństwa,
które mają wspomagać kontrolowane bezpieczne korzystanie z nośników
wymiennych w sieciach ICS.

Jednym z rozwiązań jest **SMX -- Secure Media eXchange firmy
Honeywell.** Niedługo będzie można przetestować działanie tego
rozwiązania w naszej siedzibie.

**Źródła:**\
[ISS Source: ICS Alert USB Malware Attack](https://isssource.com/ics-alert-usb-malware-attack/)
[Industrial Control System Security: 10 najważniejszych zagrożeń i środków zaradczych 2019](https://www.allianz-fuer-cybersicherheit.de/ACS/DE/_/downloads/BSI-CS/BSI-CS_005.pdf?__blob=publicationFile&v=12)
[CISA: USB Usage](https://www.us-cert.gov/ics/tips/CSAR-10-114-02)