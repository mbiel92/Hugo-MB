+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 11 – Assign designated register blocks by function (read/write/validate)"
date="2020-11-25"
author="Eugene Wypior"
image="/blog/PLC-p11-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Assign designated register blocks for specific functions in order to validate data, avoid buffer overflows and block unauthorized external writes to protect controller data.** 

**Security Objective**

**Target Group**

Integrity of PLC variables

Product Supplier

Integration / Maintenance Service Provider

> ### Guidance

Temporary memory, also known as scratch pad memory, is an easily exploitable area of memory if this practice is not followed. e.g., simply writing to a “Modbus” register that is out of bounds could lead to overwriting memory registers used for temporary calculations. 

Generally, register memory can be accessed by other devices across the PLC network for read and write operations. Some registers could be read by an HMI, and others could be written by a SCADA system, etc. Having specific register arrays for a certain application also makes it easier (in the controller or an external firewall is used) to configure Read-only access from another device/HMI. 

Examples of functions for which designated register blocks make sense are: 

*   reading 
*   writing (from HMI / Controller / other external device)
*   validating writes
*   calculations 

Ensuring external writes to allowable registers also helps in avoiding main memory reset errors either due to out-of-bound execution or malicious attempts. These designated register blocks can be used as buffers for I/O, timer, and counter writes by validating that the buffer is completely written (does not contain part old, part new data) and validating all the data in the buffer. 

**Background:** 

Main memory and register memory are used differently. Main memory is used for storing currently executing program logic whereas the register memory is used as a temporary memory by the currently executing logic. Though register memory is a temporary one, since it is being used by the executing logic it is bound to contain some important variables that would affect the main logic. 

> ### Example

**Examples for what could happen if this practice is not implemented:** (_Reference: G. P. H. Sandaruwan, P. S. Ranaweera, Vladimir A. Oleshchuk, PLC Security and Critical Infrastructure Protection):_ 

*   Siemens typically uses the scratchpad memory in the flag area from flag 200.0 to flag 255.7. If a bit is changed within this area there is a likelihood of a serious malfunction of the PLC based on the importance of that bit or byte. 
*   Assume that an attacker can gain access to one of the machines in the PLC network and infect that machine with a worm that is capable of writing arbitrary values to the register memory. Since the register memory values changed arbitrarily, it can change the pressure value.
*   Executing logic will set a new value based on the change and that may cause the system to exceed its safety margins and possibly driven to a failure.

**Examples for implementing this practice:** 

*   In a scenario where there is a safety zone (but the DCS can read), the firewall can log any “write’ attempts with a rule that these registers are READ ONLY in the safety zone. 
*   In another scenario, there could be some write-capable registers, and others are read-only, but having all the READ ONLY registers in a single array makes it easier to configure them in the controller (or a firewall). 

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

Makes it easier to protect the controller data by function (read/write/validate). 

Makes it easier for protocol sensitive firewalls to do their job: The rules get simpler because it is very clear what register blocks are allowed for the HMI to access. Makes it easier to manage the (simpler) rules in the firewall. 

Making unauthorized changes to internal temporary memory is an easily exploitable vulnerability (By-pass Logic Attack). 

When inputs and outputs to PLC routines are properly validated, any changes (by a malicious actor or by mistake) can be caught easily instead of staying in the logic sequence for long and throwing errors / causing issues later in execution. 

**Reliability** 

Makes reads and writes go faster because the number of transactions is reduced. 

Even authorized changes and programming mistakes can cause a malfunction if temporary memory is not protected. 

Network and communications errors on long messages can result in unintended errors if the validity of the data is not checked prior to processing. 

**Maintenance** 

Programming mistakes causing writing to temporary memory can make it hard to find errors, so the problem can be avoided by assigning specific registers for writes. 

> ### References

**Standard / framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA009 – Inhibit Response Function](https://collaborate.mitre.org/attackics/index.php/Inhibit_Response_Function), [TA010 – Impair Process Control](https://collaborate.mitre.org/attackics/index.php/Impair_Process_Control)

**Technique:** [T0835 – Manipulate I/O image,](https://collaborate.mitre.org/attackics/index.php/Technique/T0835)[T0836 – Modify Parameter](https://collaborate.mitre.org/attackics/index.php/Technique/T0836)

**ISA 62443-3-3** 

**SR 3.4 :** Software and Information integrity

**SR 3.5** : Input validation 

**SR 3.6** : Deterministic Output

**ISA 62443-4-2** 

**CR 3.4** : Software and Information integrity

**CR 3.5** : Input validation

**CR 3.6** : Deterministic Output

**ISA 62443-4-1** 

**SD-4:** Secure design best practices

**SI-1**: Security implementation review

**SI-2** : Secure coding standards 

**SVV-1** : Security requirements testing 

**MITRE CWE**

**CWE-787:** Out-of-bounds Write 

**CWE-653:** Insufficient Compartmentalization 

> ### What’s next?

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about instrument for plausibility checks.

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

