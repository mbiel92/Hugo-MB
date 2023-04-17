+++
lang="en-GB"
title="Defense in Depth strategies – Part 5"
date="2022-11-17"
author="Eugene Wypior"
image="/blog/DiD_87-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## Physical Security in ICS environment{ .article-section }

Physical security controls are any physical measures, either active or passive, that limit physical access to any information assets in the ICS environment. Organizations employ these measures to prevent undesirable system impacts such as the following:

*   Unauthorized physical access to sensitive locations;
*   Physical modification, manipulation, theft or another removal, or destruction of existing systems, infra­structure, communications interfaces, personnel, or physical locations;
*   Unauthorized observation of sensitive information assets through visual observation, note-taking, photographs, or other means;
*   Unauthorized introduction of new systems, infrastructure, communications interfaces, or other hard­ware; and
*   Unauthorized introduction of devices intentionally designed to cause hardware manipulation, com­munications eavesdropping, or other harmful impact such as a universal serial bus (USB) memory device, wireless access point, or Bluetooth or cellular device.

Gaining physical access to a control room or control system components often implies gaining logical access to the process control system as well. Likewise, having logical access to systems, such as command servers and control room computers, allows an adversary to exercise control over the physical process. If computers are readily accessible, and they have removable media or USB ports, it is prudent to fit the drives with locks or remove them from the computers and disable USB ports. Depending on security needs and risks, it might be also prudent to disable or phys­ically protect power buttons to prevent unauthorized use. For maximum security, servers should be placed in locked areas and protected through authentication mechanisms (such as keys). Also, network devices on the ICS network, including switches, routers, network jacks, servers, workstations, and controllers, should be located in a secured area accessible only by authorized personnel.

Physical access control systems should ensure that only authorized people have access to controlled spaces. Access to network and computer cabinets should be limited to only those who have a need such as network technicians and engineers or computer maintenance staff. Equipment cabinets should be locked, and wiring kept neat and within cabinets. Computers should be locked in secure racks and peripheral extender technology should be used to connect human-machine interfaces (HMI) to the racked computers.

Physical security for the control center/control room will reduce the potential for many threats. Control centers/control rooms frequently have consoles continuously logged onto the primary control server, where speed of response and continual view of the plant is of utmost importance. These areas will often contain the servers themselves, other critical computer nodes, and sometimes plant controllers. Access to these areas should be limited to authorized users only, by means of authentication methods such as smart or magnetic identity cards or biometric devices. In extreme cases, make the control center/control room could be made blast-proof, or an offsite emergency control center/control room could be provided so that control can be maintained if the primary control center/control room becomes uninhabitable.

Computers and computerized devices used for ICS functions (such as programmable logic controller (PLC) programming) should never leave the ICS area. Laptops, portable engineering workstations, and handhelds should be tightly secured and never used outside the ICS network.

Organizations should also address cabling design and implementation for the control network. Install cable runs to limit access to authorized personnel only and install equipment in locked cabinets with adequate ventilation and air filtration.

###### **About this article**

###### This article was prepared with the use of the publication of the U.S. Department of Homeland Security titled ‘Recommended Practice: Improving Industrial Control System Cybersecurity with Defense-in-Depth Strategies’  available [here.](https://www.cisa.gov/uscert/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)