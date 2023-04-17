+++
lang="en-GB"
title="Cyber Kill Chain - what is it and how to use it to stop advanced methods of attack?"
date="2020-08-05"
author="Sylwia Sławińska"
image="/blog/cyber-kill-chain-process.png"
+++

Recently the number of cyberattacks has increased year on year. It is
also estimated that the number of attacks conducted with the use of
[ransomware](https://seqred.pl/en/ransomware/) increases by 350%¹ each
year. Additionally, the Covid19 pandemic has caused an increase in the
number of malicious emails by 600%². An understanding of the
characteristics of attacks and strategies used by attackers is one of
the key ways of protection against potential attacks.

Cybersecurity experts have created a few models showing the
characteristics of attacks. They have described the various stages of
attacks as well as the methods and techniques used by attackers. The
following article is an introduction to the Cyber Kill Chain model --
the stages of the process and the methods of attack mitigation on each
stage of that process.

#### **In this article, we will discuss:**

-   what is the Cyber Kill Chain?
-   where does the term originate?
-   according to the Cyber Kill Chain framework, what are the stages of
    a cyber attack?
-   what security measures can be put in place to protect you from each
    stage of a cyber attack?
-   what are the ways for this framework to be used in practice?
-   the faults of the Cyber Kill Chain model.

In subsequent articles, we will also introduce: the Diamond Model, the
Mitre [\[email protected\]](/cdn-cgi/l/email-protection){.__cf_email__
cfemail="d392a7a793b0b8"} and the ICS kill chain model, we will also
discuss the specifics of using each of those models and compare their
advantages and disadvantages.

## What is the Cyber Kill Chain?

**The Cyber Kill Chain** is a model clearly illustrating the framework
of a successful cyber attack. It sorts actions taken by attackers into
systemised stages, from gathering information about a target, through
preparing all necessary tools and delivering the malware, to finally
completing the goal of an attack. The model can help us get a better
understanding of various types of attacks, including data theft,
advanced persistent attacks (ATPs), attacks conducted using malware and
be more prepared to handle them when they occur. Thanks to a good
understanding of the Cyber Kill Chain, IT security management teams can
use strategies and technologies designed to break the chain of invasive
actions and stop the attack.\

## Cyber Kill Chain- a military approach to attacks

The term „kill chain" was originally used by the military, in the
context of describing stages of attacks. A particular military kill
chain framework, called "F2T2EA", consists of the following stages:

**1.** **Find** -- identify the target,

**2.** **Determine** -- determine the
target's location,

**3.** **Route** -- monitor the target's
movement,

**4.** **Target** -- choose an adequate
measure to use on the target,

**5.** **Implementation** -- use the chosen
measure to conduct an attack,

**6.** **Review** -- review the attack's
efficiency.

This integrated, complex process, described as a chain because its
stages resemble the links of a chain (and breaking of those chains would
put the process on halt) is an effective method of protection and
prevention of attacks.

## The Stages of a Cyber Kill Chain

In 2011, Lockheed Martin applied the structure of a military kill chain
to information security, interpreting it as a method of conducting an
attack on an information network. Martin created a chain with the
following stages:

## How the Cyber Kill Chain can help you protect against attacks

### Reconnaissance

The attacker acquires all necessary information about the target with
the use of either manual methods or automated scanners designed for
mapping organizational structures, locating any security gaps and
vulnerabilities which can be exploited. The attacker's goal is to
identify and investigate security systems such as: firewalls, intrusion
prevention systems and authentication mechanisms. OSINT tools are often
use in this instance in order to access necessary information.

**Objective of defense:** detection of attempts to scan or gather
information by an attacker.

**Method of defense:**

-   periodical analysis of the visibility of the information about the
    company as well as its employees online and in publicly available
    registers(np. [e.g. Shodan](https://seqred.pl/en/shodan-improved//))
    and taking corrective actions (e.g. deleting undesirable content),
-   regularly checking logs to see who has accessed the company's
    website,
-   using tools designed to detect actions typical for the attacker to
    take during the reconnaissance phase of an attack, e.g. conducting
    network or domain scans.

### Weaponization

Attackers use the information gathered during the reconnaissance phase
to create malware and ways to exploit found vulnerabilities. Because
almost all of the attacker's actions are taken "on his side", halting
and them during this phase is essentially impossible. During this phase,
it is recommended to focus on identifying vulnerabilities and strong
points of each device and system and prepare for an attack. The
identification of vulnerabilities allows us to determine which elements
of our security could serve as a gateway for an attacker and should
therefore be treated with particular attention.

**Objective of defense:** identification of vulnerabilities and methods
of providing adequate security to key resources.

**Methods of defense:**

-   identification and upkeep of up to date information about kept and
    protected resources,
-   identification of vulnerabilities within your organization as well
    as hardening of key resources,
-   monitoring and analysing new vulnerabilities and installing updates
    containing patches,
-   using threat intelligence to recognise and prepare for possible new
    vulnerabilities.

### Delivery

Attackers attempt to deliver malware to organisations' systems or to
exploit identified weaknesses. A popular way of delivering malware is
through sending links or attachments using phishing techniques.

**Aim of defence:** to detect and prevent downloading malicious code.

**Methods of defense:**

-   increasing the level of threat awareness by educating employees and
    associates,
-   implementing additional security measures, including firewalls,
    anti-virus programs, sandboxes and other endpoint protection tools,
-   use of anti-spam mechanisms,
-   network traffic monitoring to identify and actively block threats
    based on the origin and content of packets.

### Exploitation

Using an identified vulnerability in a system to execute malicious code
provided by an attacker.

**Aim of defense:** preventing the execution of malicious software.

**Methods of defence:**

-   using SIEM (Security Information and Event Management) software to
    investigate logs and perform analyses to identify suspicious
    activities,
-   using endpoint protection tools such as EDR (endpoint detection &
    response),
-   teaching users to recognise malware and respond appropriately,
-   using threat intelligence solutions, supplying knowledge bases of
    devices providing protection against viruses, IPS or IDS.

### Installation

Installing malware on a system to gain remote access to the environment.

**Aim of defense:** wdetecting an attacker in order to prevent him
gaining access to managing operations.

**Methods of defence:**

-   HIPS (Host-based Intrusion Prevention System) to warn or block a
    trial installation on common paths,
-   periodic inspections of changes in the system's configuration
    compared to the standard configuration (baseline),
-   checking the certificates of all signed executable files,
-   separation and segregation of rights in order to prevent an
    installation,
-   two-factor authentication.

### Command and control (C2)

An attacker uses the command console to remotely execute commands on the
attacked computer to maintain and develop the attack.

**Aim of defense:** to detect and disrupt communication between the
target and the attacker.

**Methods of defence:**

-   requiring the use of internal proxy servers for all types of traffic
    (including http, DNS),
-   DNS sinkholes (DNS server returning invalid domain names) and cache
    poisoning,
-   passive monitoring of network traffic and archiving metadata on
    conversations between network components,
-   network monitoring using NIDS (network Intrusion Detection System)
    to detect unusual activities.

### Action on objectives

In the final stage, the attacker pursues the objectives of an attack,
e.g.: leaking data (violation of data confidentiality), data
modification (violation of data integrity) or system encryption
(violation of data availability).

**Aim of defense:** stopping the attacker's actions.

**Methods of defence:**

-   monitoring database activity,
-   immediate response of experts to alerts,
-   creating a plan for security incident response,
-   implementing crisis communication processes,
-   processing sensitive data in separate ICT networks or using separate
    stations,
-   using encryption methods for processed data (e.g. data carrier
    encryption, e-mail encryption),
-   systematic backup on off-line media.

## Methods of disrupting attacks

To interrupt the Cyber Kill Chain, the following types of defensive
actions can be taken:

**1.** **Detect** -- determine when and how
the attacker performs a reconnaissance of an organisation or network,

**2.** **Deny** -- stop the attack by making
revealing sensitive information and unauthorized access impossible,

**3.** **Disrupt** -- change or stop
information flow or data leakage,

**4.** **Degrade** -- limit the effectiveness
and efficiency of the attack,

**5.** **Deceive** -- disrupt an attack by
misleading or misinforming the attacker,

**6.** **Contain** -- limit the scope of an
attack to particular segments of the network or organization.

## Cyber Kill Chain Control Matrix

Knowledge of the kill chain stages, defensive actions and solutions
which can be used against attackers, allows to create a Cyber Kill Chain
Control Matrix. Its purpose is to identify the control mechanisms that
the organisation has implemented as safeguards for each stage of an
attack and to determine how they can contribute to disrupt, stop or
eliminate a cyber attack.

An example of Cyber Kill Chain Control Matrix:

![](/blog/cyber-kill-chain-table.png)

The presented matrix can be used as a template to identify resources and
assign them roles in system protection, making it is easier to identify
the stages in which our resources can provide accurate protection
against an attack. This template can help identify which resources would
be sufficient protection an attack and in which stages additional
protection is needed.

## Disadvantages of the classic Cyber Kill Chain model

Lockheed Martin's Cyber Kill Chain model used as a risk assessment tool
is not a perfect model. Its main disadvantage is that its methodology is
based on network security and prevention of malware and aimed at
reinforcing traditional defence strategies. Unfortunately, these are not
the only vectors of attacks. Because traditional kill chains in
cyberspace are not suitable for handling internal threats, e.g. one
caused by employees of a given company, there is a need to develop
separate strategies to deal with attackers coming from within the
organisations. Additionally, the first stages taking place outside the
defended network a disadvantage to the attacked system, making the
process of identifying or defending against attackers' actions very
challenging in these stages.

## Applying the Cyber Kill Chain

In the 9 years since the creation of the Cyber Kill Chain, the
technology and methods of conducting attacks have evolved significantly
and new attack vectors and ways of utilising them have emerged. Now, the
attackers tend to skip the individual stages of this model, adding new
steps or repeating them, although the Cyber Kill Chain remains widely
used.\
The model allows to determine the level of security as well as to
prevent and significantly reduce the effects of a potential attack.

Cyber Kill Chain is one of several methods of understanding the course
of cyber attacks. Over the past few years, a number of other detailed
models of hostile actions have emerged.

In our next few articles, we will present the diamond model, Mitre
[\[email protected\]](/cdn-cgi/l/email-protection){.__cf_email__
cfemail="c786b3b387a4ac"} and the kill chain model for ICS, discuss
their use and compare the pros and cons of all the described models.

**Sources:**

**1.** [Cyber Security Statistics for
2019](https://www.cyberdefensemagazine.com/cyber-security-statistics-for-2019)

**2.** [ONZ: podczas pandemii liczba
złośliwych e-maili wzrosła o 600
proc.](https://www.cyberdefence24.pl/onz-podczas-pandemii-liczba-zlosliwych-e-maili-wzrosla-o-600-proc)

**3.** [Gaining the Advantage -- Applying
Cyber Kill Chain® Methodology to Network
Defense](https://www.lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/Gaining_the_Advantage_Cyber_Kill_Chain.pdf)

**4.** [How the Cyber Kill Chain can help you
protect against
attacks](https://sbscyber.com/resources/how-the-cyber-kill-chain-can-help-you-protect-against-attacks)

## Want to find out more about tehe Cyber Kill Chain? 

[Contact us](/en/contact/)