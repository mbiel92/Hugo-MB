+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 2 – Modularise PLC code"
date="2021-09-23"
author="Eugene Wypior"
image="/blog/PLC-p2-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

> Split PLC code into modules, using different function blocks (sub-routines). Test modules independently.
> --------------------------------------------------------------------------------------------------------

**Security Objective**

**Target Group**

Integrity of PLC Logic

Product Supplier

## Guidance{ .article-section }

Do not program the complete PLC logic in one place e.g., in the main Organisation Block or main routine. Instead, split it into different function blocks (sub-routines) and monitor their execution time and their size in Kb. 

Create separate segments for logic that functions independently. This helps in input validation, access control management, integrity verification etc. 

Modularised code also facilitates testing and keeping track of the integrity of code modules. If the code inside the module has been meticulously tested, any modifications to these modules can be verified against the hash of the original code, e.g., by saving a hash of each of these modules (when that’s an option in the PLC). This way, modules can be validated during the FAT/SAT or if the integrity of the code is in question after an incident.  

## Example{ .article-section }

Gas Turbine logic is segregated into “startup”, “Inlet Guide Vanes Control”, “Bleed Valve Control” etc. so that you can apply standard logic systematically. This also helps in troubleshooting quickly if there were to be a security incident. 

Custom function blocks that are tested rigorously can be re-used without alteration (and alerted if change attempts are made) and locked against abuse/misuse with a password/digital signature. 

## Why?{ .article-section }

**Beneficial for …?**

**Why?**

**Security**

Facilitates the detection of newly added portions of code that could be malicious. Helps in logic standardisation, consistency, and locking against unauthorised modifications. 

**Reliability** 

Helps control the program flow sequence and avoid loops, which could cause the logic to not react properly or crash. 

**Maintenance** 

Modular code is not only easier to debug (modules can be tested independently) but also easier to maintain and update. 

Also, the modules may be used for additional PLCs, thus allowing for common code to be used and identified in separate PLCs. This can aid maintenance personnel with quickly recognising common modules during troubleshooting. 

## References{ .article-section }

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA002 – Execution](https://collaborate.mitre.org/attackics/index.php/Execution)  
**Technique:** [T0844 – Program Organization Units](https://collaborate.mitre.org/attackics/index.php/Technique/T0844) 

**ISA 62443-3-3** 

**SR 3.4**: Software and information integrity 

**ISA 62443-4-2** 

**CR 3.4**: Software and information integrity 

**ISA 62443-4-1** 

**SI-2: Secure coding standards** 

**MITRE CWE** 

**CWE-1120:** Excessive Code Complexity 

**CWE-653:** Insufficient Compartmentalisation 

## What’s next?{ .article-section }

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about tracking operating modes.

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

