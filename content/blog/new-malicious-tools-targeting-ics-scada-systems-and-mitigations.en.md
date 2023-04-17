+++
lang="en-GB"
title="New malicious tools targeting ICS / SCADA systems and mitigations"
date="2022-04-14"
author="Eugene Wypior"
image="/blog/AA22_103A-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++


## **ICS / SCADA systems under a new threat**{ .article-section }

Yesterday, on the 13th April, CISA, DOE and FBI released a joint Cybersecurity Advisory – Alert (AA22-103A) – warning that certain APT actors have proven to be able to gain full access to multiple Industrial Control System (ICS) / Supervisory Control and Data Acquisition (SCADA) devices using custom-build offensive tools which enable scanning, compromising and controlling some of them, including:

*   Schneider Electric MODICON and MODICON Nano programmable logic controllers (PLCs) , including (but may not be limited to) TM251, TM241, M258, M238, LMC058, and LMC078;
*   OMRON Sysmac NJ and NX PLCs, including (but may not be limited to) NEX NX1P2, NX-SL3300, NX-ECC203, NJ501-1300, S8VK, and R88D-1SN10F-ECT;
*   Open Platform Communications Unified Architecture (OPC UA) servers.

The malicious tools the APT actors are using are said to be of modular design enabling them to perform highly automated exploits on targeted devices. The tools have a virtual console with a command interface that mirrors the interface of the targeted ICS/SCADA device. Modules interact with targeted devices, enabling operations by lower-skilled cyber actors to emulate higher-skilled actor capabilities.

The APT actors can use the modules to scan for targeted devices, conduct reconnaissance on device details, upload malicious configuration/code to the targeted device, back up or restore device contents, and modify device parameters. 

In addition, the APT actors can use a tool that installs and exploits a known-vulnerable ASRock-signed motherboard driver, AsrDrv103.sys, exploiting [CVE-2020-15368](https://nvd.nist.gov/vuln/detail/CVE-2020-15368?msclkid=85419d5cb4e011ecb9c6a9a06c66a82f) to execute malicious code in the Windows kernel. Successful deployment of this tool can allow APT actors to move laterally within an IT or OT environment and disrupt critical devices or functions.

## **Mitigations**{ .article-section }

CISA advises all organisations running ICS/SCADA devices to protect their systems from the above threats by implementing the mitigations below. As the following have not been verified against all environments they should be tested before deploying in a live environment.

(The first three mitigations are advised to be implemented immediately)

*   Enforce multifactor authentication for all remote access to ICS networks and devices whenever possible.
*   Change all passwords to ICS/SCADA devices and systems on a consistent schedule, especially all default passwords, to device-unique strong passwords to mitigate password brute force attacks and to give defender monitoring systems opportunities to detect common attacks.
*   Implement a continuous OT monitoring solution to alert on malicious indicators and behaviours, watching internal systems and communications for known hostile actions and lateral movement
*   Isolate ICS/SCADA systems and networks from corporate and internet networks using strong perimeter controls, and limit any communications entering or leaving ICS/SCADA perimeters.
*   Have a cyber incident response plan, and exercise it regularly with stakeholders in IT, cybersecurity, and operations.
*   Maintain verified and reliable offline backups for faster recovery in case of a disruptive attack, and conduct hashing and integrity checks on firmware and controller configuration files to ensure validity of those backups.
*   Limit ICS/SCADA systems’ network connections to only specifically allowed management and engineering workstations (whitelisting).
*   Robustly protect management systems by configuring Device Guard, Credential Guard, and Hypervisor Code Integrity (HVCI). Install Endpoint Detection and Response (EDR) solutions on these subnets and ensure strong anti-virus file reputation settings are configured.
*   Implement robust log collection and retention from ICS/SCADA systems and management subnets.
*   Ensure all applications are only installed when necessary for operation.
*   Enforce principle of least privilege. Only use admin accounts when required for tasks, such as installing software updates.
*   Investigate symptoms of a denial of service or connection severing, which exhibit as delays in communications processing, loss of function requiring a reboot, and delayed actions to operator comments as signs of potential malicious activity.
*   Monitor systems for loading of unusual drivers, especially for ASRock driver if no ASRock driver is normally used on the system.

## **Only three weeks ago**{ .article-section }

This news comes only three weeks after, on the 24th March, CISA, DOE and FBI released a joint Cybersecurity Advisory revealing the details of a Global Energy Sector Intrusion Campaign which has been going on since 2011 and operated by Russian spies. One of the malwares identified as used by the perpetrators was TRITON which has been designed to specifically target Schneider Electric’s Triconex Tricon, a safety programmable logic controller which is designed to fail safely in case the need for an emergency shutdown.