+++
lang="pl-PL"
title="Sabotaż i błąd ludzki w czołówce zagrożeń cybernetycznych OT"
date="2020-02-05"
author="Michał Stępień"
image="/blog/Seqred_Bezpieczne_OT.jpg"
tags=['bezpieczeństwo OT', 'Czwartki OT']
+++

Przedmiotem analizy poziomu bezpieczeństwa maszyn i urządzeń jest stopień spełnienia wymagań dotyczących bezpieczeństwa fizycznego (Safety). Wraz z rozwojem elektronicznych układów, w tym programowalnych, czynnikiem wpływającym na niezawodne działanie systemów realizujących funkcje bezpieczeństwa stał się aspekt cyberbezpieczeństwa.

Coraz częściej modyfikacje programów nie wymagają fizycznej obecności programisty i mogą być przeprowadzane zdalnie (np. z wykorzystaniem zdalnego dostępu np. VPN). W ten sam sposób ataki mogą być przeprowadzane przez hakerów. Płaszczyzna ataku zwiększa się, gdyż przy modernizacji oraz budowie nowych instalacji często uczestniczą także partnerzy zewnętrzni (np. integratorzy), którzy mogą być np. celem inżynierii społecznej.

Możliwość nieautoryzowanej modyfikacji programu, szczególnie zdalnej, jest źródłem nowych zagrożeń dla bezpieczeństwa ludzi oraz procesów ze strony hakerów. Atakujący czerpią wiedzę np. z otwartych źródeł (OSINT) dzięki której mogą przeprowadzać ataki przygotowując odpowiednie narzędzia. Źródłem tych informacji są najczęściej pracownicy lub bezpośrednio firmy padające ofiarą ataków.


> ## W jaki sposób błąd ludzki spowodował odłączenie od prądu 45 milionów mieszkańców USA oraz 10 mln Kanadyjczyków?{ .article-section }

14.09.2003 12:15 system telemetrii dostarcza nieprawidłowe dane do systemu optymalizującego rozpływ energii elektrycznej w sieci elektroenergetycznej. Operator naprawia problem związany z telemetrią, ale zapomina zresetować system sterowania nadrzędnego zasilony błędnymi danymi. Dalsze kaskadowe awarie wynikające z przeciążania sieci, doprowadzą do wyłączenia 256 elektrowni, z czego 85 proc. z nich zostało wyłączone w wyniku zadziałania automatycznych zabezpieczeń. Efekt? 45 milionów mieszkańców USA oraz 10 mln Kanadyjczyków pozostaje bez prądu.

> ## 8 scenariuszy zagrożeń, które warto zaprezentować i omówić podczas okresowych szkoleń dla pracowników i dostawców zewnętrznych.{ .article-section }

**Scenariusz 1.**  
Wprowadzenie reguły niezbędnej wiedzy (need-to-know): dostęp do wrażliwych danych (w tym haseł), szczegółów budowy i funkcjonowania instalacji (ICS) przekazywany pracownikom tylko w ograniczonym, niezbędnym zakresie.

**Scenariusz 2.**  
Stworzenie ogólnych wytycznych dla motywowania, podnoszenia kompetencji oraz budowy relacji między zespołami. Wzajemne zrozumienie podstaw funkcjonowania procesów oraz elementarnych zasad bezpieczeństwa odpowiednio przez administratorów oraz operatorów może pozwolić na uniknięcie wielu elementarnych błędów, które mogą przesądzić o powodzeniu hakerów. Programy rozwijające kwalifikacje oraz szkolenia powinny być obligatoryjne i dostosowane do profilu grup pracowników (np. przekazywanie zaawansowanych informacji z zakresu cyberbezpieczeństwa operatorom, może wiązać się z niezrozumieniem oraz niechęcią do udziału w takich kursach).

**Scenariusz 3.**  
Odłączenie dostępu do Internetu systemom około-produkcyjnym oraz realizującym funkcje sterowania. Narzędzia i systemy około-biznesowe nie związane bezpośrednio z systemami automatyki, do których należą np. poczta elektroniczna oraz inne aplikacje biurowe, muszą być zabezpieczone oraz zintegrowane z inną siecią.

