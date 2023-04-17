+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 4 – Leave operational logic in the PLC wherever feasible"
date="2021-10-06"
author="Eugene Wypior"
image="/blog/PLC-p4-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **Leave as much operational logic e.g., totalising or integrating, as possible directly in the PLC. The HMI does not get enough updates to do this well.** { .article-section }

**Security Objective**

**Target Group**

Integrity of PLC Logic

Product Supplier Integration /  
Maintenance Service Provider Asset Owner 

## Guidance{ .article-section }

HMIs provide some level of coding capabilities, originally aimed to help operators enhance visualisation and alarming, that some programmers have employed to create code that should rather stay in the PLC to remain complete and auditable. 

Calculating values as close to the field as possible makes these calculations more accurate. The HMI does not get enough updates to do totalising / integrating well. Also, there is always latency between HMI and PLC. Further, when the code is in the PLC, and an HMI restarts, it can always receive totalisers/counts from a PLC. 

In particular, HMI code to be avoided is anything related to security or safety functions such as interlocks, timers, holds or permissives. 

For analysing process data values over time, a process data historian is the better choice than the HMI. Use queries in a process historian database to compare totalised values (over a period, over a batch, over a process cycle) with totals aggregated locally in PLC logic. Alert on a variance greater than that can be explained by differences in data granularity. 

## Example{ .article-section }

*   Code to establish conditions to enable/disable buttons: Enable/disable actions should be controlled on PLC layer, otherwise, actions can be performed on the HMI (or through network) in PLC, although not meeting (intended) conditions. 
*   Timers to allow actions to the operator (delay timer for consecutive motor starts, timer to consider valves closed/open or motor stopped) should not be put on the HMI layer but in the PLC governing such motor/valve. 
*   Thresholds for alarms have to be part of PLC codes although displayed on HMIs. 
*   Water tank with changing volume: The PLC which controls flow in and out of the tank can easily totalise volume (and cross-validate totals). The HMI could do this as well, but it would need to get the values from the PLC first. These values would need accurate time-stamps in order to get correct totals in case of latency or and might miss values if the HMI restarts. 

## Why? { .article-section }

**Beneficial for …?**

**Why?**

**Security**

**1\.** Allows consistency in verifying code changes. HMI coding has its change control apart from PLC, generally not with the same rigor (especially in construction and commissioning phases), not allowing system owners to have a complete view and even losing important considerations. HMI’s do not include “forced signals” or changed value lists as PLCs or SCADAs, so HMI level changes are more difficult to be detected, practically impossible to be part of an authorisation change management plan.

**2\.** For an attacker, it is harder to manipulate totals distributed over many PLCs than to manipulate totals all calculated in the HMI.

**3\.** If a portion of the enable/disable functions are not in the PLC, attackers might be able to manipulate the PLC and I/O without having to work the HMI portion as the proper information is already obfuscated on the operator screen.

**Reliability** 

**1\.** Calculations are more efficient and accurate if closer to the field. Also, totals and counts will still be available if HMI restarts (PLCs do not restart as often and usually store these values in non-volatile memory). 

**2\.** Different sources for inputs and interlocks may mean non expected failures. There can be different technologies for HMIs in a plant (SCADA layer, but also field controller panels) and changes in one of those will fail to be disseminated through the rest of layers, leading to inconsistences in visualisation and possible failures in operation. 

**Maintenance** 

Coding is easy to understand and transfer from PLC to PLC, not so much from HMIs to HMIs. 

## References{ .article-section }

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA010 – Impair Process Control](https://collaborate.mitre.org/attackics/index.php/Impair_Process_Control) 

**Technique:** [T0836 – Modify Parameter](https://collaborate.mitre.org/attackics/index.php/Technique/T0836) 

**ISA 62443-3-3** 

**SR 3.6** : Deterministic Output 

**ISA 62443-4-2** 

**CR 3.6** : Deterministic Output 

## What’s next?{ .article-section }

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about using PLC flags as integrity checks 

## Do you require help with secure coding of your PLCs?{ .article-section }

If you have any questions or require help in securely coding your PLCs, please contact SEQRED.

SEQRED specialises in providing bespoke OT and IoT cybersecurity solutions.  
Our services cover such areas as Critical Infrastructure Protection, Cloud Services Security or Audits, and Threat Intelligence. For a full list of our services visit our services page – [https://seqred.pl/en/services/](https://seqred.pl/en/services/)

###### **About this article**

You can download the full copy of the Top 20 Secure PLC Coding Practices by clicking [here.](https://www.plc-security.com/index.html#download)  

The series of these articles is written under the following license:

Copyright (c) 2021 admeritia GmbH, Langenfeld/Rheinland, Germany

Permission is hereby granted, free of charge, to any person obtaining a copy of “Top 20 Secure PLC Coding Practices” and associated documentation files, to deal in the “Top 20 Secure PLC Coding Practices” without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the “Top 20 Secure PLC Coding Practices”, and to permit persons to whom the “Top 20 Secure PLC Coding Practices” is furnished to do so, subject to the following conditions:

THE “Top 20 Secure PLC Coding Practices” IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE “Top 20 Secure PLC Coding Practices” OR THE USE OR OTHER DEALINGS IN THE “Top 20 Secure PLC Coding Practices”.
