+++
lang="en-GB"
title="Defense in Depth strategies – Part 8 – Host Security"
date="2022-12-07"
author="Eugene Wypior"
image="/blog/DiD_90-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **Host Security**{ .article-section }

The key concept of Defense in Depth is the fact that there are multiple layers of security implemented throughout the system. And so, after protecting the devices within the OT network from an outside attack with the use of policies, zones and firewalls, the next layer of security is applied directly to the hosts within the OT environment by:

*   Installing and configuring a host-based firewall
*   Implementing a rigorous password policy:
    *   Replacement of all default passwords
    *   Strong passwords
    *   Enforced password change on a pre-defined schedule (every 30 to 90 days)
*   Installing screen savers with short intervals and with a password required to log in where possible
*   Installing and keeping operating systems and hardware firmware patched up to date
*   Configuring and monitoring logs on the device
*   Disabling unused or unnecessary services and accounts
*   Replacing insecure services (telnet, RSH, rlogin) with more secure alternatives
*   Restricting access to services that one cannot disable (where possible)
*   Making and testing backups of the system in a consistent manner if not centrally controlled
*   Securing laptops and other portable and mobile devices not continuously connected to the network

### **Patch and Vulnerability Management**

Applying patches to ICS components can interfere with the ICS function. A patch to an ICS component could change the way it works, resulting in component failure or loss of functionality. All patches should be tested offline in a test environment that contains the same model and type of ICS to determine whether the patch has unintended consequences.

Application of patches and software upgrades to ICS should occur only during planned outages and at routine intervals.

### **Field Devices**

Often field devices, especially older PLCs, remote terminal units (RTUs), and intelligent electronic de­vices (IEDs) are not capable of centralized management. They also may not have the security capabilities that other components such as workstations may have (for example, limited password length and char­acters that can be used). In many instances these devices are protected behind fences, behind locked doors, or in locked cabinets; however, their configuration capabilities should be also locked down to the fullest extent possible while ensuring continued functionality.

Nowadays field personnel is increasingly using portable devices such as tablets and smartphones for in-field control functionality. System administrators must secure these devices to the fullest extent possible, remove or turn off any unnecessary services (such as email capability), and keep them up to date with the latest security patches to ensure they do not introduce malicious code into the ICS.

###### **About this article**

###### This article was prepared with the use of the publication of the U.S. Department of Homeland Security titled ‘Recommended Practice: Improving Industrial Control System Cybersecurity with Defense-in-Depth Strategies’  available [here.](https://www.cisa.gov/uscert/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)