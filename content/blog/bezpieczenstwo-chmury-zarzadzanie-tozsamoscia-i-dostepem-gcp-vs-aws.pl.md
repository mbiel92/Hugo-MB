+++
lang="pl-PL"
title="Bezpieczeństwo chmury: zarządzanie tożsamością i dostępem GCP vs. AWS"
date="2020-05-10"
author="Michał Kwiatkowski"
image="/blog/seqred-bezpieczenstwo-w-chmurze-zarzadzanie-tozsamoscia.jpg"
tags=['rozwiązania chmurowe']

+++

Cloud computing stanowi podstawę wielu projektów cyfrowej transformacji
biznesu. Firmy widzą coraz większą wartość w możliwości skalowania
środowiska, przesunięcia części odpowiedzialności za niezawodność na
dostawcę, czy łatwego dostępu dla pracowników pracujących zdalnie.
Łatwość dostępu powoduje jednak konieczność skrupulatnego zarządzania
tożsamością: dokładnego określenia kto, w jakiej sytuacji i w jakim
stopniu może korzystać z elementów infrastruktury w chmurze.

**Każdy z wiodących dostawców rozwiązań IaaS: Google w swoim GCP, Amazon
w AWS, czy Microsoft w usłudze Azure, wspomaga ten proces udostępniając
narzędzia IAM -- Identity and Access Management.** Pomimo podobnych
zakresów funkcjonalności, podejście do konstrukcji i sposobu
definiowania polityki uprawnień i bezpieczeństwa, kontrola użytkowników,
czy nawet znaczenie tych samych pojęć różnią się w zależności od
dostawcy narzędzia.

**Z artykułu dowiesz się o:**\
**1.** o sposobach zarządzania tożsamością w
systemach IAM,\
**2.** różnych podejściach do struktury
zarządzania dostępem,\
**3.** różnicach w pojęciach pomiędzy
dostawcami IaaS.

## Zarządzanie tożsamością w systemach IAM{ .article-section }

**Systemy Identity and Access Management (IAM)** służą do definiowania i
zarządzania dostępem. Najważniejszymi elementami tego narzędzia jest
zarządzanie elektroniczną tożsamością użytkowników oraz system uprawnień
do elementów infrastruktury informatycznej. Ich celem jest udzielenie
odpowiednim osobom właściwego dostępu do odpowiednich elementów
infrastruktury, w odpowiednich okolicznościach.

## Identyfikacja użytkowników w chmurze{ .article-section }

Każdy z wiodących dostawców usług chmurowych w odmienny sposób podchodzi
do identyfikacji użytkowników w swojej infrastrukturze.

### **GCP: wykorzystanie produktów z oferty Google**

GCP wykorzystuje do identyfikacji użytkowników inne produkty z oferty
Google. Przykładowo dostęp do infrastruktury możemy uzyskać na podstawie
konta Google lub konta z domeny G Suite. Do zarządzania użytkownikami
można wykorzystać także usługę Google Cloud Identity, która działa w
podobny sposób jak G Suite, nie daje jednak dostępu do programów
biurowych. Dzięki rozdzieleniu usług tożsamości od samej usługi IaaS,
użytkownik przy pomocy tego samego konta może mieć dostęp do elementów
infrastruktury należących do różnych organizacji.

### **Federacyjne zarządzanie tożsamością**

Obaj dostawcy, zarówno Amazon, jak i Google, pozwalają na rozszerzenie
swoich mechanizmów o tzw. federacyjne zarządzanie tożsamością w oparciu
o SAML 2.0.

Ta funkcjonalność, po odpowiednim skonfigurowaniu, pozwala na użycie
zewnętrznej usługi katalogowej, takiej jak: np. Microsoft Active
Directory, czy zewnętrznego dostawcy tożsamości, przykładowo Facebooka.
Do autoryzacji w AWS czy GCP wykorzystywane są wówczas konta
użytkowników z zewnętrznych rozwiązań, dzięki czemu w samych usługach
chmurowych nie są przechowywane dane logowania. Takie rozwiązanie
umożliwia wykorzystanie tych samych danych logowania pomiędzy wszystkimi
skonfigurowanymi usługami niezależnie od tego, czy znajdują się w jednej
organizacji, czy są to usługi IaaS różnych dostawców.

Rozwiązanie to spotyka się często w połączeniu z mechanizmami SSO
(single sign-on) w sytuacji, gdy firma korzysta z wielu dostawców usług
IaaS i chce ułatwić użytkownikom poruszanie się między nimi.

Odpowiednie zarządzanie tożsamością użytkowników chmury stanowi podstawę
zarządzania bezpieczeństwem oraz dostępem do zasobów chmurowych.
Kolejnym istotnym elementem jest **zdefiniowanie uprawnień każdego z
użytkowników,** a w tym zakresie narzędzia IAM także znacząco się
różnią.

## Struktury zarządzania dostępem{ .article-section }

