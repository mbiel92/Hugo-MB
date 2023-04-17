+++
lang="en-GB"
title="Ransomware – when data becomes hostage"
date="2019-12-15"
author="SEQRED"
image="/blog/Ransomware_attack-1.jpg"
tags=['ABC security', 'IT security', 'ransmoware']
+++

You sit down to your computer, drink your morning coffee, and … a multi-colored window is displayed on the monitor informing that your data has been encrypted, and only a cryptocurrency deposit on the given account will allow you to recover it. All photos, videos, documents – are gone. You’ve just become a victim of ransomware – digital blackmail.

> What is ransomware?
> -------------------

“Blackmail software” or ransomware, is a type of malware that, after infecting a computer, encrypts or blocks access to data on disks, and then informs the victim of the possibility of recovering them. Not for free – a transfer to the specified account is required.

![](/blog/Ransomware_attack-1.jpg)

> Ransomware – a bit of history
> -----------------------------

The first cases of attacks using encryption software took place in 1989. Ransomware **AIDS / PC Cyborg** targeted primarily computers of companies from the medical sector. Carried on 5.25-inch disks, it impersonated a survey about the risk of contracting HIV. The ransom message was printed on a printer connected to the computer.

With more people having access to the Internet and the introduction of asymmetric cryptography, ransomware began its path to becoming one of the most harmful types of software. By 2006, a whole range of Trojans using RSA encryption appeared (e.g., **Gpcode, Crypzip, MayArchive**) – but **CryptoLocker,**operating since September 2013, has become the greatest threat. It is estimated that over 250,000 devices fell victim to the first hundred days of its operation. The mechanism of infection was simple: the target of the attack received an e-mail with an executable hidden as a document. After running it, CryptoLocker encrypted files with selected extensions on both the local disk and available network resources. Then, in each folder with encrypted data, a text file was created containing information about the amount and how to pay the ransom. Although few victims have decided to pay, criminals have earned over USD 3 million.

Another interesting case was the **Petya ransomware,** which has been active since March 2016. It uses a different method of blocking access to the victim’s data. Not only are the user’s files encrypted, but the MFT file (master file table) as well, which consequently prevents reading the directory structure or starting Windows. It is worth noting that the targets of attacks using this virus were human resources departments in public and private companies. To increase the chance of infection, ransomware was sent as a malicious attachment pretending to be the CV of a candidate or a link to it. One of the most injured victims of the improved version of the virus – **NotPetya** – was the world’s largest transport company A.P. Møller-Maersk. As a result of the attack, the company was forced to operate without IT infrastructure for ten days. This event drew attention to the fact that not only technology companies are vulnerable to hacker attacks.

It is also worth mentioning the **WannaCry** worm, which in May 2017 affected over 100 countries. It is estimated that 200,000 computers were infected – including British healthcare systems, Russian banks, Indian railways, and companies such as Nissan and FedEx. The reason for so many computers being affected by this ransomware was an out-of-date version of Windows – the patch which could prevent the attack was released by Microsoft in April, almost a month before the first attacks occurred. This example clearly shows how important it is to perform regular software updates.

> Ransomware – the main methods of attack
> ---------------------------------------

The most common source of infection may be malware that got into our mailbox as a result of one of the organised phishing campaigns. This attack model involves impersonating the sender we know – e.g., a bank, a mobile operator, or a courier and convincing you to open the attached invoice or download it from the link provided. The invoice or other relevant document contains malware. It is worth noting here how important the psychological aspect of the attack is – the message allegedly comes from a trusted sender.

Other scenarios are based on impersonation of known software – eg, installations of the free MS Office Suite, the latest computer game titles, or “free” full versions of smartphone applications. Such programs usually turn out to be not only a waste of time but also a real threat to the security of our data.

> Who may be the victim of a ransomware attack?
> ---------------------------------------------

