+++
lang="pl-PL"
title="Zarządzanie podatnościami w środowisku automatyki przemysłowej"
date="2020-05-19"
author="Michał Stępień, Józef Sulwiński"
image="/blog/zarzadzanie-podatnosciami-automatyka-przemyslowa-ICS.jpg"
tags=['Czwartki OT']
+++

Systemy i urządzenia automatyki przemysłowej projektowane kilkanaście lub kilkadziesiąt lat temu, miały przede wszystkim zapewniać ciągłość i odpowiednią jakość procesu technologicznego oraz realizację funkcji bezpieczeństwa (rozumianej jako bezpieczeństwo procesu, ludzi i środowiska). Ze względu na otoczenie, w którym funkcjonowały (odseparowanie urządzeń i systemów OT od sieci IT – „air gap”), aspekty cyberbezpieczeństwa rzadko były brane pod uwagę przy ich projektowaniu.

Większość podatności odkrywanych obecnie w środowisku OT, było tam obecna od zawsze,  
a przy odbiorze końcowym wdrożenia nie walidowano go pod kątem bezpieczeństwa. Nawet gdyby urządzenie po zakończeniu produkcji przeszło pomyślnie testy bezpieczeństwa, to producenci oraz użytkownicy systemów ICS zostawiają otwarte drzwi atakującym nie zmieniając domyślnych haseł dostępu m.in. do paneli konfiguracji.


> Hasła do komponentów OT – powszechne źródło podatności
> ------------------------------------------------------

Domyślne hasła są jedną z podatności masowo spotykanych w rozwiązaniach OT. W większości urządzeń zalecana jest zmiana danych logowania, o czym często przypominają instrukcje użytkownika. Jak pokazuje doświadczenie, niestety nie każdy przywiązuje do tego należytą wagę. W ramach jednego z realizowanych w Seqred projektów, mieliśmy możliwość analizy wpływu całej serii urządzeń ICS pozostawionych z domyślnymi hasłami na bezpieczeństwo środowiska. Zarówno producent urządzeń, jak i ich dystrybutor wyraźnie zaznaczali, że urządzeń nie należy podłączać do sieci publicznej oraz należy zmienić hasła. Żadne z zaleceń nie zostało zrealizowane.

