+++
lang="en-GB"
title="Denial of Service & Distributed Denial of Service Attacks & Mitigation"
date="2022-06-05"
author="Eugene Wypior"
image="/blog/DoS-DDoS-2.png"
tags=['ABC security','messaging security']
+++

## What is a denial-of-service attack?{ .article-section }

A denial of service (DoS) attack is designed to overwhelm the system’s resources to the extent that it is unable to respond to legitimate service requests. Affected services may include email, websites, online banking, and many other types of services. These are known as “denial of service” attacks because the victim’s site is unable to provide services to those legitimate customers who are unable to access it since the target site is flooded with illegitimate access requests. Since the site must respond to every request, all its resources are consumed by replies to the traffic generated artificially by the attacker. This prevents the site from serving users as usual and often results in a complete shutdown of the site.

A Distributed Denial of Service (DDoS) attack is similar in that it also aims at exhausting the targeted system’s resources. A DDoS attack is initiated by a wide range of malware-infected host machines controlled by the attacker. DDoS attackers often employ the service of a botnet – a group of internet-connected devices hijacked for the purpose of carrying out large-scale attacks. It is possible to rent botnets from rogue actors, allowing unskilled users to launch DDoS attacks.

## How to know an attack is happening?{ .article-section }

The signs of a DoS attack can be similar to that of non-malicious availability issues such as technical problems with a particular network or a system administrator performing maintenance tasks. The following symptoms however could indicate a DoS or DDoS attack:

*   Unusually slow network performance (such as opening files or accessing websites),
*   Unavailability of a particular website,
*   An inability to access any website.

## How to prevent DoS (DDoS) attacks from occurring?{ .article-section }

There are several approaches that can be implemented to tackle this problem

*   Installing a firewall and configuring it to restrict traffic coming into and leaving a server; or through the use of an intrusion detection system.
*   Monitoring and analysis of the traffic that detects abnormal traffic flow and redirects such traffic away from the network. The traffic is filtered out of the DoS stream and only legitimate traffic is passed on to the network.
*   General strengthening of the network’s security posture includes hardening the internet-facing devices to prevent compromise. This includes installing and maintaining antivirus software, evaluating security settings, and following good security practices.
*   Creating and exercising a DoS attack response plan to ensure successful and efficient communication, mitigation, and recovery in the event of an attack.