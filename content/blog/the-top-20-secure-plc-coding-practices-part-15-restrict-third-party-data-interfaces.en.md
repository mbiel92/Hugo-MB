+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 15 – Restrict third-party data interfaces"
date="2020-12-23"
author="Eugene Wypior"
image="/blog/PLC-p15-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Restrict the type of connections and available data for 3rd party interfaces. The connections and/or data interfaces should be well defined and restricted to only allow read/write capabilities for the required data transfer.** 

**Security Objective**

**Target Group**

Hardening

Integration / Maintenance Service Provider

> ### Guidance

In some cases, due to long cable runs or a large exchange of data, interfaced data connections present a better business case than hard-wired data exchange between two separate parties. 

The following guidelines should be considered and followed where practical when designing and implementing a third-party data exchange interface: 

*   Use a dedicated communications module, either directly connected to the 3rd party PLC or data exchange equipment or use dedicated network equipment physically segregated from each party’s core network.
*   The MAC address of connected devices is typically available in system variables for any ICS Ethernet-enabled device, making it possible to verify device identity with a multi-factor approach (IP address + MAC maker code = trusted device). This practice is certainly not foolproof, as MAC & IP addresses can be spoofed, but it serves to raise the bar in terms of communications between trusted ICS systems and devices.
*   When selecting a protocol for 3rd party interfaces, choose a protocol that minimizes the ability of the third party to write data to the owner’s system.
*   Choose a connection method and connection port which prevents the 3rd party from being able to configure the owner’s PLC or data exchange equipment.
*   The third-party should not be able to read or write to any data that has not been explicitly defined and made available.
*   Use a watchdog timer for monitoring communication so that commands are not sent to a PLC in fault mode.
*   Serial Connection: Use a dedicated communication module for each 3rd party interface with a restricted array of data. Ensure the owner’s side of the connection is the Initiator and that the third party is the Responder.
*   Ethernet/IP: Some PLCs allow for communication modules to function as a firewall and can perform Deep Packet Inspection (DPI), or restrict communication module interfaces to limit the data exchange to a predefined subset. If these features are available, and an Ethernet/IP protocol is in use, ensure the features are enabled and configured.
*   When operational or contractual requirements prevent the owner from accomplishing the previous items, consider using a separate “data concentrator” (aka proxy/DMZ) PLC in order to buffer the data and protect the owner from unwanted writes/programming from the 3rd party. Ensure the backplane of this PLC cannot be traversed from the 3rd party network. 

> ### Example

*   Pipeline or Lease Automatic Custody Transfer (LACT) units which transfer and meter hydrocarbons or water exchanged between an upstream producing or pipeline company and a midstream pipeline company with network or serial interfaced connections sharing metering, state, and permissive information between companies.
*   Regional potable water purveyor (importer) sharing turnout water flow rate being delivered to a local municipality’s water plant. 

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

1\. Limit the exposure to 3rd party networks and equipment. 

2\. Authenticate external devices to prevent spoofing. 

**Reliability** 

Limits the ability for intentional or unintentional modifications or access from 3rd party locations or equipment. 

**Maintenance** 

> ### References

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA010 – Impair Process Control](https://collaborate.mitre.org/attackics/index.php/Impair_Process_Control)

**Technique:** [T0836 – Modify Parameter](https://collaborate.mitre.org/attackics/index.php/Technique/T0836)

**ISA 62443-3-3** 

**SR 7.6** : Network and security configuration settings  

**SR 7.7** : Least functionality

**ISA 62443-4-2** 

**CR 7.6** : Network and security configuration settings  

**CR 7.7** : Least functionality

**ISA 62443-4-1**

**SD-4:** Secure design best practices

**SI-1:** Security implementation review

**SVV-1:** Security requirements testing

> ### What’s next?

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about defining a safe process state in case of a PLC restart.

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
