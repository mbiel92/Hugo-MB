+++
lang="en-GB"
title="Can Building Management Systems be Potential Attack Vectors for Industrial Control Systems?"
date="2020-04-09"
author="Łukasz Dudkowski"
image="/blog/Seqred_Czy_systemy_BMS_moga_stanowic_wektor_ataku_dla_systemow_ICS.jpg"
+++

For many enterprises, working with advanced industrial systems the simultaneous implementation and use of Building Management Systems (BMS) is necessary. However, because their functionality is not seen as crucial for the realisation of the enterprise’s main goal, BMS security can often be overlooked or treated as less important compared to ICS security. Over the last couple of years, Building Management Systems, implemented in order to ensure proper functions of buildings’ systems, became a common target of cyber attacks. In a case where a Building Management System is connected to an Industrial Control System, an attack on a BMS can be a gateway to a security breach in an industrial automation system of an enterprise.

**In this article, you will find out:**

*   How Building Management Systems support enterprise activities,
*   How do cybersecurity threats to Building Management Systems influence ICS security,
*   How to limit the negative impact on ICS when dealing with a compromised BMS.

![](/blog/Seqred_Czy_systemy_BMS_moga_stanowic_wektor_ataku_dla_systemow_ICS.jpg)

> Building Management Systems – the Necessary Support for the Proper Functioning of an Enterprise
> -----------------------------------------------------------------------------------------------

The safe and proper use of Building Management Systems can influence the proper functioning of many aspects responsible for ICS of an enterprise, for example:

*   Warehouse operations often require the use of control systems monitoring the temperature, humidity and number of air cycles,
*   Production plants use mechanisms to control people flow and access to restricted zones with control systems by implementing access control systems, intrusion detection systems, as well as indoor and outdoor surveillance using CCTV systems,
*   The office area of an enterprise, used by engineers, system designers or management staff, needs to be equipped with systems ensuring comfortable working conditions e.g. systems allowing the adjustments of air conditioning, brightness of lighting and ones allowing for booking of conference rooms,
*   Building Management Systems are often responsible for the initial phase of setting up a “clean room”.

As shown by the examples above, adequate Building Management Systems are used alongside industrial systems, in which cases they can be used as:

*   **systems supporting the functioning of a building:** providing comfort and safety for employees,
*   **systems indirectly taking part in technological processes, including:** initial air preparation (HVAC) or passing on individual measurement parameters,
*   **systems ensuring the physical safety of industrial systems and building security** ( access control systems, CCTV systems).

> The Lower Priority of the Safety of Building Management Systems in Production Companies
> ---------------------------------------------------------------------------------------

Sometimes, Building Management Systems of industrial plants are treated with less importance than systems responsible for fulfilling the main goal of the plant. This occurs due to the pressure often put on ICS security, due to its particular importance for company activity. However, it is important to keep in mind that Building Management Systems, present in modern production plants in constantly updated versions, also require complex cybersecurity monitoring and maintenance.

In addition to the implementation of cybersecurity requirements for ICS, it is important to maintain appropriate measures when using BMS, because their safeguards could influence the overall security of key processes, particularly because the number of attacks on Building Management Systems is on the rise.

> The Threats Related to BMS
> --------------------------

During a risk assessment for cybersecurity of industrial systems it is crucial to consider the threats related to BMS. This is particularly important, because Building Management systems have become a popular target for cyberattacks. Recently, the number and variety of Smart Building systems has significantly increased. According to a report published on September 19th 2019 by Kaspersky about the security threats for Smart Building systems, 4 out of 10 computers used for Building Management have been a subject of a malware attack in the first half of 2019. The attacks were conducted mainly through the Internet, portable devices and e-mail.

If you want to find out more about the types of potential threats as well as possible outcomes of attacks on BMS, read our article on [“Smart Buildings – nearly 40 percent of systems attacked by malware”](https://seqred.pl/en/smart_building_report/).For more information on the types of systems used by Smart Buildings along with types of possible attacks, check out our article on [“Smart Buildings – Cybersecurity is key”](https://seqred.pl/en/smart-building-cybersecurity-is-key/).

> Potential Threats for ICS Caused by BMS
> ---------------------------------------

The implications of an attack on a BMS can influence the ICS on many levels:

### **1. additional attack vector**

In case of an incorrectly conducted network separation/segregation a BMS can be an additional attack vector and a potential gateway to ICS architecture.

### **2. modification of data processing in a target system**  

The use of variables of BMS technology monitoring e.g. the temperature or the water flow and transferring collected data to ICS could lead to an unauthorised manipulation occurring in the primary system, which could then affect the execution of the process in the target system.

### **3. malware infection**

The infiltration of a workstation used for a BMS by malware can result in malware being transferred to a workstation used for an ICS (e.g. due to the use of a common mass storage device).

### **4. halt in production/ lower quality of the manufactured product**

For machines used by a BMS, device tampering e.g. a drastic change of temperature or humidity in the production plant could potentially lead to a halt in production/ lower quality of the manufactured product.

### **5. gaining physical access to Industrial Control Systems**

Gaining unauthorised access to physical safety systems controlled by BMS (e.g. CCTV. ACS, IDS), could potentially allow for intrusion on the premises of a production plant, which could then lead to unauthorised persons gaining physical access to ICS.

> How to limit the negative impact on ICS caused by a compromised BMS?
> --------------------------------------------------------------------

In order to minimise the impact of a compromised BMS on an Industrial Control System it is important to consider undertaking the following actions:

**1\.** Review the Smart Building solutions. Consider a separation form ICS or, if needed, an implementation of adequate security instruments (DMZ, firewall etc.) at critical points of contact between the two systems.

**2\.** Conduct security assessments of Building Management Systems, taking into account the potential escalation of an attack on the Industrial Control System.

**3\.** During an ICS risk assessment, consider the potential threats which could be caused by an attack on BMS.

**4\.** When making plans for various emergency scenarios, be sure to take into account ones caused by a BMS malfunction to ensure business continuity in manufacturing.

**5\.** Consider implementing security measures similar to the ones used by the ICS whenever possible (e.g. for servers, workstations and removable media used within the BMS).

**References:**

*   [Kaspersky “Threat landscape for smart buildings. Q1 2019 in brief”](https://ics-cert.kaspersky.com/reports/2019/09/19/threat-landscape-for-smart-buildings-h1-2019-in-brief/)