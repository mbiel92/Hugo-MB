+++
lang="en-GB"
title="OT and IT department cybersecurity – linked or separate?"
date="2020-04-02"
author="Michał Stępień"
image="/blog/Comparison_IT_OT.jpeg"
+++


OT and IT department cybersecurity – linked or separate?
========================================================

In factories, companies and enterprises, cybersecurity for IT and OT departments should not be treated as separate issues. Historically, OT engineers have treated IT as a necessary evil, some of them even would go as far as “locking the infrastructure away” in order to “protect” it from IT department staff. Installing e.g. system updates could potentially mean interruption of system continuity operations and disturbance in monitoring control systems e.g. SCADA.

Both the similarities and the differences between IT and OT might not be clear to someone without more advanced knowledge. In “Why OT has different needs than IT” Sarah Fluchs provides a detailed comparison of the two and presents the differences between an IT and an OT environment, taking into account working conditions, project approaches, technology dynamics, organisational requirements and technologies used.

In this article, I will further examine the data shown in the table below, presenting examples, which will allow for a better understanding of IT and OT departments’ different approaches to systems.

![](/blog/Comparison_IT_OT.jpeg)

Source: [Sarah Fluchs “Why OT has different needs than IT”](https://medium.com/@fluchsfriction/why-ot-has-different-needs-than-it-18ba9baa36e7)

> Differences between OT and IT departments
> -----------------------------------------

### 1\. Operation environment

Servers operated by IT departments are usually located in air-conditioned offices or server rooms and due to the working conditions, in most cases they are not connected to capacitive power supplies. On the other hand, OT servers’ object cabinets, frequently located outside or on shop floors, can be exposed to dust and humidity. Because frequent disinfections using foam and hot water are a necessary part of maintenance, specific requirements for the degree of protection provided by mechanical casings and electrical enclosures are often put in place, e.g. IP55 is required for control cabinets. In addition to enclosure requirements, there are specific guidelines set for devices inside cabinets.

### 2\. Technology

Technologie biznesowe stosowane w sieciach IT niejednokrotnie są dostępne „z półki” np. systemy SAP i wymagają dostosowania w zakresie niezbędnych funkcjonalności do charakteru organizacji. W przypadku systemów sterowania OT zwykle są programowane pod konkretne potrzeby i właściwości typowe dla specyfiki procesu. Sterowniki oraz inne komponenty inteligentne na korzystają z protokołów typowych dla producentów urządzeń (choć są wyjątki). Ułatwieniem dla automatyków-programistów jest wspólna platforma wykorzystywana do programowania np. paneli operatorskich, sterowników programowalnych oraz np. napędów, stąd ze względu na optymalizację czasu wdrożenia preferowane są rozwiązania pochodzące od jednego dostawcy. Additionally, to make the implementation processes more time-efficient, and using one vendor components is preferable to multisource delivery.

### 3\. Design mindset

The analysis of IT systems is tied to the “network/ application” view of computer scientists, whereas the examination of OT systems is based on a “hardware” view of (electrical) engineers, analysed in the context of mechanical devices (pumps, tanks, valves, reactors etc.) of which are tied to control system components and which parameters could be measured (temperature, volume, flow etc.) and passed to system inputs. IT system design processes are conducted with regard to communication channels and configuration security, whereas OT system design processes focus more on operational requirements, remaining more committed to physical safety rather than information security.

### 4\. Priority in operations, security objectives

Priorities in operations of IT systems focus mainly on efficiency, safety and usability of functions, whereas for OT systems priorities in operations are centered around service and production continuity, as well as maintaining safety of operations and monitoring limit values.

While IT system safety objectives are confidentiality, integrity and availability of data, for ICS systems safety objectives are focused on availability, reliability and determinism of functions, with integrity of data and real-time data transmission without delay or jitter also being crucial to the processes. Additionally, IT network requirements are tied to confidentiality of data.

### 5\. Life cycle, dynamism

The life cycle of an IT system is expected to last 3-5 years. After this period of time, a system is considered obsolete and a replacement is recommended. The life cycle of OT systems lasts about 20 years, after which  
infrastructure modernisation or retrofit can be conducted when:

*   the recommendation for a modernisation of infrastructure is backed by a positive outcome of a risk assessment,
*   the project is cost-effective,
*   the availability of replacement parts is limited.

Full functionality reconstruction of OT systems should be conducted as fast as possible.

Because IT networks are much more dynamic, they have a larger number of user requirements than their OT counterparts, which can be considered more static in terms of user requirements. In general, OT networks have a more static topology with a smaller number of components, whereas IT networks are larger and more scalable.

### 6\. Organisational approach

IT systems in larger organisations are usually managed by a specialised team responsible for only a small part of the entire process (e.g. different groups are responsible for databases, communication, maintenance). Employees managing OT are usually responsible for all processes related to the system (communication between devices, parameterisation, change of faulty components, keeping documentation up to date and ongoing maintenance).

> OT and IT department cybersecurity – linked or seperate?
> --------------------------------------------------------

The cooperation between IT and OT derparments is crucial. The different viewpoints on systems, and with that the vigilance to distinct security risks can be the reason for taking into account the needs of both groups when defining project assumptions as well as implementation and maintenance of automation systems. Unfortunately, the conflict of these two perspectives on automation systems and different terminology used by the two departments often stand in the way of achieving that goal.

==========

