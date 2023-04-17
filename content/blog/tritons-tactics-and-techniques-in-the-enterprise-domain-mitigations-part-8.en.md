+++
lang="en-GB"
title="TRITON’s Tactics and Techniques in the Enterprise domain + mitigations – Part 8"
date="2022-07-13"
author="Eugene Wypior"
image="/blog/Triton-TTs-Enterprise-70-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

TRITON malware was first identified during an attack on a Saudi Arabian petrochemical plant facility in the year 2017 and it targets Schneider Electric’s Triconex Tricon controllers. This was the first time in history that safety instrumented systems were targeted with the intention to fail, potentially leading to serious damage to property and humans.

TRITON’s toolbox contains eleven of the fourteen tactics mapped by MITTRE ATT&CK Matrix for Enterprise, the universally renowned knowledge base of adversary tactics and techniques based on real-world observations. In this, 8th part of the TRITON posts, the Command and Control technics are presented.

In the MITTRE ATT&CK Enterprise matrix, Command and Control consists of techniques that adversaries may use to communicate with systems under their control within a victim network. Adversaries commonly attempt to mimic normal, expected traffic to avoid detection. There are many ways an adversary can establish command and control with various levels of stealth depending on the victim’s network structure and defenses.

The Technique used here is the Ingress Tool Transfer. Adversaries may transfer tools or other files from an external system into a compromised environment. Tools or files may be copied from an external adversary-controlled system to the victim network through the command and control channel or through alternate protocols such as [ftp](https://attack.mitre.org/software/S0095). Once present, adversaries may also transfer/spread tools between victim devices within a compromised environment (i.e. [Lateral Tool Transfer](https://attack.mitre.org/techniques/T1570)). 

![Triton's Command and Control techniques](/blog/TRITON-ENT_8.png)

###### **About this article**

This article was based on a Cybersecurity Advisory by CISA. You can read the full CSA [here.](https://www.cisa.gov/uscert/ncas/alerts/aa22-083a)

The Lateral Movement description came from the MITTRE ATT&CK website [here.](https://attack.mitre.org/tactics/TA0011/)
