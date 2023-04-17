+++
lang="pl-PL"
title="Segmentacja sieci. Ochrona systemów przemysłowych przed cyberatakami"
date="2019-08-23"
author="Michał Stępień"
image="/blog/Seqred_Segmentacja_Sieci.jpg"
tags=['automatyka przemysłowa', 'bezpieczeństwo OT', 'infrastruktura krytyczna', 'segmentacja sieci']
+++

W ostatnich latach układy automatyki przemysłowej wielokrotnie padały ofiarą ataków cybernetycznych. Wielowymiarowy atak na infrastrukturę energetyczną Ukrainy pozbawił energii blisko 225 tys. użytkowników. Czy segmentacja sieci może przyczynić się do ochrony przed atakiem lub do ograniczenia jego skutków?

**Z artykułu dowiesz się o:**

*   cyberatakach na systemy przemysłowe. Czy zagrożenie jest realne?
*   jak chronić sieci przemysłowe przed atakami
*   co to jest segmentacja sieci? Jak wpływa na poprawę bezpieczeństwa?
*   modelu Purdue – modelu referencyjnym architektury sieciowej
*   jakie jest główne źródło ataku na infrastrukturę przemysłową OT
*   przykładach dobrych praktyk z zakresu segmentacji sieci


 ## Cyberataki na sieci przemysłowe. Czy zagrożenie jest realne?{ .article-section }

Ataki hakerskie stanowią coraz poważniejszy problem mogący poważnie zagrozić funkcjonowaniu fabryk, czy sieci elektroenergetycznych. Należy przy tym zaznaczyć, że mowa jest o konkretnych, skutecznych atakach, a nie samych incydentach. Przeanalizujmy kilka z nich.

### Rok 2010 – Stuxnet – atak na infrastrukturę wzbogacania uranu w Iranie

Atak został przeprowadzony przy wykorzystaniu złośliwego oprogramowania. Pośrednim celem ataku był system SCADA oraz sterowniki PLC. Raporty donoszą, że konsekwencją tych działań było opóźnienie programu.

### Rok 2015 – wielowymiarowy atak BlackEnergy na infrastrukturę energetyczną Ukrainy

Adwersarze posłużyli się wyrafinowanymi metodami ataku: byli w stanie nie tylko przełączyć poszczególne wyłączniki na podstacjach elektroenergetycznych, ale także zmodyfikować firmware wybranych urządzeń, aby w ten sposób wpływać na sprzętowe konwertery, takie jak bramki serial – Ethernet. Przerwy w dostawie energii dotknęły 225 tys. użytkowników.

## Jak chronić sieci przemysłowe przed cyberatakami?{ .article-section }

Pierwszym z zaleceń, które zostały przekazane w dokumencie organizacji SANS opisującym szczegółowo atak na infrastrukturę elektroenergetyczną Ukrainy w 2015 oraz 2016 było przeprowadzenie odpowiedniej segmentacji sieci. **Zastosowanie prawidłowego podziału na bazie referencyjnego modelu architektury sieciowej – Purdue Model może przyczynić się do opóźnienia finalizacji ataku lub też do ograniczenia jego skutków.**

## Segmentacja sieci – co to jest? Jak przyczynia się do poprawy bezpieczeństwa?

Segmentacja sieci polega na wyodrębnieniu funkcjonalnych warstw urządzeń i metod komunikacji, co pozwala ograniczyć wymianę informacji między komponentami różnych warstw do niezbędnego minimum.

Proces segmentacji komplikuje fakt, że docelowy projekt sieci często zmienia się w trakcie jej implementacji, dlatego przydatne może okazać się zebranie jak największej ilości informacji o urządzeniach pracujących w sieci OT.

W często zmieniającym się, rozległym środowisku produkcyjnym, utrzymanie aktualności dokumentacji projektowej także może okazać się wyzwaniem. Sama lista urządzeń wraz z portami nie wystarczy. Konieczna jest dalsza analiza danych w celu pozyskania właściwych reguł na aktywne urządzenia sieciowe oddzielające poszczególne warstwy.

## **Model Purdue – model referencyjny architektury sieciowej**{ .article-section }

![](/blog/Purdue_Model_Architektury_Sieciowej.jpg)

## **Wyodrębnienie stref kluczowych**{ .article-section }

Konieczność integracji usług biznesowych między przedsiębiorstwami (Business-To-Business interface, RSG, itp.), a co za tym idzie obecność połączeń z zewnątrz w infrastrukturze przedsiębiorstwa, powoduje konieczność oceny poziomu bezpieczeństwa i wyodrębnienia stref kluczowych odpowiedzialnych za proces, w których takie bezpieczeństwo powinno być zapewnione w sposób szczególny. Izolacja powinna zostać przeprowadzona w taki sposób, aby urządzenia wymagające zapewnienia podobnego poziomu bezpieczeństwa znalazły się w tej samej lub przyległej warstwie.

Granice pomiędzy strefami powinny być przedmiotem szczególnej uwagi, poprawność reguł powinna być aktualizowana oraz weryfikowana, a ruch wewnątrz poszczególnych warstw, w miarę możliwości, powinien być monitorowany i analizowany (IPS/IDS).

