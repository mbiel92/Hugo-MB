+++
lang="en-GB"
title="Defense in Depth strategies – Part 7 – Security Architectures"
date="2022-11-30"
author="Eugene Wypior"
image="/blog/DiD_89-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **Security Architectures**{ .article-section }

Once an organization has designed and implemented a robust network architecture, they have established the security architecture for the network and systems. The security architecture includes the specific controls and their strategic placement within the network or systems to establish layers of secu­rity—Defense in Depth.

Security controls must be applied at the network, system, ap­plication, and physical layers to provide information assurance. The security controls include:

*   policy and security man­agement,
*   application security,
*   data security,
*   platform security,
*   network and perimeter security,
*   physical security,
*   and user security.

The security architecture is where all the defensive mechanisms and controls come together and overlay the network architecture. The security architecture defines where to apply Defense-in-Depth measures across the organization.

#### **Perimeter Security**

ICS perimeter security includes controls for both physical and logical security to protect the assets within those perimeters

Logical security includes controls such as:

– authentication mechanisms,

– ACLs within network components,

– intrusion detection/pre­vention systems (IDS/IPS) signatures,

– situational awareness tools,

– and other means to protect the systems on the logical plane.

#### **Firewalls** 

Firewalls are one of the many components of network security and the first line of defense within an ICS network environment. They act as gatekeepers for the network or zone perimeter and when properly configured keep the intruder out while at the same time allowing authorised data to pass.

To assure the firewall only lets trusted traffic through it should only allow passing this which is explicitly allowed and stop anything else – ‘deny all’.

The role of the firewall is to:

*   Establish domain separation.
*   Monitor (and log) system events.
*   Authenticate users before they are allowed access.
*   Monitor ingress and egress traffic and disallow unauthorized communications.

There are two types of firewalls—the host firewall and the network firewall. The host firewall protects a specific host. It can be part of the OS, or it can be an appliance directly in line with the host. The type of firewall used provides protection for the network using one of several techniques:

\*Packet filtering

*   This type of firewall filters traffic based on rules. They control traffic based on the first three levels of the open systems interconnection (OSI) model: MAC address and IP address, with some filtering based on the transport layer (port numbers).

\* Circuit level gateways

*   These types of firewalls allow only specific sessions to communicate.

\* Proxy level gateways

*   This firewall provides filtering at the application layer – it limits the types of appli­cations and protocols that communicate across security boundaries such as File Transfer Protocol (FTP), Hypertext Transfer Protocol (HTTP), and so forth.

\* Stateful inspection

*   This type of firewall is stateful because it keeps track of the “state” of the connections crossing the firewall. They match the packets with the different types of connections to determine what to allow or reject.

Firewall placement should be coordinated, planned, and carefully thought through.

Improperly placing a firewall can result in the firewall being less effective. Bypassing the firewall, whether intentional or not, is a common occurrence. Modems that connect directly to process equip­ment, vendor VPNs that connect directly to the process control network, wireless access points, and dual-NIC (Network Internet Card) computers all invalidate the effectiveness of the firewall.

#### **Data Diodes**

A unidirectional network device (also referred to as a unidirectional security gateway or data diode) is a network appliance or device that allows data to travel in only one direction. It can be often found in high-security environments, such as defense, where they serve as connections between two or more networks of differing security classifications. This technology can now be found at the industrial control level for such facilities as nuclear power plants and electric power generation.

The physical nature of unidirectional networks only allows data to pass from one side of a network connection to another and not the other way around. The benefits for the users of the higher criticality (high side) network, such as an ICS segment, include the ability to share data with a lower criticality (low side) network, such as a server in a DMZ, while preventing communications access from the low side network to the ICS network.

###### **About this article**

###### This article was prepared with the use of the publication of the U.S. Department of Homeland Security titled ‘Recommended Practice: Improving Industrial Control System Cybersecurity with Defense-in-Depth Strategies’  available [here.](https://www.cisa.gov/uscert/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)