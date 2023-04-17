+++
lang="en-GB"
title="Anti-patterns in security architecture – part 4"
date="2012-10-24"
author="Eugene Wypior"
image="/blog/Anti_patterns_4-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++


## Building an ‘on-prem’ solution in the cloud{ .article-section }

Cloud has now been around long enough for those who depend heavily on IT infrastructure to realise that moving their operations to the cloud is smart.

It is brilliant for many reasons. It gives you greater flexibility – you only pay for what you use, and you don’t have to tie a lot of capital long-term in technology, which is likely to be out of date by the time the investment has been returned. It shortens your time to market. It presents other cloud unique opportunities not available in an on-premises solution.

And so, when the time comes to shift to the cloud the enterprise will usually choose from one of the 6 most common migration strategies.

1.  Rehosting – aka ‘lift-and-shit’
2.  Replatforming – aka ‘lift-tinker-and-shitf’
3.  Repurchasing – moving to a different product
4.  Refactoring / Re-architecting – re-designing how an application is architecture and developed, typically using cloud-native features.
5.  Retire – get rid of.
6.  Retain – not to move to the cloud (temporarily anyway)

The first two migration strategies of rehosting and replatforming are guilty of being home to the anti-pattern of building an on-prem solution in the cloud – the first one more so than the second. The issue with these approaches is that an enterprise retains most of the same problems as it had within its on-prem structure including maintenance overheads for patching operating systems and software packages. These solutions are also likely to deprive the enterprise of the benefit of auto-scaling features so characteristic of the cloud. Interestingly enough, according to AWS, the rehosting solution, without implementing any cloud optimisation, could save roughly 30% of its costs in some cases.

How to identify this anti-pattern? 

Look for:

*   Database engines, files stores, load balancers, and security appliances installed on compute instances
*   Separate development as well as test, reference, production, and other environments running 24/7
*   Virtual appliances are used without considering whether cloud-native controls would be suitable

![Anti patterns in security architecture](/blog/Anti_patterns_4_graphic.png)

Best to use cloud-native features

The best approach from the migration strategies is to refactor or re-architect the solutions available on-prem using cloud-native features. In this way features, scale or performance can be added that would otherwise be difficult to achieve in the application’s existing environment. If in addition this is merged with using higher-order functions – as in the case of Platform as a Service – benefits of this solution would also include:

*   Reduction of unnecessary infrastructure management overhead
*   Ability to focus on areas of the enterprise’s unique know-how

Read the next week’s blog entry to find out about other anti-patterns.

###### **About this article**

###### This post is based on an article from the NCSC UK. To read the full version of this article click [here.](https://www.ncsc.gov.uk/whitepaper/security-architecture-anti-patterns)