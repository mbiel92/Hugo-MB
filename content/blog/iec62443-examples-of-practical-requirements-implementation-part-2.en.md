+++
lang="en-GB"
title="IEC62443 – Examples of practical requirements implementation – Part 2"
date="2022-09-28"
author="Eugene Wypior"
image="/blog/IEC62443-_2-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

The IEC 62443 defines four Security Assurance Levels required for the safe operation of ICS systems mapped to the type of possible attack the security level is designed to address. Each ICS must fulfil the requirements applicable to one of the security levels.

## **Reference architecture** { .article-section }

To increase the ICS system security, its architecture will have to be adjusted accordingly. Below is a sample network reflecting these changes.

![A sample network structure reflecting the IEC 62443 principles ](/blog/P2_figure1.png)

## **Security Assurance Level 1 (SL1) Reference Architecture**{ .article-section }

The implementation of SL1 requirements directly impacts the ICS’ network architecture by separating new network segments and introducing network zones boundaries protection. 

According to Schneider Electrics, the architecture of a sample network reflecting the SL1 requirements could thus look as follows

![Figure2 – Sample ICS segmentation as result of implementation of the IEC 62443 Security Assurance Level 1 ](/blog/P2_figure2.png)

Compared to a network not following the SL1 requirements, here the network has been divided into 7 smaller zones highlighted in grey, and in particular:

*   DMZ zone separating the Enterprise and Control Zones
*   Plant / Process Zone – containing the process and plant management solutions
*   Security Appliance Zone
*   Wireless Zone
*   Controller Zones 

Also, additional elements marked in green (i.a. additional firewalls for the purpose of network segmentation, EPO or MDM servers) comply with the conditions implied by SL1.

## **Security Assurance Level 1 requirements overview**{ .article-section }

The Security Assurance Level 1 (SL1) provides guidelines aimed at protecting the ICS system and its components against casual or coincidental mistakes. As the threat is casual or coincidental it is assumed to be coming from one’s own employees.

Each SL must fulfill a certain number of Foundational Requirements (FR) necessary to reach compliance at each level. For SL1 the number of the requirements totals 37.

The majority of them belong to the group of Identification and Authentication Control requirements where the control system can authenticate and authorise human users (including wireless), user accounts can be created and managed, password strength can be configured, and unsuccessful login attempts can be tracked.

Further, the implemented control system should i.a., be able to:

*   Monitor and control access from untrusted networks
*   Restrict code embedded in an email or on storage media
*   Generate audit records
*   Protect the integrity of transmitted information and the confidentiality of information at rest or in transit
*   Detect, prevent, and report the effects of malicious code
*   Segment networks and protect boundaries
*   Prevent messages from being received from external users or systems
*   Operate in degraded mode during a denial-of-service event as well as prohibit unnecessary functions, ports, protocols, and services

###### **About this article**

###### Ideas for this article were taken amongst other from the Schneider Electric whitepaper available [here](https://download.schneider-electric.com/files?p_enDocType=White+Paper&p_File_Name=998-20186845_GMA-US.pdf&p_Doc_Ref=998-20186845).