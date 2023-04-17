+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 10 – Validate indirections"
date="2020-11-17"
author="Eugene Wypior"
image="/blog/PLC-p10-3.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **Validate indirections by poisoning array ends to catch fence-post errors.** { .article-section }

**Security Objective**

**Target Group**

Integrity of PLC variables

Product Supplier

Integration / Maintenance Service Provider

## Guidance{ .article-section }

Indirection is the use of the value of a register in another register. There are many reasons to use indirections. 

Examples for necessary indirections are: 

*   Variable frequency drives (VFDs) that trigger different actions for different frequencies using lookup tables. 
*    To decide which pump to start running first based on their current run times 

PLCs do not typically have an “end of an array” flag so it’s a good idea to create it in software; the goal is to avoid unusual/unplanned PLC operations. 

## Example{ .article-section }

**Instruction List (IL) Programming**

The approach can be turned into a few function blocks and possibly even reused for other applications. 

**1\. Create array mask** 

Check if the array is binary-sized. If it is not binary-sized, create a mask to the next size up on a binary scale. e.g., if you have a need for 5 registers (not binary-sized): 

\[21 31 41 51 61\] 

define an array of 8: 

\[x x 21 31 41 51 61 x\] 

Next, take the index value to pick up for the indirection – in this example, it is 3. 

Caveat: Index begins at 0! 

\[21 31 41 **51** 61\]

\_\_\_\_\_\_\_\_\_\_\_^ 

Index: 3 

add an offset to it making up for the poisoned end. The offset can be 1 or higher, in this case, it is 2: 

\[x x 21 31 41 **51** 61 x\]

\_\_\_\_\_\_\_\_\_\_\_\_\_\_**^** 

Index including offset: 3 + 2 = 5 

and then AND the index including offset with a mask that equals the array size. In this example the array size is 8, thus index 7, so the mask would be 0x07. The mask makes sure the maximum index you can get is 7, for example: 

6 AND 0x07 would give back 6.  
7 AND 0x07 would give back 7  
8 AND 0x07 would give back 0.  
9 AND 0x07 would give back 1. 

This ensures you always address a value in the array. 

**2\. Insert poisoned ends** 

Poisoning ends is optional. You would be able to detect manipulated indirections without the poisoning, but poisoning helps to catch fence-post errors because you get back a value that does not make sense. 

The point is that at index 0 of the array, there should be a value that is invalid – such as -1 or 65535. This is “the poisoned end”. Likewise, at the last elements of the array you do the same: 

So, for the array above, the poisoned version could look like this: 

\[-1 -1 21 31 41 51 61 -1\] 

**3\. Record value of indirection address without mask** 

Then record the value of the indirect address without AND mask and offset: In this example, you’d record 51 for index 3. 

\[21 31 41 **51** 61\]

\_\_\_\_\_\_\_\_\_\_\_**^**

\_\_\_\_\_\_Index 3 

**4\. Execute AND mask and compare values (=indirection validation)** 

Compare your recorded value to the value after you have done the offset and the AND mask. 

      **4a. Case A: Correct Indirection** 

**First, offset:  
**Index + Offset = 3 + 2 = 5 

**Second, mask:  
**5 AND 0x07 = 5 

**Third, indirection check:  
**\[-1 -1 21 31 41 **51** 61 -1\]

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_**^**

Index including offset: 5

Value = 51 equals the recorded value, so everything is fine. 

      **4b. Case B: Manipulated Indirection** 

If you now had a manipulated indirection, let’s say 7, let us see what happens: 

**First, offset:  
**Index + Offset = 7 + 2 = 9 

**Second, mask:  
**9 AND 0x07 = 1 

**Third, indirection check:  
**\[-1 **\-1** 21 31 41 51 61 -1\]

\_\_\_\_^ 

Index including offset: **1  
**Value = **\-1** does not equal the recorded value and also indicates your poisoned end, so you’d know your indirection is manipulated. 

**5\. Execute fault/programmer alert** 

If this validated value is different from your recorded one, then you know something is wrong. Raise a software quality alarm. 

Then, check the indirection value. If it is a poisoned value, you should raise another software quality alarm. This is an indication of a fence-post error. 

## Why? 

**Beneficial for …?**

**Why?**

**Security**

Most PLCs do not have any feature to handle out-of-bounds indices for arrays. There are **two potentially dangerous scenarios** that can stem from indirection mistakes: 

**First**, if an indirection leads to reading from the wrong register, the program executes using the wrong values. 

**Second**, if a wrong indirection leads to writing to the wrong register, the program overwrites code or values you want to keep. In both cases, indirection errors can be hard to spot and can have serious impacts. They can be caused by human error but also be inserted maliciously. 

**Reliability** 

Identifies non-malicious human errors in programming. 

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

**CWE-129:** Improper Validation of Array Index

## What’s next?{ .article-section }

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about assigning designated register blocks by function (read/write/validate)

## Do you require help with secure coding of your PLCs?{ .article-section }

If you have any questions or require help in securely coding your PLCs, please contact SEQRED.

SEQRED specialises in providing bespoke OT and IoT cybersecurity solutions.  
Our services cover such areas as Critical Infrastructure Protection, Cloud Services Security or Audits, and Threat Intelligence. For a full list of our services visit our services page – [https://seqred.pl/en/services/](https://seqred.pl/en/services/)

###### **About this article**

You can download the full copy of the Top 20 Secure PLC Coding Practices by clicking [here.](https://www.plc-security.com/index.html#download)[](https://www.linkedin.com/posts/arnaudsoullie_i-created-a-short-introduction-video-to-the-ugcPost-6843118214365421568-DXAG)

The series of these articles is written under the following license:

Copyright (c) 2021 admeritia GmbH, Langenfeld/Rheinland, Germany

Permission is hereby granted, free of charge, to any person obtaining a copy of “Top 20 Secure PLC Coding Practices” and associated documentation files, to deal in the “Top 20 Secure PLC Coding Practices” without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the “Top 20 Secure PLC Coding Practices”, and to permit persons to whom the “Top 20 Secure PLC Coding Practices” is furnished to do so, subject to the following conditions:

THE “Top 20 Secure PLC Coding Practices” IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE “Top 20 Secure PLC Coding Practices” OR THE USE OR OTHER DEALINGS IN THE “Top 20 Secure PLC Coding Practices”.
