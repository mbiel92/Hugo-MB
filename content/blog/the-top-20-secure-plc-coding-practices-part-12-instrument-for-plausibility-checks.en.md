+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 12 – Instrument for plausibility checks"
date="2020-12-01"
author="Eugene Wypior"
image="/blog/PLC-p12-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Instrument the process in a way that allows for plausibility checks by cross-checking different measurements.** 

**Security Objective**

**Target Group**

Integrity oI/O values

Product Supplier

Integration / Maintenance Service Provider

> ### Guidance

There are different ways of using physical plausibility for validating measurements: 

**a) Compare integrated and time-independent measurements**

Plausibility checks can be done by integrating or differentiating time-dependent values over a period of time and comparing them to time-independent measurements. 

**b) Compare different measurement sources**

Also, measuring the same phenomenon in different ways can be a good plausibility check. Different measurement sources do not necessarily have to be different physical sensors, but can also mean using alternative communication channels (see examples). 

> ### Example

**a) Compare integrated and time-independent measurements** 

*   Metered pump and tank level gauge: volumetric change should equal integrated flow. 
*   A burner in a boiler: added caloric heat should equal temperature rise. 

**b) Compare different measurement sources** 

*   Using airspeed, artificial horizon, vertical speed, and altitude in the airplane to measure the phenomenon of the climbing / descending airplane. 
*   Comparing process parameter values from independent data loggers (tied into 4-20mA loops or relay contacts and transmitted via independent communication channels) to SCADA system data (coming in the “normal” way through PLC and HMI) and alerting on deviations and significantly off-specified values. 

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

Facilitates monitoring for manipulated values (assuming not all sensors are manipulated at once). 

**Reliability** 

Prevents acceptance or identifies (for future action) corrupted / wrong measurements as inputs. 

**Maintenance** 

Rules out the possible physical causes for failures more quickly. 

> ### References

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA010 – Impair Process Control](https://collaborate.mitre.org/attackics/index.php/Impair_Process_Control)

**Technique:** [T0806 – Brute Force I/O](https://collaborate.mitre.org/attackics/index.php/Technique/T0806)

**ISA 62443-3-3** 

**SR 3.5** : Input validation 

**SR 3.6** : Deterministic Output

**ISA 62443-4-2** 

**CR 3.5** : Input validation

**CR 3.6** : Deterministic Output

**MITRE CWE**

**CWE-754:** Improper Check for Unusual or Exceptional Conditions

> ### What’s next?

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about validating inputs based on physical plausibility.

> ### Do you require help with secure coding of your PLCs?

If you have any questions or require help in securely coding your PLCs, please contact SEQRED.

SEQRED specialises in providing bespoke OT and IoT cybersecurity solutions.  
Our services cover such areas as Critical Infrastructure Protection, Cloud Services Security or Audits, and Threat Intelligence. For a full list of our services visit our services page – [https://seqred.pl/en/services/](https://seqred.pl/en/services/)

###### **About this article**

You can download the full copy of the Top 20 Secure PLC Coding Practices by clicking [here.](https://www.plc-security.com/index.html#download)[](https://www.linkedin.com/posts/arnaudsoullie_i-created-a-short-introduction-video-to-the-ugcPost-6843118214365421568-DXAG)

The series of these articles is written under the following license:

Copyright (c) 2021 admeritia GmbH, Langenfeld/Rheinland, Germany

Permission is hereby granted, free of charge, to any person obtaining a copy of “Top 20 Secure PLC Coding Practices” and associated documentation files, to deal in the “Top 20 Secure PLC Coding Practices” without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the “Top 20 Secure PLC Coding Practices”, and to permit persons to whom the “Top 20 Secure PLC Coding Practices” is furnished to do so, subject to the following conditions:

THE “Top 20 Secure PLC Coding Practices” IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE “Top 20 Secure PLC Coding Practices” OR THE USE OR OTHER DEALINGS IN THE “Top 20 Secure PLC Coding Practices”.
