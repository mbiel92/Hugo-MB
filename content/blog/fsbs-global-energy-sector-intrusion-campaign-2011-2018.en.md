+++
lang="en-GB"
title="FSB's Global Energy Sector Intrusion Campaign 2011-2018"
date="2022-03-28"
author="Eugen Wypiór"
image="/blog/FSBGlobalCampaign31.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Last week, on Thursday, the 24th of March 2022 the US Justice
Department officially charged four Russian officials accusing them of
carrying out hundreds of cyberattacks targeting critical infrastructure
facilities worldwide. The list of affected countries includes Saudi
Arabia and the United States where, among other enterprises, the men
hacked the Wolf Creek Nuclear Operation Corporation, which runs a
nuclear plant in Kansas.

The accused are [three Russian Federal Security Service (FSB) agents and a Russian Federation Central Scientific Research Institute of Chemistry and Mechanics (TsNIIKhM) [employee].
The three FSB officers are all believed to be members of a cybercrime
unit within the FSB known as 'Berserk Bear', 'Energetic Bear',
'Dragonfly', 'Crouching Yeti', 'Koala' or 'Havex'

On the same day the CISA together with the FBI and DOE issued a joint
Cybersecurity Advisory (CSA) relating to these indictments breaking down
the hacking campaign into two main areas:

## 1. Global Energy Sector Intrusion Campaign, 2011 to 2018{ .article-section }

Starting as far back as 2011 through 2018 the three FSB agents gained
unauthorised remote access to computer systems of oil and gas, energy,
nuclear power plant, and utility companies in the US and worldwide. They
deployed malware designed to collect ICS-related information on
compromised networks and exfiltrated enterprise and ICS data.

Since the year 2013, they used now commonly known and well-documented
Tactics, Techniques, and Procedures (TTPs) to gain access to the
victims' networks.

The TTPs included:\
- spearphishing emails,\
- redirects to compromised websites -- watering hole,\
- malicious versions of legitimate software updates on multiple ICS
vendor websites.

One such malicious code incorporated in software updates was the Remote
Access Trojan (RAT) Havex, which via a command and control (C2) server
allows for the installation of additional malware on infected systems,
extracting data, including system information, lists of files and
installed programs, e-mail address books, and virtual private network
(VPN) configuration files.

Starting from 2016 the hackers began widely targeting the US Energy
Sector using the above methods. Having illegally accessed compromised
networks the actors conducted network discovery, moved laterally, and
gained persistence. They then exfiltrated crucial information from the
enterprises including their operational technology environments such as
vendor information, reference documents, ICS architecture, and layout
diagrams.

This behaviour is common for Russian hacking groups, who will often
study critical infrastructure, subsequently compromise it, and then stay
seemingly passive for months or years without taking visible action.

## 2. Compromise of a Saudi Arabia petrochemical plant in 2017 with the use of TRITON{ .article-section }

According to the indictments, a cyber actor with ties to the Russian
Federation Central Scientific Research Institute of Chemistry and
Mechanics (TsNIIKhM) is accused of having infiltrated a foreign
petrochemical plant with the use of the TRITON (a.k.a HatMan) malware in
2017, leading to two emergency shutdowns at the facility. It is believed
that the real purpose for this intrusion was to trigger an explosion but
a mistake in the code prevented from this to happen.

TRITON is a custom-built, sophisticated, multi-stage malware affecting
Schneiders Electric's Triconex Tricon, a safety programmable logic
controller (PLC) (also known as a safety instrumented system \[SIS\]),
which monitors industrial processes to prevent hazardous conditions.

TRICON malware affects Triconex Tricon PLCs by modifying in-memory
firmware to add additional programming. The extra functionality allows
an attacked to read/modify memory contents and execute custom code,
disabling the safety system. As the Triconex systems are used in many
environments, the capacity to disable, inhibit or modify the ability of
a process to fail safely could result in physical consequences.

###### **About this article**

###### This article was based on a Cybersecurity Advisory by CISA. You can read the full CSA [here](https://www.cisa.gov/uscert/ncas/alerts/aa22-083a)
