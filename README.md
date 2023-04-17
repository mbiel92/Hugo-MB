# Projekt finalnej strony www

1. Menu
2. Komponenty

## ToDo
- [ ] wprowadzenie treści do wszystkich stron z usługami
- [ ] dodanie animacji
- [ ] modyfikacja strony tytułowej wg scenariusza Eugeniusza
- [ ] dodanie obsług landing pages dla GB, DE, CH
- [ ] dodanie artykułów z blogu
- [ ] dodanie newsów
- [ ] dodanie oprawnych description dla wszystkich plików
- [ ] automatyzacja publikacji (Cloudflare + S3)
## Menu

Poniżej znajduje się struktura menu.

English:
    - About
        - Seqred
        - Press Releases
        
    - Services
        - Critical Infrastructure protection
        - Security Audit ICS
        - Smart Building Cybersecurity
        - Cybersecurity Bill of Materials
        - Penetration tests
        - Security code review
        - Secure Product Development
        - Red Team
        - Cloud Services Security
        - Network segmentation
        - Mobile device security
        - Threat Intelligence
        - Open Source Intelligence / OSINT
        - NIS Directive Audit
        - AMI system security
        - AWS Level 1 MSSP

    - Products
        - SMX Secure Media Exchange
        - Secure Remote Access

    - Events

    - Blog

    - Contact
    

Polskie:
    - O nas
        - Seqred
        - Informacje prasowe

    - Usługi
        - Infrastruktura Krytyczna
        - Audyt OT
        - Cyberbezpieczeństwo Smart Building
        Cybersecurity Bill of Materials
        - Testy penetracyjne
        - Audyt bezpieczeństwa kodu
        - Secure Product Development
        - Red Team
        - Bezpieczeństwo Usług Chmurowych
        - Segmentacja sieci
        - Urządzenia mobilne
        - Threat Intelligence
        - Open Source Intelligence / OSINT
        - Audyt KSC
        - Zabezpieczenia systemów AMI

    - Produkty
        - SMX Secure Media Exchange
        - Secure Remote Access

    - Szkolenia
        - Konferencje i wykłady
        - Bezpłatne konsultacje dla startupów
        - Cyberbezpieczeństwo systemów przemysłowych
  
    - Kariera
  
    - Wiedza
        - Blog
        - Czwartki OT
        - Bezpieczne zakupy OT
        - Prezentacje z wykładów
        - Infografiki
        - Poradniki
  
    - Kontakt

## Nagłówki

Nagłówki sekcji (te napisy w ramkach) są tworzone z wykorzystaniem znaczników ```##``` w markdown.

Przykład:

```
## Challenges{ class="section-header my-4" }
```


## Komponenty

### bt-card

Karta ( na podstawie komponentu card z biblioteki bootstrap ) w której obrazek może być położony z lewej strony lub z prawej strony lub u góry lub na dole.

Parametry:
    - class
    - body-class
    - image
    - title
    - image-position
    - image-class

Przykład:

```
{{< bt-card class="border-0 mb-3" image="http://place-hold.it/400x200" body-class="ps-0" image-position="right" image-class="rounded-end my-auto d-block img-fluid-full" >}}
##### Cybersecurity{ class="card-title" }
Cybersecurity audit may include penetration tests of components such as: SCADA system, operator and engineering stations, devices providing remote access, control devices: PLC, IED, RTU using network protocols, among others IEC60870-5: 104, IEC 61850, DNP3 and Modbus TCP / IP.
{{< /bt-card >}}
```

### button

Tworzy odnośnik w postaci przycisku.

Parametry:
- class - nazwa klas dodawanych do przycisku
- label - tekst wyświetlany na przycisku
- href - odnośnik do strony otwieranej po naciśnięciu przycisku

Przykład:

```
{{< button class="btn-primary text-white" label="Contact Us" href="/services/" >}}
```

### card

Tworzy kartę z obrazkiem u góry w oparciu o style z bibiloteki bootstrap.

Parametry:
- image - URL do obrazka
- title - teksty tytułowy
    
Przykład:

```
{{< card image="/img/rysunek.png" title="Karta informacyjna">}}test wewnętrzny{{< /card >}}
```

### carousel

Tworzy komponent carousel w oparciu o style bootstrap. Parametry są przechowywane we frontmatter w tagu carouselitems

Parametry:
- id - identyfikator komponentu carousel (powinien być unikalny na stronie)

Przykład frontmatter:

```
+++
[[carouselitems]]
label="Critical infrastructure protection"
src="/img/services/header-critical-infrastructure-cybersecurity.jpg"
shorttext="comprehensive analysis of critical infrastructure components in terms<br>of possible threats"
fulltext="assessment of the security level of components and systems included in the infrastructure, aimed at finding critical vulnerabilities and recommending solutions to maintain business continuity"
button="More"
link="/services/critical-infrastructure-protection/"
[[carouselitems]]
label="Smart Building Cybersecurity"
src="/img/services/header-smart-building.jpg"
shorttext="identification and reduction of cyber risks for Smart Buildings"
fulltext="a comprehensive service that allows to assess the state of security, identify risk areas and present recommendations and for Smart Building systems and components"
button="More"
link="/services/smart-building/"
+++
```

Przykład wywołania:

```
{{< container type="fluid" class="px-0">}}
    {{% carousel id="service-gallery" %}}
{{< /container >}}
```

### column

Tworzy kolumnę w oparciu o style bootstrap. Umożliwia przypisanie klas stylów do elementu kolumny (class) oraz wewnątrz kolumny (innerclass)

Przykład:

{{< column class="col-md-6" innerclass="text-center" >}}Kolumna{{< /column >}}

### container

Tworzy kontener bootstrap. Umożliwia utworzenie również kontenera typu fluid (po wykorzystaniu parametru type="fluid").

Parametry:
- type - fluid. Tworzy kontener typu fluid
- class - umożliwia dodanie klas css (np. po to aby określić liczbę kolumn)

Przykład:

```
{{< container type="fluid" class="bg-sq-3" >}}{{< /container >}}
```

### css

Komponent umożliwia dodanie stylu css do generowanego pliku

Przykład:

```
{{< css >}} .text-red { color: red } {{< /css >}}
```

### element

Tworzy elementy html typu <div>

Parametry:
- class - umożliwia ustalenie klasy stylów tworzonego elementu

Przykład:

```
{{< element class="" >}}
Tekst
{{< /element >}}
```

### horizontal-card

