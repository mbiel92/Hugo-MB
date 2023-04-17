+++
lang="en-GB"
title="TRITON’s Tactics and Techniques in the ICS domain"
date="2022-05-05"
author="Eugene Wypior"
image="/blog/Triton-TTP-ICS-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

TRITON malware was originally deployed in 2017 to disrupt the operations of a petrochemical plant in Saudi Arabia and it has recently made headlines on the occasion of an indictment by the U.S Department of Justice in a case of a Global Energy Sector Intrusion Campaign that lasted from 2011 to 2018.

TRITON has the capability to reprogram Schneider Electric’s Triconex Tricon controllers with custom attacker-defined payloads when a Triconex device is running in ‘Program’ mode. These controllers belong to the class of safety instrumented systems and are supposed to be triggered if they detect dangerous conditions, as a last line of defence to prevent disasters that might cost human lives, returning industrial processes to safe levels or alternatively shutting them down altogether. This was the first time in the history of Industrial Control Systems that these safety instrumented systems were targeted to fail.

According to Dragos, a U.S cybersecurity consultancy, the malicious actor which engineered and deployed TRITON in Saudi Araba has been using some degree of the same technology to aim at targets in other parts of the world including North America.

The Cybersecurity & Infrastructure Security Agency has recently published a Cybersecurity Advisory which details mitigations and ICS Best Practices (please refer to SEQRED’s recent OT Thursdays entries). Below are TRITON’s capabilities mapped to the ATT&CK for ICS framework from the same advisory.

![Triton Tactics & Technics](/blog/Triton-TTPs-CIS-659x1024.png)

###### **About this article**

This article is based on CISA’s Alert (AA22-083A).  You can read the full advisory [here.](https://www.cisa.gov/uscert/ncas/alerts/aa22-083a)
