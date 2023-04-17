+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 20 – Monitor PLC memory usage and trend it on the HMI"
date="2021-02-02"
author="Eugene Wypior"
image="/blog/PLC-p20-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Measure and provide a baseline for memory usage for every controller deployed in the production environment and trend it on the HMI.**

**Security Objective**

**Target Group**

Monitoring

Integration / Maintenance Service Provider

Asset Owner

> ### Guidance

Since the increase of lines of code in the logic can also lead to increased memory consumption at runtime, it is recommended for PLC programmers to track any deviation from the baseline and dedicate an alarm class to this event.

> ### Example

In Rockwell Allen Bradley PLCs, a baseline can be established on a controller and memory usage can be tracked using the RSLogix 5000 Task Monitor Tool. Not only the main memory but also the I/O memory and Ladder/Tag memory can be tracked using trends. 

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

Increased memory usage can be an indicator of the PLC running altered code. 

**Reliability** 

Tracking memory usage for the running programs could be useful in avoiding total memory consumption and eventual fault state for the PLC controller. 

**Maintenance** 

Tracking memory usage could be used in tuning and finding the best scan time for the monitored controller but also in troubleshooting problems and issues related to faulty states. 

> ### References

**Standard/framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA002 – Execution](https://collaborate.mitre.org/attackics/index.php/Inhibit_Response_Function)

**Technique:** [T0873 – Project File Infection](https://collaborate.mitre.org/attackics/index.php/Technique/T0816)

**ISA 62443-3-3** 

**SR 3.4**: Software and information integrity 

**ISA 62443-4-2** 

**EDR 3.2**: Protection from malicious code 

> ### What’s next?

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about trapping false negatives and false positives for critical alerts.

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

