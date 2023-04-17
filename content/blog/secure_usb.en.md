+++
lang="en-GB"
title="How to safely use removable media in ICS networks?"
date="2020-01-09"
author="Józef Sulwiński, Michał Stępień"
image="/blog/Bezpieczne_USB.jpg"
tags=['critical insfrastructure', 'ics']
+++

It’s been 10 years since the alert issued by Cybersecurity and Infrastructure Security Agency (CISA) indicating the risks associated with using USB media as one of the sources of threat to control systems. Despite the passage of years, these threats still exist, and as the example of an attack known as Operation Copperfield shows, we should be afraid of them all the time. It is worth noting that the Federal Office for Information Security in a report published in 2019 lists them as one of the main threats to ICS systems.


> USB storage devices as one of the sources of threats for industrial control systems
> -----------------------------------------------------------------------------------

On 11th December 2017 at 01:21 night shift employee in one of the industrial plants in the Middle East connected a USB drive to a shared workstation, which is used by dozens of employees every day. The employee watched the movie La La Land, which he had downloaded to his USB drive during the break. He did not know that his actions initiated a sequence of events that could have had catastrophic consequences for his organization. With the launch of the film, a well-prepared attack, known as Operation Copperfield, began.

Data carriers such as USB drives, external drives and memory cards are widely used. Employees use them both in the office and in ICS networks. They often take them home to continue working on projects or just copy the latest movies or music. Third-party suppliers often bring their own computers (BYOD), which store configuration data and service software, which is often used for various installations at different customers. **Unfortunately, employees and external suppliers are often unaware of the effects of malware. Despite the high knowledge of health and safety aspects and physical security, there is still a low awareness of cyber threats.**

> ### Three risk scenarios that are worth discussing during periodic training sessions for employees and external suppliers

**Scenario 1.**  
USB storage devices may have been infected in an office network or in a private environment. As a result, malware can be transferred to these networks with ICS solutions (even if they are physically isolated from intranet) using these media.

**Scenario 2.**  
The portable workstations used for maintenance may have been infected while accessing the Internet, the office network or in the infrastructure of the external provider. When using such a device in the ICS network, we expose our critical automation systems and components to infection with malicious code.

**Scenario 3.**  
Project files or service applications may be properly crafted and could contain malicious code leading to infection or data leakage.

> Methods of protection against threats associated with removable media
> ---------------------------------------------------------------------

**1.** introduction of whitelisting procedure of removable media (only registered media are allowed for use),

**2.** always checking removable media for malware on an isolated workstation or in a kiosk with a different operating system than maintenance computers,

**3.** clear, unique marking of removable media dedicated for private use (they must not be used in protected networks),

**4.** clear, unique marking of removable media dedicated exclusively to OT networks,

**5.** installing physical barriers preventing unauthorized use of built-in USB ports (sealing, installation of USB blocks or desoldering of circuits),

**6.** implementation of mechanisms for full encryption of data carriers.

> Requirements and control mechanisms for external suppliers using mobile devices in our network
> ----------------------------------------------------------------------------------------------

For external suppliers, it is worth introducing the following requirements and control mechanisms:

**1.** data exchange can only take place via and using the abovementioned control mechanisms,

**2.** implementation of network quarantine mechanisms for connections of external service providers devices,

**3.** mandatory anti-virus scanning of all external devices before connecting them to the network,

**4.** ensuring by the owner of a given resource full encryption of portable computers used for service purposes.

Is the threat mentioned at the beginning so serious that it requires the introduction of so many security solutions? Unfortunately, it is. Experience has shown that removable media and portable computers are used to transfer malware even to galvanically isolated networks. This was the primary way of STUXNET worm spreading.

Finally, it is worth pointing out emerging security solutions that are intended to support the controlled safe use of removable media in ICS networks.  
One of the solutions is **SMX – Secure Media eXchange from Honeywell**. Soon it will be possible to test the operation of this solution in our office.

**Źródła:**  
[ISS Source: ICS Alert USB Malware Attack](https://isssource.com/ics-alert-usb-malware-attack/)  
[Industrial Control System Security: Top 10 Bedrohungen und Gegenmaßnahmen v1.3](https://www.allianz-fuer-cybersicherheit.de/ACS/DE/_/downloads/BSI-CS/BSI-CS_005.pdf?__blob=publicationFile&v=12)  
[CISA: USB Usage](https://www.us-cert.gov/ics/tips/CSAR-10-114-02)