Tworzy kartę (komponent card z biblioteki bootastrap), w której obrazek jest umieszczony po lewej stronie tekstu.

Parametry:
- image - URL do obrazka
- title - tekst tytułowy karty

Przykład:

```
{{< horizontal-card image="/img/icons/icon_red_team.png" title="" >}}
__Red Teaming:__ actions that allow testing of teams, processes and technologies readiness to protect critical infrastructure control systems, by simulating real-world attacks trying to breach the defenses.
{{< /horizontal-card >}}
```

### info

Na postawie tekstu zawartego pomiędzy tagami ```{{< info >}}``` wyświetla karty informacyjne (z użyciem komponentu card z biblioteki bootstrap). Kolejne karty są rozdzielane w pliku md za pomocą znacznika ```<--->```

Parametry:
- class - umożliwia dodanie klas css (np. po to aby określić liczbę kolumn)

Przykład:

```
{{< info class="row-cols-md-3 row-cols-sm-1 py-4" >}}
# __4tn USD__

estimated losses on four-day
blackout in the USA in 2003
<--->
# __7__{ .text-primary }

110kV transmission lines were disconnected as a result of the cyber attack in Ukraine in 2016
<--->
# __61%__{ .text-primary }

companies experienced network attacks only in 2018
{{< /info >}}
```

### masonry

Tworzy zestaw kart w układzie cegieł.

Przykład:
```
{{< container class="py-4" >}}
{{< masonry class="row-cols-1 row-cols-md-2 g-4" >}}
{{< column class="col-md-6" >}}
{{< horizontal-card image="/img/icons/icon_red_team.png" title="" >}}
__Red Teaming:__ actions that allow testing of teams, processes and technologies readiness to protect critical infrastructure control systems, by simulating real-world attacks trying to breach the defenses.
{{< /horizontal-card >}}
{{< /column >}}
{{< column class="col-md-6" >}}
{{< horizontal-card image="/img/icons/icon_threat_intelligence.png" title="" >}}
__Threat Intelligence:__ proactive reduction of cyber threats in the organization by providing, in advance, information about upcoming threats.
{{< /horizontal-card >}}
{{< /column >}}
{{< column class="col-md-6" >}}
{{< horizontal-card image="/img/icons/icon_audit.png" title="" >}}
__Cybersecurity Audit:__ security assessment of critical infrastructure components, key organizational layer processes to identify threats, and implement corrective actions. A special case of such an audit is the examination of compliance with the polish implementation of NIS Directive (Ustawa o Krajowym Systemie Cyberbezpieczeństwa).

Cybersecurity audit may include __penetration tests__ of components such as: SCADA system, operator and engineering stations, devices providing remote access, control devices: PLC, IED, RTU using network protocols, among others IEC60870-5: 104, IEC 61850, DNP3 and Modbus TCP / IP.
{{< /horizontal-card >}}
{{< /column >}}
{{< column class="col-md-6" >}}
{{< horizontal-card image="/img/icons/icon_cbom.png" title="" >}}
__CBOM:__ analysis of third-party software components along with their versions and existing vulnerabilities based on the source code, firmware or reverse engineering of the device itself. Security assessment and audit of non-public, software components implemented by the device manufacturer.
{{< /horizontal-card >}}
{{< /column >}}
{{< column class="col-md-6" >}}
{{< horizontal-card image="/img/icons/icon_penetration_tests.png" title="" >}}
__Segmentation and separation of OT networks__ network monitoring to identify key devices and isolating selected system components to ensure the required level of security.
{{< /horizontal-card >}}
{{< /column >}}
{{< /masonry >}}
{{< /container >}}
```

### mosaic

Tworzy mozaikę z kart (wg stylów z bootstrap). Karty mają rysunek po lewej stronie, a tekst po prawej. Kolejne karty są rozdzielane za pomocą znacznika ```<--->```

Parametry:
- class - przekazuje klasy stylów

Przykład:

```
{{< mosaic class="pb-4" >}}

![image](/img/icons/icon_profit.png)
an assessment of potential threats related to key critical infrastructure components
<--->
![image](/img/icons/icon_lock.png)
practical preparation of organizations and security teams (SOC) if a cyber attack occurs
<--->
![image](/img/icons/icon_computer.png)
identification and assessment of vulnerabilities in the device firmware

{{< /mosaic >}}
```

### related

Wyświetla powiązane artykuły z bieżącym artykułem (na podstawie tagów określonych we frontmatter bieżącego artykułu).

Przykład:
```
{{< related >}}
```
    
### row

Tworzy wiersz. Wiersz jest potrzebny do podziały wiersza na kolumny (innymi słowy trzeba zastosować ten element zanim utworzysz kolumnę).

Przykład:
```
{{< row class="row-cols-4" >}}
{{< column >}}
tekst kolmumny
{{< /column >}}
{{< /row >}}
```

### testimonial

Tworzy kartę w oparciu o style z bibiloteki bootstrap na potrzeby wyświetlania rekomendacji.

Przykład:

```
{{< testimonial title="CIO of one of the major Polish banks" >}}
Responsible, trustworthy, dependable, dedicated, these words would precisely describe Jozef’s and his way of working with clients. I have the pleasure of working with Jozef and as a consultant he can set the standards that people should follow. I wish him the very best and I can give him my highest marks as his satisfied client
{{</ testimonial >}}
```

## Status
    
