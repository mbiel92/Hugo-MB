+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 5 – Use PLC flags as integrity checks"
date="2021-10-13"
author="Eugene Wypior"
image="/blog/PLC-p5-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **Put counters on PLC error flags to capture any math problems** { .article-section }

**Security Objective**

**Target Group**

Integrity of PLC Logic

Product Supplier  
Integration /  
Maintenance Service Provider

## Guidance{ .article-section }

If the PLC code was working fine but suddenly does a divide by zero, investigate. If something is communicating peer to peer from another PLC and the function/logic does a divide by zero when it wasn’t expected, investigate. 

Most programmers will ignore the issue as a math error or worse yet, might presume their code is perfect and let the PLC enter a hard fault state. During code development, engineers need to test and validate their code modules (snippets or routines) by inputting data outside of expected bounds. This may be termed Unit Level Test. 

Assign different, locked memory segments for firmware, logic, and protocol stack. Test the protocol stack for abuse cases. Abuse cases could be peculiar flag conditions in a packet header. 

## Example{ .article-section }

PLC faults caused by out-of-bounds data are very common. This happens, for example, when an input value causes array indices go out of bounds, or timers with negative presets, or divide by zero exceptions. 

Typical flags of interest are 

*   divide by zero 
*   counter overflow
*   negative counter or timer preset
*   I/O scan overrun

## Why? { .article-section }

**Beneficial for …?**

**Why?**

**Security**

Attacks on PLCs could include changing its logic, activating a new program, testing new code, loading a new process recipe, inserting auxiliary logic to send messages, or activating some feature. Since most PLCs do not provide cryptographic integrity checks, flags can be a good indicator if one of the above logic changes happens. 

**Reliability** 

Flags taken seriously can avoid the PLC running with programming or I/O errors. Also, if an error occurs, the source of the failure is more obvious. 

**Maintenance** 

/

## References{ .article-section }

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA010 – Impair Process Control](https://collaborate.mitre.org/attackics/index.php/Impair_Process_Control) 

**Technique:** [T0836 – Modify Parameter](https://collaborate.mitre.org/attackics/index.php/Technique/T0836) 

**ISA 62443-3-3** 

**SR 3.5** : Input Validation

**SR 3.6** : Deterministic Output 

**ISA 62443-4-2** 

**CR 3.5**: Input Validation 

**CR 3.6**: Deterministic Output 

**ISA 62443-4-1** 

**SI-2:** Secure coding standards

**SVV-1**: Security requirements testing 

**MITRE CWE** 

**CWE-128:** Wrap-around 

**CWE-190:** Integer Overflow 

**CWE-369:** Divide by Zero 

**CWE-754:** Improper Check for Unusual or Exceptional Conditions 

## What’s next?{ .article-section }

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about using cryptographic and/or checksum integrity checks for PLC code. 

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