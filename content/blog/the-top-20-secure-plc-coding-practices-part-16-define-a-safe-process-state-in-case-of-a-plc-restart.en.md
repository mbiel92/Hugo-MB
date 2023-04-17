+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 17 – Summarise PLC cycle times and trend them on the HMI"
date="2021-01-05"
author="Eugene Wypior"
image="/blog/PLC-p16-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Define safe states for the process in case of PLC restarts (e.g., energize contacts, de-energize, keep the previous state)**

**Security Objective**

**Target Group**

Resilience

Product Supplier

Integration / Maintenance Service Provider

> ### Guidance

If something commands a PLC to restart in the middle of a working process, we should expect the program to pick up smoothly with minimal disruption to the process. Make sure that the process it controls is restart-safe. 

If it is not practical to configure the PLC to restart-safely, be sure that it alerts you to this fact and that it does not issue any new commands. Also, for that case, ensure that the Standard Operating Procedures (SOP) have very clear instructions for setting the manual controls so that the PLC will start up the process properly. 

Also, document all start-up, shut-down, steady-state control, and flying control system restart procedures. 

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

**Eliminates potential unexpected behavior:** 

The most basic attack vector for a PLC is to force it to crash and/or restart. For many PLCs, it is not that hard to do, because many PLCs cannot cope well with unexpected inputs or too much traffic. While there are several diagnostics for controller actions while it is running, how it handles startup up with a running process is usually not clear. This may be uncommon, but it is a basic attack vector if we take into account the malicious behavior of an attacker. 

**Reliability** 

**Avoid unexpected delays:** 

If after a PLC power on, the state machine initializes to a state with some conditions that don’t let the process to start, and the operator cannot normalize the system, a technician would need to enter the PLC program to force the conditions to go to the desired state to be able to start operation. This could cause delays and production losses. 

**Maintenance** 

> ### References

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA009 – Inhibit Response Function](https://collaborate.mitre.org/attackics/index.php/Inhibit_Response_Function)

**Technique:** [T0816 – Device Restart/Shutdown](https://collaborate.mitre.org/attackics/index.php/Technique/T0816)

**ISA 62443-3-3** 

**SR 3.6** : Deterministic Output

**ISA 62443-4-2** 

**CR 3.6** : Deterministic Output

**ISA 62443-4-1**

**SVV-1:** Security requirements testing

> ### What’s next?

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about summarizing PLC cycle times and trending them on the HMI.

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
