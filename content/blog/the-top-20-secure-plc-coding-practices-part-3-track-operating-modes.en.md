+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 3 – Track operating modes"
date="2021-10-06"
author="Eugene Wypior"
image="/blog/PLC-p3-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **Keep the PLC in RUN mode. If PLCs are not in RUN mode, there should be an alarm to the operators.** { .article-section }

**Security Objective**

**Target Group**

Integrity of PLC Logic

Integration / Maintenance Service Provider Asset Owner 

## Guidance{ .article-section }

If PLCs are not in RUN mode (e.g., PROGRAM mode), their code could be changed to track the RUN mode. Some PLCs have a checksum to alert for code changes, but if they do not, there’s at least an indirect indicator of a potential issue while tracking operating modes: 

*   If PLCs are not in RUN mode, there should be an alarm to the operators. If they are aware that someone is supposed to be working on that control system, they can acknowledge the alarm and move on. 
*   The HMI should be configured to re-alert the operator toward the end of the shift about the presence of the alarm. The goal should be to keep track of any staff or contractors in the plant doing work that might impact the process. 

Exception case: If the plant is in a testing or development phase, consider disabling this alarm but the plant should be isolated from higher levels of the network. 

## Example{ .article-section }

If the PLC does not have a hardware switch for changing operating modes, it is recommended to at least make use of software mechanisms that can restrict changing PLC code, e.g., password protection in engineering software for reading and writing PLC code. 

## Why? { .article-section }

**Beneficial for …?**

**Why?**

**Security**

The operating mode (run / edit / write; for Allen Bradley PLCs: RUN / PROGram / REMote) determines if PLC can be tampered with. If the key-switch is in REMote state, it is technically possible to make changes to the PLC program over the communication interfaces even if the PLC is running. 

**Reliability** 

/

**Maintenance** 

/ 

## References

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA009 – Inhibit Response Function](https://collaborate.mitre.org/attackics/index.php/Inhibit_Response_Function) 

**Technic:** [T0858 – Utilize/Change Operating Mode](https://collaborate.mitre.org/attackics/index.php/Technique/T0858)

**ISA/IEC 62443-4-1** 

**SI-1 :** Security implementation review

## What’s next?{ .article-section }

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about the importance of leaving the operational logic in the PLC wherever feasible. 

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