Zarządzanie uprawnieniami ma na celu umożliwienie użytkownikom
wykonywania operacji, które są im potrzebne do wykonania swoich
obowiązków oraz ograniczenie jego możliwości tylko i wyłącznie do tych,
które są mu niezbędne.

### **Prostota rozwiązań AWS**

Amazon konstruując strukturę uprawnień w AWS postawił na prostotę i
granularność. Aby skonfigurować politykę dostępu należy, poza
wyspecyfikowaniem jakich akcji (mapujących się bezpośrednio do metod API
AWSa) polityka dotyczy, wskazać na odpowiedni obiekt.

Każdy zasób (resource) w momencie utworzenia jest oznakowywany unikalnym
identyfikatorem ARN (ang. Amazon Resource Name).

Przykłady:\
arn:aws:cloudwatch:us-west-2:123456789012:alarm:suspiciousActivity\
arn:aws:iam::123456789012:server-certificate/division_abc/subdivision_xyz/ProdServerCert

Konfigurując politykę dostępu odwołujemy się do obiektu używając jego
ARNa. Fakt, że jako zasób uznawane są nawet bardzo szczegółowe obiekty
sprawia, że uprawnienia nadawać można z bardzo dużą dokładnością, nawet
do pojedynczego alarmu w AWS Cloud Watch czy Topica w SNSie.

Bardziej ogólny dostęp możemy specyfikować stosując wildcardy, tj. znaki
wieloznaczne, najczęściej „\*".

Większość ARNów zawiera w sobie ścieżkę. Znakiem gwiazdki możemy
zakończyć ścieżkę na dowolnym poziomie, co pozwala odwołać się do
wszystkich obiektów zawartych w zasobie przed wildcardem. Dla przykładu
nadając usłudze uprawnienia do obiektu arn:aws:iam::123456789012:user/\*
nadamy jej dostęp do wszystkich użytkowników.

Dodatkowo usługa Amazonu pozwala na utworzenie użytkowników nie mających
dostępu do panelu administracyjnego infrastruktury, jedynie dostęp do
API i narzędzi tekstowych.

### **Hierarchizacja uprawnień GCP**

Google zastosował bardziej złożone rozwiązanie opierając je na
hierarchizacji. Głównym obiektem, o który opiera się struktura uprawnień
jest Projekt. Zasoby w Projekcie mają domyślnie skonfigurowany określony
poziom dostępu. Przykładowo App Engine będą automatycznie mogły
korzystać z utworzonych w ramach tego samego Projektu bucketów z danymi.

Dzięki zastosowaniu hierarchii uprawnienia mogą być przyznawanie nie
tylko pojedynczym zasobom czy użytkownikom, ale też bardziej ogólnym,
logicznym kontenerom.

Takimi kontenerami mogą być:

-   Wspomniane wcześniej Projekty, zawierające zasoby związane z jednym
    przedsięwzięciem,
-   Foldery, w których można umieścić Projekty ale też inne Foldery, w
    celu grupowania zasobów
-   Organizacje -- najwyższy obiekt w hierarchii zawierający w sobie
    wszystkie pozostałe.

**W jaki sposób uprawnienia są propagowane w takiej strukturze?**\
Przykładowo nadając użytkownikowi rolę developerską w folderze, ten sam
użytkownik będzie miał analogiczną rolę i wynikające z niej uprawnienia
we wszystkich projektach, które się w tym folderze znajdują i wszystkich
zasobach, z jakich te projekty się składają, co ilustruje poniższy
diagram:

![](/blog/obraz-chmura.png)

###### Źródło diagramu: [Dokumentacja GCP](https://cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy) na licencji [Creative Commons 4.0](https://creativecommons.org/licenses/by/4.0/)
\
O ile struktura uprawnień w AWS może się wydawać bardziej intuicyjna, o
tyle często przy konfigurowaniu, zwłaszcza większych środowisk, spotyka
się polityki i uprawnienia o większym niż zalecane zakresie, by ułatwić
zarządzanie i przyspieszyć tę konfigurację. Często zamiast szczegółowo
określać zasoby, których polityki i uprawnienia dotyczą spotyka się
bardzo ogólną definicję np. do wszystkich zasobów na danego typu
(arn:aws:s3:::\*).

Z kolei w przypadku GCP zdarzają się sytuacje, gdzie tej szczegółowości
przy definicji uprawnień brakuje i trzeba obejść takie przypadki
uprawnieniami bardziej ogólnymi, odnoszącymi się do projektów.

## Różne funkcje pod identycznymi nazwami{ .article-section }

Poza odmiennym podejściem do zarządzania dostępem, w zrozumieniu różnic
pomiędzy GCP i AWS staje na przeszkodzie także brak standardu
nazewniczego. Tak samo nazwane funkcje i obiekty w obu usługach działają
inaczej i mają inne zastosowanie.

Najwięcej rozbieżności jest wokół określeń Polityki i Roli.

### **Pojęcie Polityki w GCP i AWS**

