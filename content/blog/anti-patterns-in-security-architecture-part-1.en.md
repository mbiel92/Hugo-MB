+++
lang="en-GB"
title="Anti-patterns in security architecture – part 1"
date="2022-10-04"
author="Eugene Wypior"
image="/blog/Anti_patterns_1_v3-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

An Anit-pattern is a common solution or repeated behaviour that is ineffective or has the potential to create more problems than the advantages it is supposed to bring. 

In security architecture, an anti-pattern is a system design that should be avoided for security reasons.

Here is a list of solutions that can cause potential problems, aka anti-patterns.

1.  ‘Browse-up’ for administration
2.  Management bypass
3.  Back-to-back firewalls
4.  Building an ‘on-prem’ solution in the cloud
5.  Uncontrolled and unobserved third-party access
6.  The un-patchable system 

## **‘Browse-up’ for administration**{ .article-section }

These days for a regular computer to operate off-line is most unusual. In practical terms, computers can be part of a global network of systems and devices. Some of these devices and networks are more trustworthy for a user, some less.

The less trusted systems (sometimes referred to as the low side) are those in which a user has less confidence in their integrity. The more trusted systems (or the high side) are those where confidence in integrity is higher. 

This anti-pattern is all to common and entails performing system administration tasks from a device less trusted than the system being administered.

How to know if you are ‘browsing-up’ for administration?

If you are performing administration activities via a remote desktop from a device that is part of a less trusted system, you are guilty of using this anti-pattern.

The same applies if you have less confidence in the integrity of a third-party device such as a remote desktop or shell to connect to a network, than your own.

And the most common example – is if you use the same device to read emails or browse the web as well as perform administrative tasks using a remote desktop or shell on the same device then you are browsing-up too. 

Better ‘browse-down’.

To avoid the possibility of system compromise, administration tasks of production systems should only be performed on high-integrity devices. Such devices should not natively be used to browse the web or open external email.

If one however decides to use the same device for less safe activities, one ought to ‘browse-down’. The ‘browse-down’ model implies that the risk activities are performed in a separate processing context which will depend on the user’s unique circumstances, but the aim is to ensure that should the activity in the less trusted environment lead to a compromise then the attacker would have no administrative access to the more trusted environment. This could be achieved for example by using a virtual machine on the administrative device to perform the activities on less trusted systems.

Read the next week’s blog entry to learn about further anti-patterns.

###### **About this article**

###### This post is based on an article from the NCSC UK. To read the full version of this article click [here.](https://www.ncsc.gov.uk/whitepaper/security-architecture-anti-patterns)