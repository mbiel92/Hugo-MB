+++
lang="en-GB"
title="TRITON’s Tactics and Techniques in the Enterprise domain + mitigations – Part 1"
date="2022-05-26"
author="Eugene Wypior"
image="/blog/Triton-TTs-Enterprise-63_1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Today we continue looking at the tactics, techniques, and specific threat actor activities as well as detection & mitigations for the TRITON malware in the Enterprise domain. As the Tactics deployed by TRITON’s operators cover almost all of the Tactics mapped by ATT&CK we decided to divide the original source provided by the Cybersecurity and Infrastructure Security Agency into several parts.

As a reminder, TRITON malware was first identified during an attack on a Saudi Arabian petrochemical plant facility in the year 2017 and it targets Schneider Electric’s Triconex Tricon controllers. This was the first time in history that safety instrumented systems were targeted with the intention to fail, potentially leading to serious damage to property and humans.

In this part 1, we present the first three Tactic categories with related Techniques in the ATT&CK matrix – Reconnaissance, Resource Development and Initial Access
{{< row >}}
![TRITON Tactic and Technics with Mitigations in the Enterprise domain](/blog/TRITON-ENT_1.png)
{{< /row >}}
Next week, we will present the Execution and Persistence Techniques of the TRITON malware.