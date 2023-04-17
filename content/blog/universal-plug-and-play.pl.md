+++
lang="pl-PL"
title="Universal Hack and Play / Co to jest UPnP i jakie kryje zagrożenia?"
date="2019-03-15"
author="Michał Niwicki"
image="/blog/Universal_Plug_and_Play_UPnP.jpg"
tags=['ABC Bezpieczeństwa']
+++

Universal Hack and Play / Co to jest UPnP i jakie kryje zagrożenia?

## Do czego służy i jak działa UPnP{ .article-section }

Zdecydowana większość prywatnych użytkowników w Internecie nie podłącza swoich urządzeń do globalnej sieci bezpośrednio, tylko za pomocą routera, który umożliwia komputerom z sieci prywatnej dostęp do Internetu z wykorzystaniem jednego adresu IP (adres routera). Proces translacji to NAT (Network Address Translation).

Jeśli zależy nam, aby aplikacja działająca za NAT’em była dostępna z Internetu, musimy na routerze zmapować zewnętrzny port na wewnętrzny adres IP oraz numer portu. Taka operacja wymaga uprawnień administratora. Jeśli jednak administrator włączył usługę UPnP na routerze, aplikacja może wysłać do routera żądanie zmapowania portu bez konieczności logowania się do panelu administracyjnego routera.

**Przykładowy reqest:**

<?xml version=”1.0″?>  
<s:Envelope xmlns:s=”http://schemas.xmlsoap.org/soap/envelope/” s:encodingStyle=”http://schemas.xmlsoap.org/soap/encoding/”>  
<s:Body>  
<u:AddPortMapping xmlns:u=”urn:schemas-upnp-org:service:WANIPConnection:1″>  
<NewRemoteHost></NewRemoteHost>  
<NewExternalPort>18080</NewExternalPort>  
<NewProtocol>TCP</NewProtocol>  
<NewInternalPort>8080</NewInternalPort>  
<NewInternalClient>192.168.1.100</NewInternalClient>  
<NewEnabled>1</NewEnabled>  
<NewPortMappingDescription>Kamera IP</NewPortMappingDescription>  
<NewLeaseDuration>0</NewLeaseDuration>  
</u:AddPortMapping>  
</s:Body>  
</s:Envelope>

## Gdzie kryją się zagrożenia?{ .article-section }

Przede wszystkim, dowolne urządzenie działające w intranecie, na którego konsolę możemy się zalogować z Internetu daje nam dostęp do zasobów znajdujących się za NAT’em. NAT nie chroni przed dostępem do zdalnej konsoli, jeśli można ją udostępnić za pomocą UPnP.

Przyglądając się kopercie SOAP’owej wywołującej serwis routera, zadać możemy sobie pytanie: czy zamiast numeru portu i adresu IP, na którym nasłuchuje nasza aplikacja, możemy podać inne, dowolne wartości tych pól? Niestety możemy. W ten sposób dowolny działający za NAT’em serwis, taki jak na przykład udział sieciowy serwera multimediów, interfejs webowy kamery internetowej, drukarkę, czy nawet panel administracyjny samego routera można udostępnić z dowolnego komputera w intranecie wysyłając jedno żądanie http.

![](/blog/Universal_Plug_and_Play_UPnP.jpg)

To niestety nie wszystko. Okazuje się bowiem, że niektóre oprogramowanie działające na routerach przedkłada konfigurację UPnP nad statyczne mapowania portów. W efekcie, celowo udostępnioną usługę można zastąpić inną usługą, niekoniecznie działającą w sieci intranet.

![](/blog/UPnP_Universal_Plug_and_Play.jpg)

Co więcej, jednen z popularniejszych open source’owych firmware pozwala na takie zmapowanie portów przez usługę UPnP, że requesty kierowane do maszyny działającej w strefie zdemilitaryzowanej, będą kierowane do podstawionego sztucznie hosta.

## Jak żyć z Universal Plug and Play?{ .article-section }