**W przypadku AWS polityką jest zbiór pojedynczych uprawnień.**
Stosujemy go, aby zgrupować uprawnienia dające określony dostęp do danej
funkcjonalności. Przykładowo jedna z dostarczanych i zarządzanych przez
Amazona polityk „AmazonEC2ReadOnlyAccess" grupuje uprawnienia do odczytu
statusu i konfiguracji usług:

-   EC2
-   EC2 Auto Scaling

oraz do odczytu konfiguracji usług powiązanych, np. monitoringu EC2

Tak zdefiniowane Polityki dołączamy do Roli, grupy użytkowników, czy
bezpośrednio do użytkownika lub zasobu, w celu określenia ich uprawnień.
Najbliższym odpowiednikiem takiego obiektu w GCP jest Rola.

**Mianem Polityki w chmurze Google określa się definicje dostępu do
danego zasobu** (w tym Projektu, czy Folderu). W Polityce zawarte są
zasady, jaka Rola przypada określonym użytkownikom. Po dołączeniu
Polityki do Projektu, w momencie próby uzyskania dostępu do Cloud
Storage w tym Projekcie, zostanie sprawdzone, czy Rola do jakiej
przypisany jest próbujący uzyskać dostęp użytkownik posiada wymagane
uprawnienie. Polityka pozwala również określić dodatkowe warunki, w
jakich użytkownik posiada (lub nie posiada danej roli), np. konkretne
godziny, w których może wykonywać operacje czy datę, po której dostęp
wygasa.

### **Pojęcie Roli w GCP i AWS**

Jak przez GCP rozumiana jest w takim razie wspomniana wcześniej Rola?
Rola jest obiektem analogicznym do Polityki w AWS, czyli zbiórem
pojedynczych uprawnień dającym dostęp do konkretnej funkcjonalności.

Rola w AWS jest odmiennym rozwiązaniem -- można w uproszczeniu
powiedzieć, że jest użytkownikiem bez tożsamości. Nie jest ona
przypisana do konkretnej osoby, a dostęp do niej konfiguruje się jej
podobnie jak dla użytkownika. Inni użytkownicy lub zasoby uzyskują do
niej czasowy dostęp, aby wykonywać operacje z wykorzystaniem jej
uprawnień. Używa się jej głównie przy korzystaniu z federacji
tożsamości, ale też w przypadku, gdy aplikacje muszą pobierać informacje
lub wprowadzać zmiany w infrastrukturze AWS.

Tego typu różnic można znaleźć więcej. W analizie obu rozwiązań pomocna
może być tabela z dokumentacji GCP, która zestawia ze sobą identycznie
nazwane funkcjonalności:


| Concept | AWS |Google Cloud |
|---------|-----|-------------|
| Programmatic identity | [IAM role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html) and instance profile | [Cloud IAM service account](https://cloud.google.com/iam/docs/service-accounts#what_are_service_accounts) |
| User identity | Managed in IAM. Identity federated to external identitymanagement system | Managed outside Cloud IAM. Identity federated to external identity management system |
| Policy | A document that explicitly lists permissions | A list of bindings. A binding binds a list of members to a role |
| Policy attachment | Policy attached to an IAM user or group or a resource | Policy attached to resource |
| Policy evaluation | Deny by default | Deny by default |
| Permission collection | Policy | Role |
| Predefined set of permissions | Managed policies | Predefined roles |
| Auditing IAM calls | AWS CloudTrail | Audit logging |
| Versioning | Yes | No |

\
Źródło: [Dokumentacja GCP](https://cloud.google.com/docs/compare/aws/management) na licencjiCreative Commons 4.0

### Podsumwanie

Przy rosnącej z roku na rok popularności usług chmurowych, rośnie
również liczba organizacji korzystających z usług więcej niż jednego ich
dostawcy. W multicloudowych środowiskach funkcjonalności typu federacja
tożsamości oraz dogłębna znajomość cech szczególnych dla rozwiązań
każdego z dostawców jest niezwykle przydatna.

Systemy IAM w GCP i AWS służą temu samemu celowi i w obydwu usługach
pełnią zbliżoną rolę, pomimo że zaprojektowane zostały w zupełnie
odmienny sposób. Pomimo wielu różnic, które dzieliły oba narzędzia w
przeszłości to wraz z ich rozwojem coraz większa liczba funkcjonalności
jest między nimi wspólna. Obecnie oba rozwiązania pozwalają na
zrealizowanie podobnej polityki bezpieczeństwa, choć innymi metodami. Z
tego powodu wybór jednego lub drugiego dostawcy coraz częściej
podyktowany jest innymi aspektami dostarczanych usług.

**Źródła:**

-   [dokumentacja GCP dla techników biegłych w tematach AWS,
    AZURE](https://cloud.google.com/docs/compare)
-   [dokumentacja
    AWS](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
-   [dokumentacja GCP](https://cloud.google.com/iam/docs)