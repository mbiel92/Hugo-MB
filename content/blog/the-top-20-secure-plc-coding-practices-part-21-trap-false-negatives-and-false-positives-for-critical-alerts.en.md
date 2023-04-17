+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 21 – Trap false negatives and false positives for critical alerts"
date="2021-02-09"
author="Eugene Wypior"
image="/blog/PLC-p21-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Identify critical alerts and program a trap for those alerts. Set the trap to monitor the trigger conditions and the alert state for any deviation.**

**Security Objective**

**Target Group**

Monitoring

Integration / Maintenance Service Provider

> ### Guidance

In most cases, alert-states are boolean (True, False) and triggered by certain conditions as displayed below. E.g., the trigger bit for the alert ‘overpressure’ becomes TRUE, if Condition 1 ‘pressure switch 1’, Condition 2 ‘pressure sensor value over critical threshold’, through n., are TRUE. 

 ![](/blog/Top_20_21_pic1-300x101.jpg)

To masquerade an attack, an adversary could suppress the alert trigger bit and cause a false negative. 

A trap for false negatives monitors the conditions for the trigger bit and the negated trigger bit itself. With this simple setup, a false negative is detected. See the following picture: 

![](/blog/Top_20_21_pic2-300x95.jpg)

In other cases, an adversary could deliberately cause false positives, to wear down the process operator’s attention. 

In the same manner of the false-negative trap, false positives can also be detected by monitoring the alert trigger bit and if the trigger conditions are met. If the conditions are NOT met, but the trigger bit is active, a false positive is detected: See the following picture: 

![](/blog/Top_20_21_pic3-300x102.jpg)

### Example

**Example 1:** Siemens offers in their Siemens S7-1200/1500 Products a Webserver with a wide range of functions, for example, display of the PLC-State, cycle time, or scope records. It also has the option to view and modify data tables and variables. The access rights to the Webserver can be modified in the PLC-Hardware Settings. In case of misconfigured access rights, an adversary could gain access to the PLC Variables and Datablocks. To create a false positive, the adversary selects an alert trigger bit and alters the state. 

**Example 2:** In the Triton/Trisys/HatMan attack, rogue code suppressed alert states. 

**Example 3:** A bus-injection attack could send a false positive alert to a high-level SCADA client. 

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

Mitigates false negative or false positives of critical alert messages caused by an adversary obfuscating their attack (i.e., rogue code, bus injection, tampering with accessible PLC state tables on unsecured web servers). 

**Reliability** 

/

**Maintenance**

/

> ### References

**Standard/framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA009 – Inhibit Response Function](https://collaborate.mitre.org/attackics/index.php/Inhibit_Response_Function)

**Technique:** [T0878 – Alarm Suppresion](https://collaborate.mitre.org/attackics/index.php/Technique/T0878)

**ISA 62443-3-3** 

**SR 3.5**: Input Validation

**ISA 62443-4-2**

**CR 3.5**: Input Validation

**ISA 62443-4-1**

**CI-1:** Security Implementation Review

**MITRE CWE**

**CWE-754:** Improper Check for Unusual or Exceptional Conditions

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