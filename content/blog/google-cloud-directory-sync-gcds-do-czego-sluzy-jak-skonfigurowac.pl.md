+++
lang="pl-PL"
title="Do czego służy i jak skonfigurować Google Cloud Directory Sync (GCDS)?"
date="2020-06-09"
author="Michał Kwiatkowski"
image="/blog/Google_Directory_Sync.jpg"
tags=['rozwiązania chmurowe']
+++

# Do czego służy i jak skonfigurować Google Cloud Directory Sync (GCDS)?


Duża część bezpieczeństwa firmy zależy od tego, czy pracownicy
przestrzegają odpowiednich procedur. Niestety, wielokrotnie zdarza się,
że polityki bezpieczeństwa, pomimo że w założeniu bardzo dobrze
zabezpieczają firmowe zasoby, w praktyce są dla pracowników uciążliwe i
bardziej zachęcają do ich obchodzenia niż przestrzegania. Stąd żółte
karteczki czy zeszyty z hasłami. Można oczywiście próbować zaostrzać
konsekwencje i dokładnie weryfikować, jak pracownicy stosują się do
wymagań i zaleceń, jednak poza przypadkami, gdy jest to niezbędne
praktyka pokazuje, że nie przynosi to spodziewanych efektów.

Nowoczesnym podejściem do bezpieczeństwa jest kompromis pomiędzy
skomplikowaniem zabezpieczeń, a wygodą pracowników. Odchodzi się od
skomplikowanych haseł, czy ich częstych zmian, na rzecz ich długości.
Zmniejsza się też ilość danych uwierzytelnienia, jakie pracownik musi
pamiętać na rzecz np. systemów SSO (Single Sign On -- system
umożliwiający dostęp do wielu systemów po jednokrotnym zalogowaniu).
Ułatwia to również zarządzanie infrastrukturą w organizacji, przez
centralizację systemów zarządzania dostępem i użytkownikami, czy
współdzielenie danych między nimi. Początkowy wysiłek przy wdrożeniu
takich rozwiązań zmniejsza późniejszą ilość trywialnych problemów, jakie
musi rozwiązywać dział IT.

W wielu organizacjach często istnieje połączenie zestawu biurowego
Google -- G Suite, czyli programów biurowych oraz poczty, z lokalnym
zarządzaniem dostępem do zasobów np. na dyskach sieciowych czy stacjach
roboczych. Dla takich organizacji SSO czy federacja tożsamości mogą być
rozwiązaniami zdecydowanie zbyt skomplikowanymi, więc dla swojej chmury
Google wypuściło narzędzie GCDS (Google Cloud Directory Sync).

## Czym jest Google Cloud Directory Sync (GCDS)?

Google Cloud Directory Sync (w skrócie GCDS) to usługa z chmury Google
pozwalająca na odwzorowanie struktury lokalnej usługi katalogowej np.
Microsoft Active Directory, czy OpenLDAP lub dowolnej innej obsługującej
standardowy protokół LDAP. W efekcie otrzymujemy tych samych
użytkowników i grupy w G Suite, jakie były skonfigurowane w usłudze
katalogowej na naszym serwerze. Dzięki temu użytkownicy mogą używać tych
samych danych do logowania do poczty czy arkuszy Google, co do lokalnych
dysków sieciowych czy stacji roboczej.

Synchronizacja poprzez GCDS przebiega tylko w jedną stronę tj. od
lokalnej usługi katalogowej do chmury Google, dane na lokalnym serwerze
nie są nadpisywane, więc narzędzie jest przydatne w infrastrukturze, w
której zarządzanie użytkownikami może odbywać się głównie poprzez
lokalny serwer.

![](/blog/Guardian-Nozomi-Networks-Aktywna-identyfikacja-urzadzen-OT-.jpg)

## Jak wdrożyć GCDS -- krok po kroku

Podstawowy proces instalacji Google Cloud Directory Sync jest dość
prosty i intuicyjny. Na potrzeby demonstracji przyjmijmy, że nasza
domena w Google to „example.com", a w naszym środowisku lokalnym
korzystamy z Active Directory.

**1. Zainstaluj aplikację**

GCDS jest narzędziem, które jest instalowane i uruchamiane na serwerze w
sieci lokalnej. Narzędzie pobieramy bezpośrednio od Google:
https://tools.google.com/dlpage/dirsync\
Po ściągnięciu, instalacji i uruchomieniu aplikacji możemy przejść do
konfiguracji synchronizacji.

