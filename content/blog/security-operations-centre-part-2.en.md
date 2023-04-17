+++
lang="en-GB"
title="Security Operations Centre – part 2"
date="2021-12-14"
author="Eugene Wypior"
image="/blog/SOCp2-2.png"
tags=['ABC security','IT security', 'response&recovery']
+++

> ## **You can only truly protect what you know you have**{ .article-section }

#### 1\. Asset inventory  

You must understand what your assets are in order to understand what you are going to protect. Make sure you have identified all the devices that are on your network as well as what systems, applications, and services have been installed and are running on them.

A thorough inventory of assets will contain not only the name of the asset but the asset’s description, criticality, operating system, business owner, technical owner, location and configuration, and vulnerabilities information.

And as new elements are added to the company’s digital landscape over time deploying an automated tool for the purpose of discovering new assets is a natural extension of keeping your inventory always current and up to date.

#### 2\. Vulnerability assessment  

In the process of inventorying your assets, identifying and eliminating vulnerabilities inherent in them improves the business’s security posture reducing the attack surface. The hardening of the IT landscape is not a one-off event though. It is an ongoing process. In addition to the benefit of increasing the infrastructure’s security, the enterprise might be required to undergo periodical vulnerability assessments to be compliant with contractual and regulatory requirements.

#### 3\. Baseline  

Establish and understand the baseline of your system and network behaviour. What is the ‘picture’ of the system in its natural state of operation? If you have a ‘picture’ of your system’s behaviour in its normal state you are able to better identify exceptions to that state such as unexpected reboots, unusual spikes in the outbound network activity, errors, etc. which can be early indicators of malicious activity in the enterprise’s environment.

> ## **The Security Operations Centre’s monitoring tools  { .article-section }
> **

There are a number of systems and network monitoring technologies available and new ones are being developed with time. Depending on the business’s requirements one can implement a combination of them for the SOC’s use. The most widely known are:

#### 1\. Intrusion Detection and Intrusion Prevention Systems (IDS / IPS)

Both the IDS and IPS are situated inside the network and monitor the traffic made through the firewall. The IDS detects known attackers and known attacker activity alongside anomalies in the network behaviour and sends alerts to the management terminal. The IPS adds an additional layer of protection. It actively defends the network by stopping attacks alongside alerting.

#### 2\. Security Information and Event Monitoring (SIEM)

According to Gartner, Security Information and Event Monitoring (SIEM) toll supports threat detection, compliance, and security incident management through the collection and analysis (both near real-time and historical) of security events, as well as a wide variety of other event and contextual data sources. The core capabilities are a broad scope of log event collection and management, the ability to analyze log events and other data across disparate sources, and operational capabilities (such as incident management, dashboards, and reporting).

In other words, SIEM is an automated system that collects and analyses log files, security alerts, and events from other security systems across the network – such as endpoint security, firewalls, Intrusion Detection Systems (IDS), etc. – into one place so security teams can analyze data easier and as result accelerate the detection and response to threats. SIEMs offer powerful log search features, the ability to trigger alerts using rules and generate reports that organisations can provide to auditors to demonstrate compliance with various regulations. It also allows SOC teams to use purpose-designed frameworks and workflows and pre-build dashboards to streamline their Threat Management operations.

#### 3\. Security Orchestration, Automation and Response (SOAR)

The term SOAR was first coined by Gartner. It is a tool that allows collecting data about security threats from multiple sources, enables incident analysis, triage and prioritization, and responds to security events without human assistance.

#### 4\. User Entity Behaviour Analytics (UEBA)

UEBA is an analytics layer that tracks normal and abnormal behaviour for users and entities such as databases, servers, and devices. It looks for patterns that don’t match established baselines and identifies potential security threats faster and more effectively than humans. It helps analysts spot abnormal behaviours such as logins attempted from unusual locations.

#### 5\. Other SOC monitoring tools  

Data Leakage Prevention (DLP)

Endpoint Detection and Response (EDR)

Governance Risk and Compliance (GRC)

Firewalls

> #### Next week

Next week we will continue with the Security Operation Centres’ processes.

> ## Do you require help with Managed Security for your solution on Amazon Web Services?{ .article-section }

SEQRED offers AWS level 1 Managed Security Services. 

To discuss your requirements, contact SEQRED at biuro@seqred.pl.

###### **About this guide**

The idea for this article was inspired by an in-house presentation by Józef Sulwiński which you can watch [here.](https://www.youtube.com/watch?v=gvgg6sGibv4)
