+++
lang="en-GB"
title="Cyber Threats - Detection, Response, Mitigation I"
date="2022-01-25"
author="Eugen Wypiór"
image="/blog/DRM-1.png"
tags=['ABC security','IT security', 'response&recovery']
+++

The number of cyberattacks on businesses is constantly rising. According
to surveys conducted by Accenture there were on average 270 attacks per
company in 2021 which is a 31% increase compared with 2020.

 A heightened state of awareness and ability to conduct proactive threat
hunting and the implementation of mitigating procedures is what will
improve organisations and businesses to improve functional resilience by
reducing the risk of compromise or severe business degradation.

This two-part guide provides practical advice on threat detection,
incident response, and mitigations of cyberattacks' effects on IT and OT
infrastructure.


## **1. Detection**{ .article-section }

Implement strong log collection and retention. Organisations lacking a
centralised log collection and monitoring have a limited ability to
investigate incidents or detect threat actors' behaviour.

Look for behavioural evidence or network and host-based artefacts from
the depository of known Tactics, Techniques and Procedures (TTPs). Use
the MITRE ATT&CK for Enterprise framework for reference

For login credentials in particular:

To detect brute password guessing and password spraying activity review
authentication logs for system and application login failures of valid
accounts. Look for multiple, failed authentication attempts across
multiple accounts.

To detect if compromised credentials were used combined with a Virtual
Private Server look for:

-   Suspicious 'impossible login' activity. This could be logins with
    changing username, user agent strings, and IP address combinations;
    or logins where the IP address does not match with the geographic
    location expected for the user
-   Also, one IP used for multiple accounts (except where expected)
    should be flagged up as a possible threat.
-   " Impossible travel" (i.e. where a user seems to be logging in from
    multiple IP addresses that are at such geographical distance that a
    person couldn't possibly travel between these locations during the
    time period between the logins -- this might result in false
    positives if legitimate users deploy VPN solutions)
-   Unusual user agent strings which may indicate bot activity
-   Unusual activity in typically dormant accounts
-   suspicious privileged account use after resetting passwords or
    applying user account mitigations

In the case of OT/ICS systems take note of unexpected equipment
behaviour, such as random reboots of digital controllers and other OT
hardware and software. Also, record delays or disruptions in
communication with field equipment or other OT devices. Check if system
parts or components are lagging or are unresponsive.

## **2. Incident Response**{ .article-section }

If an organisation detects a potential stealthy threat actor has gained
unauthorised access to their IT or IT network, they should immediately:

-   Isolate affected systems
-   Secure backups making sure backup data is offline and safe. Whenever
    possible the backup should be scanned with antivirus software to
    ensure it is malware-free
-   Collect and review relevant logs, data, and artifacts
-   Ensure the threat has been irreversibly eradicated from the network
    (avoid residual issues that could enable follow-on exploitation. If
    sufficient expertise is not available in-house, consider obtaining
    support from a third-party IT Cybersecurity specialist
-   Depending on the particulars of the incident you might want (or
    must) report it to relevant stakeholders and relevant authorities

In the case of enterprises with OT assets or CI nature a resilience plan
should be in place which regulates how to operate if they lose access or
control of, the IT and/or OT environment.

## What's next?{ .article-section }

Next week you will find out how to mitigate the effects of a cyber
threat.

## Do you suspect your system might have been compromised?{ .article-section }

[SEQRED [offers comprehensive cybersecurity services
solutions.]{style="color: #000000;"}]{style="color: #e02b20;"}

[[To discuss your requirements, contact
SEQRED at [\[email protected\]](/cdn-cgi/l/email-protection)

#### **About this guide**

This article was written based on the joint Cybersecurity Advisory authored by CISA. You can read it [here.](https://www.cisa.gov/uscert/ncas/alerts/aa22-011a)
To read the full survey by Accenture click [here.](https://www.accenture.com/_acnmedia/PDF-165/Accenture-State-Of-Cybersecurity-2021.pdf)