**2. Połącz się z G Suite**

Na karcie **Google Domain Configuration** w zakładce **Connection
Settings** należy zdefiniować dane domeny Google, do której będziemy
synchronizować informacje o naszych użytkownikach.

![](/blog/GCDS-Google-Domain-Configuration.jpg)

W Zakładce **Connection Settings** (Ustawienia połączenia) wprowadzamy
nazwę naszej domeny Google (example.com).

Jeśli nasza nazwa domeny lokalnej jest inna niż domeny Google, można
wymusić jej zmianę. Wtedy każdy adres e-mail użytkowników z naszej
domeny lokalnej zostanie zmieniony, by dopasować go do domeny w G Suite.
Przykładowo
uż[\[email protected\]](/cdn-cgi/l/email-protection){.__cf_email__
cfemail="a6dfd2cdc9d1c8cfcde6c2c9cbc3c8c7cac9cdc7cac8c788d6ca"} zostanie
zaimportowany do G Suite jako
uż[\[email protected\]](/cdn-cgi/l/email-protection){.__cf_email__
cfemail="176e637c7860797e7c57726f767a677b723974787a39"}

Następnie klikniamy **Authorize Now**.\
Otworzy się standardowe okno logowania do G Suite, gdzie należy
zalogować się kontem z uprawnieniami administratoracyjnymi aby
autoryzować aplikację.

Jeśli proces się powiedzie, pojawi się komuniakt. **GCDS is now
authorized.**

**3. Zdefiniuj ustawienia LDAP**

Na karcie **LDAP Configuration** w zakładce **Connection Settings**
należy wprowadzić adres lokalnego AD (usługi katalogowej) wspierającego
protokół LDAP oraz wybrać sposób komunikacji i użytkownika, za pomocą
którego GDCS będzie pobierał z naszego AD informacje. Można też określić
obiekt w AD, którego zawartość będzie synchronizował GDCS (Base DN). Dla
całej domeny „domenalokalna.pl" będzie to: „dc=domenalokalna,dc=pl".

Następnie należy kliknąć przycisk **Testuj połączenie.** Program połączy
się z serwerem LDAP i spróbuje zalogować się, aby zweryfikować
wprowadzone ustawienia.

