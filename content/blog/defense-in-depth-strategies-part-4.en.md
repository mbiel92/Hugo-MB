+++
lang="en-GB"
title="Defense in Depth strategies – Part 4"
date="2022-11-09"
author="Eugene Wypior"
image="/blog/DiD_86-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

## **Risk Management Approach – Asset Inventory and Risk Characterisation**{ .article-section }

The attack surface for an operation includes all the vectors associated with gaining access to the systems or equipment considered critical to business operations. To implement con­trols necessary to reduce the attack surface for critical assets, an organization must first identify the systems and components they consider business or mission critical. Then they must determine the criticality of the assets based on its function and importance to business operations. The business then performs a cybersecurity risk analysis of the system to identify the current threats, vulnerabil­ities, and risks to the system and/or operations, and the potential impact should a threat be carried out.

![Risk Management Approach - Asset Inventory and Risk Characterisation](/blog/DiD4_Risk-Management-Approach_v2.png)

#### Asset Inventory

A comprehensive inventory of ICS assets develops a baseline understanding among all stakeholders relative to the support infrastructure (both IT and ICS). Organizations should identify systems (including hardware, software, and supporting infrastructure technologies) and analyse dependencies to understand both the function of the asset itself and the resources required to support critical functions.

#### Categorise Asset Criticality

Asset criticality depends on:

*   the type of information generated, processed, stored, and disseminated on and from the ICS,
*   the function of the ICS asset within the overall operation,
*   assigning a security categorization for that asset based on the potential impact (low, moderate, or high) on the organisation should an event occur that jeopardises its ability to:
    *   accomplish its mission,
    *   protect its assets,
    *   fulfil its legal responsibilities,
    *   maintain its day-to-day functions,
    *   protect individu­als.

#### Identify Security Risks

To define and articulate the risk to ICS, organisations must identify the potential threats to the ICS and the vulnerability of the system to those threats. This information provides the current security risk exposure for the ICS.

#### Determine Potential Impact

An organization can estimate the likelihood of a threat actor carrying out a threat or exploiting a vulnerability by considering the potential channels for threat exploitation, such as whether the system is in a higher or lower security zone on the network, its access and privilege requirements, its security configuration, and identifying any exceptions to security policy. The potential impact of a threat actor compromising or making an asset unavailable (for example, financial, damage to other systems or to the public, including human safety concerns) is based on the criticality of the system or information, the visibility of the system or the exploit, and the ability to quickly remediate any damage caused by the compromise. This step identifies both direct and collateral impacts.

#### Identify and Tailor Controls

Based on the criticality level of the ICS baseline security controls are put into place.

Additionally, security controls for ICS may be based on the regulatory requirements for the sector. Control tailoring may add or subtract controls from the recommended control set.

An important part of identifying and tailoring security controls is to remember that policies and pro­cedures are critical controls as well. Organizations should review and update policies and procedures to drive the implementation of Defense-in-Depth practices.

#### Implement Security Controls 

Security considerations and policies should be integrated into existing policies and procedures and considered an integral part of the system life cycle. Security controls should not be viewed as an ICS ‘add-on’.

Apply security controls to ICS according to priority. The most critical (high impact) and most vul­nerable (high likelihood) systems should be the priority for risk reduction and mitigation activities. Pervasive vulnerabilities, such as the use of unsupported operating systems (OS), are also a good starting point for applying security controls. Regular system updates can provide far-reaching protection and re­duce risk across many systems. Security controls for the human aspect of security should include cyber­security awareness training that undergoes regular review and frequent testing. This process significantly reduces the physical business attack surface.

#### Monitor and adjust

Security for any system is never a “once and done” activity. Organizations constantly change ICS environments—adjusting settings, replacing or upgrading older systems, implementing new capabilities, releasing vendor patches—and the threats to ICSs and operations constantly evolve. Security monitoring is critical to ensure ongoing system protection.

Asset owners should review or assess the implementation status for all security controls periodical­ly throughout the system development life cycle. This provides an important indicator of whether the controls work as intended and reduce risk. Asset owners may need additional or compensating controls to further reduce risk, so they should revisit the control selection process and properly address identified risks.

###### **About this article**

###### This article was prepared with the use of the publication of the U.S. Department of Homeland Security titled ‘Recommended Practice: Improving Industrial Control System Cybersecurity with Defense-in-Depth Strategies’  available [here.](https://www.cisa.gov/uscert/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)