Musimy pamiętać, że **NAT nie stanowi zabezpieczenia sieci.** Pozorne poczucie bezpieczeństwa i przekonanie, że to co jest „za NAT’em” nie jest dostępne z internetu, jest niestety błędne i niebezpieczne. Usługa UPnP, jeśli pozostanie włączona na routerach brzegowych, stanowi zagrożenie dla zasobów intranetu. Co więcej, wszystkie wymienione wyżej ćwiczenia wykonane zostały z włączonym, znajdującym się na routerze firewall’em.

**Najbezpieczniejszym rozwiązaniem jest wyłączenie UPnP.**

Jeśli takie rozwiązanie nie jest możliwe, **przegląd tablicy mapowań UPnP w panelu administracyjnym routera oraz ograniczenie dostępu dla usług w intranecie do konkretnych maszyn zminimalizuje ryzyko ich ataku.**

> Jak dowiedzieć się, jakie urządzenia znajdują się w naszej sieci?  
> Praktyczna strona ataków na UPnP
> ----------------------------------------------------------------------------------------------------

Żeby dowiedzieć się, jakie urządzenia wspierające UPnP znajdują się w naszej sieci wysyłamy po UDP zapytanie M-SEARCH na broadcastowy adres ip 239.255.255.250 i port 1900:

— pytnon start —  
import socket

query = ‘M-SEARCH \* HTTP/1.1\\r\\n’ \\  
‘HOST:239.255.255.250:1900\\r\\n’ \\  
‘ST:upnp:rootdevice\\r\\n’ \\  
‘MX:2\\r\\n’ \\  
‘MAN:”ssdp:discover”\\r\\n’ \\  
‘\\r\\n’

s = socket.socket(socket.AF\_INET, socket.SOCK\_DGRAM, socket.IPPROTO\_UDP)  
s.settimeout(10)  
s.sendto(query, (‘239.255.255.250’, 1900) )

try:  
while True:  
resp, addr = s.recvfrom(65507)  
print addr, resp  
except socket.timeout:  
pass  
— python end —

Wszystkie urządzenia w naszej sieci wspierające UPnP wyślą odpowiedź zawierającą adres URL, pod którym znajduje się specyfikacja usługi (zazwyczaj url do pliku xml). Przykład odpowiedzi poniżej:

(‘192.168.1.123’, 1900) HTTP/1.1 200 OK  
CACHE-CONTROL: max-age=10800  
EXT:  
LOCATION: http://192.168.1.123:80/asdf/xxd.xml  
SERVER: HPUX/1.2 UPnP/1.0 MP HP1500/1.0  
ST: upnp:rootdevice  
USN: uuid:221a7e80-1dd2-11b2-84d4-be4840a50825::upnp:rootdevice  
CONTENT-TYPE: text/xml; charset=”utf-8″  
CONTENT-LENGTH: 613  
CONTENT-LANGUAGE: ja

Aby uprościć nieco metodę wyszukiwania oraz konwersację z urządzeniami UPnP, użyjemy gotowej biblioteki języka python UPnPy.

Wyszukamy urządzenia typu Internet Gateway Devices i utworzymy nowe reguły przekierowania portów. Kod poniżej:

— python start —  
import upnpy

upnp = upnpy.UPnP()  
upnp.discover()

upnp.select\_igd()  
upnp.select\_service(‘urn:schemas-upnp-org:service:WANIPConnection:1’)

upnp.execute(‘AddPortMapping’, 80, ‘TCP’, 8888, ‘192.168.1.100’, ‘WWW’)  
— python end —

## **Na czym polega zagrożenie?**{ .article-section }

Modyfikując umiejętnie argumenty funcji upnp.execute możemy udostępnić do Internetu usługi/urządzenia, które powinny pozostać w sieci lokalnej. Co więcej, wszystko dzieje się bez konieczności podawania hasła administratora routera, na którym dokonywane są zmiany.

Ktoś powie, że komunikacja UPnP ogranicza się do sieci lokalnej – z Internetu nikt nie zmieni konfiguracji mapowania portów. To prawda. Wystarczy jednak, że z naszej lokalnej sieci nieświadomy użytkownik, malware lub znajomy dla żartu wywoła funkcję execute w następujący sposób:

upnp.execute(‘AddPortMapping’, 1900, ‘UDP’, 1900, ‘192.168.1.1’, ‘JOKE’)

i w ten sposób udostępni możliwość enumeracji urządzeń sieci lokalnej z Internetu.


