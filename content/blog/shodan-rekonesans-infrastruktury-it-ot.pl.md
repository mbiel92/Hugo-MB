+++
lang="pl-PL"
title="Shodan improved – zaawansowany rekonesans z użyciem Shodana"
date="2019-06-26"
author="Jakub Dzieciątko"
image="/blog/Seqred_Shodan.jpg"
tags=['bezpieczeństwo IT', 'narzędzia', 'shodan']
+++

Dobrze przeprowadzony rekonesans jest podstawą dalszych działań ofensywnych podczas testów bezpieczeństwa. Umiejętność wyszukiwania informacji i odpowiedniego ich uporządkowania może decydować o łatwości późniejszych faz, a w skrajnych przypadkach nawet o ich wykonalności.

Wykrycie większej ilości hostów, czy działających na nich usług, zwiększa powierzchnię ataku (attack surface), dając większą swobodę zespołowi wykonującemu zadanie. Pozwala też na dokładniejszą weryfikację bezpieczeństwa testowanej organizacji.

Również w przypadku ataków socjotechnicznych rekonesans jest niezwykle istotny. Dodatkowe informacje pozwalają precyzyjniej przygotowywać testy spear phishingowe, czy lepiej reagować w przypadku fizycznych testów penetracyjnych.

**W tym artykule chciałbym podzielić się narzędziami pomagającymi na gromadzenie i analizowanie informacji z popularnej wyszukiwarki Shodan.**


## Co to jest Shodan?{ .article-section }

Shodan to przydatne narzędzie w początkowej fazie testu. Pozwala na bardzo szybkie sprawdzenie, jakie urządzenia danej organizacji są dostępne w sieci.

Shodan jest wyszukiwarką (często porównywaną do Google’a), która indeksuje i pozwala na przeglądanie urządzeń podłączonych do Internetu. Posiada specjalne skanery stworzone wyłącznie na potrzeby budowy własnej bazy danych. Każdy z nich nieustannie wybiera losowy publiczny adres IP, skanuje wybrany port i umieszcza wyniki w bazie, która następnie jest udostępniona do przeszukiwania.

Shodan pozwala na błyskawiczne odnajdywanie systemów pod kątem podatności, przynależności do danej organizacji, rodzaju wykorzystanego protokołu, lokalizacji i wiele innych. To wszystko bez wysłania nawet jednego pakietu w stronę docelowego systemu.

Pomimo, że wyszukiwarka jest niezwykle potężnym narzędziem, posiada swoje ograniczenia. Czasem chcielibyśmy przedstawić wyniki w innej formie niż w przeglądarce lub wygenerowanym przez Shodana raporcie, robić bardziej złożone zapytania lub rozbudować uzyskane wyniki o własne, dodatkowe skrypty.

Shodan udostępnia API (Application Programming Interface) pozwalające odpytywać swoją bazę. W darmowej wersji dostępne jest do 100 wyników w każdym zapytaniu, istnieją też mniej ograniczone wersje płatne (subskrypcja z płatnością co miesiąc). Istnieją narzędzia potrafiące doskonale wykorzystywać API, takie jak biblioteka shodan w Pythonie albo recong. Jeśli wcześniej nie były Ci znane te narzędzia, polecam się z nimi zapoznać.

Nie znalazłem jednak narzędzia pozwalającego na praktycznie dowolną analizę zebranych wyników. Po przetestowaniu różnych metod (m.in. ręczne przeklejanie do Excela – nigdy więcej) zdecydowałem się stworzyć własne narzędzie, dające dużo elastyczności w zbieraniu i prezentacji wyników.

## Narzędzie ShoSearch – zbieranie danych z API i zapisywanie ich lokalnie{ .article-section }

Pierwsze narzędzie dotyczy zbierania danych z API i zapisywania ich lokalnie. Wykorzystuje bazę danych mongodb, ponieważ wyniki z API są w formacie JSON, który bardzo łatwo umieszczać w tego typu nierelacyjnej bazie. Jest bardzo proste – jako argumenty przyjmuje klucz API, treść zapytania oraz nazwę kolekcji, do której mają trafić wyniki.

Narzędzie można uruchomić kilka razy dla tej samej kolekcji, wypełniając ją danymi naszego celu badanego od różnych stron – na przykład wykonując zapytania o podatne hosty w danej organizacji, wszystkie hosty w danym systemie autonomicznym itp.

![](/blog/ShoSearch.jpg)

[Pobierz ShoSearch](https://github.com/seqred-s-a/shosearch)

## Narzędzie ShoView – generowanie raportów na podstawie zawartości bazy mongodb{ .article-section }

Kolejne narzędzie służy do generowania raportów na podstawie zawartości bazy mongodb.  
Jego przewagą nad standardową metodą odpytywania Shodana jest możliwość korzystania z dowolnych filtrów, jakie obsługuje mongodb ([pełna lista filtrów w dokumentacji mongodb](https://docs.mongodb.com/manual/reference)).

Możemy więc wyświetlić wszystkie hosty ze zidentyfikowanymi podatnościami (-q ‘{„vulns” : {„$exists” : true}}’), albo wszystkie hosty z serwerem nginx, albo połączyć te filtry w dowolny sposób i wyświetlić to, co jest potrzebne w danym teście.

![](https://seqred.pl/blog/ShoView.png)

Wyszukiwarka Shodan nie posiada możliwości filtrowania np. po rDNS, a w niektórych wersjach API nie można filtrować po podatnościach. To narzędzie pozwala to zrobić, korzystając z filtrów mongodb.

Co więcej, template dołączony do tego narzędzia podświetla na czerwono podatności z dostępnym exploitem na exploit-db / rapid7 (metasploit). Po nasunięciu myszką na podatność wyświetla się jej opis oraz odnośniki do dodatkowych informacji lub w przypadku „czerwonych” wpisów, link do exploita.

[Pobierz ShoView](https://github.com/seqred-s-a/shoview)

![](/blog/Seqred_Shodan_3.png)

Odpowiednie przeprowadzenie rekonesansu pomaga uniknąć niebezpiecznych przeoczeń w trakcie testu i ułatwia późniejszy powrót do zebranych informacji.

Oprócz do Shodana, podobne podejście można zastosować w stosunku do innych narzędzi zwracających wyniki w formacie JSON.


