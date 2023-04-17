+++
lang="en-GB"
title="Software Defined Network Security Benefits"
date="2022-06-27"
author="Eugene Wypior"
image="/blog/SDNSecurityB-1.png"
tags=['ABC security','messaging security']
+++

## **What is SDN?**{ .article-section }

Traditional networking uses integrated hardware and software to direct traffic across a series of routers and switches.

Originally SDN was designed to virtualize the network by separating the control plane that manages the network from the data plane where traffic flows. There is a smart controller running specialized software that manages all network traffic in the data centre, and a series of routers and switches that forward packets of traffic.

There are a number of advantages to virtualizing the network:

*   it can be spun up and down dynamically,
*   it can be fine-tuned for specific application uses cases,
*   security policies can be installed on each individual network.

 Nowadays SDN is being used in many more areas than just within the confines of the data centre such as in the Wide Area Network to control how enterprises connect to their branch offices. This application is called SD-WAN and it uses software to aggregate multiple types of network connections, such as broadband, MPLS or wireless to create strong and cost-effective connections.

## **SDN security benefits**{ .article-section }

Due to their non-hardware origin Software Defined Networks enable many new types of security controls, such as:

*   ### **Microsegmentation**
    
    – it is considerably easier to map as many isolated networks as required due to the lack of constraints inherent in the physical hardware. Any number of applications can be run on their own virtual network and only connecting those networks as needed. Which in practical terms means that in case of a security breach of one network the attacker can no longer pivot to other assets of the infrastructure. And there is no increase in capital expenses since cloud microsegmentation is based on software configurations. It can however increase operational expenses due to managing multiple overlapping networks and connectivity.
    
*   ### **SDN firewalls (e.g., security groups)**
    
    – SDN firewalls are usually policy sets that define rules for inbound and outbound traffic to a single asset or a group of assets, independent of network location (within a given virtual network). For example, you can create a set of firewall rules applicable to assets with a particular tag. The tagging capability however depends on the platform
    
*   ### **Automatically generated rule sets**
    
    – it is possible to create firewall rulesets that will apply to assets such as virtual machines deployed in multiple subnets, regardless of their subnet IP address.
    
*   ### **Deny by default**
    
    – often the default setting for an SDN firewall is set to ‘deny’, opposite to most physical networks. It is then up to the user to setup desired permissions.
    
*   ### **Enhanced manageability**
    
    – software firewalls are managed outside the system they apply to, without additional hardware costs or the need for provisioning. This hugely simplifies managing them, for example if there is the need to isolate every single virtual machine on the same virtual subnet. Compared, host firewalls are difficult to manage at scale, and if the system they are on is compromised, they are easy to alter and disable. It is also not viable from a cost perspective to route all internal traffic through a network firewall.
    
*   ### **Default elimination of network attacks**
    
    – when used in the cloud environment, depending on the cloud provider many network attacks – e.g., ARP spoofing – are neutralised by default.
    
*   ### **Packets encryption**
    
    – possibility to encrypt packets as they are encapsulated.
    
*   ### **Dynamic routing and design**
    
    – like security groups, other routing and network design can be dynamic and coupled with the orchestration layer – for example bridging of virtual networks or connecting to internal PaaS services.
    

###### **About this article**

###### This article was based on a number of sources publicly available on the internet including the shared responsibility in the cloud concept as presented by MS – you can view it [here](https://docs.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility).