**The target of an attack can be any network user – both an individual and a company.** The motivation for attacks is the chance of others paying the ransom. A state institution or company has a lot more to lose than the average Joe: data loss can translate into company paralysis. In March 2019, Norsk Hydro (a Norwegian giant producing aluminum, among others) became convinced how expensive an attack could be. The **LockerGoga** ransomware has paralyzed the company’s operations, generating losses of USD 35-41 million. The growing **RYUK** ransomware attacks and **RaaS-type services** confirm that hackers choose organizations as targets for which the attack can be costly, and there is a good chance that a high ransom will be paid.

> RYUK ransomware
> ---------------

RYUK is a specific ransomware, which generated a profit of 705 BTC (about PLN 10 million) in just the first few months of its activity. How is it different from its competitors? Only large companies were targeted. To maximize the likelihood of a successful attack, the software was enriched with mechanisms responsible for disabling automatic backup services and anti-viruses, as well as deleting existing backups. When data is encrypted after a few weeks, and the ransom demand is displayed, it is too late, with the company only having incomplete backups.

The attack method includes the following steps:

*   infection of one of the computers with “any” malware that will give the opportunity of exploring the infrastructure,
*   an assessment of whether the infected computer belongs to the organization known as HVT (high-value target), and thus whether further actions and involvement are justified,
*   in the case of the identification of a target, the organization’s infrastructure (domain controller) is invaded, and valuable data is stolen,
*   the last step is to infect as much infrastructure as possible with the RYUK ransomware.

Considering the extent of the attack, earlier theft of sensitive data, and the destruction of backups, the RYUK malware attack is deplorable.

> RaaS: Ransomware-as-a-Service – buy yourself ransomware!
> --------------------------------------------------------

Recently, a ransomware distribution model in which malware and attack are treated as a form of service has become popular. For a relatively small amount of profits from paid extortion or fees, the buyer in Dark Web receives documentation, specially prepared software, a guide on how to effectively carry out infections, and full technical support on specific ransomware. Examples are the Philadelphia, RaasBerry, Frozr Locker, and Satan packages. This model allows advanced hackers (creating malware) to avoid risks and the process of having to attack and then preform extortion. People who cannot develop their ransomware or are unable to carry out an effective attack get a powerful weapon ready for use.

> How to protect yourself from ransomware?
> ----------------------------------------

To increase your online security, there are a few simple rules to remember:

*   data backup should be an essential part of computer usage routine – this will help you alleviate data loss problems,
*   be careful when using the Internet – do not go into suspicious links and do not install software from an unreliable source,
*   before opening an attachment or clicking on a link, make sure you know the sender – a significant amount of attacks involve impersonating a company that you trust from which you can expect messages, e.g. telecommunications or courier,
*   do not use an administrator account if it is not necessary,
*   do not use public WiFi networks (before you do, be sure to [read the article on how to use WiFi safely),](https://seqred.pl/en/secure-wifi/)
*   regularly update software – some attacks target existing software vulnerabilities (e.g. browsers),
*   use unique passwords for different sites – hijacking one password will not result in hijacking all accounts,
*   if possible, enable two-factor authentication – even if criminals take over your passwords, they will still not be able to log into your account,
*   take care of your privacy – the less third parties can learn about you, the more difficult it will be to prepare a dedicated attack for you.

> I was attacked, what now?
> -------------------------

There is no system that cannot be infected. Malware developers regularly invent better techniques to outsmart even the most cautious and suspicious users. If you have already become a victim of ransomware – not all is lost!

We recommend that you do not pay the ransom, as there is no guarantee that we will regain access to our data after the money has been transferred. What’s more – by paying criminals, we show that this method of extorting money brings results.

If you have a backup – restoring it should limit the losses associated with the attack. However, not everyone remembers to perform regular backups and then it is necessary to find a way to decrypt data. There are services that specialise in free help for victims of ransomware attacks:

*   [NoMoreRansom!](https://www.nomoreransom.org/pl/index.html) – Polish support site for ransomware victims,
*   [ID Ramsomware](https://id-ransomware.malwarehunterteam.com/) – a ransomware identification tool and a set of instructions on how to recover data,
*   [Kaspersky NoRansom FAQ](https://noransom.kaspersky.com/pl/faq-pl/) – a collection of questions and answers prepared by Kaspersky.

[Do you have any questions about ramsomware? Write to us!](https://seqred.pl/en/contact/)