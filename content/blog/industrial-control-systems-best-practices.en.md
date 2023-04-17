+++
lang="en-GB"
title="Industrial Control Systems Best Practices"
date="2022-04-07"
author="Eugene Wypior"
image="/blog/ICS-Best-Practices-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Along with the US Department of Justice naming four Russian spies in late March this year and accusing them of hacking activities spanning nearly a decade impacting critical infrastructure across the globe, CISA has issued a joint Cybersecurity Advisory relating to this finding.

As part of the advisory CISA published the following list of Industrial Control Systems (ICS) Best Practices aimed at improving their cyber posture.

*   Update all software. Use a risk-based assessment strategy to determine which ICS networks, assets, and zones should participate in the patch management program.
*   Test all patches in out-of-band testing environments before implementation into production environments.
*   Harden software configuration on field devices, including tablets and smartphones.
*   Replace all end-of-life software and hardware devices.
*   Disable unused ports and services on ICS devices (after testing to ensure this will not affect ICS operation).
*   Restrict and manage remote access software. Enforce MFA for remote access to ICS networks.
*   Configure encryption and security for network protocols within the ICS environment.
*   Do not allow vendors to connect their devices to the ICS network. The use of a compromised device could introduce malware.
*   Disallow any devices that do not live solely on the ICS environment from communicating on the platform. ‘Transient devices’ provide risk exposure to the ICS environment from malicious activity in the IT or other environments to which they connect.
*   Maintain an ICS asset inventory of all hardware, software, and supporting infrastructure technologies.
*   Maintain robust host logging on critical devices within the ICS environment, such as jump boxes, domain controllers, repository servers, etc. These logs should be aggregated into a centralized log server for review.
*   Ensure robust physical security is in place to prevent unauthorized personnel from accessing controlled spaces that house ICS equipment.
*   Regularly test manual controls so that critical functions can be kept running if ICS/OT networks need to be taken offline.