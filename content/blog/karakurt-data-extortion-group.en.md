+++
lang="en-GB"
title="Karakurt Data Extortion Group"
date="2022-09-12"
author="Eugene Wypior"
image="/blog/Karakurt-1.jpg"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Just over three months ago, on June 1st, the FBI, the Cybersecurity & Infrastructure Security Agency (CISA), the US Treasury Department and the Financial Crimes Enforcement Network (FinCEN) jointly issued a Cybersecurity Advisory on the Karakurt Team (Karakurt Lair). This comes nearly seven months after Accenture reported on this group dating their first activities back to June 2021 when they registered domains with their name followed by a Twitter handle.

Karakurt is an organised online extortion group that steals data and demands a ransom in exchange for not making the data public. Known ransom demands have ranged from 25,000 USD to 13,000,000 USD in Bitcoin. Karakurt solely exfiltrates data for extortion and does not deploy ransomware.

## **Karakrut Techniques**{ .article-section }

The Karakrut actors use a wide range of techniques as described MITRE in their ATT&CK techniques typology for enterprise

### **Reconnaissance**

Typically, Karakurt actors would purchase stolen login credentials including emails and gather information about the victim’s business relationships (i.e. managed service providers, contractors, etc) that can be used during targeting. This can be done via targeted phishing campaigns or OSINT.

### **Initial access**

Karakurt actors would exploit common intrusion vulnerabilities for initial access, especially:

*   the Log4j “Log4Shell” Apache Logging Service vulnerability and vulnerabilities in outdated firewall appliances,
*   outdated VPN appliances,
*   phishing and spear phishing
*   malicious macros as email attachments
*   purchased stolen credentials, including VPN and RDP credentials

### **Privilege escalation**

Once Karakurt actors establish access, Cobalt Strike beacons are deployed to enumerate a network, followed by installing Mimikatz to pull plain-text credentials and subsequently using AnyDesk to obtain persistent remote control and utilize additional situation-dependent tools to elevate privileges and move laterally within a network.

### **Exfiltration**

Karakurt actors then compress and exfiltrate large sums of data using open-source applications and File Transfer Protocol (FTP) services, such as Filezilla, and cloud storage services including Rclone and Mega.nz

### **Extortion** 

Following the exfiltration of data, Karakurt actors present the victim with ransom notes by way of “readme.txt” files, via emails sent to victim employees over the compromised email networks, and emails sent to victim employees from external email accounts. The ransom notes reveal the victim has been hacked by the “Karakurt Team” and threaten public release or auction of the stolen data. The instructions include a link to a TOR URL with an access code. Visiting the URL and inputting the access code open a chat application over which victims can negotiate with Karakurt actors to have their data deleted.

## **Mitigations**{ .article-section }

To protect an organisation from falling prey to Karakrut CISA advises the following mitigations:

*   Implement a recovery plan to maintain and retain multiple copies of sensitive or proprietary data and servers in a physically separate, segmented, and secure location (i.e., hard drive, storage device, the cloud).
*   Implement network segmentation and maintain offline backups of data to ensure limited interruption to the organization.
*   Regularly back up data and password-protect backup copies offline. Ensure copies of critical data are not accessible for modification or deletion from the system where the data resides.
*   Install and regularly update antivirus software on all hosts and enable real-time detection.
*   Install updates/patch operating systems, software, and firmware as soon as updates/patches are released.
*   Review domain controllers, servers, workstations, and active directories for new or unrecognized accounts.
*   Audit user accounts with administrative privileges and configure access controls with the least privilege in mind. Do not give all users administrative privileges.
*   Disable unused ports.
*   Consider adding an email banner to emails received from outside your organization.
*   Disable hyperlinks in received emails.
*   Enforce multi-factor authentication.
*   Use National Institute for Standards and Technology (NIST) standards for developing and managing password policies.

*   Use longer passwords consisting of at least 8 characters and no more than 64 characters in length;
*   Store passwords in hashed format using industry-recognized password managers;
*   Add password user “salts” to shared login credentials;
*   Avoid reusing passwords;
*   Implement multiple failed login attempt account lockouts;
*   Disable password “hints”;
*   Refrain from requiring password changes more frequently than once per year. **Note:** NIST guidance suggests favoring longer passwords instead of requiring regular and frequent password resets. Frequent password resets are more likely to result in users developing password “patterns” cyber criminals can easily decipher.
*   Require administrator credentials to install software.

*   Only use secure networks and avoid using public Wi-Fi networks. Consider installing and using a VPN.
*   Focus on cyber security awareness and training. Regularly provide users with training on information security principles and techniques as well as overall emerging cybersecurity risks and vulnerabilities (i.e., ransomware and phishing scams).