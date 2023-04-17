+++
lang="en-GB"
title="‘Pipedream’ – a surfacing threat targeting Industrial Control Systems (ICS)"
date="2022-04-28"
author="Eugene Wypior"
image="/blog/Pipedream-59-1.png"
tags=['ABC security','Cybersecurity Maturity Model Certification', 'messaging security']
+++

Two weeks ago, Dragos, the US-based industrial cybersecurity expert, reported it has identified and analysed a new Industrial Control Systems (ICS)-specific malware named PIPEDREAM. This malware is a modular ICS attack framework that can be used to disrupt, degrade, and potentially destroy industrial environments and processes. It is the seventh known malware of this type preceded by STUXNET, HAVEX, BLACKENERGY2, CRASHOVERRIDE/INDUSTROYER, TRISIS/TRITON, and INDUSTROYER.

Dragos attributes PIPEDREAM to CHERNOVITE (Dragos-designated) Activity Group assessed to be highly motivated, skilled in software development methods, well versed in ICS protocols and intrusion techniques, and well-funded – most likely state-sponsored. Dragos assesses that CHERNOVITE can achieve Stage 2 of the ICS Cyber Kill chain through a focus on manipulation of Industrial Control Systems.

PIPEDREAM is a collection of utilities that includes tools for reconnaissance, manipulation, and disruption of PLCs as well as tools for intrusion operations against Windows devices. It can impact a wide variety of Programmable Logic Controllers (PLCs) and industrial software, including specific Omron and Schneider Electric PLCs, and Open Platform Communications Unified Architecture (OPC UA) servers. At the highest level, the PLC-related components of PIPEDREAM provide the adversary with an interface for manipulating the targeted devices. Tools in PIPEDREAM can scan for new devices, brute force passwords, sever connections, and then crash the target device. To accomplish these goals, PIPEDREAM uses several different protocols, including Omron’s proprietary FINS, Modbus, and Schneider Electric’s implementation of CODESYS.

While PIPEDREAM is designed to specifically target Schneider Electric and Omicron PLCs it could be targeting other vendors as well.

Dragos divides PIPEDREAM into the following utilities:

EVILSCHOLAR – A capability designed to discover, access, manipulate, and disable Schneider Electric PLCs. It contains a CODESYS library that potentially allows it to target other vendors’ devices.

BADOMEN – A remote shell capability designed to interact with Omron software and PLCs.

MOUSEHOLE – A scanning tool designed to use OPC UA to enumerate PLCs and OT networks.

DUSTTUNNEL – A custom remote operational implant capability to perform host  
reconnaissance and command-and-control.

LAZYCARGO – A capability that drops and exploits a vulnerable ASRock driver to load an  
unsigned driver.

PIPEDREAM is a highly capable offensive ICS attack framework. It can execute 38% of known ICS attack techniques and 83% of known ICS attack tactics as measured against the MITRE ATT&CK for ICS behaviour matrix. PIPEDREAM’s primary application is to target equipment in Liquefied Natural Gas (LNG) and electric power environments however it can be assumed that its capabilities can be easily adapted to target other environments.

According to Dragos assessment PIPEDREAM has not yet been deployed in the wild.

### **Mitigations**

Monitor ICS networks for lateral movement – carry out network traffic monitoring with a focus on lateral communication rather than incoming and outgoing traffic as PIPEDREAM has the ability to move from Engineering Workstation to PLC and then from PLC to PLC. Especially watch out for changes to PLCs taking place outside of regular maintenance periods.

Change default credentials, especially on Schneider Electric TM2xx series starting with firmware 5.0 where the devices use default credentials. These should be changed to a complex password using the EcoStruxure software.

For all Schneider Electric TM2xx series PLCs restrict access to UDP/1740-1743, TCP/1105, and TCP/11740.

Restrict access to TCP/11740 for non-Schneider  PLCs known to communicate with this port from the  
engineering workstation.

Restrict the workstation from making outbound network connections, especially to internet services.

PLC network telemetry analysis – monitor for atypical exchanges with PLCs from non-standard workstations or accounts.

Observe affected PLCs for new egress connections – Look for comms to other PLCs on the network, on UDP/1740-1743, TCP/1105, and TCP/11740.

Disable the Schneider NetManage discovery service as it is used by CHERNOVITE to discover PLCs.

Ensure network isolation for safety system components, and monitor safety system networks for new connections or devices. Verify all configuration changes are in compliance with change management procedures.

Create and update an ICS-focused Incident Response Plan for operating with the hampered or degraded control system. Conduct a Table Top Excercise based on CHERNOVITE’s ICS Cybel Kill Chain with the emphasis on PIPEDREAM.