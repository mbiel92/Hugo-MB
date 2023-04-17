+++
lang="en-GB"
title="TRITON’s Tactics and Techniques in the Enterprise domain + mitigations – Part 6"
date="2022-07-29"
author="Eugene Wypior"
image="/blog/Triton-TTs-Enterprise-68-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

TRITON malware was first identified during an attack on a Saudi Arabian petrochemical plant facility in the year 2017 and it targets Schneider Electric’s Triconex Tricon controllers. This was the first time in history that safety instrumented systems were targeted with the intention to fail, potentially leading to serious damage to property and humans.

TRITON’s toolbox contains eleven of the fourteen tactics mapped by MITTRE ATT&CK Matrix for Enterprise, the universally renowned knowledge base of adversary tactics and techniques based on real-world observations. In this, 6th part of the TRITON posts, the Lateral Movement technic is presented.

In the MITTRE ATT&CK Enterprise matrix, Lateral Movement consists of techniques that adversaries use to enter and control remote systems on a network. Following through on their primary objective often requires exploring the network to find their target and subsequently gaining access to it. Reaching their objective often involves pivoting through multiple systems and accounts to gain. Adversaries might install their own remote access tools to accomplish Lateral Movement or use legitimate credentials with native network and operating system tools, which may be stealthier.

![Triton's Tactics and Technics in the Enterprise domain with mitigations  - Lateral Movement](/blog/TRITON-ENT_6.png)

Next week, we will present the Collection techniques of the TRITON malware.

###### **About this article**

This article was based on a Cybersecurity Advisory by CISA. You can read the full CSA [here.](https://www.cisa.gov/uscert/ncas/alerts/aa22-083a)

The Lateral Movement description came from the MITTRE ATT&CK website [here.](https://attack.mitre.org/tactics/TA0008/)
