+++
lang="en-GB"
title="Cyber Threats - Detection, Response, Mitigation II"
date="2022-02-01"
author="Eugen Wypiór"
image="/blog/DRM-II-1.png"
tags=['ABC security','IT security', 'response&recovery']
+++

## **Mitigations**{ .article-section }

The following advice can enhance organisations' cyber resilience against cyber threats.


## **Preparedness**{ .article-section }

#### Establish Reporting Procedures and Ensure Cybersecurity staff continuity

Establish your 'go-to persons' list for the case of a suspected incident
with clear roles and responsibilities.

Ensure staff is aware of the list and know-how and when to report an
incident.

Cybercriminals are known to target organisations on weekends and
holidays to take advantage of the potential lack of cybersecurity
personnel onsite able to respond to an attack. Identify support IT/OT
security personnel who can be available on-demand to respond to an
incident. This is especially important in the case of Critical
Infrastructure organisations which should proactively protect themselves
by minimising gaps in coverage.

Assign IT/OT security personnel to monitor strategic internal security
capabilities and who are able to recognise unusual behaviour and flag
any identified Indicators of Compromise (IOCs) and Tactics, Techniques
and Procedures (TTPs) for instant response.

#### Design, keep up-to-date, and practice a Cyber Incident Response, Resilience and Business Continuity Plan

Design, keep up-to-date, and practice a Cyber Incident Response,
Resilience, and Business Continuity Plan.

Check that staff knows the main action plan points they need to follow
in case of an incident (Do they have the required access? Are they
familiar with the processes?)

**In the specific case of OT assets/networks**

Develop a resilience plan which considers how to ensure business
continuity in case of loss of control of the IT and/or OT environment.

Determine the interdependencies of the OT and IT networks and have
documented workarounds in place or manual controls to be able to isolate
ICS networks if the connections present risk to the safe and reliable
operation of OT processes. Drill contingency plans on a regular basis,
especially aspects relating to manual controls, so that in case of a
cyber incident safety-critical functions can be sustained. Verify that
the OT network can work at the required capacity even if the case were
the IT network is compromised.

Test manual controls regularly for critical functions can be operational
in case ICS or OT network must be taken offline.

Introduce data backup procedures on both the IT and OT networks. Run
backups frequently and regularly. Also, test backup procedures on a
regular basis ensuring backups are isolated from network connections.

Independently of the backup procedure, generate recovery documents
containing configuration settings for common devices and critical OT
equipment. These can speed up recovery from a cyber incident. 

## **Enhance your Organisation's Cyber Posture**{ .article-section }

#### Identity and Access Management

Require Multi-Factor Authentication (MFA) for all users, no exceptions.

Introduce a strong passwords policy for accounts. Prohibit the use of
the same password across multiple accounts or to be stored on a system
connected to the network.

Introduce a strong password policy for service accounts.

 Secure credentials using virtualising solutions, disabling the storage
of clear-text passwords in LSASS memory, and other techniques.

#### Protective Controls and Architecture

Identify, detect, and follow up unusual activity that could be the
indicator of a threat actor's or malware's lateral movements. Deploy
network monitoring tools and host-based logs and monitoring tools,
especially tools specifically useful for detecting lateral connections
such as an Endpoint Detection and Response (EDR) tool.

Enable strong spam filters to prevent phishing emails (including those
with executable files) from reaching end-users and raise user online
safety awareness.

 Implement fitting network segmentation between IT and OT networks as it
diminished the hacker's ability to infiltrate the OT infrastructure in
case the IT network is compromised.

Define a Demilitarized Zone (DMZ) that stops uncontrolled communication
between the IT and OIT networks.

Organise OT assets into logical zones by considering criticality,
consequence, and operational necessity. Define acceptable communication
conduits between the zones and deploy security controls to filter
network traffic and monitor communications between zones. Prohibit ICS
protocols from crossing the IT network.

#### Vulnerability and Configurations Management

Update operating systems, other software, applications, and firmware on
IT network assets, in a timely manner. Make patching known exploited
Common Vulnerabilities and Exposures (CVEs) your priority, followed by
critical and high vulnerabilities that allow for remote code execution
or denial-of-service on internet-facing equipment.

Use industry-recommended antivirus programs set to conduct regular scans
of IT network assets using up-to-date signatures.

 Disable all unnecessary ports and protocols.

 Ensure OT hardware is in read-only mode.

## Do you suspect your system might have been compromised?{ .article-section }

[SEQRED [offers comprehensive cybersecurity services
solutions.]{style="color: #000000;"}]{style="color: #e02b20;"}

To discuss your requirements, contact 
SEQRED [\[email protected\]](/cdn-cgi/l/email-protection)

###### **About this guide**

This article was written based on the joint Cybersecurity Advisory
authored by CISA. You can read it [here.](https://www.cisa.gov/uscert/ncas/alerts/aa22-011a)