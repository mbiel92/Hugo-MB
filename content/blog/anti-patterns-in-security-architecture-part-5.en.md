+++
lang="en-GB"
title="Anti-patterns in security architecture – part 5"
date="2012-11-01"
author="Eugene Wypior"
image="/blog/Anti_patterns_5-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++


## Uncontrolled and unobserved third-party access{ .article-section }

These days more and more enterprises outsource support for some or all of their systems to a third party. If an enterprise does this, it becomes dependent on another organisation’s security standards and procedures to keep its own system secure.

To administer the enterprise’s system, the third party will often require remote access. It is common practice to allow third parties to have access through a bastion host, either over the internet from an allowed list of locations, or over a private network. However, there are often not enough controls in place to limit the operations that can be performed via the bastion host. If this is the case, and a bastion host (or the device used by the third-party) is compromised, then an attacker could gain significant access to connected systems.

The risk of third-party compromise can be greatly reduced by locking these accesses down and efficiently auditing the connection.

#### How to identify this anti-pattern?

Look for ‘umbilical cords’ out of network diagrams to find possible uncontrolled and unobserved third-party access.

![Uncontrolled and unobserved third-party access](/blog/Anti_patterns_5_graphic.png)

#### Best practices to prevent this anti-pattern:

A good contract

*   Choose third parties carefully with a contract that particularly specifies the controls relating to the people, processes and technology that will be used for the service in question.

Constrained access

*   Apply the principle of least privilege only allowing remote and authenticated users to have logical access to the systems they need to reach in order to constrain access.

A thorough audit trail

*   Ensure you have the audit trail you need to support incident response and support effective protective monitoring.

Ask your supplier

*   Ask your supplier how they prevent attackers from moving laterally between their other clients and your systems.

Multi-factor authentication 

*   Ensure that remote support staff use multi-factor authentication and ensure they do not share credentials – this will help to account for individual actions in event of a breach.

Isolated third-party access

*   Provide separate isolated third-party access systems for different third parties.

Read the following week’s blog entry to find out about other anti-patterns.

###### **About this article**

###### This post is based on an article from the NCSC UK. To read the full version of this article click [here.](https://www.ncsc.gov.uk/whitepaper/security-architecture-anti-patterns)