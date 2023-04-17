+++
lang="pl-PL"
title="Wiele podatności w Gameloop – zdalne wykonanie kodu, eskalacja uprawnień"
date="2020-12-17"
author="Maciej Miszczyk"
image="/blog/Seqred_CVE.jpg"
tags=['cve']
+++

#### Gameloop to emulator system Android stworzony przez Tencent. Podczas testów, zidentyfikowaliśmy wiele podatności mogących prowadzić do wykonania kodu i eskalacji uprawnień w emulowanym systemie.

*   CVEID: **CVE-2020-29008**
*   Podatny produkt i jego wersja: **Tencent Gameloop (wszystkie wersje)**
*   Typ podatności: **CWE-284: Niewłaściwa kontrola dostępu**

*   CVEID: **CVE-2020-29009**
*   Podatny produkt i jego wersja: **Tencent Gameloop (wszystkie wersje wcześniejsze niż 3.21.736.100)**
*   Typ podatności: **CWE-284: Niewłaściwa kontrola dostępu**


> ### Podsumowanie

Wszystkie wersje emulatora Gameloop wcześniejsze niż 3.21.736.100 pozwalają na zdalne wykonanie kodu w systemie operacyjnym gościa z uprawnieniami roota przez niezabezpieczone połączenie do ADB na porcie 5555. Dodatkowo, wszystkie wersje pozwalają nieuprzywilejowanemu lokalnemu atakującemu na eskalację do roota.

> ### Opis

Wszystkie wersje emulatora Gameloop pozwalają nieuprzywilejowanemu lokalnemu atakującemu (np. zainstalowanym aplikacjom i atakującym, którzy uzyskali nieuprzywilejowany dostęp przez wykorzystanie innej podatności) uzyskać uprawnienia roota poprzez wykorzystanie niezabezpieczonego programu su. Użytkownik nie będzie poinformowany o próbie uzyskania dostępu i nie będzie mógł jej zablokować. Ta podatność znana jest jako CVE-2020-29008.

Dodatkowo, wersje poniżej 3.21.736.100 akceptują połączenia ADB na porcie TCP 5555. Połączenia te pozwalają atakującemu na wykonywanie poleceń z uprawnieniami roota. W przeciwieństwie do większości urządzeń z Androidem posiadającym dostęp przez ADB, połączenie nie wymaga zgody użytkownika i nie może zostać przez niego zablokowane. Ta podatność otrzymała oznaczenie CVE-2020-29009.

> ### Reprodukcja

**1.** CVE-2020-29008:

su -c \[polecenie\_do\_wykonania\]

**2.**CVE-2020-29009:

adb connect \[addres\_ip\_emulatora\]:5555; adb shell

> ### Rozwiązanie

Zaktualizuj Gameloop do najnowszej wersji. Nie instaluj niezaufanych aplikacji w systemie operacyjnym gościa.