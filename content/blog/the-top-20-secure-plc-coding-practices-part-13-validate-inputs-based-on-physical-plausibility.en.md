+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 13 – Validate inputs based on physical plausibility"
date="2020-12-08"
author="Eugene Wypior"
image="/blog/PLC-p13-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Ensure operators can only input what’s practical or physically feasible in the process. Set a timer for an operation to the duration it should physically take. Consider alerting when there are deviations. Also alert when there is unexpected inactivity.** 

**Security Objective**

**Target Group**

Integrity oI/O values

Integration / Maintenance Service Provider

> ### Guidance

**a) Monitor expected physical durations**

If the operation takes longer than expected to go from one extreme to the other, that is worthy of an alarm. Alternatively, if it does it too quickly, that is worthy of an alarm too. 

A simple solution could be a step-timeout alert. This would be useful for sequence/step-controlled tasks. For example, the step “move object from A to B” takes 5 sec from start of the step until the transition condition (sensor: object arrived at B) is met. If the condition is met significantly too early or too late, the step-timeout is alert triggered. 

**b) Monitor expected physical repeating activity**

Physical plausibility checking can also mean alert for physically implausible inactivity: If there is an expectation of a regular, repeating cycle of events (e.g., batches, diurnal patterns), an inactivity timer would alert if something which is expected to change (discrete or analog value) remains static for far too long. 

> ### Example

**a) Monitor expected physical durations** 

*   The gates on a dam takes a certain time to go from fully closed to fully open
*   In a wastewater utility, a wet well takes a certain time to fill

**b) Monitor expected physical repeating activity** 

*   Manufacturing process or pipeline batching should regularly cycle between control ranges or operating modes.
*   Municipal wastewater treatment plants typically have a diurnal cycle of activity / pattern of influent flow rates. 

**c) Limit operator entry for set points to what’s practical/physically possible.** 

*   e.g., Oldsmar Florida case allowed for operator input that’s a) thousands of times more than what was typically needed b) that’s physically not possible. Try to configure the operational limits in the PLC code wherever possible instead of using HMI scripts. 

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

**1\.** Deviations can indicate an actuator was already in the middle of a travel state or that someone is trying to fake the I/O, e.g., by doing a replay attack. 

**2\.** Inactivity alerts facilitate monitoring for frozen or forced constant values which could be the result of system or device tampering. 

**Reliability** 

**1\.** Deviations give you an early alert for broken equipment due to electrical or mechanical failures. 

**2\.** Inactivity alerts help flag measurements or system control loops which may be failing (thus static) due to physical device fault or an issue with the logic control algorithm or failed/improper operator input. 

**Maintenance** 

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

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about disabling unneeded / unused communication ports and protocols.

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