**Scenariusz 4.**  
Wprowadzenie ustandaryzowanych procesów rekrutacji, przyjmowania oraz zwalniania personelu. Proces standaryzacji powinien obejmować także zewnętrznych wykonawców, takich jak: dostawcy produktów i usług, integratorzy.

**Scenariusz 5.**  
Opracowanie i stosowanie odpowiednich polityk i procedur obsługi technicznej systemów i urządzeń. Przykłady obejmują zasady korzystania z nośników wymiennych, zasady komunikacji w korespondencji e-mail i sieciach społecznościowych, reguły dotyczące stosowania haseł oraz instalacji własnego oprogramowania.

**Scenariusz 6.**  
6) Wprowadzenie odpowiednich polityk dla krytycznych procesów przemysłowych. Zalicza się do nich np. standardy dotyczące bezpieczeństwa i zarządzania konfiguracją. W ich tworzeniu oraz wypełnianiu uczestniczą eksperci do spraw bezpieczeństwa oraz odpowiednie zespoły pracowników (np. utrzymania ruchu, inwestycji, zakupów technicznych). Działania polegające na wdrożeniu zmian, modernizacji, aktualizacji systemów automatyki będą konsultowane, a do ich integracji dojdzie po akceptacji działu bezpieczeństwa. Ważne jest przy tym dokumentowanie wszystkich uzgodnień oraz stosowanie dodatkowych środków bezpieczeństwa, np. reguły czterech oczu (four-eyes principle).

**Scenariusz 7.**  
Automatyczne monitorowanie stanu systemów oraz konfiguracji (o ile możliwe).

**Scenariusz 8.**  
Bezpieczne przechowywanie projektów oraz konfiguracji.

Warto podkreślić, że zapewnienie bezpieczeństwa cybernetycznego nie jest stanem (jak może to mieć miejsce w przypadku niemodernizowanych instalacji), lecz procesem – metody oraz środki bezpieczeństwa podlegają zmianom. Warto zaangażować zespoły odpowiedzialne za Systemy Automatyki w cykliczne szkolenia pozwalające na podnoszenie świadomości bezpieczeństwa w OT (Cybersecurity) w obliczu nowych zagrożeń.

> ## Obszary ryzyk: Ludzie, proces, technologia{ .article-section }

Ponieważ środowisko cybernetyczne współtworzą: ludzie, proces oraz technologie, zapewnienie określonego poziomu bezpieczeństwa nie może być ograniczone jedynie do środków technicznych, ale powinno uwzględniać także wprowadzenie oraz aktywne stosowanie przepisów organizacyjnych. Scenariusze opisane powyżej mogą się zmaterializować w wynikiu sabotażu lub szpiegowania, ale także zaniedbań i błędów ludzkich. Wspólnym mianownikiem tych wszystkich działań są niedociągnięcia organizacyjne. Pomimo obecności określonych procedur, mogą one być nieprzestrzegane, a ich skuteczność niewalidowana w praktyce (działaniach).

> ## Działania pomagające zmniejszyć ryzyko ataku:{ .article-section }

**1.** podpisywanie dostosowanych do oczekiwań oraz wymagań zobowiązań kontraktowych z operatorami zewnętrznych komponentów w celu zapewnienienia należytego poziomu świadczenia usług, np. poprzez umowę o gwarantowanym poziomie usług (SLA),

**2.** współpraca tylko z zaufanymi oraz jeśli to możliwe certyfikowanymi zewnętrznymi dostawcami usług,

**3.** stosowanie chmury prywatnej w celu zachowania kontroli oraz chronienia wiedzy (know-how) o procesie,

**4.** zastosowanie silnych mechanizmów kryptograficznych, takich jak szyfrowanie lub kontrola integralności, w celu ochrony danych przechowywanych w chmurze,

**5.** Korzystanie z wirtualnych sieci prywatnych (VPN) w celu zabezpieczenia połączenia między wydzieloną siecią korporacyjną, a komponentami zewnętrznymi.
