+++
lang="pl-PL"
title="Inżynieria społeczna i phishing zagrożeniami dla pracowników OT oraz zewnętrznych partnerów"
date="2020-02-12"
author="Michał Stępień"
image="/blog/Phishing_inzynieria_spoleczna_OT.jpg/"
+++

Grudzień 2014, pracownik elektrowni jądrowej należącej do firmy Korea
Hydro and Nuclear Power Co (KHNP) otrzymuje maila z załącznikiem w
formacie .HWP (procesor słów w języku koreańskim). Rozszerzenie nie
wzbudza podejrzeń, gdyż jest ono powszechnie wykorzystywane w Korei
Południowej. Załącznik o nazwie „program sterowania" po otwarciu
powoduje lawinowy łańcuch zdarzeń prowadzący do wycieku informacji o
danych z elektrowni oraz destrukcję dysków przez malware usuwający
główny rekord rozruchowy (MBR).

## Inżynieria społeczna{ .article-section }

Inżynieria społeczna jest metodą uzyskiwania nieautoryzowanego dostępu
do informacji lub systemów informatycznych zwykle za pomocą środków
nietechnicznych. Wykorzystuje ona cechy ludzkie, takie jak ciekawość,
chęć niesienia pomocy, wiara, strach lub szacunek dla autorytetów.
Atakujący bazując na wspomnianych czynnikach prowokują sytuacje, w
których ofiary (np. pracownicy) działają nieostrożnie lub bezmyślnie.
Przykładem takich działań jest wysyłanie fałszywych wiadomości e-mail
(phishing). Treść wiadomości jest atrakcyjna dla ofiar i zachęca do
otwarcia załączników zawierających złośliwe oprogramowanie (malware) lub
odwiedzenia zainfekowanej strony internetowej. Przykładami takich danych
mogą być pliki spakowane projektów na sterowniki (np. PLC lub robota)
oraz link prowadzący do stron, z których można je pobrać..

## Poniżej prezentujemy 4 scenariusze zagrożeń, które warto zaprezentować i omówić podczas okresowych szkoleń dla pracowników i dostawców zewnętrznych { .article-section }

**Scenariusz 1.**\
Atakujący wykorzystuje ataki phishingowe do uzyskania danych logowania
ofiary lub do rozpowszechniania złośliwego oprogramowania za
pośrednictwem fałszywych wiadomości.

**Scenariusz 2.**\
Wiadomości e-mail zawierające pozornie nieszkodliwe i niegroźne linki
lub załączniki, a w rzeczywistości wspierające instalację złośliwego
oprogramowania np. w postaci trojanów. Konsekwencją może być także
zainfekowanie oprogramowaniem typu [ransomware w celu zaszyfrowania
danych oraz wymuszenia
okupu.](https://seqred.pl/ransomware-co-to-jest-jak-sie-zabezpieczyc-jak-usunac/)

**Scenariusz 3.**\
Ataki kierowane typu „spear phishing" dotykają zwykle grupę osób,
precyzyjnie wybranych przez atakujących. Ofiary mają określone
kompetencje lub dysponują informacjami, infrastrukturą których
pozyskanie wspiera realizację ataku. Przesyłane wiadomości e-mail są
zwykle personalizowane. Do przygotowania treści atakujący wykorzystują
wiedzę pozyskaną z otwartych źródeł (OSINT) publikowanych m.in. na
stronach internetowych firmy lub w mediach społecznościowych.

**Scenariusz 4.**\
Atakujący uzyskują nieautoryzowany dostęp do budynku lub na teren
zakładu dzięki zachowaniu pewności siebie oraz przyjaznego usposobienia
wobec załogi oraz pracowników firm zewnętrznych (wtargnięcie z
identyfikatorem -- Tailgating lub nie -- Piggybacking) lub przez
podszywanie się pod personel np. udając serwisanta.

## Działania pomagające zmniejszyć ryzyko ataku:{ .article-section }

**1.** Przeprowadzanie okresowych szkoleń,
dedykowanych dla zespołów OT w celu podnoszenia świadomości
cyberbezpieczeństwa,

**2.** Organizacyjne środki podnoszące
cyberbezpieczeństwo: przygotowanie oraz egzekwowanie polityk
bezpieczeństwa

-   identyfikacja oraz klasyfikacja wartościowych informacji dla
    przedsiębiorstwa
-   ustanawianie zasad m.in. tworzenia, przechowywania, przywracania
    oraz weryfikacji kopii zapasowych danych,
-   wprowadzenie umowy o poufności i/lub prywatności dla pracowników
    oraz partnerów zewnętrznych i dostawców usług,
-   ustalenie zasad niszczenia informacji drukowanych (np. w
    niszczarkach) oraz elektronicznych (np. bezpieczne usuwanie danych z
    cyfrowych nośników pamięci),
-   zasady korzystania z urządzeń mobilnych (np. wykorzystanie folii
    prywatyzujących oraz zabezpieczanie nośników danych).

**3.** wprowadzenie kanałów informowania o
incydentach lub podejrzanych zachowaniach. Sposób raportowania powinny
być zdefiniowany oraz ustrukturyzowany. Informowanie o zdarzeniach,
które nie naruszały bezpieczeństwa (false-positive) nie może być
obarczone konsekwencjami dla strony zgłaszającej,

**4.** wykorzystanie technicznych mechanizmów
bezpieczeństwa w celu wyegzekwowania stosowania regulacji oraz
automatycznej detekcji naruszenia polityk bezpieczeństwa lub ataków.
Przykładami działań mogą być kontrola dostępu fizycznego oraz
monitorowanie bezpieczeństwa urządzeń i logowanie zdarzeń,

**5.** tworzenie kopii zapasowych oraz
okresowe próby przywracania danych i aplikacji w celu sprawdzenia
gotowości organizacji do odzyskania informacji w przypadku wystąpienia
rzeczywistego incydentu.

W ramach przygotowań do działań wykorzystujących inżynierię społeczną
oraz phishing, atakujący często pozyskują wiedzę o organizacji z
otwartych źródeł (OSINT). Zachęcamy do kontaktu w sprawie możliwości
przeprowadzenia takiej analizy dla Państwa przedsiębiorstwa w celu
identyfikacji krytycznych informacji, wspierających realizację
konkretnych ataków na Państwa organizację.

**Źródła:**\
[Industrial Control System Security](https://www.allianz-fuer-cybersicherheit.de/ACS/DE/_/downloads/BSI-CS/BSI-CS_005.pdf?__blob=publicationFile&v=12)
[Korean Nuclear Plant Faces Data Leak and Destruction](https://www.trendmicro.com/vinfo/us/security/news/cyber-attacks/korean-nuclear-plant-faces-data-leak-and-destruction)
[ICS Defense Use Case (DUC) Dec 30, 2014](https://ics.sans.org/media/ICS-CPPE-case-Study-2-German-Steelworks_Facility.pdf)