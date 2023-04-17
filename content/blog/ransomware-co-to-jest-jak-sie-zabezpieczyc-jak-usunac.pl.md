+++
lang="pl-PL"
title="Ransomware – co to jest i jak go usunąć? Jak się zabezpieczyć?"
date="2020-07-27"
author="Łukasz Dudkowski / Seqred"
image="/blog/Ransomware-infografika-Seqred_in.jpg"
tags=['ransomware']
+++

Siadasz do komputera, pijesz poranną kawę i… na monitorze wyświetla się pstrokate okno informujące Cię, że Twoje dane zostały zaszyfrowane i tylko wpłata kryptowaluty na podany rachunek pozwoli Ci je odzyskać. Wszystkie zdjęcia, filmy, dokumenty – przepadły. Właśnie stałeś się ofiarą ransomware – cyfrowego szantażu. Jak do tego doszło? Czy można odzyskać dane?

#### **Z tego artykułu dowiesz się:**

*   co to jest ransomware
*   jakie są główne metody ataku
*   jakie zagrożenia niosą poszczególne rodzaje ransomware
*   kto może stać się ofiarą ataku
*   jak się zabezpieczyć przed ransomware
*   jak usunąć ransomware
*   jak odzyskać dane po ataku
*   RaaS: Ransomware-as-a-Service, czyli kup sobie ransomware

Przeczytaj artykuł i pobierz infografikę, aby dowiedzieć się czym jest ransomware i jak się przed nim zabezpieczyć. Infografika podsumowuje najważniejsze informacje. W artykule znajdziesz więcej szczegółów, w szczególności opis różnych przypadków ransomware.

> Co to jest ransomware?
> ----------------------

**Ransomware, czyli oprogramowanie szantażujące,** to rodzaj złośliwego oprogramowania, które po zarażeniu komputera szyfruje lub blokuje dostęp do danych zawartych na dyskach, a następnie informuje ofiarę o możliwości ich odzyskania. Oczywiście nie za darmo – wymagany jest przelew na wskazane konto.

![](/blog/Ransomware-co-to-jest.jpg)

> Pierwsze przypadki ataków: ransomware IDS / PC Cyborg
> -----------------------------------------------------

Pierwsze przypadki ataków z użyciem oprogramowania szyfrującego miały miejsce już w 1989 r. ransomware AIDS / PC Cyborg brał na cel przede wszystkim komputery firm z sektora medycznego. Przenoszony na dyskietkach 5,25 cala podszywał się pod ankietę dotyczącą ryzyka zarażenia się wirusem HIV. Wiadomość o okupie była drukowana na podłączonej do komputera drukarce.

> Rodzaje ransomware – jedne z najbardziej szkodliwych rodzajów oprogramowania
> ----------------------------------------------------------------------------

### Gpcode, Crypzip, MayArchive, CryptoLocker

Wraz z upowszechnieniem się dostępu do Internetu oraz wprowadzeniem kryptografii asymetrycznej, ransomware rozpoczęło swoją drogę do stania się jednym z najbardziej szkodliwych rodzajów oprogramowania. Już w 2006 r. pojawiła się cała gama trojanów stosujących szyfrowanie RSA (np. Gpcode, Crypzip, MayArchive) – ale prawdziwie globalnym zagrożeniem stał się działający od września 2013 r. CryptoLocker. Szacuje się, że w ciągu pierwszych stu dni jego działania ofiarą padło ponad 250 tysięcy urządzeń. Mechanizm infekcji był prosty: cel ataku otrzymywał wiadomość e-mail z ukrytym jako dokument plikiem wykonywalnym. Po uruchomieniu go CryptoLocker szyfrował pliki o wybranych rozszerzeniach zarówno na dysku lokalnym, jak i dostępnych zasobach sieciowych. Następnie, w każdym folderze z zaszyfrowanymi plikami tworzony był plik tekstowy zawierający informacje na temat wysokości i sposobu wpłaty okupu. Pomimo, że niewiele ofiar zdecydowało się zapłacić, przestępcy zarobili ponad 3 miliony USD.

