+++
lang="pl-PL"
title="Jak ograniczyć skuteczność ataków na lokalne konta administratora w ICS"
date="2020-06-03"
author="Józef Sulwiński / Michał Stępień"
image="/blog/Bezpieczenstwo_hasla_blog.jpg"
tags=['czwartki OT']
+++

Aplikacje funkcjonujące w środowisku ICS do poprawnego działania wymagają zazwyczaj specjalnych dostępów, co często powoduje nadanie zbyt szerokiego zakresu uprawnień, np. lokalnego administratora, czy w skrajnych przypadkach administratora domeny. Dość częstą praktyką jest również współdzielenie przez użytkowników systemów ICS kont w aplikacjach i systemach operacyjnych. W przypadku incydentów bezpieczeństwa trudno jest w takim środowisku przeprowadzić konstruktywną analizę powłamaniową (ustalić kto i kiedy przeprowadził analizowane działania w systemie teleinformatycznym). Taka konfiguracja systemów może ułatwić przestępcy ingerencję w systemy sterowania. Dlatego konta, które posiadają specjalne uprawnienia powinny być objęte szczególnym nadzorem. Jeżeli musimy działać w tak skonfigurowanym środowisku, np. gdy wynika to z zaleceń producenta systemu ICS, to zadbajmy o podstawowe zasady higieny.

**Z artykułu dowiesz się:**

*   jak tworzyć silne hasło administratora
*   jak monitorować próby logowania – już wkrótce
*   czy można blokować i co należy uwzględnić blokując konta użytkowników ICS? – juz wkrótce

![](/blog/Bezpieczenstwo_hasla_blog.jpg)

**3 działania, które pozwalają ograniczyć skuteczność ataków na lokalne konta administratora:**

*   wymuszenie stosowania silnego hasła,
*   ograniczenie liczby prób logowania, po których konto jest blokowane. Ze względu na możliwość przeprowadzenia ataku DoS, użycie możliwe tylko dla systemów, dla których blokada dostępu nie wpłynie na ciągłość działania procesu, a korzyści przeważają nad zagrożeniami,
*   rejestrowanie prób logowania oraz okresowy przegląd dzienników zdarzeń.

> Silne hasło lokalnego administratora
> ------------------------------------

Silne hasło lokalnego administratora stanowi jedno z najważniejszych zabezpieczeń dostępu do systemów ICS. Stacje robocze w środowisku ICS często wykorzystują platformę Microsoft Windows, dlatego pokażemy, w jaki sposób ustawić silne hasło w tym środowisku.

Jeśli korzystasz z oprogramowania Windows, także Windows 7\* (Professional, Ultimate lub Enterprise) to ustawienia lokalnych polityk bezpieczeństwa haseł znajdziesz po uruchomieniu: **secpol.msc.**

_\* Wsparcie dla systemu Windows 7 skończyło się 14 stycznia 2020, jednak jest on wciąż wykorzystywany w wielu instalacjach przemysłowych. Nie zalecamy korzystania z niewspieranych rozwiązań._

**Ustawienia zasad haseł dla konta w Windows**

[![](/blog/Ustawienia-zasad-hasel-dla-konta-w-Windows.jpg)](/blog/Ustawienia-zasad-hasel-dla-konta-w-Windows.jpg)

W celu skonfigurowania polityki haseł po wybraniu w lewym panelu zakładki: Zasady konta (Account policies) przechodzimy następnie do Zasad haseł (Password policy).

**Zalecane jest ustawienie co najmniej:**

