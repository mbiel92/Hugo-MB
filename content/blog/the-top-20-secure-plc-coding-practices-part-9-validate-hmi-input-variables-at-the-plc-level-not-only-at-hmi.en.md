+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 9 – Validate HMI input variables at the PLC level, not only at HMI"
date="2021-11-10"
author="Eugene Wypior"
image="/blog/PLC-p9-3.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **HMI access to PLC variables can (and should) be restricted to a valid operational value range at the HMI, but further cross-checks in the PLC should be added to prevent, or alert on, values outside of the acceptable ranges which are programmed into the HMI.** { .article-section }

**Security Objective**

**Target Group**

Integrity of PLC variables

Product Supplier

Integration / Maintenance Service Provider

## Guidance{ .article-section }

Input validation could include out-of-bounds checks for valid operational values as well as valid values in terms of data types that are relative to the process. 

If a PLC variable receives a value that is out-of-bounds, provide PLC logic to either 

*   input a **default value** to that variable which does not negatively affect the process, and can be used as a flag for alerts, or 
*   input the **last correct value** to that value and log the event for further analysis. 

## Example{ .article-section }

**Example 1**

An operation requires a user to input a value on an HMI for valve pressure. Valid ranges for this operation are 0-100, and the user’s input is passed from the user input function on the HMI to the V1 variable in the PLC. In this case, 

1\. HMI input to variable V1 has a restricted range of 0-100 (dec.) programmed into the HMI. 

2\. The PLC has a cross-check logic that states: 

IF V1 < 0 OR IF V1 > 100, SET V1 = 0. 

This provides a positive response of a presumably safe value to an invalid input to that variable. 

**Example 2**

An operation requires user input for measurement thresholds to a variable that should always be within an INT2 data range. The user input is passed from the HMI into the V2 variable in the PLC, which is a 16-bit data register. 

1\. HMI input to variable V2 has a restricted range of -32768 to 32767 (dec.) programmed into the HMI. 

2\. The PLC has data-type cross-check logic that monitors the overflow variable (V3), which exists just after V2 in the PLC’s memory structure: 

IF V2 = -32768 OR IF V2 = 32767 AND V3 != 0, 

SET V2 = 0 AND SET V3 = 0 AND SET DataTypeOverflowAlarm = TRUE. 

**Example 3**

Scale PV (Process Value), SP (Set Point) and CV (Control Variable) for PID (Proportional, Integral, Derivative controller) to consistent or raw units to eliminate scaling errors causing control problem. Incorrect scaling might lead to inadvertent abuse cases. 

## Why? { .article-section }

**Beneficial for …?**

**Why?**

**Security**

**1.**

While HMIs typically provide some sort of input validation, a malicious actor can craft or replay modified packets to send arbitrary values to the variables in the PLC which are open to outside influence (open to values passed from an HMI, for example). 

**2.**

PLC protocols are typically marketed as “open” protocols and published to the general public, so creating malware that utilizes “open” protocol information can be trivial to develop. PLC variable mapping can typically occur through traffic analysis during the reconnaissance phases of an attack, thus providing the intruder with the necessary information to craft malicious traffic to the target and thereby manipulate a process with unauthorized tools. Cross-checking values passed into the PLC before implementing that data into the process ensures valid data ranges and mitigates an invalid value in those memory locations by forcibly setting safe ranges when a value is detected as out-of-bounds during the course of the PLC scan. 

**Reliability** 

/

**Maintenance** 

/

## References{ .article-section }

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA010 – Impair Process Control](https://collaborate.mitre.org/attackics/index.php/Impair_Process_Control)

**Technique:** [T0836 – Modify Parameter](https://collaborate.mitre.org/attackics/index.php/Technique/T0806)

**ISA 62443-3-3** 

**SR 3.5** : Input validation 

**SR 3.6** : Deterministic Output

**ISA 62443-4-2** 

**CR 3.5** : Input validation

**CR 3.6** : Deterministic Output

**ISA 62443-4-1** 

**SI-2 :** Secure coding standards

**SVV-1:** Security requirements testing 

**MITRE CWE**

**1320:** Improper Protection for Out of Bounds Signal Level Alerts 

## Practical example{ .article-section }

Arnaud SOULLIÉ gives a practical example for the reason to validate HMI input variables at the PLC level not only at HMI in a short video (see the link in sources under the article).

## What’s next?{ .article-section }

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about validating indirections.

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