| # | Done        |Url | Filename |
|---|-------------|----|----------|
|   2| <ul><li>[x]</li></ul> | https://seqred.pl/en/ | index.en.md 
|  50| <ul><li>[ ]</li></ul> | https://seqred.pl/en/red-teaming-2/ | services/red-teaming-2.en.md
|  94| <ul><li>[X]</li></ul> | https://seqred.pl/en/critical_infrastructure/ | services/critical_infrastructure.en.md
|  98| <ul><li>[X]</li></ul> | https://seqred.pl/threat-intelligence-en/ | services/threat-intelligence.en.md
|  92| <ul><li>[X]</li></ul> | https://seqred.pl/en/cbom-en/ | services/cbom-en.en.md
|  93| <ul><li>[X]</li></ul> | https://seqred.pl/en/cloud-services-security/ | services/cloud-services-security.en.md
| 102| <ul><li>[X]</li></ul> | https://seqred.pl/en/penetration-tests/ | services/penetration-tests.en.md
| 104| <ul><li>[X]</li></ul> | https://seqred.pl/en/secure-product-development-2/ | services/secure-product-development-2.en.md
| 105| <ul><li>[X]</li></ul> | https://seqred.pl/en/red-teaming/ | services/red-teaming.en.md
| 106| <ul><li>[X]</li></ul> | https://seqred.pl/en/network-segmentation/ | services/network-segmentation.en.md
| 107| <ul><li>[X]</li></ul> | https://seqred.pl/en/mobile-device-security/ | services/mobile-device-security.en.md
| ???| <ul><li>[X]</li></ul> | https://seqred.pl/en/security-audit-ics/ | services/ot-audit.en.md  
| ???| <ul><li>[X]</li></ul> | https://seqred.pl/en/smart-building-cybersecurity/ | services/smart-building.en.md     
| ???| <ul><li>[X]</li></ul> | https://seqred.pl/en/security-code-review/ | services/code-review.en.md        
| ???| <ul><li>[ ]</li></ul> | https://seqred.pl/en/open-source-intelligence/ | services/open-source-intelligence.en.md
| ???| <ul><li>[ ]</li></ul> | https://seqred.pl/en/nis-directive-audit/ | services/nis-directive-audit.en.md  
| ???| <ul><li>[ ]</li></ul> | https://seqred.pl/en/ami-system-security/ | services/ami-system-security.en.md   
| ???| <ul><li>[ ]</li></ul> | https://seqred.pl/en/aws-level-1-mssp-eng/ | services/aws-level-1-mssp-eng.en.md     
|   1| <ul><li>[ ]</li></ul> | https://seqred.pl/ | index.pl.md 
|   3| <ul><li>[ ]</li></ul> | https://seqred.pl/blog/ | blog/blog.pl.md
|   4| <ul><li>[ ]</li></ul> | https://seqred.pl/en/blog-en/ | blog/blog.en.md
|   5| <ul><li>[ ]</li></ul> | https://seqred.pl/en/about/ | about/about.en.md
|   6| <ul><li>[ ]</li></ul> | https://seqred.pl/o-nas/ | about/about.pl.md
|   7| <ul><li>[X]</li></ul> | https://seqred.pl/en/universal-plug-and-play-en/ | blog/universal-plug-and-play.en.md
|   8| <ul><li>[X]</li></ul> | https://seqred.pl/universal-plug-and-play/ | blog/universal-plug-and-play.pl.md
|   9| <ul><li>[ ]</li></ul> | https://seqred.pl/en/jozef-sulwinski-2/ | about/jozef-sulwinski.en.md
|  10| <ul><li>[ ]</li></ul> | https://seqred.pl/jozef-sulwinski/ | about/jozef-sulwinski.pl.md
|  11| <ul><li>[ ]</li></ul> | https://seqred.pl/krzysztof-swaczynski/ | about/krzysztof-swaczynski.pl.md
|  12| <ul><li>[ ]</li></ul> | https://seqred.pl/en/krzysztof-swaczynski-2/ | about/krzysztof-swaczynski.en.md
|  13| <ul><li>[ ]</li></ul> | https://seqred.pl/en/contact/ | contact/contact.en.md
|  14| <ul><li>[ ]</li></ul> | https://seqred.pl/kontakt/ | contact/contact.pl.md
|  15| <ul><li>[ ]</li></ul> | https://seqred.pl/lukasz-drazek/ | about/lukasz-drazek.pl.md
|  16| <ul><li>[ ]</li></ul> | https://seqred.pl/dariusz-fabiszewski/ | about/dariusz-fabiszewski.pl.md
|  17| <ul><li>[ ]</li></ul> | https://seqred.pl/en/dariusz-fabiszewski-2/ | about/dariusz-fabiszewski.en.md
|  18| <ul><li>[ ]</li></ul> | https://seqred.pl/dariusz-fabiszewski-doradca-seqred/ | press/dariusz-fabiszewski-doradca-seqred.pl.md
|  19| <ul><li>[X]</li></ul> | https://seqred.pl/en/dariusz-fabiszewski-executive-board-advisor-in-seqred/ | press/dariusz-fabiszewski-executive-board-advisor-in-seqred.en.md
|  20| <ul><li>[ ]</li></ul> | https://seqred.pl/dariusz-fabiszewski-strategicznym-doradca-zarzadu-seqred/ | press/dariusz-fabiszewski-strategicznym-doradca-zarzadu-seqred.pl.md
|  21| <ul><li>[X]</li></ul> | https://seqred.pl/en/dariusz-fabiszewski-executive-board-advisor/ | press/dariusz-fabiszewski-executive-board-advisor.en.md
|  22| <ul><li>[X]</li></ul> | https://seqred.pl/en/software-defined-peremeter/ | blog/software-defined-peremeter.en.md
|  23| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-cloud-and-the-dark-web/ | blog/the-cloud-and-the-dark-web.en.md
|  24| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-1-introduction/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-1-introduction.en.md
|  25| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-10-validate-indirections/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-10-validate-indirections.en.md
|  26| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-11-assign-designated-register-blocks-by-function-read-write-validate/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-11-assign-designated-register-blocks-by-function-read-write-validate.en.md
|  27| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-12-instrument-for-plausibility-checks/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-12-instrument-for-plausibility-checks.en.md
|  28| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-13-validate-inputs-based-on-physical-plausibility/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-13-validate-inputs-based-on-physical-plausibility.en.md
|  29| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-14-disable-unneeded-unused-communication-ports-and-protocols/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-14-disable-unneeded-unused-communication-ports-and-protocols.en.md
|  30| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-15-restrict-third-party-data-interfaces/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-15-restrict-third-party-data-interfaces.en.md
|  31| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-16-define-a-safe-process-state-in-case-of-a-plc-restart/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-16-define-a-safe-process-state-in-case-of-a-plc-restart.en.md
|  32| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-17-summarise-plc-cycle-times-and-trend-them-on-the-hmi/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-17-summarise-plc-cycle-times-and-trend-them-on-the-hmi.en.md
|  33| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-18-log-plc-uptime-and-trend-it-on-the-hmi/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-18-log-plc-uptime-and-trend-it-on-the-hmi.en.md
|  34| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-19-log-plc-hard-stops-and-trend-them-on-the-hmi/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-19-log-plc-hard-stops-and-trend-them-on-the-hmi.en.md
|  35| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-2-modularise-plc-code/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-2-modularise-plc-code.en.md
|  36| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-20-monitor-plc-memory-usage-and-trend-it-on-the-hmi/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-20-monitor-plc-memory-usage-and-trend-it-on-the-hmi.en.md
|  37| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-21-trap-false-negatives-and-false-positives-for-critical-alerts/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-21-trap-false-negatives-and-false-positives-for-critical-alerts.en.md
|  38| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-3-track-operating-modes/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-3-track-operating-modes.en.md
|  39| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-4-leave-operational-logic-in-the-plc-wherever-feasible/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-4-leave-operational-logic-in-the-plc-wherever-feasible.en.md
|  40| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-5-use-plc-flags-as-integrity-checks/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-5-use-plc-flags-as-integrity-checks.en.md
|  41| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-6-use-cryptographic-and-or-checksum-integrity-checks-for-plc-code/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-6-use-cryptographic-and-or-checksum-integrity-checks-for-plc-code.en.md
|  42| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-7-validate-timers-and-counters/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-7-validate-timers-and-counters.en.md
|  43| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-8-validate-and-alert-for-paired-inputs-outputs/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-8-validate-and-alert-for-paired-inputs-outputs.en.md
|  44| <ul><li>[X]</li></ul> | https://seqred.pl/en/the-top-20-secure-plc-coding-practices-part-9-validate-hmi-input-variables-at-the-plc-level-not-only-at-hmi/ | blog/the-top-20-secure-plc-coding-practices/the-top-20-secure-plc-coding-practices-part-9-validate-hmi-input-variables-at-the-plc-level-not-only-at-hmi.en.md
|  45| <ul><li>[X]</li></ul> | https://seqred.pl/en/zero-trust-architecture/ | blog/zero-trust-architecture.en.md
|  46| <ul><li>[ ]</li></ul> | https://seqred.pl/en/candidates/ | career/candidates.en.md
|  47| <ul><li>[ ]</li></ul> | https://seqred.pl/en/career/ | career/career.en.md
|  48| <ul><li>[ ]</li></ul> | https://seqred.pl/zaproszenie-sniadanie-technologiczne/ | events/zaproszenie-sniadanie-technologiczne.pl.md
|  49| <ul><li>[ ]</li></ul> | https://seqred.pl/cyberbezpieczenstwo-systemow-przemyslowych/ | services/cyberbezpieczenstwo-systemow-przemyslowych.pl.md
|  51| <ul><li>[ ]</li></ul> | https://seqred.pl/dla-akcjonariuszy/ | shareholders/dla-akcjonariuszy.pl.md
|  52| <ul><li>[ ]</li></ul> | https://seqred.pl/bug-bounty-1/ | events/bug-bounty-1.pl.md
|  53| <ul><li>[ ]</li></ul> | https://seqred.pl/partnerstwo-nozomi-networks/ | events/partnerstwo-nozomi-networks.pl.md
|  54| <ul><li>[ ]</li></ul> | https://seqred.pl/pierwszy-rok-seqred/ | events/pierwszy-rok-seqred.pl.md
|  55| <ul><li>[X]</li></ul> | https://seqred.pl/anonimowosc-w-sieci/ | blog/anonimowosc-w-sieci.pl.md
|  56| <ul><li>[X]</li></ul> | https://seqred.pl/bezpieczenstwo-hasel/ | blog/bezpieczenstwo-hasel.pl.md
|  57| <ul><li>[X]</li></ul> | https://seqred.pl/bezpieczne_wifi/ | blog/bezpieczne_wifi.pl.md
|  58| <ul><li>[X]</li></ul> | https://seqred.pl/elektroenergetyka-zagrozenia/ | blog/elektroenergetyka-zagrozenia.pl.md
|  59| <ul><li>[ ]</li></ul> | https://seqred.pl/en/anniversary/ | events/anniversary.en.md
|  60| <ul><li>[X]</li></ul> | https://seqred.pl/en/behavioral-biometrics/ | blog/behavioral-biometrics.en.md
|  61| <ul><li>[X]</li></ul> | https://seqred.pl/en/botnet-mirai/ | blog/botnet-mirai.en.md
|  62| <ul><li>[ ]</li></ul> | https://seqred.pl/en/bug-bounty/ | events/bug-bounty.en.md
|  63| <ul><li>[X]</li></ul> | https://seqred.pl/en/cve-bluestacks/ | blog/cve-bluestacks.en.md
|  64| <ul><li>[X]</li></ul> | https://seqred.pl/en/electroenergetics-threats/ | blog/electroenergetics-threats.en.md
|  65| <ul><li>[X]</li></ul> | https://seqred.pl/fuzzowanie_afl/ | blog/fuzzowanie_afl.pl.md
|  66| <ul><li>[X]</li></ul> | https://seqred.pl/podstawy-bezpieczenstwa-it/ | blog/podstawy-bezpieczenstwa-it.pl.md
|  67| <ul><li>[ ]</li></ul> | https://seqred.pl/rocznica/ | events/rocznica.pl.md
|  68| <ul><li>[X]</li></ul> | https://seqred.pl/secon-2019-bezpieczenstwo/ | blog/secon-2019-bezpieczenstwo.pl.md
|  69| <ul><li>[X]</li></ul> | https://seqred.pl/tagowanie-pamieci/ | blog/tagowanie-pamieci.pl.md
|  70| <ul><li>[ ]</li></ul> | https://seqred.pl/zgloszenie-podatnosci/ | events/zgloszenie-podatnosci.pl.md
|  71| <ul><li>[X]</li></ul> | https://seqred.pl/en/it-security-basics/ | blog/it-security-basics.en.md
|  72| <ul><li>[X]</li></ul> | https://seqred.pl/en/memory-tagging-extension/ | blog/memory-tagging-extension.en.md
|  73| <ul><li>[X]</li></ul> | https://seqred.pl/en/secure-passwords/ | blog/secure-passwords.en.md
|  74| <ul><li>[X]</li></ul> | https://seqred.pl/en/secon-2019/ | blog/secon-2019.en.md
|  75| <ul><li>[X]</li></ul> | https://seqred.pl/en/shodan-improved/ | blog/shodan-improved.en.md
|  76| <ul><li>[X]</li></ul> | https://seqred.pl/en/ot_network_segmentation/ | blog/ot_network_segmentation.en.md
|  77| <ul><li>[X]</li></ul> | https://seqred.pl/en/secure-wifi/ | blog/secure-wifi.en.md
|  78| <ul><li>[X]</li></ul> | https://seqred.pl/en/smart_building_report/ | blog/smart_building_report.en.md
|  79| <ul><li>[X]</li></ul> | https://seqred.pl/en/ransomware/ | blog/ransomware.en.md
|  80| <ul><li>[X]</li></ul> | https://seqred.pl/en/secure_usb/ | blog/secure_usb.en.md
|  81| <ul><li>[X]</li></ul> | https://seqred.pl/biometria-behawioralna/ | blog/biometria-behawioralna.pl.md
|  82| <ul><li>[X]</li></ul> | https://seqred.pl/inwentaryzacja-i-kontrola-zasobow-sprzetowych-w-ics/ | blog/inwentaryzacja-i-kontrola-zasobow-sprzetowych-w-ics.pl.md
|  83| <ul><li>[ ]</li></ul> | https://seqred.pl/en/contact-honeywell/ | contact/contact-honeywell.en.md
|  84| <ul><li>[ ]</li></ul> | https://seqred.pl/white-papers-2/ | contact/white-papers-2.pl.md
|  85| <ul><li>[ ]</li></ul> | https://seqred.pl/white-papers/ | contact/white-papers.pl.md
|  86| <ul><li>[X]</li></ul> | https://seqred.pl/zapewnienie-ciaglosci-dzialania-w-obliczu-pandemii-cyberatakow-zagrozen/ | blog/zapewnienie-ciaglosci-dzialania-w-obliczu-pandemii-cyberatakow-zagrozen.pl.md
|  87| <ul><li>[ ]</li></ul> | https://seqred.pl/en/secure-remote-access-eng/ | products/secure-remote-access-eng.en.md
|  88| <ul><li>[ ]</li></ul> | https://seqred.pl/en/contact-honeywell/thank-you/ | contact/contact-honeywell.en.md
|  89| <ul><li>[ ]</li></ul> | https://seqred.pl/audyt-bezpieczenstwa-urzadzen-mobilnych/ | services/audyt-bezpieczenstwa-urzadzen-mobilnych.pl.md
|  90| <ul><li>[ ]</li></ul> | https://seqred.pl/audyt-kodu/ | services/audyt-kodu.pl.md
|  91| <ul><li>[ ]</li></ul> | https://seqred.pl/audyt-ksc/ | services/audyt-ksc.pl.md
|  95| <ul><li>[ ]</li></ul> | https://seqred.pl/red-team/ | services/red-team.pl.md
|  96| <ul><li>[X]</li></ul> | https://seqred.pl/secure-product-development/ | services/secure-product-development.pl.md
|  97| <ul><li>[ ]</li></ul> | https://seqred.pl/segmentacja-sieci/ | services/segmentacja-sieci.pl.md
|  99| <ul><li>[ ]</li></ul> | https://seqred.pl/uslugi-chmurowe/ | services/uslugi-chmurowe.pl.md
| 100| <ul><li>[ ]</li></ul> | https://seqred.pl/en/security-audit-ics/ | services/security-audit-ics.en.md
| 101| <ul><li>[ ]</li></ul> | https://seqred.pl/en/smart-building-cybersecurity/ | services/smart-building-cybersecurity.en.md
| 103| <ul><li>[ ]</li></ul> | https://seqred.pl/en/security-code-review/ | services/security-code-review.en.md
| 108| <ul><li>[ ]</li></ul> | https://seqred.pl/en/nis-directive-audit/ | services/nis-directive-audit.en.md
| 109| <ul><li>[X]</li></ul> | https://seqred.pl/bezpieczne_usb/ | blog/bezpieczne_usb.pl.md
| 110| <ul><li>[ ]</li></ul> | https://seqred.pl/partnerstwo-honeywell-seqred/ | press/partnerstwo-honeywell-seqred.pl.md
| 111| <ul><li>[ ]</li></ul> | https://seqred.pl/bezpieczny-zdalny-dostep/ | products/bezpieczny-zdalny-dostep.pl.md
| 112| <ul><li>[X]</li></ul> | https://seqred.pl/cyberbezpieczenstwo-infografika/ | blog/cyberbezpieczenstwo-infografika.pl.md
| 113| <ul><li>[X]</li></ul> | https://seqred.pl/czy-systemy-bms-moga-stanowic-wektor-ataku-dla-systemow-ics/ | blog/czy-systemy-bms-moga-stanowic-wektor-ataku-dla-systemow-ics.pl.md
| 114| <ul><li>[ ]</li></ul> | https://seqred.pl/en/bug-bounty-for-seqred/ | press/bug-bounty-for-seqred.en.md
| 115| <ul><li>[ ]</li></ul> | https://seqred.pl/secure-remote-access/ | products/secure-remote-access.pl.md
| 116| <ul><li>[X]</li></ul> | https://seqred.pl/shodan-rekonesans-infrastruktury-it-ot/ | blog/shodan-rekonesans-infrastruktury-it-ot.pl.md
| 117| <ul><li>[X]</li></ul> | https://seqred.pl/smart_building_raport/ | blog/smart_building_raport.pl.md
| 118| <ul><li>[ ]</li></ul> | https://seqred.pl/en/foundation-of-cybermadeinpoland/ | events/foundation-of-cybermadeinpoland.en.md
| 119| <ul><li>[ ]</li></ul> | https://seqred.pl/pierwszy-rok-dzialalnosci-seqred-za-nami/ | press/pierwszy-rok-dzialalnosci-seqred-za-nami.pl.md
| 120| <ul><li>[ ]</li></ul> | https://seqred.pl/en/partnership-with-nozomi-networks/ | press/partnership-with-nozomi-networks.en.md
| 121| <ul><li>[ ]</li></ul> | https://seqred.pl/en/partnership-with-honeywell/ | press/partnership-with-honeywell.en.md
| 122| <ul><li>[ ]</li></ul> | https://seqred.pl/en/seqreds-first-year-of-operation-is-behind-us/ | press/seqreds-first-year-of-operation-is-behind-us.en.md
| 123| <ul><li>[ ]</li></ul> | https://seqred.pl/bezpieczne-zakupy/ | services/bezpieczne-zakupy.pl.md
| 124| <ul><li>[X]</li></ul> | https://seqred.pl/cyberbezpieczenstwo_smart_building/ | blog/cyberbezpieczenstwo_smart_building.pl.md
| 125| <ul><li>[X]</li></ul> | https://seqred.pl/en/smart-building-cybersecurity-is-key/ | blog/smart-building-cybersecurity-is-key.en.md
| 126| <ul><li>[ ]</li></ul> | https://seqred.pl/informacje-prasowe/ | press/informacje-prasowe.pl.md
| 127| <ul><li>[ ]</li></ul> | https://seqred.pl/en/press-releases/ | press/press-releases.en.md
| 128| <ul><li>[ ]</li></ul> | https://seqred.pl/zalozenie-grupy-cybermadeinpoland/ | events/zalozenie-grupy-cybermadeinpoland.pl.md
| 129| <ul><li>[X]</li></ul> | https://seqred.pl/en/cve-gurux-gxdlms-director/ | blog/cve-gurux-gxdlms-director.en.md
| 130| <ul><li>[X]</li></ul> | https://seqred.pl/en/cve-remote-code-execution-in-memu/ | blog/cve-remote-code-execution-in-memu.en.md
| 131| <ul><li>[X]</li></ul> | https://seqred.pl/en/fuzzing-afl/ | blog/fuzzing-afl.en.md
| 132| <ul><li>[X]</li></ul> | https://seqred.pl/jak-zapewnic-bezpieczenstwo-pracy-zdalnej/ | blog/jak-zapewnic-bezpieczenstwo-pracy-zdalnej.pl.md
| 133| <ul><li>[X]</li></ul> | https://seqred.pl/ransomware-co-to-jest-jak-sie-zabezpieczyc-jak-usunac/ | blog/ransomware-co-to-jest-jak-sie-zabezpieczyc-jak-usunac.pl.md
| 134| <ul><li>[X]</li></ul> | https://seqred.pl/zdalny-dostep-do-systemow-ics-zasady-bezpieczenstwa/ | blog/zdalny-dostep-do-systemow-ics-zasady-bezpieczenstwa.pl.md
| 135| <ul><li>[X]</li></ul> | https://seqred.pl/aplikacje_chmurowe_zagrozenia_ot/ | blog/aplikacje_chmurowe_zagrozenia_ot.pl.md
| 136| <ul><li>[X]</li></ul> | https://seqred.pl/atak-przez-zdalny-dostep-ics/ | blog/atak-przez-zdalny-dostep-ics.pl.md
| 137| <ul><li>[X]</li></ul> | https://seqred.pl/ataki_dos/ | blog/ataki_dos.pl.md
| 138| <ul><li>[X]</li></ul> | https://seqred.pl/awarie_techniczne_ics/ | blog/awarie_techniczne_ics.pl.md
| 139| <ul><li>[X]</li></ul> | https://seqred.pl/bezpieczenstwo-chmury-zarzadzanie-tozsamoscia-i-dostepem-gcp-vs-aws/ | blog/bezpieczenstwo-chmury-zarzadzanie-tozsamoscia-i-dostepem-gcp-vs-aws.pl.md
| 140| <ul><li>[X]</li></ul> | https://seqred.pl/bezpieczenstwo-ot-it-razem-czy-oddzielnie/ | blog/bezpieczenstwo-ot-it-razem-czy-oddzielnie.pl.md
| 141| <ul><li>[X]</li></ul> | https://seqred.pl/cve-2020-10551-eskalacja-uprawnien-w-qqbrowser/ | blog/cve-2020-10551-eskalacja-uprawnien-w-qqbrowser.pl.md
| 142| <ul><li>[X]</li></ul> | https://seqred.pl/cve-gurux-gxdlms-director-2/ | blog/cve-gurux-gxdlms-director-2.pl.md
| 143| <ul><li>[X]</li></ul> | https://seqred.pl/cve-zdalne-wykonanie-kodu-memu/ | blog/cve-zdalne-wykonanie-kodu-memu.pl.md
| 144| <ul><li>[ ]</li></ul> | https://seqred.pl/infrastruktura-krytyczna/ | services/infrastruktura-krytyczna.pl.md
| 145| <ul><li>[X]</li></ul> | https://seqred.pl/inzynieria-spoleczna-i-phishing/ | blog/inzynieria-spoleczna-i-phishing.pl.md
| 146| <ul><li>[X]</li></ul> | https://seqred.pl/sabotaz-blad-ludzki-ot/ | blog/sabotaz-blad-ludzki-ot.pl.md
| 147| <ul><li>[X]</li></ul> | https://seqred.pl/segmentacja-sieci-ot/ | blog//segmentacja-sieci-ot.pl.md
| 148| <ul><li>[X]</li></ul> | https://seqred.pl/zabezpieczenie_infrastruktury/ | blog/zabezpieczenie_infrastruktury.pl.md
| 149| <ul><li>[X]</li></ul> | https://seqred.pl/en/cloud-computing-security-identity-and-access-management-comparison-for-gcp-and-aws/ | blog/cloud-computing-security-identity-and-access-management-comparison-for-gcp-and-aws.en.md
| 150| <ul><li>[X]</li></ul> | https://seqred.pl/en/cyber-kill-chain-what-is-it-and-how-to-use-it-to-stop-advanced-methods-of-attack/ | blog/cyber-kill-chain-what-is-it-and-how-to-use-it-to-stop-advanced-methods-of-attack.en.md
| 151| <ul><li>[ ]</li></ul> | https://seqred.pl/audyt-ot/ | services/audyt-ot.pl.md
| 152| <ul><li>[ ]</li></ul> | https://seqred.pl/cbom/ | services/cbom.pl.md
| 153| <ul><li>[ ]</li></ul> | https://seqred.pl/smart_building/ | services/smart_building.pl.md
| 154| <ul><li>[ ]</li></ul> | https://seqred.pl/testy-penetracyjne/ | services/testy-penetracyjne.pl.md
| 155| <ul><li>[ ]</li></ul> | https://seqred.pl/smx-secure-media-exchange/ | products/smx-secure-media-exchange.pl.md
| 156| <ul><li>[ ]</li></ul> | https://seqred.pl/cyberbezpieczenstwo-prezentacje/ | events/cyberbezpieczenstwo-prezentacje.pl.md
| 157| <ul><li>[X]</li></ul> | https://seqred.pl/en/cve-2020-10551-privilege-escalation-in-qqbrowser/ | blog/cve-2020-10551-privilege-escalation-in-qqbrowser.en.md
| 158| <ul><li>[X]</li></ul> | https://seqred.pl/en/revolte-an-attack-exploiting-the-reuse-of-the-same-keystream-by-vulnerable-base-stations/ | blog/revolte-an-attack-exploiting-the-reuse-of-the-same-keystream-by-vulnerable-base-stations.en.md
| 159| <ul><li>[X]</li></ul> | https://seqred.pl/cve-eskalacja-uprawnien-w-andy/ | blog/cve-eskalacja-uprawnien-w-andy.pl.md
| 160| <ul><li>[X]</li></ul> | https://seqred.pl/en/cve-privilege-escalation-in-andy/ | blog/cve-privilege-escalation-in-andy.en.md
| 161| <ul><li>[ ]</li></ul> | https://seqred.pl/en/services/ | services/services.en.md
| 162| <ul><li>[X]</li></ul> | https://seqred.pl/google-cloud-directory-sync-gcds-do-czego-sluzy-jak-skonfigurowac/ | blog/google-cloud-directory-sync-gcds-do-czego-sluzy-jak-skonfigurowac.en.md
| 163| <ul><li>[X]</li></ul> | https://seqred.pl/jak-ograniczyc-skutecznosc-atakow-na-lokalne-konta-administratora-w-ics/ | blog/jak-ograniczyc-skutecznosc-atakow-na-lokalne-konta-administratora-w-ics.pl.md
| 164| <ul><li>[X]</li></ul> | https://seqred.pl/jak-wlaczyc-uwierzytelnianie-wieloskladnikowe-w-office-365/ | blog/jak-wlaczyc-uwierzytelnianie-wieloskladnikowe-w-office-365.pl.md
| 165| <ul><li>[X]</li></ul> | https://seqred.pl/nowy-atak-revolte-pozwala-hakerom-odkodowac-szyfrowanie-volte-w-celu-szpiegowania-rozmow-telefonicznych/ | blog/nowy-atak-revolte-pozwala-hakerom-odkodowac-szyfrowanie-volte-w-celu-szpiegowania-rozmow-telefonicznych.pl.md
| 166| <ul><li>[X]</li></ul> | https://seqred.pl/zarzadzanie-podatnosciami-w-srodowisku-automatyki-przemyslowej/ | blog/zarzadzanie-podatnosciami-w-srodowisku-automatyki-przemyslowej.pl.md
| 167| <ul><li>[X]</li></ul> | https://seqred.pl/cve-2020-29007-zdalne-wykonanie-kodu-w-mediawiki-score/ | blog/cve-2020-29007-zdalne-wykonanie-kodu-w-mediawiki-score.pl.md
| 168| <ul><li>[ ]</li></ul> | https://seqred.pl/en/ami-system-security/ | contact/ami-system-security.en.md
| 169| <ul><li>[X]</li></ul> | https://seqred.pl/en/cve-2020-29007-remote-code-execution-in-mediawiki-score/ | blog/cve-2020-29007-remote-code-execution-in-mediawiki-score.en.md
| 170| <ul><li>[ ]</li></ul> | https://seqred.pl/en/events/ | events/events.en.md
| 171| <ul><li>[X]</li></ul> | https://seqred.pl/en/how-to-enable-multi-factor-authentication-in-office-365/ | blog/how-to-enable-multi-factor-authentication-in-office-365.en.md
| 172| <ul><li>[ ]</li></ul> | https://seqred.pl/konferencje/ | events/konferencje.pl.md
| 173| <ul><li>[ ]</li></ul> | https://seqred.pl/polityka-prywatnosci/ | policies/polityka-prywatnosci.pl.md
| 174| <ul><li>[ ]</li></ul> | https://seqred.pl/zabezpieczenia-smart-licznikow-systemow-ami/ | contact/zabezpieczenia-smart-licznikow-systemow-ami.pl.md
| 175| <ul><li>[ ]</li></ul> | https://seqred.pl/en/privacy-policy/ | policies/privacy-policy.en.md
| 176| <ul><li>[X]</li></ul> | https://seqred.pl/model-diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa/ | blog/model-diamentowy-powlamaniowa-analiza-incydentow-bezpieczenstwa.pl.md
| 177| <ul><li>[X]</li></ul> | https://seqred.pl/mitre-attck-analiza-atakow-w-celu-skuteczniejszej-ochrony/ | blog/mitre-attck-analiza-atakow-w-celu-skuteczniejszej-ochrony.pl.md
| 178| <ul><li>[X]</li></ul> | https://seqred.pl/en/lets-face-it-smart-buildings-are-insecure/ | blog/lets-face-it-smart-buildings-are-insecure.en.md
| 179| <ul><li>[X]</li></ul> | https://seqred.pl/cyber-kill-chain-co-to-jest-i-jak-wykorzystac-go-do-powstrzymania-zaawansowanych-atakow/ | blog/cyber-kill-chain-co-to-jest-i-jak-wykorzystac-go-do-powstrzymania-zaawansowanych-atakow.pl.md
| 180| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-resiliance-improvement-guide-part-i-introduction/ | blog/small-business-cyber-resiliance-improvement-guide-part-i-introduction.en.md
| 181| <ul><li>[X]</li></ul> | https://seqred.pl/podsumowanie-incydentu-w-colonial-pipeline/ | blog/podsumowanie-incydentu-w-colonial-pipeline.pl.md
| 182| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-resilience-improvement-guide-part-ii-backing-up/ | blog/small-business-cyber-resilience-improvement-guide-part-ii-backing-up.en.md
| 183| <ul><li>[X]</li></ul> | https://seqred.pl/en/proactive-approach-to-incident-response-part-1-introduction/ | blog/proactive-approach-to-incident-response-part-1-introduction.en.md
| 184| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-resilience-improvement-guide-part-iii-protecting-your-organisation-from-malware/ | blog/small-business-cyber-resilience-improvement-guide-part-iii-protecting-your-organisation-from-malware.en.md
| 185| <ul><li>[X]</li></ul> | https://seqred.pl/en/proactive-approach-to-incident-response-part-2-cross-train-your-teams/ | blog/proactive-approach-to-incident-response-part-2-cross-train-your-teams.en.md
| 186| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-resilience-improvement-guide-part-iv-keeping-your-mobile-devices-safe/ | blog/small-business-cyber-resilience-improvement-guide-part-iv-keeping-your-mobile-devices-safe.en.md
| 187| <ul><li>[X]</li></ul> | https://seqred.pl/en/proactive-approach-to-incident-response-part-3-establishing-ot-security-baseline/ | blog/proactive-approach-to-incident-response-part-3-establishing-ot-security-baseline.en.md
| 188| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-resilience-improvement-guide-part-v-using-passwords-to-protect-your-data/ | blog/small-business-cyber-resilience-improvement-guide-part-v-using-passwords-to-protect-your-data.en.md
| 189| <ul><li>[X]</li></ul> | https://seqred.pl/en/proactive-approach-to-incident-response-part-4-practicing-your-incident-response-plan/ | blog/proactive-approach-to-incident-response-part-4-practicing-your-incident-response-plan.en.md
| 190| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-resilience-improvement-guide-part-vi-avoiding-phishing-attacks/ | blog/small-business-cyber-resilience-improvement-guide-part-vi-avoiding-phishing-attacks.en.md
| 191| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-security-response-and-recovery-part-i-introduction/ | blog/small-business-cyber-security-response-and-recovery-part-i-introduction.en.md
| 192| <ul><li>[ ]</li></ul> | https://seqred.pl/en/aws-level-1-mssp-eng/ | contact/aws-level-1-mssp-eng.en.md
| 193| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-security-response-and-recovery-part-ii-prepare-for-incidents/ | blog/small-business-cyber-security-response-and-recovery-part-ii-prepare-for-incidents.en.md
| 194| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-security-response-and-recovery-part-iii-identify-whats-happening/ | blog/small-business-cyber-security-response-and-recovery-part-iii-identify-whats-happening.en.md
| 195| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-security-response-and-recovery-part-iv-resolve-the-incident/ | blog/small-business-cyber-security-response-and-recovery-part-iv-resolve-the-incident.en.md
| 196| <ul><li>[ ]</li></ul> | https://seqred.pl/rekrutacja/ | career/rekrutacja.pl.md
| 197| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-security-response-and-recovery-part-v-report-the-incident-to-the-wider-stakeholders/ | blog/small-business-cyber-security-response-and-recovery-part-v-report-the-incident-to-the-wider-stakeholders.en.md
| 198| <ul><li>[X]</li></ul> | https://seqred.pl/en/small-business-cyber-security-response-and-recovery-part-vi-learn-from-the-incident/ | blog/small-business-cyber-security-response-and-recovery-part-vi-learn-from-the-incident.en.md
| 199| <ul><li>[X]</li></ul> | https://seqred.pl/en/data-privacy-data-security-vol-i/ | blog/data-privacy-data-security-vol-i.en.md
| 200| <ul><li>[X]</li></ul> | https://seqred.pl/en/data-privacy-data-security-vol-ii/ | blog/data-privacy-data-security-vol-ii.en.md
| 201| <ul><li>[X]</li></ul> | https://seqred.pl/en/data-privacy-data-security-vol-iii/ | blog/data-privacy-data-security-vol-iii.en.md
| 202| <ul><li>[X]</li></ul> | https://seqred.pl/en/data-privacy-data-security-vol-iii-2/ | blog/data-privacy-data-security-vol-iii-2.en.md
| 203| <ul><li>[X]</li></ul> | https://seqred.pl/en/security-operations-centre-part-1/ | blog/security-operations-centre-part-1.en.md
| 204| <ul><li>[X]</li></ul> | https://seqred.pl/en/security-operations-centre-part-2/ | blog/security-operations-centre-part-2.en.md
| 205| <ul><li>[X]</li></ul> | https://seqred.pl/kariera/ | career/kariera.pl.md
| 206| <ul><li>[X]</li></ul> | https://seqred.pl/en/security-operations-centre-part-3/ | blog/security-operations-centre-part-3.en.md
| 207| <ul><li>[X]</li></ul> | https://seqred.pl/en/security-operations-centre-part-4/ | blog/security-operations-centre-part-4.en.md
| 208| <ul><li>[X]</li></ul> | https://seqred.pl/en/security-operations-centre-part-5/ | blog/security-operations-centre-part-5.en.md
| 209| <ul><li>[X]</li></ul> | https://seqred.pl/en/cyber-threats-detection-response-mitigation-i/ | blog/cyber-threats-detection-response-mitigation-i.en.md
| 210| <ul><li>[X]</li></ul> | https://seqred.pl/en/cyber-threats-detection-response-mitigation-ii/ | blog/cyber-threats-detection-response-mitigation-ii.en.md
| 211| <ul><li>[X]</li></ul> | https://seqred.pl/en/common-cloud-vulnerabilities/ | blog/common-cloud-vulnerabilities.en.md
| 212| <ul><li>[X]</li></ul> | https://seqred.pl/en/common-attack-vectors-in-the-cloud/ | blog/common-attack-vectors-in-the-cloud.en.md
| 213| <ul><li>[X]</li></ul> | https://seqred.pl/en/best-practices-for-securing-your-cloud/ | blog/best-practices-for-securing-your-cloud.en.md
| 214| <ul><li>[X]</li></ul> | https://seqred.pl/en/industrial-network-security-architecture-introduction/ | blog/industrial-network-security-architecture-introduction.en.md
| 215| <ul><li>[X]</li></ul> | https://seqred.pl/en/industrial-network-security-architecture-network-segmentation/ | blog/industrial-network-security-architecture-network-segmentation.en.md
| 216| <ul><li>[X]</li></ul> | https://seqred.pl/en/industrial-network-security-architecture-asset-and-network-management/ | blog/industrial-network-security-architecture-asset-and-network-management.en.md
| 217| <ul><li>[X]</li></ul> | https://seqred.pl/en/fsbs-global-energy-sector-intrusion-campaign-2011-2018/ | blog/fsbs-global-energy-sector-intrusion-campaign-2011-2018.en.md
| 218| <ul><li>[X]</li></ul> | https://seqred.pl/en/industrial-network-security-architecture-network-segmentation-2/ | blog/industrial-network-security-architecture-network-segmentation-2.en.md
| 219| <ul><li>[X]</li></ul> | https://seqred.pl/en/industrial-network-security-architecture-network-protection/ | blog/industrial-network-security-architecture-network-protection.en.md
| 220| <ul><li>[ ]</li></ul> | https://seqred.pl/bezplatne-konsultacje-cyberbezpieczenstwa-dla-startupow/ | contact/bezplatne-konsultacje-cyberbezpieczenstwa-dla-startupow.pl.md
| 221| <ul><li>[X]</li></ul> | https://seqred.pl/czwartki-ot-bezpieczenstwo-systemow-przemyslowych/ | blog/czwartki-ot-bezpieczenstwo-systemow-przemyslowych.pl.md
| 222| <ul><li>[ ]</li></ul> | https://seqred.pl/threat-intelligence/ | services/threat-intelligence.pl.md

# hugo-final-test
