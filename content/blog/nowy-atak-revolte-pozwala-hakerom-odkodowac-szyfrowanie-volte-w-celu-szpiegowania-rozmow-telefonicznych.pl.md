+++
lang="pl-PL"
title="Nowy atak ReVoLTE pozwala odkodować szyfrowanie VoLTE w celu szpiegowania rozmów telefonicznych"
date="2020-08-24"
author="Seqred"
image="/blog/atak-ReVoLTE.jpg"
+++

Naukowcy z Ruhr University Bochum i New York University Abu Dhabi zaprezentowali nowy atak o nazwie ReVoLTE, który pozwala na przeprowadzanie zdalnych ataków poprzez złamanie szyfrowania używanego w połączeniach głosowych technologii Voice over LTE (VoLTE) i odtworzenie treści rozmów.

Atak ReVoLTE jest możliwy, ponieważ większość operatorów telefonii komórkowej często używa tego samego strumienia kluczy szyfrujących dla dwóch następujących po sobie połączeń głosowych VoLTE, które w efekcie są transmitowane poprzez to samo połączenie radiowe między telefonem a stacją bazową 4G LTE.

> Jak działa podsłuchiwanie rozmów z wykorzystaniem metody ReVoLTE?
> -----------------------------------------------------------------

W celu przeprowadzenia ataku napastnik musi być podłączony do tej samej stacji bazowej co ofiara i użyć sniffer, aby monitorować i nagrać wykonywane przez ofiarę połączenie, którego dotyczy atak i które ma zostać później odszyfrowane. Ofiara ataku rozmawia z inną osobą nieświadoma zagrożenia, po czym kończy rozmowę.

W kolejnym kroku atakujący dzwoni do ofiary w ciągu 10 sekund od zakończenia połączenia, dzięki czemu stacja bazowa nawiązuje z telefonem ofiary nowe połączenie VoLTE przy użyciu tego samego połączenia radiowego, z którego korzystano poprzednio. Standardowa konfiguracja stacji bazowej powoduje, że nowe połączenie raz jeszcze wykorzystuje ten sam strumień szyfrujący, jak przy poprzednim połączeniu.

Teraz atakujący muszą jak najdłużej utrzymać połączenie. Strumień danych nowego połączenia jest ponownie nagrywany w postaci pliku tekstowego, a nagranie takie pozwoli atakującemu obliczyć wstecznie strumień klucza szyfrującego, jaki był używany w pierwszym połączeniu.

Zdaniem badaczy, XOR strumienia kluczy szyfrujących z ramek połączenia głosowego obu rozmów pozwala na odszyfrowanie treści pierwszej rozmowy. Porównanie danych z obu połączeń wykorzystujących ten sam strumień szyfrujący pozwala na odseparowanie i odszyfrowanie tego strumienia. Pozostaje jeszcze kwestia długości strumienia szyfrującego i tu ważne są umiejętności socjotechniczne atakującego, który musi przeprowadzić z ofiarą rozmowę, która będzie trwała przynajmniej tak długo, jak rozmowa ją poprzedzająca. Dzięki temu atakujący otrzymuje strumień danych szyfrujących, który jest tak samo długi, jak w przypadku pierwszej rozmowy i może zdekodować całość pierwszego połączenia.

> Wyniki testów z wykorzystaniem metody ReVoLTE
> ---------------------------------------------

W ramach testu użyto analizatora downlink Airscope stworzonego przez Software Radio System oraz trzech telefonów z systemem Android. Nagrano zaszyfrowany ruch pomiędzy stacją bazową telefonii komórkowej a telefonem ofiary, dzięki czemu zespół uzyskał dane atakowanych połączeń. Porównanie dwóch nagranych rozmów pozwoliło na określenie klucza szyfrującego, aby odszyfrować pierwszą z rozmów. Według ekspertów, przeprowadzenie takiego ataku oraz odszyfrowanie transmisji na linii stacja bazowa – abonent może kosztować nie więcej niż 7.000 dolarów. Na pierwszy rzut oka sporo, ale pytanie jaką wartość może mieć podsłuchana rozmowa?

[Więcej szczegółów oraz nagranie przedstawiające atak ReVoLTE](https://thehackernews.com/2020/08/a-team-of-academic-researcherswho.html)
