+++
lang="en-GB"
title="Shared Responsibility for Security in the Public Cloud"
date="2022-05-12"
author="Eugene Wypior"
image="/blog/Cloud-Tuesdays-20-2.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

In general, cloud infrastructure can be broadly divided into two main layers.

Firstly, there all are the hardware resources – the storage systems, servers, switches, routers, firewalls, etc – which are the underlying, the ‘invisible’, part of any cloud environment. All these devices need to be secured, physically and digitally, to ensure a safe and uninterrupted environment on which the functional side of the cloud can be virtualised. This part is managed by the cloud provider and the cloud services user has no access to this sphere of the cloud.

Secondly, there is the abstract infrastructure of the cloud, the cloud itself, created by the virtualisation of the underlying resources mentioned above. The cloud environment is the compute, network, and storage assets which can be pulled, if needed on demand, from the resources pool, and returned to the pool when no longer required.

As already stated above, the responsibility for the security of the physical data centre, network and hosts always lies with the public cloud provider.

All cloud resources abstracted from this physical layer and utilised by the user come in the form of Infrastructure as a Service (IaaS) and include such areas as operating systems, network controls, applications, identity and directory infrastructure, accounts and identities, endpoints, information & data itself. The security of these is the sole responsibility of the cloud services user. An example of an IaaS public cloud service is the Amazon EC2 Instance. Once the user deploys an EC2 instance, they are solely responsible for the management of the guest operating system (including updates and security patches), any application software or utilities installed by the customer on the instances, and the configuration of security groups (a type of software firewall).

The least security responsibility falls onto the user in the cloud when they use Software as a Service (SaaS) cloud solutions. Here, the customer is only responsible for securing the data & information, endpoints, accounts & identities. An example of SaaS is online Google suite or the Microsoft 365 suite.

In respect to the scope of shared security PaaS (Platform as a Service) resides between SaaS and IaaS. Here the security responsibility demarcation line is fluid and will depend on the platform and provider used. In general, the areas of responsibility which can lay on either the side of the provider or the user will be that of network controls, applications, and identity & directory infrastructure. The responsibility will be always clearly defined by the provider, and it is the user’s responsibility to know what their share of it covers. Examples of PaaS include AWS’s Lambda or Elastic Beanstalk or GCP’s Google App Engine.

All the above is in line with the concept of shared responsibility model. In general, the provider is responsible for ‘Security of the Cloud’ whereas the customer is responsible for ‘Security in the Cloud’. And by rule of thumb, the more technical computing skills your service requires, the bigger your share in the responsibility for the security of your environment. The important thing to remember is – always check with the provider of the solution you are using to find out what their share in the model covers.

###### **About this article**

This article was based on a number of sources publicly available on the internet including the shared responsibility in the cloud concept as presented by MS – you can view it [here](https://docs.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility).