Celem zastosowania odpowiedniej separacji sieci OT od warstwy biznesowej oraz Internetu jest utrudnienie dostępu potencjalnych adwersarzy do urządzeń bezpośrednio odpowiedzialnych za ciągłość procesu.

Warstwy niższe, niebiznesowe, mają bezpośredni wpływ na życie ludzkie, a także ciągłość przebiegu procesu, dlatego zapewnienie bezpieczeństwa jest szczególnie ważne.

## Dostęp do urządzeń z Internetu – główne źródło ataków na infrastrukturę przemysłową OT{ .article-section }

Według raportów czołowego producenta oprogramowania antywirusowego, w II połowie 2018 roku, głównym źródłem ataków na infrastrukturę przemysłową był dostęp do urządzeń z Internetu. Stanowiły one około 1/3 wszystkich ataków przeprowadzonych na te urządzenia. Dane te nie uwzględniały ataków z wykorzystaniem wiadomości e-mail, takich jak: phishing, whaling czy spear phishing.

Według danych dostępnych na portalu [Shodan,](https://seqred.pl/shodan-rekonesans-infrastruktury-it-ot/) z dnia pisania artykułu, blisko 11 tysięcy urządzeń sieciowych trzech czołowych producentów systemów automatyki było wystawionych do Internetu. Dane z innych portali zagranicznych pokazują, że liczba ta może być nawet czterokrotnie wyższa. Gdyby udało się przeprowadzić skuteczny atak tylko na część z nich wiele państw oraz globalnych korporacji musiałoby stawić czoła destabilizacji.

> ## Brak bezpośredniego podłączenia systemu automatyki do Internetu nie zapewnia bezpieczeństwa{ .article-section }

Pomimo tego, że w poszczególnych warstwach sieci przemysłowych OT wykorzystuje się różne protokoły przemysłowe, sama ich różnorodność nie zapewnia cyberbezpieczeństwa. Brak bezpośredniego podłączenia sterownika automatyki do Internetu, nie oznacza, że połączenie z nim nie jest możliwe z komputera znajdującego się w wewnętrznej sieci. Warto poznać przyczynę z której wynika ten problem.

W przemyśle występują dwie podstawowe rodziny protokołów: routowalne oraz nieroutowalne. Różnią się one zasięgiem oraz dostępnością przekazywanych informacji.

Protokoły routowalne mogą być wykorzystywane do wymiany danych i być transportowane do innych warstw przez urządzenia sieciowe, takie jak routery czy firewalle. Najczęściej korzystają one z warstwy IP modelu ISO-OSI (TCP/IP lub UDP/IP).

Dla protokołów nieroutowalnych, urządzeniami ograniczającymi zasięg przekazywania informacji są wspomniane wcześniej aktywne urządzenia sieciowe. Pierwotnie wykorzystywane: Modbus RTU, Profibus DP, DNP3, IEC60870-5:101 zostały uzupełnione takimi protokołami jak: Modbus TCP, Profinet, DNP3 po TCP/UDP a także IEC60870-5:104.

Przekazywanie informacji pomiędzy sieciami należącymi do różnych grup, jest możliwe nie tylko przy wykorzystaniu dedykowanego konwertera, ale także dzięki zastosowaniu opcjonalnych modułów komunikacyjnych do sterowników PLC. Zastosowanie takich rozwiązań wymaga przy tym modyfikacji programu sterującego, ale umożliwia przekazywanie informacji z jednej podsieci do innej np. routowalnej (Profinet) do nieroutowalnej (Profibus DP).

Przykład ataku na sieć elektroenergetyczną Ukrainy pokazuje, że samo zapewnienie różnorodności protokołów (routowalnych i nieroutowalnych) nie oznacza, że potencjalni adwersarze nie będą w stanie zagrozić infrastrukturze krytycznej.

## Przykłady dobrych praktyk z zakresu segmentacji sieci:{ .article-section }

Segmentacja sieci nie może być działaniem jednorazowym, należy ją rozumieć jako proces i dbać o aktualność reguł, czy oprogramowania na urządzeniach. Poniżej przedstawiamy zestawienie dobrych praktyk, które mogą pomóc w ochronie przed cyberatakiem:

*   zastosowanie reguły minimalnych uprawnień oraz ograniczenie stacji oraz osób mających dostęp do najniższych warstw,
*   cykliczna aktualizacja i weryfikowanie poprawności reguł sieciowych aktywnych urządzeń umożliwia proaktywne podniesienie poziomu bezpieczeństwa,
*   przeniesienie urządzeń zapewniających zdalny dostęp poza sieć przemysłową OT do warstw wyższych – pozwala na właściwe zarządzanie oraz ograniczenie dostępu do urządzeń do niezbędnego minimum. Działania niepożądane mogą być przy tym rejestrowane lub wykrywane przez narzędzia takie jak IDS / IPS,
*   dla procesów krytycznych oraz układów bezpieczeństwa można rozważyć rozwiązania zapewniające fizyczną separację, takie jak air-gap.

[Chcesz porozmawiać o bezpieczeństwie systemów przemysłowych? Skontaktuj się z nami. Chętnie pomożemy!](https://seqred.pl/kontakt/)
