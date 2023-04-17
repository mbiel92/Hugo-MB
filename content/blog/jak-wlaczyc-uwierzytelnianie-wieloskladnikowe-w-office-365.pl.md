+++
lang="pl-PL"
title="Jak włączyć uwierzytelnianie wieloskładnikowe w Office 365"
date="2020-05-25"
author="Michał Kwiatkowski"
image="/blog/Uwierzytelnianie_wielopoziomowe.jpg"
tags=['rozwiązania chmurowe']
+++

Pandemia koronawirusa wymusiła na wielu organizacjach przyspieszoną transformację cyfrową i przejście z pracy stacjonarnej na zdalną. Ta nagła zmiana wiązała się z koniecznością szybkiego udostępnienia użytkownikom narzędzi, które pozwalają na zdalny dostęp do zasobów firmy. W ciągu kilku dni nastąpiło przeniesienie funkcjonowania procesów biznesowych wielu organizacji do świata wirtualnego. Ze względu na tempo zmian nie wszyscy pracownicy zostali odpowiednio przygotowani do pracy zdalnej, a systemy teleinformatyczne nie zostały odpowiednio zabezpieczone. Wykorzystują to przestępcy, działając szybko i na masową skalę. Dużą część ich działalności stanowią próby wyłudzenia danych logowania przez próby phishingu, ale dzięki uwierzytelnianiu wieloskładnikowemu można skutecznie zapobiec negatywnym skutkom takiego ataku.

**Z artykułu dowiesz się o:**

*   wzroście liczby ataków phishingowych podczas pandemii Covid-19
*   czym jest MFA – Multi-Factor Authentication (uwierzytelenianie wieloskładnikowe)
*   konfiguracji drugiego składnika uwierzytelniania w Office 365

