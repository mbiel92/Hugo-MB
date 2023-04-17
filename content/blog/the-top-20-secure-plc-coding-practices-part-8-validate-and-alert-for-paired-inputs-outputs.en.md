+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 8 – Validate and alert for paired inputs / outputs"
date="2021-11-03"
author="Eugene Wypior"
image="/blog/PLC-p8-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **If you have paired signals, ensure that both signals are not asserted together. Alarm the operator when input / output states occur that are physically not feasible. Consider making paired signals independent or adding delay timers when toggling outputs could be damaging to actuators.**{ .article-section }

**Security Objective**

**Target Group**

Integrity of PLC variables

Resilience

Product Supplier

Integration / Maintenance Service Provider

## Guidance{ .article-section }

Paired inputs or outputs are those that physically cannot happen at the same time; they are mutually exclusive. Though paired signals cannot be asserted at the same time unless there is a failure or malicious activity, PLC programmers often do not prevent that assertion from happening. 

Validation is easiest to directly do in the PLC, because the PLC is aware of the process state or context. Paired signals are easier to recognize and track if they have sequential addresses (e.g., input 1 and input 2). 

Another scenario where paired inputs or outputs could cause problems is when they are not asserted at the same time, but toggled quickly in a way that damages actuators. 

## Example{ .article-section }

**Examples of paired signals:** 

*   START and STOP 
    *   Independent start & stop: Configure start and stop as discrete outputs instead of having a single output that can be toggled on/off. By design, this does not allow simultaneous triggers. For an attacker, it is way more complicated to rapidly toggle on / off if two different outputs have to be set.
    *    Timer for restart: Also consider adding a timer for a re-start after a stop is issued to avoid rapid toggling off start/stop signals. 
*   FORWARD and REVERSE 
*   OPEN and CLOSE 

**Examples for toggling paired signals that could be damaging:** 

If the PLC / MCC accepts a discrete input, this provides an easy option for an attacker to cause physical damage on actuators. The well-known scenario for toggling outputs to do damage would be an MCC, but this practice applies to all scenarios where toggling outputs could do damage. A proof of concept where rapidly toggling outputs could cause real damage was the Aurora Generator Test in 2007 conducted by the Idaho National Laboratory, where toggling outputs out of sync caused circuit breaker damage. 

## Why? { .article-section }

**Beneficial for …?**

**Why?**

**Security**

 1. If PLC programs do not account for what is going to happen if both paired input signals are asserted at the same time, this is a good attack vector. 

2\. Both paired input signals being asserted is a warning that there is an operational error, programming error, or something malicious is going on. 

3\. This avoids an attack scenario where physical damage can be caused to actuators.

**Reliability** 

 1. Paired input signals can point to a sensor being broken or mis-wired or that there is a mechanical problem like a stuck switch. 

2\. Quickly toggling start and stop could also be done by mistake, so this also prevents damage that might be done inadvertently. 

**Maintenance** 

/

## References{ .article-section }

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA010 – Impair Process Control](https://collaborate.mitre.org/attackics/index.php/Impair_Process_Control)

**Technique:** [T0836 – Modify Parameter, T0806 – Brute Force I/O](https://collaborate.mitre.org/attackics/index.php/Technique/T0806)

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

**CWE-754**: Improper Check for Unusual or Exceptional Conditions

## What’s next?{ .article-section }

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about validating HMI input variables at the PLC level, not only at HMI.

## Do you require help with secure coding of your PLCs?{ .article-section }

If you have any questions or require help in securely coding your PLCs, please contact SEQRED.

SEQRED specialises in providing bespoke OT and IoT cybersecurity solutions.  
Our services cover such areas as Critical Infrastructure Protection, Cloud Services Security or Audits, and Threat Intelligence. For a full list of our services visit our services page – [https://seqred.pl/en/services/](https://seqred.pl/en/services/)