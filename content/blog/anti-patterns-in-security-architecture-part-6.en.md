+++
lang="en-GB"
title="Anti-patterns in security architecture – part 6"
date="2012-11-08"
author="Eugene Wypior"
image="/blog/Anti_patterns_6-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++


## The un-patchable system{ .article-section }

There are systems that can’t stop and must be operational all around the clock. This is a lack of design foresight as such systems can’t have security patches applied without scheduling a downtime window. And the more complex the system, and depending on implemented technologies, the length of time required to patch might turn out impossible to schedule due to the role the system plays.

The worst choice in such scenarios is for the patches to be deferred in time until a point when their application would require a considerable downtime window which in practical terms means, the system keeps on going unpatched and becomes un-patchable.

#### How to identify this anti-pattern?

Identify the lack of redundancy within the system architecture.

Systems requiring all elements to be operational all the time are not suited for phased upgrades – where the system can remain operational, whilst non-active components undergo maintenance.

![The un-patchable system](/blog/Anti_patterns_6_graphic.png)

#### Solution – design for easy maintenance little and often

Design systems with the necessity for maintenance and patching in mind. This could mean incorporating a certain percentage of resource redundancy which can be then used to facilitate maintenance while allowing the system to remain operational without a break. Or it could mean designing the system in a way where patches can be applied in phases, without the need to disrupt operations. This is likely to incur higher onset infrastructure costs, but in long run, the overall costs of running the system should be lower due to:

*   Fewer and shorter outages
*   Reduced risk of compromise (which can be costly and potentially result in irreparable loss such as loss of customer trust)

###### **About this article**

###### This post is based on an article from the NCSC UK. To read the full version of this article click [here.](https://www.ncsc.gov.uk/whitepaper/security-architecture-anti-patterns)