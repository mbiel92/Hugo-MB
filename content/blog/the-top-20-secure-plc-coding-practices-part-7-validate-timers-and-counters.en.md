+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 7 – Validate timers and counters"
date="2021-10-28"
author="Eugene Wypior"
image="/blog/PLC-p7-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **If timers and counters values are written to the PLC program, they should be validated by the PLC for reasonableness and verify backward counts below zero**{ .article-section }

**Security Objective**

**Target Group**

Integrity of PLC variables

Integration / Maintenance Service Provider  
Asset Owner

## Guidance{ .article-section }

Timers and counters can technically be preset to any value. Therefore, the valid range to preset a timer or counter needs to/should be restricted to meet the operational requirements. 

If remote devices such as an HMI write timer or counter values to a program: 

*   do not let the HMI write to the timer or counter directly but go through a validation logic 
*   validate presets and timeout values in the PLC 

Validation of timer and counter inputs is easy to be done directly in the PLC (without the need for any network device capable of Deep Packet Inspection), since the PLC “knows” what the process state or context is. It can validate “what’ it gets and “when” it gets the commands or setpoints. 

## Example{ .article-section }

During PLC startup, timers and counters are usually preset to certain values. 

If there is a timer that triggers alarms at 1.3 seconds, but that timer is preset maliciously to 5 minutes, it might not trigger the alarm. 

If there is a counter that causes a process to stop when it reaches 10,000 but that is set to 11,000 from the beginning, the process might not stop. 

## Why? { .article-section }

**Beneficial for …?**

**Why?**

**Security**

If I/O, timers, or presets are written directly to I/O, not being validated by the PLC, the PLC validation layer is evaded and the HMI (or other network devices) are assigned an unwarranted level of trust. 

**Reliability** 

The PLC can also validate when an operator accidentally presets bad timer or counter values. 

**Maintenance** 

Having valid ranges for timers and counters documented and automatically validated may help when updating logic. 

## References{ .article-section }

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA010 – Impair Process Control](https://collaborate.mitre.org/attackics/index.php/Impair_Process_Control)

**Technique:** [T0836 – Modify Parameter](https://collaborate.mitre.org/attackics/index.php/Technique/T0836)

**ISA 62443-3-3** 

**SR 3.5** : Input validation 

**ISA 62443-4-2** 

**CR 3.5** : Input validation

**ISA 62443-4-1** 

**SI-2 :** Secure coding standards

**SVV-1:** Security requirements testing 

## Practical example{ .article-section }

 Arnaud SOULLIÉ gives a practical example for the reason to validate timers and counters in a short video (see the link in sources under the article).

## What’s next?{ .article-section }

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about validating and alerting for paired inputs / outputs.

## Do you require help with secure coding of your PLCs?{ .article-section }

If you have any questions or require help in securely coding your PLCs, please contact SEQRED.

SEQRED specialises in providing bespoke OT and IoT cybersecurity solutions.  
Our services cover such areas as Critical Infrastructure Protection, Cloud Services Security or Audits, and Threat Intelligence. For a full list of our services visit our services page – [https://seqred.pl/en/services/](https://seqred.pl/en/services/)

###### **About this article**

You can download the full copy of the Top 20 Secure PLC Coding Practices by clicking [here.](https://www.plc-security.com/index.html#download)  

To watch Arnaud SOULLIÉ’s video on a practical example for implementing this coding practice click [here.](https://www.linkedin.com/posts/arnaudsoullie_i-created-a-short-introduction-video-to-the-ugcPost-6843118214365421568-DXAG)

The series of these articles is written under the following license:

Copyright (c) 2021 admeritia GmbH, Langenfeld/Rheinland, Germany

Permission is hereby granted, free of charge, to any person obtaining a copy of “Top 20 Secure PLC Coding Practices” and associated documentation files, to deal in the “Top 20 Secure PLC Coding Practices” without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the “Top 20 Secure PLC Coding Practices”, and to permit persons to whom the “Top 20 Secure PLC Coding Practices” is furnished to do so, subject to the following conditions:

THE “Top 20 Secure PLC Coding Practices” IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE “Top 20 Secure PLC Coding Practices” OR THE USE OR OTHER DEALINGS IN THE “Top 20 Secure PLC Coding Practices”.