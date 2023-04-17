+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 17 – Summarise PLC cycle times and trend them on the HMI"
date="2021-01-12"
author="Eugene Wypior"
image="/blog/PLC-p17-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Summarize PLC cycle time every 2-3 seconds and report to HMI for visualization on a graph**

**Security Objective**

**Target Group**

Monitoring

Integration / Maintenance Service Provider

> ### Guidance

Cycle times are usually system variables in a PLC and can be used for summarizing in PLC code. Summarization should be done to calculate average, peak, and minimum cycle times. The HMI should trend these values and alert if there are significant changes. 

The cycle time is the time it takes to compute each iteration of logic for the PLC. The iterations are the combination of Ladder Diagrams (LD), Function Block Diagrams (FBD), Instruction List (IL), and Structured Text (ST). These logic components may be joined together with the Sequential Function Charts (SFC). 

Cycle times should be constant on a PLC unless there are changes to e.g. 

*   network environment
*   PLC logic
*   process 

Therefore, unusual cycle time changes can be an indicator that PLC logic changed and thus provide valuable information for integrity checks. 

Visualizing values over time using a graph provides an intuitive way to draw attention to anomalies that would be harder to notice by just having absolute values. 

> ### Example

Many PLCs have a “maximum cycle time” monitoring at the hardware level. If the cycle time exceeds the maximum value, the hardware sets the CPU to STOP (5). Of course, attackers are aware of this and will keep a possible attack code as lean as possible to minimize the impact on the overall cycle time. In an additional software cycle time monitoring program, a reference cycle time tref is defined as base cycle time. As small fluctuations are natural, an acceptable threshold needs to be defined (1,3) The cycle monitoring is triggered, if the threshold is exceeded (2,4). 

![](/blog/Graph1-1-1024x408.png)

Any deviance from the reference time can be stored in a log file like this: 

![](/blog/Table2.png)

If cycle times are trended to the HMI, heavy CPU loads are visible at a glance. The following example diagram shows a PLC-Program with periodically executed malicious code. (1,3) show acceptable cycle time fluctuations (“noise”) during normal operation, attack code is executed on (2,4) which increase the cycle time. 

![](/blog/Graph2-2.png)

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

Attacks to PLCs include changing their logic, activating a new program, testing new code, loading a new process recipe, inserting auxiliary logic to send messages, or activating some feature. For most PLCs, traditional cryptographic integrity checks are not feasible. However, it’s good to alert if any of the above logic changes happen. Since cycle times are rather constant under normal circumstances, changes in cycle times are a good indicator that the logic in one of the above logic components has changed. 

**Reliability** 

See security, but for non-malicious causes. 

**Maintenance** 

/

> ### References

**Standard/framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA002 – Execution](https://collaborate.mitre.org/attackics/index.php/Execution)

**Technique:** [T0873 – Project File Infection](https://collaborate.mitre.org/attackics/index.php/Technique/T0873)

**ISA 62443-3-3** 

**SR 3.4**: Software and information integrity

**ISA 62443-4-2** 

**EDR 3.2**: Protection from malicious code

**MITRE CWE**

**CWE-754:** Improper Check for Unusual or Exceptional Conditions

> ### What’s next?

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about logging PLC uptime and trending it on the HMI.

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
