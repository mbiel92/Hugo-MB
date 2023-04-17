+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 6 – Use cryptographic and / or checksum integrity checks for PLC code"
date="2021-10-21"
author="Eugene Wypior"
image="/blog/PLC-p6-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

> ### **Use cryptographic hashes, or checksums if cryptographic hashes are unavailable, to check PLC code integrity and raise an alarm when they change** 

**Security Objective**

**Target Group**

Integrity of PLC Logic

Product Supplier  
Integration / Maintenance Service Provider  
Asset Owner

## Guidance{ .article-section }

**A) Checksums** Where (cryptographic) hashes are not feasible, checksums may be an option. Some PLCs generate a unique Checksum when code is downloaded into the PLC Hardware. The Checksum should be documented by the manufacturer/integrator after SAT and be part of warranty / service conditions. 

If the checksum feature is not natively available in the controller, this can also be generated in the EWS/HMI and probed e.g., once a day to compare with the hash of the original code in the PLC to verify that they are matching. While this won’t provide real-time alerts, it’s good enough to track if anyone is attempting changes to the PLC code. 

The checksum value can also be moved into a PLC register and configured for an alarm when it changes, the value can be sent to historians, etc. 

**B) Hashes** PLC CPUs generally do not have the processing capacity to generate or check hashes while running. Attempting a hash might actually cause the PLC to crash. But the PLC’s engineering software might be able to calculate hashes from the PLC code and save them either in the PLC or somewhere else in the control system. 

## Example{ .article-section }

PLC vendors that are known to have checksum features: 

\* Siemens (see example) 

\* Rockwell 

Also, external software can be used for generating checksums: 

\* Version dog 

\* Asset Guardian 

\* PAS 

**Siemens implementation example** 

Example for creating checksums in Siemens S7-1500 PLC: 

GetChecksum-Function Block reads actual checksum and with a lightweight script, the “SAT-Checksum” can be stored as reference. A deviance from the Reference-Checksum can be stored with the Datalog-Function.

![](/blog/Top_20_Secure_PLC_Coding_Practices5-1024x216.png)

**Rockwell Implementation Example:** 

This is a partial example of how an organization can develop a level of PLC program change detection capability within their ICS environment. This example is specifically for a Rockwell Automation ControlLogix PLC and is not complete; however, it illustrates how to retrieve the PLC processor state into a register within the PLC. Once in a register in the PLC, the organization can use it to create a configuration change alarm for display on an HMI, transmit the raw state information to an HMI for trending and monitoring, or send it to a Historian for long term capture. 

This practice provides an opportunity, using existing tools and capabilities, to gain situational awareness of when critical cyber assets change. It is up to the organization to complete the use of this example in a method that works best in their environment. 

1\. From the Controller Properties Dialog Box, select the configure button on “Change to Detect”

![Top_20_Secure_PLC_Coding_Practices_V1.0](/blog/Top_20_Secure_PLC_Coding_Practices_V1.0-1024x701.jpg)

2\. Within the selection window, choose all items to be monitored 

![](/blog/Top_20_Secure_PLC_Coding_Practices.png)

3\. Create a Tag to receive the processor state information. This tag can be of type “LINT” or a 2-word array of type “DINT” 

![](/blog/Top_20_Secure_PLC_Coding_Practices2-1024x128.png)

4\. Use the Get System Values (GSV) instruction to get the processor state information from memory and move it into a Tag that can be used in logic or read at the HMI 

![](/blog/Top_20_Secure_PLC_Coding_Practices3-1024x263.png)

![](/blog/Top_20_Secure_PLC_Coding_Practices4.png)

## Why? { .article-section }

**Beneficial for …?**

**Why?**

**Security**

Knowing if PLC code was tampered with is essential for both noticing a compromise and verifying if a PLC is safe to operate after a potential compromise. 

**Reliability** 

Hashes or checksums can also be a means to verify if the PLC is (still) running code approved by the integrator/manufacturer. 

**Maintenance** 

/

## References{ .article-section }

**Standard / framework**

**Mapping**

 

**MITRE ATT&CK for ICS** 

**Tactic:** [TA002 – Execution](https://collaborate.mitre.org/attackics/index.php/Execution)**,** [TA010 – Impair Process Control](https://collaborate.mitre.org/attackics/index.php/Impair_Process_Control)

**Technique:** [T0873 – Project File Infection](https://collaborate.mitre.org/attackics/index.php/Technique/T0873)**,** [T0833 – Modify Control Logic](https://collaborate.mitre.org/attackics/index.php/Technique/T0833) 

**ISA 62443-3-3** 

**SR 3.4** : Software and information integrity 

 

**ISA 62443-4-2** 

**CR 3.4** : Software and information integrity 

**EDR 3.12** : Provisioning product supplier roots of trust 

**ISA 62443-4-1** 

**SI-1 :** Security implementation review

**SVV-1:** Security requirements testing 

 

**MITRE CWE** 

**CWE-345:** Insufficient Verification of Data Authenticity 

*   **(child) CWE-353:** Missing Support for Integrity Check 
*    **(child) CWE-354:** Improper Validation of Integrity Check Value 

> ### What’s next?

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about using cryptographic and/or checksum integrity checks for PLC code. 

> ### Do you require help with secure coding of your PLCs?

If you have any questions or require help in securely coding your PLCs, please contact SEQRED.

SEQRED specialises in providing bespoke OT and IoT cybersecurity solutions.  
Our services cover such areas as Critical Infrastructure Protection, Cloud Services Security or Audits, and Threat Intelligence. For a full list of our services visit our services page – [https://seqred.pl/en/services/](https://seqred.pl/en/services/)