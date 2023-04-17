+++
lang="en-GB"
title="Zero Trust Architecture"
date="2021-11-30"
author="Eugen Wypior"
image="/blog/Bezpieczenstwo-systemow-automatyki-przemyslowej.jpg"
tags=['ABC security','IT security', 'response&recovery']
+++

For many years the infrastructure security model was based on securing the perimeter of the environment. Defenses were built at the perimeter of the network to prevent malicious actors from getting inside. However, once an attacker broke through the perimeter and was inside the environment, they could move laterally between assets with a good degree of ease. There was a rather good chance their actions would not be questioned by the system. And although breaches were occurring, they were not as common as nowadays. Why? What has changed?

With the arrival of new IT technologies such as Cloud computing and Software as Service, the environment landscape has changed. The definition of perimeter itself became blurred as it was no longer possible to automatically trust devices that were inside the network. A paradigm shift occurred making thinking in terms of ‘inside the network vs outside the network’ obsolete.

The Zero Trust Architecture paradigm assumes that nothing on the network can be trusted unless it can prove its trustworthiness. It brings the security perimeter as close to individual devices as possible and treats every device as if it is continuously exposed to the internet. It introduces a shift from protecting the network to protecting the data resources on the network.

 ## Zero Trust principles{ .article-section }

#### 1\. Trust Nothing, Verify Everything

Assume the network is always hostile and that internal and external threats are always present. Only grant access to data through protected connections, regardless of where the data is located.

#### 2. Determine the degree of trust

Determine who is to be granted access based on the degree of trust that can be gleaned from the various properties of the request for access: account, device, IP address, location, time, type, and amount of information requested.

#### 3\. Assume Breach

Assume that the network has been breached and you must contain the attacker. As result, any device on the network must prove that is it trustworthy. Identify an object using a single identification source followed up by letting the object prove its authorisation using multiple-factor authentication.

#### 4. Implement the Principle of Least Privilege

Manage access using the Principle of Least Privilege giving the individual only the access required for them to complete the task and nothing more. If the individual does not need an access right, they should not have it.

#### 5. Micro-segmentation – Pomegranate model

Segment and isolate your infrastructure as much as possible and as much as practical.

## Zero Trust implementation{ .article-section }

For an organisation to implement the Zero Trust Architecture it must:

#### 1\. Account for all the resources on its network and define the surface it wants to secure

An inventory of all the resources on the network is required – apps, software, file shares, service, etc, deployed in the organisation’s environment. You can only protect what you know you have.

#### 2. Define permissible process flows and behaviours

Define what request in what configurations you allow based on the Principle of Least Privilege.

#### 3. Create policies and rules

After you have taken inventory of the resources on your network and what or who accesses and uses what in your environment you can start designing and creating policies and rules to enforce them.

#### 4. Do extensive monitoring and logging

Continuously monitor your Micro-permitters for indicators of misuses or compromise or for attackers wanting to compromise your resources.

## Do you require help with protecting your IT or OT system?{ .article-section }

SEQRED offers assistance in providing comprehensive security solutions for IT and OT systems. It offers services in the areas of Security Audits, Network Segmentation, Mobile Device Security, Cloud Security, and many others.

To discuss your requirements, contact SEQRED at biuro@seqred.pl.