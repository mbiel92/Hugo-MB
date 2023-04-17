+++
lang="en-GB"
title="Compute in the cloud relevant security considerations"
date="2022-05-09"
author="Eugene Wypior"
image="/blog/Cloud-Tuesdays-21-7.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Cloud computing is fundamentally based on pooling resources and virtualisation is the technology used to convert fixed infrastructure into these pooled resources. At its most basic, virtualisation abstracts resources from their underlying physical assets. You can virtualise nearly anything in technology, from entire computers to networks to code.

Many security processes are designed with the expectation of physical control over the underlying infrastructure and virtualisation adds two new layers for security controls:

*   Security of the virtualisation technology itself, e.g., securing a hypervisor.
*   Security controls for the virtual assets in many cases must be implemented differently than they would be in the corresponding physical equivalent.

Virtualisation security in cloud computing still follows the shared responsibility model – the cloud provider will always be responsible for securing the physical infrastructure and the virtualisation platform itself, whereas the cloud customer is responsible for properly implementing the available virtualised security controls and understanding the underlying risks, based on what is implemented and managed by the cloud provider.

Some of the most relevant categories of virtualisation in cloud computing include compute, network, storage, and containers.

## **Compute in the cloud relevant security considerations…**{ .article-section }

Compute virtualisation abstracts the running of code from the underlying hardware. Instead of running directly on the hardware, the code runs on top of an abstraction layer that enables more flexible usage, such as running multiple operating systems on the same hardware. Depending on the virtualisation model deployed compute can come in forms of Virtual Machines, Containers or Serverless applications. The below security considerations apply broadly to compute in the form of Virtual Machines.

#### **… on the side of the Cloud Provider**

The primary security responsibilities of the cloud provider in compute virtualisation are to enforce isolation and maintain a secure virtualisation infrastructure.

*   Isolation ensures that compute processes or memory in one virtual machine/container is not visible to another. It is the separation of different tenants, even when they are running processes on the same physical hardware.
*   The cloud provider is also responsible for securing the underlying infrastructure and the virtualisation technology from external attack or internal misuse. This means using patched and up-to-date hypervisors that are properly configured and supported with processes to keep them up to date and secure over time. The inability to patch hypervisors across a cloud deployment could create a fundamentally insecure cloud when a new vulnerability in the technology is discovered.

Cloud providers should also support the secure use of virtualisation for cloud users. This means creating a secure chain of processes from the image (or other sources) used to run the virtual machine all the way through a boot process with security and integrity. This ensures that tenants cannot launch machines based on images that they shouldn’t have access to, such as those belonging to another tenant, and that a running virtual machine (or other processes) is the one the customer expects to be running.

In addition, cloud providers should assure customers that volatile memory is safe from unapproved monitoring, since important data could be exposed if another tenant, a malicious employee, or even an attacker is able to access running memory.

#### **… on the side of the Cloud User** 

The primary responsibility of the cloud user is to properly implement the security of the workload deployed in the virtualised environment. 

Firstly, the cloud user should take advantage of the security controls for managing their virtual infrastructure, which will vary based on the cloud platform and often include:

Identity and Access Management (IAM) – includes identification, authentication, and authorisations (including access management). It determines who can do what within the cloud platform. The specific options, configurations, and even concepts vary heavily between cloud providers and platforms. Each has its own implementation and may not even use the same definitions for things like “groups” and “roles.”

No matter the platform or provider there is always an account owner with super-admin privileges to manage the entire configuration. This should be enterprise-owned (not personal), tightly locked down, and nearly never used.

Separate from the account-owner super-admin accounts for individual admin use can usually be created. These privileges ought to be used sparingly; this should also be a smaller group since compromise or abuse of one of these accounts could allow someone to change or access essentially everything and anything. 

All privileged user accounts should use multi-factor authentication (MFA). If possible, all cloud accounts (even individual user accounts) should use MFA. It’s one of the single most effective security controls to defend against a wide range of attacks. This is also true regardless of the service model: MFA is just as important for SaaS as it is for IaaS.

Monitoring and logging are more complex in cloud computing.

*   IP addresses in logs won’t necessarily reflect a particular workflow since multiple virtual machines may share the same IP address over a period, and some workloads like containers and serverless may not have a recognisable IP address at all. Thus, some other unique identifiers in the logs must be collected to be assured of what the log entries, refer to. These unique identifiers need to account for ephemeral systems, which may only be active for a short period of time.
*   Logs need to be offloaded and collected externally more quickly due to the higher velocity of change in the cloud. Logs can be easily lost in an auto-scale group if they aren’t collected before the cloud controller shuts down an unneeded instance.

Image asset management. Cloud compute deployments are based on master images—be it a virtual machine, container, or other code—that is then run in the cloud. This is often highly automated and results in a larger number of images to base assets on, compared to traditional computing master images. Managing these—including which meet security requirements, where they can be deployed, and who has access to them—is an important security responsibility.

Use of dedicated hosting, if available, based on the security context of the resource. In some situations, the user can specify that their assets run on hardware dedicated only to them (at a higher cost), even on a multitenant cloud. This may help meet compliance requirements or satisfy security needs in special cases where sharing hardware with another tenant is considered a risk.

Secondly, the cloud user is also responsible for security controls within the virtualised resource. This includes all the standard security for the workload, be it a virtual machine, container, or application code.

Ensuring deployment of only secure configurations is of particular concern (e.g., a patched, updated virtual machine image). Due to the automation of cloud computing, it is easy to deploy older configurations that may not be patched or properly secured.