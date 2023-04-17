+++
lang="en-GB"
title="Industrial Network Security Architecture - Asset and Network Management"
date="2022-03-23"
author="Eugen Wypiór"
image="/blog/AssetNetworkManagement-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Quickly advancing digitalisation and rapid spread of the Industrial
Internet of Things (IIoT) entails the growth in number of connected
devices in industrial networks, which in return increases the surface
for a potential cyberattack. This situation demands the network owner to
have the most current, real-time inventory of all network devices for
the sake of a root cause analysis in case of a cyber incident.

The IEC 62443 which is an international series of standards that address cybersecurity for operational technology in automation and control systems, sets the
requirements for auditing and monitoring of the assets in sections SR2.8
and SR7.8.

Section SR2.8 on Auditable events states:

'The control system shall provide the capability to generate audit
records relevant to security for the following categories: access
control, request errors, operating system events, control systems,
backup and restore events, configuration changes, potential
reconnaissance activity, and audit log events. Individual audit records
shall include the timestamp, source (originating device, software
process or human user account), category, type, event ID and even
result."

Section SR7.8 on Control system component inventory
states:

'A control system component inventory may include but is not limited to
component ID, capability, and revision level. The component inventory
should be consistent with the system under consideration. A formal
process of configuration management should be deployed to keep control
of the changes in the component inventory baseline.'

The above sections of the IEC 62443 can be realised by implementing a central Network Management System (NMS) based on the ISO Network Management framework model FCAPS (Fault, Configuration, Accounting, Performance, Security Management).

NMS with these parameters:

-   enables full visibility of assets
-   manages the flow of information
-   enables the diagnosis of network problems
-   provides the physical topology of the network
-   provides user access control between the different zones of the IT
    and OT network.

###### **About this article**

This article was inspired by a Siemens publications. You can read the full text by clicking [here.](https://new.siemens.com/global/en/products/automation/industrial-communication/industrial-network-solutions/white-paper-industrial-network-security-architecture.html)