+++
lang="en-GB"
title="Anti-patterns in security architecture – part 3"
date="2012-10-18"
author="Eugene Wypior"
image="/blog/Anti_patterns_3-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++


## Back-to-back firewall{ .article-section }

Some wrongly believe that there is a security benefit in ‘doubling up’ on firewalls to implement the same set of controls. In addition, some believe it is beneficial if the two firewalls come from different manufacturers. The thinking behind the second part is that coming from different sources will not have the same vulnerabilities. But all such a solution brings is additional costs, complexity, and maintenance overheads.

 After all, in the case of a standard OSI layer 3/4 firewall all it does is allow to pass (or not) communication according to its settings. Putting two firewalls with the same set of settings, back-to-back is like straining pasta with two same-grade strainers. 

Some people might ask ‘But what if there is a vulnerability that can be exploited in one firewall, but not the other?’ Although it is always possible that there might be a vulnerability in a device, firewalls don’t tend to have vulnerabilities that can be exploited to yield code execution from processing the header of a TCP/IP packet. The vulnerabilities possible to occur in a firewall will be present in their management interfaces. The solution to this problem is not to expose their management interfaces to untrusted networks.

How to know if you are using a back-to-back firewall solution?

Look for two firewalls in series in a network architecture diagram.

![Figure 1 – How to identify a back-to-back firewall anti-pattern (Security architectures anti-patterns. Six design patterns to avoid when designing computer systems. Rich Crowther; NCSC)](/blog/Anti_patterns_3_graphic.png)

Better do it once but well

Rather than for a peculiar reason have two firewalls, maintain well, and configure well one firewall or network appliance. You can achieve this by applying these simple good practices:

*   Prevent exposing the management interfaces of network appliances to untrusted networks, and properly manage the credentials used with them (always change vendor-supplied default settings for your own)
*   Have a simple policy configuration to minimise the possibility of accidental mistakes
*   Deploy configuration management tools to ensure you know what the configuration should be, so you can tell when it isn’t correct

There is always an exception

What would life be without exceptions – two firewalls back-to-back make sense if they act as a contract enforcement point between two entities that are connecting to each other. If both parties agree on which subnets in their respective networks can communicate using which protocols, then both can ensure this is enforced by applying the agreed controls on a firewall they each manage.

Read the next week’s blog entry to learn about other anti-patterns.

###### **About this article**

###### This post is based on an article from the NCSC UK. To read the full version of this article click [here.](https://www.ncsc.gov.uk/whitepaper/security-architecture-anti-patterns)