### Petya

Innym ciekawym przypadkiem był aktywny od marca 2016 r. ransomware Petya. Zastosowano w nim odmienną metodę blokowania dostępu do danych ofiary. Zaszyfrowane zostają nie tylko pliki użytkownika, ale również plik MFT (master file table), co w konsekwencji uniemożliwia odczytanie struktury katalogów lub uruchomienie systemu Windows. Warto zwrócić uwagę, że celem ataków z użyciem tego wirusa były działy kadr w firmach publicznych i prywatnych. By zwiększyć szansę infekcji ransomware przesyłano jako złośliwy załącznik udający CV kandydata lub link do niego. Jedną z najbardziej poszkodowanych ofiar ulepszonej wersji wirusa – **NotPetya** – była największa na świecie firma transportowa A.P. Møller-Maersk. W wyniku ataku spółka zmuszona była funkcjonować bez infrastruktury IT przez 10 dni. Zdarzenie to zwróciło uwagę na fakt, że nie tylko firmy technologiczne narażone są na ataki hakerów.

### WannaCry

Warto wspomnieć również o robaku WannaCry, który w maju 2017 r. dotknął swoim działaniem ponad 100 krajów. Szacuje się, że zainfekowano 200 tysięcy komputerów – w tym także systemy brytyjskiej służby zdrowia, rosyjskie banki, indyjskie linie kolejowe oraz takie firmy jak Nissan czy FedEx. Przyczyną tak dużego zasięgu tego ransomware był brak bieżących aktualizacji systemu Windows – poprawka została udostępniona przez Microsoft jeszcze w kwietniu, prawie miesiąc przed wystąpieniem pierwszych ataków. Przykład ten dobitnie pokazuje jak ważne jest wykonywanie regularnych aktualizacji oprogramowania.

### Przykłady ataków z 2020 roku

*   Firma Visser Precision projektująca i produkująca elementy dla Boeinga, Tesli, SpaceX, Honeywella i Joe Gibbs Racing padła ofiarą ransomware **DopplePaymer.** Przestępcy ujawnili poufne dane firmy z powodu nieopłacenia okupu.
*   EDP – gigant energetyczny z Portugalii padł ofiarą ransomware **Ragnar Locker**. Przestępcy żądają 10 milionów dolarów w zamian za 10 terabajtów wykradzionych danych.
*   firma konsultingowa Cognizant pracująca m.in. dla Facebooka padła ofiarą ransomware **Maze.** Atak miał wpływ na funkcjonowanie części klientów.
*   University of California San Francisco, School of Medicine – 1 czerwca 2020 r. utraciła dostęp do części serwerów na skutek ataku ransomware. Uczelnia zapłaciła 1,14 mln dolarów za odzyskanie dostępu do danych badawczych.

> Oprogramowanie ransomware – główne metody ataku
> -----------------------------------------------

Najczęstszym źródłem infekcji może być złośliwe oprogramowanie, które trafiło do naszej skrzynki pocztowej w wyniku jednej ze zorganizowanych kampanii phishingowych. Ten model ataku zakłada podszycie się pod znanego nam nadawcę – np. bank, operatora telefonii komórkowej lub firmę kurierską i przekonanie do otwarcia załączonej faktury lub ściągnięcia jej spod wskazanego linku. Faktura lub inne ważne dokumenty zawierają szkodliwe oprogramowanie. Warto zauważyć w tym miejscu jak ważną rolę odgrywa aspekt psychologiczny przeprowadzonego ataku – wiadomość rzekomo przychodzi od zaufanego nadawcy.

Inne scenariusze bazują na podszywaniu się pod znane oprogramowanie – np. instalacje darmowego pakietu MS Office, najnowsze tytuły gier komputerow ych lub „darmowe” pełne wersje aplikacji dla smartfonów. Takie programy najczęściej okazują się nie tylko stratą czasu, ale także realnym zagrożeniem bezpieczeństwa naszych danych.