Aby uświadomić sobie, jak duże jest prawdopodobieństwo wystąpienia ataku wystarczy skorzystać z np. wyszukiwarki [Shodan](https://seqred.pl/shodan-rekonesans-infrastruktury-it-ot/) oraz jednej z utrzymywanych baz domyślnych haseł dla urządzeń ICS np.  
na stronie [GitHub](https://github.com/scadastrangelove/SCADAPASS/blob/master/scadapass.csv) czy [Critifence](http://critifence.com/default-password-database/)

**Lista domyślnych haseł do urządzeń automatyki**

[![](/blog/domyslne-hasla-urzadzenia-automatyki-przemyslowej-ICS-1.jpg)](/blog/domyslne-hasla-urzadzenia-automatyki-przemyslowej-ICS-1.jpg)

Źródło: [GitHub](https://github.com/scadastrangelove/SCADAPASS/blob/master/scadapass.csv)

Atakujący, zanim wykorzystają siłowe metody odgadywania haseł, takie jak: słownikowa lub bruteforce, sprawdzają listę znanych haseł w powyższych źródłach. Jeśli sposób na odgadnięcie danych logowania jest zbyt czasochłonny, poszukują innych metod na wykonanie operacji bez konieczności logowania. Do tego celu wykorzystują luki bezpieczeństwa w oprogramowaniu umożliwiające np. zdalne wykonanie kodu bez konieczności logowania, o których informacje także pozyskują z Internetu.

> Bazy podatności – źródło informacji o lukach bezpieczeństwa
> -----------------------------------------------------------

W ramach procesu „responsible disclosure”, penetesterzy po znalezieniu podatności dokonują jej zgłoszenia producentowi urządzenia, który ma czas na przygotowanie niezbędnych aktualizacji. Po udostępnieniu przez producenta poprawek następuje publikacja informacji o znalezionej podatności. Listę zgłoszonych luk bezpieczeństwa można znaleźć w biuletynach producentów rozwiązań ICS lub oraz w Internecie np. na stronie [Exploit Database](https://www.exploit-db.com/exploits/40779)

   
**Baza podatności urządzeń uwzględniająca automatykę**

[![](/blog/2-baza-podatnosci_ICS.jpg)](/blog/2-baza-podatnosci_ICS.jpg)

Źródło: [Exploit Database](https://www.exploit-db.com/exploits/40779)

Należy zwrócić uwagę, że udostępnienie poprawki przez producenta rzadko kiedy jest tożsame z jej instalacją w środowisku ICS klienta. Z tego powodu, atakujący wykorzystują informacje o opublikowanych lukach bezpieczeństwa do przygotowania scenariusza ataku na infrastrukturę OT. Zdarza się, że na stronach z informacjami o podatnościach publikowane są gotowe skrypty automatyzujące działania w ramach prowadzonego ataku.

> Podatności typu zero-day używane w zaawansowanych atakach na OT
> ---------------------------------------------------------------

Dla systemów OT użycie znanych podatności stanowi ważny element wektora ataku. Obecnie jednym ze scenariuszy zaawansowanych ataków jest wykorzystanie wiedzy o zidentyfikowanej luce bezpieczeństwa (tzw. zero-day) jeszcze przed publikacją poprawek, czy zaleceń przez producenta urządzenia ICS.

Podczas testów bezpieczeństwa urządzeń OT zidentyfikowaliśmy nieznaną dotychczas podatność implementacji protokołu DLMS/COSEM. W przypadku, gdyby taka luka bezpieczeństwa została odkryta przez atakujących możliwe byłoby użycie jej w celu zatrzymania urządzeń ICS. Informacje o niej upubliczniliśmy dopiero po udostępnieniu poprawki przez producenta. Pokazuje to, że możliwe jest odnalezienie nowych podatności dla urządzeń automatyki.

> Czy producenci dbają o bezpieczeństwo urządzeń?
> -----------------------------------------------

[Analiza bezpieczeństwa przeprowadzona w USA oraz UK](https://moniotrlab.ccis.neu.edu/wp-content/uploads/2019/09/ren-imc19.pdf) obejmująca 35 tys. testów wykazała, że ponad połowa z 81 komponentów IoT posiadała podatności już w momencie zakupu. Luki bezpieczeństwa dotyczyły m.in. nadużywana uprawnień (np. poprzez nagrywanie dźwięku lub obrazu) oraz braku lub błędnej implementacji mechanizmów bezpiecznej transmisji danych. Opierając się na wynikach badań dla urządzeń OT, można postawić tezę, że dla producentów urządzeń cyberbezpieczeństwo nie było kluczowym czynnikiem uwzględnianym przy projektowaniu, produkcji oraz sprzedaży urządzeń.

W ostatnich latach obserwujemy rozbudowę oferty urządzeń OT z zaimplementowanymi funkcjami bezpieczeństwa. Należy mieć jednak na uwadze, że wykorzystywane w środowisku ICS protokoły komunikacyjne są niezabezpieczone, a cykl wymiany urządzeń wynosi zazwyczaj dziesiątki lat. Wprowadzenie przez producentów lepiej zabezpieczonych sterowników spowoduje podniesienie bezpieczeństwa w perspektywie następnych 10-20 lat. Przynajmniej do tego czasu to do użytkownika należy zadbanie o bezpieczeństwo własnej infrastruktury.

> Jak zadbać o zarządzanie podatnościami urządzeń w środowisku ICS
> ----------------------------------------------------------------

W procesie wykrywania podatności urządzeń pomocne jest wykonanie inwentaryzacji sprzętu oraz komponentów oprogramowania (więcej na temat metod przeczytasz w artykule: Inwentaryzacja i kontrola zasobów sprzętowych w środowisku ICS). W celu automatyzacji procesu detekcji znanych podatności w urządzeniach OT, wykorzystuje się narzędzia m.in. Guardian (Nozomi Networks) oraz TenableOT (Tenable). Pozyskane wyniki pozwalają odpowiedzieć na pytania, które urządzenia w sieci ICS mają podatności oraz czy wymagają aktualizacji lub zastosowania dodatkowej ochrony.

### Identyfikacja podatności z wykorzystaniem Guardian firmy Nozomi Networks

Oprogramowanie Guardian zapewnia skuteczną detekcję oraz widoczność w środowisku OT oraz IoT. Oprócz funkcji takich jak: wykrywanie zasobów, wizualizacja sieci, monitorowanie ryzyka, identyfikacja zagrożeń oraz ocena podatności, Guardian oferuje wykrywanie luk bezpieczeństwa w oparciu o aktualne dane pozyskane m.in. z platformy OTThreadFeed. Narzędzie prezentuje informacje o urządzeniach oraz zidentyfikowanych podatnościach, a dzięki nadawaniu ocen (scoringu), wspomaga proces określania priorytetów aktualizacji.

**Podatności urządzeń ICS zidentyfikowane przez Guardian**

[![](/blog/Guardian-podatnosci-urzadzen-ICS-OT.jpg)](/blog/Guardian-podatnosci-urzadzen-ICS-OT.jpg)

### Identyfikacja podatności w Tenable.OT

Kolejnym narzędziem jest produkt firmy Tenable (Indegy), znanej z flagowego produktu jakim jest Tenable.SC do zarządzania podatnościami IT. Tenable.OT to rozwiązanie dedykowane dla środowiska OT, wyspecjalizowane jest w znajdowaniu podatności w urządzeniach ICS. W środowisku testowym, omawiane narzędzie dość szybko znalazło podatność systemu DCS. Zidentyfikowana luka bezpieczeństa pozwala zdalnym użytkownikom ominąć uwierzytelnienie i zmodyfikować pliki na stacji roboczej z uprawnieniami systemowymi.

**Podatności systemu DCS zidentyfikowane w Tenable.OT**

[![](/blog/tenable-OT-podatnosci-systemu-DCS.jpg)](/blog/tenable-OT-podatnosci-systemu-DCS.jpg)

Wykorzystanie rozwiązań takich jak Nozomi czy Tenable.OT pozwala na sprawne znajdowanie podatności w systemach przemysłowych, ale należy pamiętać, że to dopiero początek procesu zarządzania podatnościami.

> ### Aktualizacje urządzeń OT

Znalezienie i wylistowanie podatności stanowi wprowadzenie do zadań związanych z usuwaniem luk, np. poprzez wprowadzenie zmian w konfiguracji lub wdrożenie poprawek producenta. W większości przypadków, urządzenia w środowisku ICS nie mogą być aktualizowane automatycznie. Zmiana konfiguracji urządzeń sterujących, czy wgranie nowej wersji oprogramowania niesie ze sobą ryzyko zakłócenia ciągłości procesu. Nieplanowane przerwy serwisowe wynikające z błędów przy aktualizacji lub nieoczekiwanej konieczności dostosowania programów sterowania są kosztowne lub mogą stwarzać dodatkowe ryzyka dla bezpieczeństwa ludzi, środowiska lub parametrów jakościowych produktu lub usługi.

Departament Bezpieczeństwa Krajowego Stanów Zjednoczonych w 2008 roku wskazywał na wspomniane ryzyka, publikując rekomendacje w zakresie instalacji poprawek.

**Wytyczne Departamentu Bezpieczeństwa Krajowego Stanów Zjednoczonych dotyczące zarządzania aktualizacjami w ICS**

[![](/blog/zarzadzanie-aktualizacjami-ics-department-of-homeland-security.jpg)](/blog/zarzadzanie-aktualizacjami-ics-department-of-homeland-security.jpg)

Źródło: [Department of Homeland Security “Recommended Practice for Patch Management of Control Systems”](https://www.us-cert.gov/sites/default/files/recommended_practices/RP_Patch_Management_S508C.pdf)

Zalecanym przez DHS (Department of Homeland Security) postępowaniem przed podjęciem decyzji o dokonaniu aktualizacji urządzeń automatyki jest przeprowadzenie analizy istotności zidentyfikowanej podatności. W przypadku, gdy luka bezpieczeństwa dotyczy komponentów przemysłowych należy uwzględnić poniższe warunki:

*   jeśli lukę bezpieczeństwa można tymczasowo zabezpieczyć (np. zmieniając regułę na firewall’u lub stosując obejście), to z aktualizacją powinno poczekać się do planowanego przestoju,
*   jeśli nie można zastosować alternatywnych mechanizmów zaradczych oraz ryzyko dla organizacji jest nieakceptowalne, a zachowanie ciągłości procesu nie jest krytyczne, należy wykonać kopię zapasową oraz wgrać poprawki.

Warto zwrócić uwagę, że zidentyfikowanie podatności w komponencie środowiska ICS nie są wystarczającą przesłanką do instalacji poprawek, czy zmiany konfiguracji urządzenia. Nierzadko na możliwość instalacji poprawek w środowisku OT trzeba czekać długie miesiące. Objęcie procesem zarządzania podatnościami systemów automatyki jest bardzo istotne z perspektywy bezpieczeństwa, ale w pierwszej kolejności należy zadbać o właściwą architekturę bezpieczeństwa oraz zapewnić odpowiednią separację i segmentację sieci OT.

Przeczytaj [o segmentacji i separacji sieci w ochronie systemów przemysłowych](https://seqred.pl/segmentacja-sieci-ot/)