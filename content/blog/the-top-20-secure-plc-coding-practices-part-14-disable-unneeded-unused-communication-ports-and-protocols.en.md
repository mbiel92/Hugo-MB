+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 14 – Disable unneeded / unused communication ports and protocols"
date="2020-12-15"
author="Eugene Wypior"
image="/blog/PLC-p14-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **PLC controllers and network interface modules generally support multiple communication protocols that are enabled by default. Disable ports and protocols that are not required for the application.**

**Security Objective**

**Target Group**

Hardening

Integration / Maintenance Service Provider

> ### Guidance

Common protocols usually enabled by default are e.g., HTTP, HTTPS, SNMP, Telnet, FTP, MODBUS, PROFIBUS, EtherNet/IP, ICMP, etc.  
Best practice is to develop a data flow diagram that depicts the required communications between the PLC and other components in the system.  
The data flow diagram should show both the physical ports on the PLC as well as the logical networks they are connected to. For each physical port, a list of required network protocols should be identified and all others disabled.

> ### Example

For example, many PLCs include an embedded web server for maintenance and troubleshooting. If this feature will not be used, if possible, it should be disabled as this could be an attack vector.

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

Every enabled port and protocol add to the PLC’s potential attack surface. The easiest way to make sure an attacker can’t use them for unauthorized communication is to disable them altogether.

**Reliability** 

If a PLC cannot communicate via a certain port or protocol, this also reduces the potential amount of (malformed) traffic, be it malicious or not, which decreases the chances of the PLC crashing because of unintended / malformed communication packages.

**Maintenance** 

Disabling unused ports and protocols also facilitates maintenance, because it reduces the PLC’s overall complexity. What’s not there does not need to be administrated or updated.

> ### References

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA005 – Discovery](https://collaborate.mitre.org/attackics/index.php/Discovery)

**Technique:** [T0808 – Control Devices Identification,](https://collaborate.mitre.org/attackics/index.php/Technique/T0808) [T0841 – Network Service Scanning](https://collaborate.mitre.org/attackics/index.php/Technique/T0841), [T0854 – Serial Connection Enumeration](https://collaborate.mitre.org/attackics/index.php/Technique/T0854)

**ISA 62443-3-3** 

**SR 7.6** : Network and security configuration settings  

**SR 7.7** : Least functionality

**ISA 62443-4-2** 

**EDR 2.13:** Use of physical diagnostic and test interfaces

**ISA 62443-4-1**

**SD-4:** Secure design best practices

**SI-1:** Security implementation review

**SVV-1:** Security requirements testing

> ### What’s next?

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about restricting third-party data interfaces.

> ### Do you require help with secure coding of your PLCs?

If you have any questions or require help in securely coding your PLCs, please contact SEQRED.

SEQRED specialises in providing bespoke OT and IoT cybersecurity solutions.  
Our services cover such areas as Critical Infrastructure Protection, Cloud Services Security or Audits, and Threat Intelligence. For a full list of our services visit our services page – [https://seqred.pl/en/services/](https://seqred.pl/en/services/)

###### **About this article**

You can download the full copy of the Top 20 Secure PLC Coding Practices by clicking [here.](https://www.plc-security.com/index.html#download)

The series of these articles is written under the following license:

Copyright (c) 2021 admeritia GmbH, Langenfeld/Rheinland, Germany

Permission is hereby granted, free of charge, to any person obtaining a copy of “Top 20 Secure PLC Coding Practices” and associated documentation files, to deal in the “Top 20 Secure PLC Coding Practices” without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the “Top 20 Secure PLC Coding Practices”, and to permit persons to whom the “Top 20 Secure PLC Coding Practices” is furnished to do so, subject to the following conditions:

THE “Top 20 Secure PLC Coding Practices” IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE “Top 20 Secure PLC Coding Practices” OR THE USE OR OTHER DEALINGS IN THE “Top 20 Secure PLC Coding Practices”.