[![](/blog/Ransomware-metody-infekcji.jpg)](/blog/Ransomware-metody-infekcji.jpg)

> Kto może być ofiarą ataku ransomware?
> -------------------------------------

**Celem ataku może być każdy użytkownik sieci – zarówno osoba indywidualna jak i firma.** Istotną przesłanką do dokonania ataku jest szansa na zapłatę okupu oraz jego wysokość. Firma lub instytucja państwowa ma dużo więcej do stracenia ma niż przeciętny Kowalski: utrata danych może przełożyć się na paraliż firmy.

W marcu 2019 roku firma Norsk Hydro (norweski gigant produkujący między innymi aluminium) przekonała się jak bardzo kosztowny może być atak. Ransomware oprogramowaniem **LockerGoga** doprowadził do paraliżu działalności firmy generując straty na poziomie 35-41 milionów USD. Zyskujące popularność ataki ransomware **RYUK** oraz usługi typu **RaaS** potwierdzają, że hakerzy jako cel ataku wybierają organizacje, dla których atak może być kosztowny i istnieje duża szansa na to, że wysoki okup zostanie zapłacony.

> Ransomware RYUK
> ---------------

RYUK to szczególny przypadek ransomware, który już w ciągu pierwszych miesięcy swojej aktywności przyniósł przestępcom zysk w wysokości 705 BTC (około 10 milionów PLN). Czym różni się od swoich konkurentów? Na celowniku znalazły się tylko duże firmy. Aby zmaksymalizować prawdopodobieństwo udanego ataku oprogramowanie wzbogacono o mechanizmy odpowiedzialne za wyłączanie usług automatycznych kopii zapasowych, antywirusów oraz usuwania istniejących backupów. Kiedy po kilku tygodniach dochodzi do zaszyfrowania danych i wyświetlenia żądania okupu jest już za późno – firma w najlepszym wypadku posiada jedynie niepełne kopie zapasowe.

W uproszczeniu sposób ataku obejmuje następujące kroki:

*   infekcja jednego z komputerów „dowolnym” malware, który da nam możliwość rekonesansu infrastruktury,
*   ocena czy zainfekowany komputer należy do organizacji określanej jako HVT (high value target), a co za tym idzie czy dalsze działania i zaangażowanie są uzasadnione,
*   w przypadku identyfikacji wartościowego celu następuje nacieranie na infrastrukturę organizacji (kontroler domeny) oraz kradzież wartościowych danych,
*   ostatnim krokiem jest infekcja jak największej części infrastruktury ransomware RYUK z żądaniem okupu.

Mając na uwadze rozległość ataku, wcześniejszą kradzież danych wrażliwych oraz działania mające na celu na przykład zniszczenie kopii zapasowych, atak malware RYUK, często jest opłakany w skutkach.

> Jak się zabezpieczyć przed złośliwym oprogramowaniem
> ----------------------------------------------------

By zwiększyć swoje bezpieczeństwo w sieci należy pamiętać o kilku prostych zasadach:

