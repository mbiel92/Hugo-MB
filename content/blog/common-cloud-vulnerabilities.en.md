+++
lang="en-GB"
title="Common Cloud Vulnerabilities"
date="2022-02-22"
author="Eugen Wypiór"
image="/blog/C-Cloud-Vuln-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++



The increased popularity of cloud services in recent years goes only
hand in hand with the increased interest of malicious actors in the
opportunities that this new sphere of computing technology brings.

Among the most common cloud attack vectors used by these rogue actors is
cloud vulnerability exploitation. According to the 2021 IBM Security
X-Force Cloud Threat Landscape report cloud vulnerabilities keep rising
and have increased over 150% in the last five years.

The regularly exploited vulnerabilities and misconfigurations are:

-   Resources, such as VMware, are connected to the internet by mistake
    with default security settings. This comprises wrongly configured
    platforms and poorly implemented network controls that leave
    internal services unprotected on the internet, for example, the
    Remote Desktop Protocol (RDP) -- which accounted for the access
    vector in over 70% of cloud resources offered for sale on the dark
    web -- or misconfigured object storage services.
-   Inadequate access control mechanisms, like the absence of
    Multifactor Authentication (MFA) for Software as a Service (SaaS)
    solutions and federated solutions with home pages available from the
    Internet. Lack of this additional check allows an attacker to
    authenticate themselves into an account without further problems.
-   Inadequate segmentation of virtual networks and lacking integrity
    trust relationships between cloud resources and on-premises
    environments.

An additional factor leading to compromised cloud space is the fact that
businesses are still learning how to monitor and detect threats in the
cloud. Also, some of them lack the know-how when it comes to configuring
security settings for cloud environments as opposed to on-premises
environments.

The three repeatedly used methods rogue actors use to break into the
cloud environment are:

-   Password spraying -- a technique preferred by threat actors as using
    one password against multiple users avoids account lockouts that
    would normally happen when brute forcing a single account with many
    passwords.
-   Software vulnerability -- securing each individual application
    deployed in the cloud can be challenging for cybersecurity staff,
    due to the many types and brands of software that are cloud
    compatible.
-   On-premises to cloud pivot -- threat actors breaching the
    on-premises hosted systems and moving along to the cloud
    environment. This can allow the malicious actor to escalate their
    advantage and access even more resources of the compromised
    organisation.

###### **About this article**

This article was based on the 2021 IBM Security X-Force Cloud Threat Landscape Report. To read the full report click [here.](https://www.ibm.com/downloads/cas/WMDZOWK6)
