+++
lang="en-GB"
title="Anti-patterns in security architecture – part 2"
date="2012-10-10"
author="Eugene Wypior"
image="/blog/Anti_patterns_2-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## Management bypass{ .article-section }

Defence-in-depth is a widely accepted approach to protecting the critical resources of a system. In addition, a good system architecture practice is to separate the data plane from the management plane. This separation can be achieved with network controls. It is however a common mistake to only apply the defense-in-depth approach to the data plane, and not to the management plane.

How to know if you are using a ‘management bypass?’

If you can access any management interface from components within different system layers from a single switch used for management, without the need to traverse the corresponding layers, then you have a management bypass anti-patters issue.

![How to identify a management bypass anti-pattern](/blog/IEC62443-_4_1_graphic.png)

Implement layered defenses in management planes

The obvious solution to this problem is to implement layered defenses like those used in data planes into the management plane.

Other good practices for securing the management interfaces include:

*   Ensuring privileged users carry out their administrative duties in a more trusted environment
*   Ensuring privileged users handle their email and web browsing in a separate less trusted environment
    *   Design the less trusted environment with anticipation of compromise so when it is compromised you are able to find out ‘when’ and ‘how’ while at the same time the breach doesn’t have a big impact on your important systems
*   Use strong authentication mechanisms including 2FA
*   Use different credentials for different layers to help prevent lateral movement
*   Protecting the exposure of management interfaces
    *   Expose management interfaces to a dedicated management network where possible
    *   Limit authorised IP addresses to those used by dedicated management services
    *   Deploy jump servers where management interfaces need to be exposed to less trusted networks
*   Restrict how systems on the data plane communicate with management plane infrastructure and vice-versa
*   Send log files to secure storage in real-time in case of the need for analysis of an attack

Read the next week’s blog entry to learn about further anti-patterns.

###### **About this article**

###### This post is based on an article from the NCSC UK. To read the full version of this article click [here.](https://www.ncsc.gov.uk/whitepaper/security-architecture-anti-patterns)