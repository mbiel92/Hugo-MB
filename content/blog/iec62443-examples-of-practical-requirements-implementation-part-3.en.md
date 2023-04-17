+++
lang="en-GB"
title="IEC62443 – Examples of practical requirements implementation – Part 3"
date="2022-10-06"
author="Eugene Wypior"
image="/blog/IEC62443-_3-2.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **Security Assurance Level 2**{ .article-section }

Additionally, to the specification of SL1, IEC 62443-3-3 defines a further 23 requirements (or enhancements to SL1) necessary to be compliant with SL2. The most prominent of them are:

*   Just as in the case of SL1 a good number of requirements cover the area of Identification and Authentication Control. The main difference lies in the fact that in addition to authenticating and authorising human users, SL2 adds software processes and users to the list, and wireless users are verified against certificates issued by certificate authority added to the network, whereas before it was the network infrastructure itself conducting the authentication process.
*   Another enhancement on SL2 vs SL1 is the feature of the control system to be able to deny access requests from untrusted networks unless approved by an assigned role rather than mainly monitoring the traffic as in the case of SL1. The process becomes more automated.
*   Through the implementation of the network Intrusion Detection System support in SL2 the control system is able to employ malicious code protection at all entry and exit points.
*   On top of being able to provide the integrity of transmitted information of SL1, SL2 is also required to protect the integrity of sessions.
*   Adding to the ability to generate audit accounts of SL1, SL2 shall also protect it with the employment of an event server as a centralised depository for equipment records.
*   Using VPN initiated from a firewall an SL2 compliant control system protects the confidentiality in remote access traversing an untrusted network.
*   To further protect critical systems, communication from them is transported over different networks than information transmitted for non-critical purposes. This implies physical segmentation of control system networks from their non-control counterparts.
*   With the use of an Intrusion Detection System, the control system is able to produce a list of installed components with associated properties.

Introducing SL2 requirements entails changes to network assets valid for SL1 in the form of additional products/devices such as a unified account management appliance, Certificate Authority, Back-up Server, Event Server, and Network Intrusion Detection System have been added to the network and highlighted in green below

![– Sample ICS segmentation and changes to equipment / devices as result of implementation of the IEC 62443 Security Assurance Level 2 ](/blog/IEC62443-_3_graphic.png)

*   Additionally, two further network segments have been separated within the Control Network

###### **About this article**

###### Ideas for this article were taken amongst other from the Schneider Electric whitepaper available [here](https://download.schneider-electric.com/files?p_enDocType=White+Paper&p_File_Name=998-20186845_GMA-US.pdf&p_Doc_Ref=998-20186845).