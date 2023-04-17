+++
lang="en-GB"
title="TRITON’s Tactics and Techniques in the Enterprise domain + mitigations – Part 2"
date="2022-07-02"
author="Eugene Wypior"
image="/blog/Triton-TTs-Enterprise-64-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Today comes part 2 of the tactics, techniques, and specific threat actor activities as well as detection & mitigations for the TRITON malware in the Enterprise domain.

According to the ATT&CK matrix, after the malicious actor had established initial access to the targeted environment, their next step is the Execution phase, during which, the rogue actor creates his own accounts in the compromised system. This is then followed by the Persistence phase of operations enabling the actor to remain in the system.

As a reminder, TRITON malware was first identified during an attack on a Saudi Arabian petrochemical plant facility in the year 2017 and it targets Schneider Electric’s Triconex Tricon controllers. This was the first time in history that safety instrumented systems were targeted with the intention to fail, potentially leading to serious damage to property and humans.

![Triton Execution and Persistence](/blog/TRITON-ENT_2_2.png)

Next week, we will present the Defense Evasion Techniques of the TRITON malware.