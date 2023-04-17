+++
lang="en-GB"
title="Best Practices for Securing your Cloud"
date="2022-03-08"
author="Eugen Wypiór"
image="/blog/Best-Practices-Cloud-4.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

There is a good number of boxes for you to tick to make sure the
security of your cloud environment is as robust against potential
breaches as you can make it.

## 1. Compliance{ .article-section }

Follow at least one of the available security frameworks that describe
what a secure cloud environment looks like. And while compliance is no
replacement for security using such a framework for assessment will help
you realise what controls are needed to secure data and endpoints.

## 2. Asset inventory{ .article-section }

You can only extend your protection to the assets you know you have --
this applies to the cloud too. Make a comprehensive inventory of your
dominion in the cloud: instances, storage, cloud provider services, or
cloud tools. This is especially important if you are simultaneously
using cloud solutions from different providers. If possible, try to
automate the inventory process. This will allow you to implement an
integrated security approach.

## 3. Data security{ .article-section }

Know and correctly label your data and establish the level of security
it requires. Assign controls determining where specific data should
reside such as in a SaaS application or cloud-provider storage. Also
decide, based on data sensitivity, whether the data is exposed to the
public and levels of access privileges.

## 4. Zero trust{ .article-section }

Wherever practically possible implement virtual network
micro-segmentation to restrict access to resources and to reduce the
scope of lateral movement in case of a compromise. A good use for this
kind of approach is an example where an enterprise has many applications
running in one cloud environment, some of which serve the public and
others that rely on sensitive information. Using micro-segmentation can
place them within different segments requiring different access
privileges.

## 5. Strong access control{ .article-section }

Users are given only the necessary access needed to be able to access
the applications they need at the level they need to perform their tasks
-- Principle of least privilege; the same applies to resources which
might need to communicate with other resources following the same
principle. Automate security group privileges and creation of new users
to least privilege by default. Implement MFA for privileged accounts.
Check systems are frequently tested for policy compliance.

## 6. 'Bastion' or 'Transit' VN{ .article-section }

Deploy 'Bastion' or 'Transit' Virtual Networks to connect multiple,
different cloud networks. It is especially advisable to use it for less
trusted or untrusted networks, including the Internet, to reduce the
cloud attack surface and minimize the risk of unauthorized access to
cloud resources.

## 7. Cloud web application defenses{ .article-section }

Use solutions such as web application firewalls and vulnerability
management for applications and unmanaged cloud resources.

## 8. Trust relationships assessment{ .article-section }

It is a critical part of the security communication strategy between a
cloud environment and on-premises resources. This is of relevance where
private clouds may be linked with on-premises assets on a regular basis.

## 9. Monitoring and detection capacity{ .article-section }

Enable cloud-native tools and technologies to watch out for hostile
activity and proof of compromise and identify and deploy audit logging
requirements.

## 10. Provisioning policies and resources lifecycles{ .article-section }

Apply policies defining who can provision resources, their types,
duration, and their placement. Implement automation to exclude human
error.

## **About this article**

This article was based on the 2021 IBM Security X-Force Cloud Threat
Landscape Report. To read the full report click [here.](https://www.ibm.com/downloads/cas/WMDZOWK6)



