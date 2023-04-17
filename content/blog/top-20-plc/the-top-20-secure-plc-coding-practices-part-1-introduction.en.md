+++
title = "The Top 20 Secure PLC Coding Practices. Part 1 – Introduction"
author = "Eugen Wypior"
date = "2021-09-16"
summary="For many years, the workhorses of industrial automation as some call the Programmable Logic Controllers (PLCs) have been insecure by design. Several years into customising and applying best practices from IT gave rise to secure protocols, encrypted communications, network segmentation etc. However, to date, there has not been a focus on using the characteristic features in PLCs (or SCADA/DCS) for security, or how to program PLCs with security in mind."
image = "/blog/PLC-p1-1.png"
+++

{{< image >}}

For many years, the workhorses of industrial automation as some call the Programmable Logic Controllers (PLCs) have been insecure by design. Several years into customising and applying best practices from IT gave rise to secure protocols, encrypted communications, network segmentation etc. However, to date, there has not been a focus on using the characteristic features in PLCs (or SCADA/DCS) for security, or how to program PLCs with security in mind. This gap has been filled now with the PLC Security Top 20 List project initiated with Jake Brodsky’s talk at the S4 annual event in Miami Beach in 2020 (see link to talk below this article).

Over the next weeks, in its ‘OT Thursdays’ series SEQRED will publish details of each of the 20 Secure PLC Coding Practices.

## Who should read and implement the Secure PLC Coding Practices?{ .article-section }

These practices have been created as guidelines for engineers creating software (ladder logic, function charts etc.) to help improve the security posture of Industrial Control Systems. These practices leverage natively available functionality in the PLC/DCS. Little to no additional software tools or hardware is needed to implement these practices. They can all be fit into the normal PLC programming and operating workflow. More than security expertise, good knowledge of the PLCs to be protected, their logic, and the underlying process is needed for implementing these practices.

To fit the scope of the Top 20 Secure PLC Coding practices list, practices need to involve changes made directly to a PLC.

## What are the benefits of applying Secure PLC Coding Practices?{ .article-section }

Using these practices clearly has security benefits – mostly either reducing the attack surface or enabling faster troubleshooting if a security incident were to happen. However, many practices have additional benefits beyond security. Some also make the PLC code more reliable, easier to debug and maintain, easier to communicate, and possibly also leaner. Further, the secure PLC coding practices not only help users in the event of a malicious attacker but also make the PLC code more robust to withstand accidental misconfiguration or human error.

## What's next?{ .article-section }

The second article in this series will cover the first Secure PLC Coding Practice – Modularising PLC code. 

## Do you require help with secure coding of your PLCs?{ .article-section }

If you have any questions or require help in securely coding your PLCs, please contact SEQRED.

SEQRED specialises in providing bespoke OT and IoT cybersecurity solutions. Our services cover such areas as Critical Infrastructure Protection, Cloud Services Security or Audits, and Threat Intelligence. For a full list of our services visit our services page – https://seqred.pl/en/services/


### About this article { .article-section }

To view Jake Brodsky’s talk at the S4 2020 event [click here](https://www.youtube.com/watch?v=JtsyyTfSP1I). You can download the full copy of the Top 20 Secure PLC Coding Practices by [clicking here](https://plc-security.com/#download).

The series of these articles is written under the following license:


> Copyright (c) 2021 admeritia GmbH, Langenfeld/Rheinland, Germany
> Permission is hereby granted, free of charge, to any person obtaining a copy of “Top 20 Secure PLC Coding Practices” and associated documentation files, to deal in the “Top 20 Secure PLC Coding Practices” without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the “Top 20 Secure PLC Coding Practices”, and to permit persons to whom the “Top 20 Secure PLC Coding Practices” is furnished to do so, subject to the following conditions:

> THE “Top 20 Secure PLC Coding Practices” IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE “Top 20 Secure PLC Coding Practices” OR THE USE OR OTHER DEALINGS IN THE “Top 20 Secure PLC Coding Practices”.
