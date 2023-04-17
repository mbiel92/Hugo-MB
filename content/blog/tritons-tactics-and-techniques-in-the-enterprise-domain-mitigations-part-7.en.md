+++
lang="en-GB"
title="TRITON’s Tactics and Techniques in the Enterprise domain + mitigations – Part 7"
date="2022-07-06"
author="Eugene Wypior"
image="/blog/Triton-TTs-Enterprise-69-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

TRITON malware was first identified during an attack on a Saudi Arabian petrochemical plant facility in the year 2017 and it targets Schneider Electric’s Triconex Tricon controllers. This was the first time in history that safety instrumented systems were targeted with the intention to fail, potentially leading to serious damage to property and humans.

TRITON’s toolbox contains eleven of the fourteen tactics mapped by MITTRE ATT&CK Matrix for Enterprise, the universally renowned knowledge base of adversary tactics and techniques based on real-world observations. In this, 7th part of the TRITON posts, the Collection technic is presented.

In the MITTRE ATT&CK Enterprise matrix, Collection consists of techniques adversaries may use to gather information and the sources information is collected from that are relevant to following through on the adversary’s objectives. Frequently, the next goal after collecting data is to steal (exfiltrate) the data. Common target sources include various drive types, browsers, audio, video, and email. Common collection methods include capturing screenshots and keyboard input.

![Triton's Tactics and Technics in the Enterprise domain with mitigations](/blog/TRITON-ENT_7-1.png)

Next week, we will present the Command and Control techniques of the TRITON malware.

###### **About this article**

This article was based on a Cybersecurity Advisory by CISA. You can read the full CSA [here.](https://www.cisa.gov/uscert/ncas/alerts/aa22-083a)

The Lateral Movement description came from the MITTRE ATT&CK website [here.](https://attack.mitre.org/tactics/TA0008/)
