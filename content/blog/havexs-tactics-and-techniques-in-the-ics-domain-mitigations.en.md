+++
lang="en-GB"
title="Havex’s Tactics and Techniques in the ICS domain + mitigations"
date="2022-04-21"
author="Eugene Wypior"
image="/blog/Havex-TTs-58-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Just under a month ago, the Cybersecurity & Infrastructure Security Agency (CISA) issued a joint Cybersecurity Advisory (CSA) containing details of a Global Energy Sector Intrusion Campaign executed between 2011 and 2018 by the Russian FSB. During that time, the FSB gained remote access to U.S. and international Energy Sector networks, deployed ICS malware, and collected and exfiltrated enterprise and ICS-related data.

One of the identified malicious tools used in the years 2013 and 2014 was the remote access Trojan (RAT) Havex – also known as Backdoor.Oldrea.

Using MITRE’s ATT&CK for Industrial Control Systems (ICS) framework CISA mapped Havex’s capabilities as follows:

![](/blog/Havex-TTs-table-1024x612.png)

### **Mitigation**

To harden their ICS/OT environment, CISA recommends the Energy Sector along with other critical infrastructure (CI) organisations to implement the following mitigations:

*   Implement and ensure robust network segmentation between IT and ICS networks to limit the ability of cyber threat actors to move laterally to ICS networks if the IT network is compromised.
*   Implement a network topology for ICS that has multiple layers, with the most critical communications occurring in the most secure and reliable layer. re.
*   Use one-way communication diodes to prevent external access, whenever possible.
*   Set up DMZs to create a physical and logical subnetwork that acts as an intermediary for connected security devices to avoid exposure.
*   Employ reliable network security protocols and services where feasible.
*   Consider using virtual local area networks (VLANs) for additional network segmentation, for example, by placing all printers in separate, dedicated VLANs and restricting users’ direct printer access. This same principle can be applied to the segmentation of portions of the process for which devices are used. As an example, systems that are only involved in the creation of one component within an assembly line that is not directly related to another component can be on separate VLANs, which allows for identification of any unexpected communication, as well as segmentation against potential risk exposure on a larger scale.
*   Implement perimeter security between network segments to limit the ability of cyber threat actors to move laterally.

*   Control traffic between network segments by using firewalls, intrusion detection systems (IDSs), and rules for filtering traffic on routers and switches.
*   Implement network monitoring at key chokepoints—including egress points to the internet, between network segments, core switch locations—and at key assets or services (e.g., remote access services).
*   Configure an IDS to create alarms for any ICS traffic outside normal operations (after establishing a baseline of normal operations and network traffic).
*   Configure security incident and event monitoring to monitor, analyze, and correlate event logs from across the ICS network to identify intrusion attempts.