[[![](/blog/GCDS-LDAP-Configuration.jpg)

**4. Zdecyduj, co i jak synchronizować**

Na karcie **General Settings** należy wybrać obiekty, które chcemy
synchronizować. W zależności od tego co wybierzemy, odsłonią się kolejne
karty, które będą dotyczyły ustawień specyficznych dla każdego typu
obiektu. Poza tymi ustawieniami, w każdej z odsłoniętych kart pojawią
się zakładki dotyczące zasad wyszukiwania (Search Rules) oraz wykluczeń
(Exlusion Rules). Dla wszystkich typów obiektów do synchronizacji należy
wprowadzić przynajmniej jedną zasadę wyszukiwania, żeby GDCS mógł pobrać
wymagane informacje. Dla każdego z tych typów podpowiadana jest również
treść zasady, która obejmie wszystkie obiekty w lokalnym AD danego typu.

![](/blog/GCDS-General-Settings.jpg)

**a. Synchronizacja jednostek organizacyjnych**

Jeśli chcemy przenieść do G Suite nie tylko użytkowników, ale także całą
strukturę organizacji to na karcie **Org Units** należy określić w jaki
sposób będzie się ona mapować do jednostek organizacyjnych w domenie
Google.

Należy określić do jakich nazw w G Suite mają być zmapowane jednostki
organizacyjne najwyższego poziomu na lokalnym AD, do którego GCDS będzie
mieć dostęp.\
GCDS mapuje podorganizacje w usłudze katalogowej na jednostki
organizacyjne Google o takiej samej nazwie.

Zaznaczone pole „Do not create or delete Google Organizations..."
sprawia, że jednostki organizacyjne nie będą synchronizowane do G Suite.
Zamiast tego, jeśli mamy już utworzoną inną strukturę w G Suite, to przy
pomocy zasad mapowań z karty „User Accounts" możemy przenosić
użytkowników pomiędzy jednostkami organizacyjnymi.

![](/blog/GCDS-Org-Units.jpg)

![](/blog/GCDS-Org-Units-Add-Mapping.jpg)

**b.Synchronizacja użytkowników**

Na karcie **User Accounts** określa się konkretne atrybuty kont
użytkowników , oraz jak mają być odzwierciedlone w G Suite. Niezbędne
jest podanie pod jaką nazwą atrybutu znajduje się adres e-mail każdego
użytkownika. Przydatne jest też podanie unikalnego atrybutu, kont
użytkowników. Pomaga to uniknąć błędów synchronizacji w przypadku, gdy
inne pola takie jak nazwa użytkownika czy nazwisko ulegają zmianie.

Należy również zdecydować, jak system ma potraktować istniejących w G
Suite użytkowników, których nie znaleziono w naszej usłudze katalogowej.

![](/blog/GCDS-User-Accounts-User-Attributes.jpg)

W zakładce „Additional User Attributes" możemy podać dodatkowe,
opcjonalne atrybuty o jakie zostaną wzbogacone profile użytkowników w G
Suite, w tym również hasło. Co ułatwi użytkownikom logowanie do usług
Google, jednak jeśli naszym lokalnym AD jest Microsoft Active Directory,
to synchronizacja haseł przez GDCS nie jest możliwa i należy użyć
osobnej aplikacji: G Suite Password Sync.

![](/blog/GCDS-User-Accounts-Additional-User-Attributes.jpg)

**c. Dodatkowe informacje dla profili użytkowników**

Do G Suite możemy też synchronizować informacje kontaktowe użytkowników
takie jak np. lokalizacja biura, numer telefonu, czy nazwa departamentu
i przełożonego. W tym celu należy na karcie **User Profiles** określić
informacje o profilu dla użytkowników.

Wystarczy w zakładce **User Profile Attributes** w zaprezentowane pola
wprowadzić odpowiadające im atrybuty z lokalnego AD.

**5.Zweryfikuj synchronizację**

**1.] Ustawianie powiadomień**

GCDS wysyła powiadomienia za każdym razem, gdy dochodzi do
synchronizacji danych między usługą katalogową, a G Suite. Aby otrzymać
takie powiadomienia na stronie **Notifications** należy określić
szczegóły dotyczące serwera pocztowego oraz tego, kto powinien być
powiadamiany pocztą elektroniczną po synchronizacji.

Kliknij **Test Notification**, aby wysłać wiadomość testową na podane
adresy.

![](/blog/GCDS-Notifications.jpg)

**2. Ustawienie parametrów logowania**

Na karcie **Logging** należy określić **nazwę pliku** i **poziom
szczegółowości** logów jakie narzędzie będzie generować.

![](/blog/GCDS-Logging.jpg)

**3. Weryfikacja ustawień synchronizacji**

GCDS pozwala na przeprowadzenie testu wprowadzonych ustawień. Taka
operacja nie powoduje żadnych zmian ani w lokalnej usłudze katalogowej,
ani w G Suite. Generuje natomiast raport informujący, jakie zmiany w G
Suite zostałyby wprowadzone w przypadku uruchomienia rzeczywistej
synchronizacji. Aby uruchomić taką symulację na stronie **Sync** kliknij
przycisk **Simulate sync**, aby przetestować swoje ustawienia.

**Podczas symulacji GCSP wykona następujące czynności:**

-   połączy się z domeną Google i wygeneruje listę użytkowników, grup i
    współdzielonych kontaktów,
-   połączy się z serwerem katalogu LDAP i wygeneruje listę
    użytkowników, grup i współdzielonych kontaktów,
-   wygeneruje listę różnic,
-   zapisze wszystkie zdarzenia w logu.

Jeśli operacja się powiedzie, otrzymamy raport z informacjami o
zmianach.

Gdy masz całkowitą pewność, że konfiguracja jest poprawna, kliknij
przycisk **Sync & apply**, aby rozpocząć synchronizację.

![](/blog/GCDS-Sync.jpg)

GDCS pozwala na dużo bardziej skomplikowaną konfigurację, czy to w
zakresie ilości danych przesyłanych do G Suite czy w zakresie filtrów,
gdy nasze lokalne AD jest niezwykle skomplikowane. Jeśli chcemy uprościć
zarządzanie użytkownikami administratorom, a użytkownikom zmniejszyć
ilość loginów do zapamiętania to w przypadku, gdy nie możemy pozwolić
sobie na złożone rozwiązania jak federacja tożsamości, GDCS jako sposób
synchronizacji danych może z powodzeniem go zastąpić.