+++
lang="en-GB"
title="IEC62443 – Examples of practical requirements implementation – Part 4"
date="2022-10-13"
author="Eugene Wypior"
image="/blog/IEC62443-_4-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **Security Assurance Level 3**{ .article-section }

By definition should an SL3-compliant system be able to withstand intentional violation of its integrity by the use of sophisticated means with moderate resources, IACS-specific skills, and moderate motivation. In practical terms, it means that a system should be able to withstand attacks carried out by cybercriminals, competitors, professional cyber thieves, or hacktivists.

To fulfill this requirement, IEC 62443-3-3 defines a further 30 requirements (or enhancements to SL2) necessary for a control system to be compliant with SL3. 

A significant difference at SL3 is that several requirements are implemented directly into the ICS components such as mandatory secure protocols and the use of secure elements to protect keys – private, public, and symmetric. In practical terms, this means that where in SL2 required features could have been implemented via new software, in SL3 equipment will likely has to be replaced or redesigned.

Apart from the above-mentioned hardware key differentiator some other important differences to SL2 include such features as: 

*   Unique software process and device identification and authentication
*   Support for multifactor authentication for untrusted interfaces
*   Identification and reporting of unauthorised wireless devices
*   Prevention of password reuse for a configurable number of generations for human users
*   Centrally managed system-wide audit trail by adding a SIEM server
*   Use of secure protocols to support cryptographic mechanisms to recognise changes to information during communication
*   Centrally managed malicious code protection mechanisms through the EPO and SIEM servers
*   Reporting the current security settings on end devices with the use of the EPO server and the network management systems

Introducing SL3 requirements may result in the need to add/change devices, e.g. the event server from SL2 must be changed to SIEM server in order to meet additional SL3 requirements. In addition, e.g. GPS time source and wireless threat detection should be included in the network architecture.

![Sample ICS segmentation and changes to equipment / devices as result of implementation of the IEC 62443 Security Assurance Level 3 ](/blog/IEC62443-_4_graphic.png)

###### **About this article**

###### Ideas for this article were taken amongst other from the Schneider Electric whitepaper available [here](https://download.schneider-electric.com/files?p_enDocType=White+Paper&p_File_Name=998-20186845_GMA-US.pdf&p_Doc_Ref=998-20186845).