*   **regularnie wykonuj kopie zapasowe** – pozwoli Ci to złagodzić problemy związane z utratą danych,
*   **zachowaj ostrożność podczas korzystania z Internetu** – nie wchodź w podejrzane linki ani nie instaluj oprogramowania z niepewnego źródła,
*   **przed otwarciem załącznika lub kliknięciem w link upewnij się, że znasz jego nadawcę** – znaczna część ataków polega na podszyciu się pod firmę cieszącą się zaufaniem od której wiadomości możemy się spodziewać, np.: telekomunikacyjną lub kurierską,
*   **nie korzystaj z konta administratora, jeżeli nie jest to konieczne,**
*   **nie korzystaj z publicznych sieci WiFi** (zanim to zrobisz koniecznie [przeczytaj artykuł jak bezpiecznie korzystać z WiFi),](https://seqred.pl/bezpieczne_wifi)
*   **regularnie aktualizuj oprogramowanie** – część ataków na cel bierze istniejące luki w oprogramowaniu (np. przeglądarkach),
*   **stosuj unikatowe hasła dla różnych stron** – przejęcie jednego hasła nie będzie niosło za sobą przejęcia wszystkich kont,
*   jeżeli to możliwe, **włącz dwuskładnikowe uwierzytelnianie** – nawet jeżeli przestępcy przejmą Twoje hasła to nadal nie będą mogli zalogować się na Twoje konto,
*   **dbaj o swoją prywatność** – im mniej osoby trzecie mogą się o Tobie dowiedzieć, tym trudniej będzie przygotować dedykowany Ci atak – [przeczytaj artykuł, jak pozostać anonimowym w sieci.](https://seqred.pl/anonimowosc-w-sieci/)

> Zostałem zaatakowany, co teraz? Jak usunąć ransomware? Jak odzyskać dane?
> -------------------------------------------------------------------------

Nie ma systemu, którego nie dałoby się w jakiś sposób zainfekować. Twórcy złośliwego oprogramowania regularnie wymyślają coraz to nowsze techniki pozwalające na przechytrzenie nawet najbardziej ostrożnych i podejrzliwych użytkowników. Jeżeli już zostałeś ofiarą ransomware – nie wszystko stracone!

#### **Nie płać okupu!**

Zalecamy, by nie płacić okupu, gdyż nie ma żadnej gwarancji, że po przekazaniu pieniędzy odzyskamy dostęp do naszych danych. Co więcej – płacąc przestępcom pokazujemy, że taka metoda wyłudzania pieniędzy przynosi efekty.

#### **Kopia zapasowa**

Jeżeli posiadasz kopię zapasową – jej przywrócenie powinno ograniczyć straty związane z atakiem.

[![](/blog/Ransomware-placic-czy-nie-placic-2.jpg)](/blog/Ransomware-placic-czy-nie-placic-2.jpg)

> Darmowa pomoc w odzyskaniu danych dla ofiar ransomware
> ------------------------------------------------------

Nie każdy pamięta o wykonywaniu regularnych backupów dlatego w przypadku ataku konieczne jest znalezienie sposobu na odszyfrowanie danych. Z pomocą przychodzą serwisy specjalizujące się w darmowej pomocy ofiarom ataków ransomware:

*   [NoMoreRansom!](https://www.nomoreransom.org/pl/index.html) – polska strona wsparcia dla ofiar ransomware,
*   [ID Ramsomware](https://id-ransomware.malwarehunterteam.com/) – narzędzie do identyfikacji ransomware oraz zbiór instrukcji w jaki sposób można odzyskać dane,
*   [Kaspersky NoRansom FAQ](https://noransom.kaspersky.com/pl/faq-pl/) – zbiór pytań i odpowiedzi przygotowany przez firmę Kaspersky.

> RaaS: Ransomware-as-a-Service – czyli kup sobie ransomware!
> -----------------------------------------------------------

Popularny ostatnio koncept obejmujący model dystrybucji oprogramowania ransomware, w którym malware oraz atak traktowany jest jako forma usługi. Za stosunkowo niewielką kwotę lub podział zysków z opłaconych haraczy kupujący w Dark webie otrzymuje dokumentację, specjalnie przygotowane oprogramowanie, poradnik jak skutecznie przeprowadzić infekcje oraz pełne wsparcie techniczne na temat konkretnych ransomware. Przykładami mogą być pakiety Philadelphia, RaasBerry, Frozr Locker i Satan. Model taki pozwala zaawansowanym hakerom (tworzącym złośliwe oprogramowanie) zdjąć z siebie ryzyko oraz proces związany z bezpośrednim atakiem, a następnie negocjowaniem czy wymuszaniem haraczu. Osoby nieposiadające umiejętności stworzenia własnego oprogramowania ransomware bądź nie potrafiące przeprowadzić skutecznego ataku dostają potężną broń gotową do użycia.

Masz pytania związane z ransomware?
-----------------------------------

[Napisz do nas](/kontakt)
