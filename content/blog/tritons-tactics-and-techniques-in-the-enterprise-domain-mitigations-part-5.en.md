+++
lang="en-GB"
title="TRITON’s Tactics and Techniques in the Enterprise domain + mitigations – Part 5"
date="2022-07-22"
author="Eugene Wypior"
image="/blog/Triton-TTs-Enterprise-67-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

TRITON malware was first identified during an attack on a Saudi Arabian petrochemical plant facility in the year 2017 and it targets Schneider Electric’s Triconex Tricon controllers. This was the first time in history that safety instrumented systems were targeted with the intention to fail, potentially leading to serious damage to property and humans.

TRITON’s toolbox contains eleven of the fourteen tactics mapped by MITTRE ATT&CK Matrix for Enterprise, the universally renowned knowledge base of adversary tactics and techniques based on real-world observations. In this, 5th part of the TRITON posts, the Discovery Technics are presented.

In the MITTRE ATT&CK Enterprise matrix, the hacker’s tactic focused on mapping the target’s environment is called Discovery and consists of technics aimed at gaining knowledge about the target’s system and internal network. During this stage, the adversary observes the compromised environment exploring the topography around their entry point to see how it could benefit their current objective. They explore what elements of the system they can take control of. System tools native to the operating system are often used to achieve this goal of gathering information that takes place after access has been gained.

![Triton's Tactics and Technics in the Enterprise domain with mitigations](/blog/TRITON-ENT_5.png)

Next week, we will present the Lateral Movement techniques of the TRITON malware.

###### **About this article**

This article was based on a Cybersecurity Advisory by CISA. You can read the full CSA [here.](https://www.cisa.gov/uscert/ncas/alerts/aa22-083a)