[Przeczytaj także: jak zapewnić bezpieczeństwo podczas pracy zdalnej](https://seqred.pl/jak-zapewnic-bezpieczenstwo-pracy-zdalnej/)

> Ataki phishingowe podczas pandemii Covid-19
> -------------------------------------------

Podczas pandemii i przymusowego pobytu w domach obserwujemy znaczny wzrost ataków phishingowych, nakierowanych na uzyskanie dostępu do platform społecznościowych oraz chmurowych narzędzi umożliwiających zdalny dostęp do zasobów firmy. Jednym z bardziej popularnych scenariuszy jest podszycie się pod aplikację powiązaną z Office 365. Taki atak wymaga jedynie dobrze spreparowanej strony logowania. Jeśli ofiara wypełni wymagane pola, atakujący może w łatwy sposób uzyskać dostęp do chmury organizacji, a tym samym dostęp do wiadomości, plików, danych klientów czy danych finansowych firmy itd.

**Czy każdy pozna się na fałszywym ekranie logowania?**

[![](/blog/phishing-falszywy-ekran-logowania.jpg)](/blog/phishing-falszywy-ekran-logowania.jpg)

> Uwierzytelnianie wieloskładnikowe (MFA – Multi-Factor Authentication) – ochrona przez nieautoryzowanym dostępem
> ---------------------------------------------------------------------------------------------------------------

Uznanym sposobem zabezpieczenia przed atakami nastawionymi na kradzież hasła jest wykorzystanie uwierzytelnienia wieloskładnikowego (zwanego weryfikacją wieloetapową). Oznacza to dodanie dodatkowych poświadczeń wymaganych od użytkownika, aby przejść proces logowania i uzyskać dostęp do systemu. Przykładowo, aby zalogować się do Office 365 oprócz podania nazwy użytkownika i hasła, użytkownik będzie musiał podać hasło jednorazowe, wysłane do niego za pomocą SMS-a.

### Różnorodne czynniki uwierzytelniania

Aby autoryzację można było uznać za wieloskładnikową, musi ona wymagać poświadczeń z więcej niż jednej grupy:

*   element, który użytkownik pamięta: najczęściej hasło lub odpowiedź na pytanie,
*   element, który użytkownik posiada: w tej grupie mieszczą się urządzenia, które użytkownik nosi przy sobie. Mogą to być karty kodów, klucze usb, karty chipowe, czy telefon,
*   uwierzytelnienia biometryczne: skany siatkówki, odciski palca, analiza głosu czy twarzy (przeczytaj więcej o biometrii),
*   lokalizacja, np. wykorzystywana przez Google do blokady logowania w przypadku prób podejmowanych z miejsc odległych lub nietypowych dla użytkownika,
*   czas, np. wprowadzenie ograniczenia czasowego dostępu do systemów uzależnione od godzin pracy poszczególnych pracowników.

Warto zaznaczyć, że powyższe zabezpieczenia nie uchronią użytkownika przed przypadkowym udostępnieniem swojego hasła podczas ataku phishingowego. Ochrona polega na uniemożliwieniu przestępcy dostępu do zawartości chmury, ponieważ bez kolejnego składnika uwierzytelniania nie będzie mógł pozytywnie przejść procesu logowania.

> Konfiguracja drugiego składnika uwierzytelniania w Office 365
> -------------------------------------------------------------

Office 365 nawet w najbardziej ograniczonej licencji pozwala na włączenie do procesu logowania aplikacji mobilnej jako dodatkowego składnika uwierzytelniania.

**Jak skonfigurować i aktywować taki mechanizm?**

**1.** Zaloguj się na konto z uprawnieniami administracyjnymi i przejdź do aplikacji Centrum Administracyjne.

[![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja_krok-1.jpg)](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja_krok-1.jpg)

**2.** Rozwiń w menu opcję Użytkownicy i wybierz pozycję Aktywni użytkownicy, a gdy zobaczysz listę użytkowników zarejestrowanych w domenie, wybierz przycisk Uwierzytelnianie wieloskładnikowe na górze listy, który przeniesie Cię na odpowiedni ekran konfiguracji.

[![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja_krok-2a.jpg)](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja_krok-2a.jpg)

**3.** otrzymasz listę użytkowników z informacją, jaki status ma ich MFA (uwierzytelnianie wieloskładnikowe). Przed dokonaniem modyfikacji na poziomie poszczególnych użytkowników przejrzyj i dostosuj określone ustawienia dla całej organizacji. W tym celu wybierz Ustawienia usługi.

[![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja-krok-3.jpg)](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja-krok-3.jpg)

Jeśli chcesz pozwolić użytkownikom na korzystanie z aplikacji, które nie mają wbudowanego procesu uwierzytelnienia firmy Microsoft, np. niektóre aplikacje mailowe, wybierz opcję zezwolenia użytkownikom na tworzenie haseł aplikacji.

[![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja-krok-4.jpg)](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja-krok-4.jpg)

W kolejnym kroku możesz wybrać jakim kanałem ma przebiegać dodatkowa weryfikacja:

*   połączenie telefoniczne oraz SMS są najprostszą i najbardziej dostępną metodą, ale generują dodatkowe koszty przy każdej próbie uwierzytelnienia,
*   powiadomienie przez aplikację mobilną jest dla wielu użytkowników najwygodniejsze, ale wymaga zainstalowania aplikacji Microsoft Authenticator,
*   kod weryfikacyjny jest dość popularną opcją, również w aplikacjach innych producentów, np. Amazon, czy OVH, wymaga jednak tokenu sprzętowego lub aplikacji generującej kody. Funkcjonalność tego typu oferuje wspomniany wcześniej Microsoft Authenticator, ale można skorzystać z innych rozwiązań, np. Authy, AndOTP czy Google Authenticator.

Po dokonaniu odpowiednich modyfikacji zapisz zmiany i wróć na ekran z listą użytkowników.

Aby uruchomić mechanizm uwierzytelnienia wieloskładnikowego dla jednego lub większej liczby użytkowników zaznacz ich – wówczas po prawej stronie ekranu pojawi się przycisk Włącz. Po włączeniu tej opcji, przy próbie zalogowania się do jednego z elementów Office 365 przez przeglądarkę użytkownikowi zostanie wyświetlona prośba o podanie dodatkowych informacji, a następnie kreator konfiguracji.

Proces konfiguracji jest prosty i intuicyjny, jednak dobrą praktyką jest przetestowanie go na mniejszej grupie użytkowników. Należy zaznaczyć, że w Microsoft Authenticator wyświetlana jest opcja „logowanie przez aplikację”, której użytkownik nie powinien uruchamiać do momentu ukończenia kreatora konfiguracji MFA, ponieważ wyświetli ona kolejny ekran logowania i kolejny kreator konfiguracji MFA, co spowoduje przerwanie procesu i ewentualne problemy.

[![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja-krok-5.jpg)](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja-krok-5.jpg)

Po uruchomieniu usługi każdy z użytkowników może zarządzać nią w swoim panelu.

Proces uruchmienia wieloskładnikowego uwierzytelnienia jest prosty, a korzystanie z tego zabezpieczenia nie jest dla użytkownika skomplikowane, ani uciążliwe. Warto wprowadzić takie zabezpieczenie, aby uchronić całą organizację przed utratą danych.
