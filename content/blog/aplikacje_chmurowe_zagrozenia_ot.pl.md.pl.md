+++
lang="pl-PL"
title="Aplikacje chmurowe jednym z zagrożeń dla sieci OT"
date="2020-01-22"
image="/blog/Seqred_cloud_OT.jpg"
author="Michał Stępień"
tags=['automatyka przemysłowa', 'czwartki OT', 'infrastrukura krytyczna']
+++

## Aplikacje chmurowe jednym z zagrożeń dla sieci OT{ .article-section }

Zjawisko outsourcingu zasobów znane z IT zyskuje swoich zwolenników
także w środowisku OT, czyli tam, gdzie występują systemy automatyki.

## Wykorzystanie usług chmurowych w systemach OT{ .article-section }

### Zdalny monitoring procesów oraz zużycia mediów

Usługi chmurowe są proponowane np. do prezentacji zużycia mediów oraz
możliwości optymalizacyjnych, analizy pętli regulacji i dostrajania
nastaw regulatorów. Realizacja bezpośrednich zadań sterowania dla
procesów szybkozmiennych pozostaje jeszcze nieosiągalna (ze względu na
występowanie opóźnień przy transmisji danych). Ciągle rośnie
wykorzystanie komponentów chmurowych do gromadzenia oraz przetwarzania
danych historycznych, obliczania złożonych modeli (np. modelowania
uszkodzeń, realizacji algorytmów regulacji), a także optymalizacji
procesów.

### Zdalny monitoring maszyn i systemów automatyki procesowej

Dostawcy usług chmurowych oferują aplikacje wykorzystywane (np. przez
integratorów, dział utrzymania ruchu) do nawiązania zdalnego połączenia
ze sterownikami maszyn. Takie rozwiązania są dedykowane zwłaszcza dla
małych i średnich przedsiębiorstw (sektor MŚP), dla których integracja
własnych aplikacji (np. zakup i utrzymanie sprzętu, licencji na
oprogramowanie) często okazują się ekonomicznie nieuzasadnione. Systemy
wykorzystujące komponenty chmurowe mogą okazać się konkurencyjne cenowo,
a ponadto często oferują takie korzyści jak: skalowalność, redundancję
oraz opłatę za użycie (Pay-Per-Use).

Wadą stosowania takich rozwiązań w sieciach przemysłowych jest oddanie
kontroli nad bezpieczeństwem (np. informacji oraz częściowo urządzeń)
podmiotom zewnętrznym, np. dostawcom usług chmurowych.


## 3 scenariusze zagrożeń, które warto zaprezentować i omówić podczas okresowych szkoleń dla pracowników i dostawców zewnętrznych.{ .article-section }

**Scenariusz 1.**

Modyfikacja lub zakłócenie komunikacji pomiędzy urządzeniami lokalnymi
(np. sterownikami) oraz aplikacjami chmurowymi (Cloud) np. poprzez ataki
na dostępność usług (ataki typu DoS). Jeśli dane przekazywane z systemów
automatyki będą niewłaściwe lub niedostępne, może to prowadzić do
wygenerowania nieprawidłowego modelu procesu. W przypadku, gdy taki
model wykorzystywany jest bezpośrednio do realizacji zadań sterowania
(np. kotłem, wentylacją oraz rekuperacją w celu optymalizacji zużycia
mediów w budynku), błędne informacje doprowadzą do zaburzenia systemów
HVAC.

**Scenariusz 2.**

Wykorzystanie błędów implementacyjnych lub niewystarczających
mechanizmów bezpieczeństwa w celu uzyskania dostępu do danych
przechowywanych na serwerach zewnętrznych (kradzież danych, usunięcie),

**Scenariusz 3.**

Jeśli dane klientów dzierżawiących infrastrukturę lub usługi\
chmurowe nie są odizolowane we właściwy sposób, atak na zasoby jednego
klienta, może doprowadzić do zakłóceń lub wtórnych ataków na pozostałych
(collateral damage).

## Działania pomagające zmniejszyć ryzyko ataku na sieć OT związane z wykorzystaniem komponentów chmurowych?

**1.** podpisywanie dostosowanych do
oczekiwań oraz wymagań zobowiązań kontraktowych z operatorami
zewnętrznych komponentów w celu zapewnienienia należytego poziomu
świadczenia usług, np. poprzez umowę o gwarantowanym poziomie usług
(SLA),

**2.** współpraca tylko z zaufanymi oraz
jeśli to możliwe certyfikowanymi zewnętrznymi dostawcami usług,

**3.** stosowanie chmury prywatnej w celu
zachowania kontroli oraz chronienia wiedzy (know-how) o procesie,

**4.** zastosowanie silnych mechanizmów
kryptograficznych, takich jak szyfrowanie lub kontrola integralności, w
celu ochrony danych przechowywanych w chmurze,

**5.** Korzystanie z wirtualnych sieci
prywatnych (VPN) w celu zabezpieczenia połączenia między wydzieloną
siecią korporacyjną, a komponentami zewnętrznymi.

Warto wskazać, że przed przystąpieniem do samodzielnej implementacji
rozwiązań chmurowych w przedsiębiorstwie, warto przeprowadzić np. audyt
gotowości przedsiębiorstwa do wdrożenia usług cyfrowych (zgodnych z ideą
Industry 4.0). Jest wiele firm oferujących takie rozwiązania, a jedną z
nich jest firma Siemens. Więcej na temat bezpieczeństwa rozwiązań
chmurowych poruszymy w cyklu artykułów: „Wtorki w chmurze" -- pierwszy
odcinek już niebawem na LinkedIn

**Źródło:**

[Industrial Control System Security: 10 najważniejszych zagrożeń i
środków zaradczych
2019](https://www.allianz-fuer-cybersicherheit.de/ACS/DE/_/downloads/BSI-CS/BSI-CS_005.pdf?__blob=publicationFile&v=12){rel="noopener noreferrer"
target="_blank"}