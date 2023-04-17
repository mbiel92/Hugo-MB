+++
lang="en-GB"
title="IEC62443 – Examples of practical requirements implementation – Part 1"
date="2022-09-22"
author="Eugene Wypior"
image="/blog/IEC62443-1-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **IEC 62443 – an introduction**{ .article-section }

In the last decade, industrial automation systems have become the subject of an unprecedented scale of cyber-attacks. Along with the scale of these attacks, their technical sophistication also increases, causing a constantly growing level of threat to these systems. In response to this situation, based on the work and experience gathered by the Industrial Automation and Control System Security standards committee (ISA99) the International Electrotechnical Commission (IEC) approved in 2021 the IEC 62443 family of standards that provide a realistic and achievable model to mitigate security threats in the Industrial Automation Control System.

The IEC 62443 describes the essential safety risk prevention requirements for component manufacturers, system integrators and system users, and aims to ensure the safe operation of Industrial Control Systems (ICS) – from design, through implementation, to management.

The IEC 62443 series of standards can be used in various industrial control segments, has been approved by many countries and is evolving to become the industry standard.

## **Security Assurance Levels**{ .article-section }

One of the concepts used within the IEC 62443 are the Security Assurance Levels.

The Security Assurance Levels define four levels of security required for the safe operation of ICS systems mapped to the type of possible attack the security level is designed to address. Each ICS must fulfill the requirements applicable to one of the security levels.

![Figure 1 – IEC 62443 Security Assurance Levels](/blog/Table1-2.jpg)

## **Defense in Depth**{ .article-section }

The Defense in Depth approach utilises a multilayer security concept for holistic all-round and in-depth protection against cyberattacks as recommended by the IEC 62443 standard. It encompasses plant security, network security and system integrity and involves the implementation of the following six steps:

*   Creating a Security Plan where all the network assets are inventoried and mapped, the assets’ security configuration and vulnerabilities are reviewed and assessed.
*   Separating Networks by their major function such as enterprise, plant, process, and field zones with inter-zone conduits clearly identified.
*   Protecting the Perimeter by protecting the conduits between the zones.
*   Segmenting the Network by dividing zones created during network separation into smaller zones based on function and location.
*   Hardening of Devices
*   Active Monitoring of the network activity and the regular Updating of the products firmware

###### **About this article**

###### Ideas for this article were taken amongst other from the Schneider Electric whitepaper available [here](https://download.schneider-electric.com/files?p_enDocType=White+Paper&p_File_Name=998-20186845_GMA-US.pdf&p_Doc_Ref=998-20186845).