*   minimalnej długości hasła (Minimum password length) składającej się z co najmniej 8 znaków. Warto sprawdzić, jaką wartość ma ustawiona liczba znaków – jeśli jest ustawiona na 0, to zasada nie obowiązuje.
*   hasła muszą spełniać wymagania co do złożoności (Password must meet complexity requirements). Włączenie tego ustawienia (enabled) wymusza stosowanie zasad dotyczących tworzenia silnego hasła, m.in. wykorzystania znaków specjalnych oraz wykluczenia możliwości wpisania w polu hasła nazwy użytkownika,
*   wyłączenie (disabled) przechowywania hasła przy użyciu zasad szyfrowania odwracalnego (Store passwords using reversible encryption) zapewnia obsługę aplikacji korzystających z protokołów wymagających hasła użytkownika do uwierzytelnienia. Przechowywanie zaszyfrowanych w sposób odwracalny haseł oznacza, że możliwe będzie ich odszyfrowanie. Doświadczony atakujący, który jest w stanie złamać to szyfrowanie, może następnie zalogować się do przy użyciu przejętego konta.

**Pozostałe pola pozwalają na:**

*   ustawienie wymuszania tworzenia historii haseł (enforce password history), które określa liczbę unikatowych nowych haseł, które muszą być powiązane z kontem użytkownika, aby można było ponownie użyć starego hasła.
*   ustawienie maksymalnego okresu ważności hasła (maximum password age) określa czas (w dniach), w którym hasło może być używane, zanim system zacznie wymagać od użytkownika jego zmiany. Zalecana przez Microsoft wartość wynosi między 30, a 90 dni. W ten sposób atakujący ma ograniczony czas na złamanie hasła użytkownika i uzyskanie dostępu do zasobów,
*   ustawienie zasady minimalnego okresu ważności hasła (minimum password age) określa czas (w dniach), w którym hasło będzie wykorzystane, zanim użytkownik będzie mógł je zmienić.

Wymagania dotyczące polityki haseł mogą wynikać z przyjętych polityk wewnętrznych organizacji oraz dobrych praktyk.

### Jak tworzyć silne hasła

Jeszcze do niedawna tzw. “silne hasło”, czyli hasło, które było trudne do odgadnięcia oraz złamania metodami siłowymi, było jednocześnie bardzo trudne do zapamiętania. Aby utrudnić przestępcom działania, administratorzy systemów wymuszali na użytkownikach odpowiednią konstrukcję hasła (np. co najmniej 8 znaków, jedna duża litera, jeden znak specjalny, jedna cyfra, cyfry nie mogą znajdować się obok siebie). Użytkownicy rzadko kiedy byli w stanie je zapamiętać dlatego na monitorach i biurkach zaczęły pojawiać się żółte karteczki z zapisanym hasłem. Jeśli użytkownik zapamiętał tak skomplikowane hasło to często korzystał z niego także w innych serwisach (np. w sklepach internetowych, prywatnej poczcie). Problem został dostrzeżony już kilka lat temu. W publikacji NIST 800-63B przedstawiono nowe zalecenia wskazujące np. że wymuszanie powyższej konstrukcji haseł oraz ich okresowej zmiany nie jest już uznawane za dobrą praktykę.

Dobrą praktyką jest umożliwienie użytkownikowi wpisania hasła o minimalnej długości 8 znaków (rekomendowane są dłuższe hasła), które będą składały się z kilku niepowiązanych ze sobą pojęciowo słów, np. KawaTramwajRyba. Przykład ten został przez nas zaczerpnięty ze strony [gov.pl,](https://www.gov.pl/web/baza-wiedzy/jak-tworzyc-bezpieczne-hasla) gdzie wskazano również inne dobre przykłady.

Co roku publikowane są rankingi najgorszych, czyli najbardziej popularnych, łatwych do odgadnięcia, haseł. Jeśli korzystasz z haseł znajdujących się [na liście](https://pclab.pl/news82882.html) – zmień je natychmiast. Na pierwszych miejscach znajdują się 123456, 123456789 oraz qwerty.

W kolejnych odcinkach omówimy w jaki sposób i pod jakimi warunkami blokować dostęp do konta w systemach ICS przy nieudanych próbach logowania oraz jak rejestrować takie zdarzenia.