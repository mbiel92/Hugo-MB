+++
lang="en-GB"
title="Enterprise Connected Devices – a cyber security challenge – Part 2"
date="2022-09-26"
author="Eugene Wypior"
image="/blog/Screenshot-2022-09-26-at-22.03.27-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Enterprise Connected Devices (ECDs) are all the devices that interact with, hold, or process an organisation’s data and can include end-user devices such as laptops and smartphones, physical devices connected to the Internet (IoT) such as cameras, and distinct ECDs (devices for specific use for enterprises).

ECDs are an attractive target for various rogue actors due to the potential access of valuable, sensitive, or personal data, which can be turned into a financial gain once acquired.

## Who targets Enterprise Connected Devices?{ .article-section }

Some years back persons acquiring an unauthorised access to a computer or network were commonly known as hackers. Nowadays, the variety of persons and groups conducting such activities is usually categorised based on various factors that can be attributed to them.

#### Nation-state actors

Some of the most resourceful hackers are those backed by governments and intelligence agencies and are actively targeting ECDs for espionage purposes. One such example can be that of the Russian-backed hacking group STRONTIUM (aka Fancy Bear, aka APT 28) who in 2020 compromised popular IoT devices such as VOIP phones, office printers and video decoders across multiple customer locations.

Nation-state actors specialise in targeting a range of sectors including defense, education, engineering, government, IT, medicine, and military.

The goals of cyber espionage campaigns are most often focused on the theft of information without the target being aware of any malicious activity.

#### Cybercriminals

Cybercriminals are financially motivated, and their capabilities vary. They often attempt to disrupt services via DDoS attacks or encrypt data through ransomware and demand payment. Cybercriminals will likely try to gain access to insecure ECDs by openly scanning for vulnerabilities that can be exploited.

## How do threat actors target Enterprise Connected Devices?{ .article-section }

#### Unpatched and outdated IoT devices

The usual way threat actors breach the security of ECDs is by taking advantage of technical vulnerabilities and poor cyber security of devices which can happen especially if manufacturers don’t fix known issues and users don’t apply updates.

Devices especially prone to a security breach are IoT devices. This is because they possess fewer processing and storage capabilities than more complex devices, which makes it difficult to fit them for example with antivirus software solutions.

Further, unpatched devices can lead to data breaches or exposed information, manipulation of other assets, access to servers and systems, deployment of malware, or even physical disruption of operations.

In addition, a lot of legacy IoT devices were not designed and built with security in mind and they simply are incapable of receiving remote patches.

To make things worse, some organisations are not equipped with the capability to monitor and manage whether an ECD is supported or not.

At the same time, with the ongoing development of new technologies, it has become ongoingly easier and cheaper for cyber criminals to acquire tools used to launch high-volume, low-sophistication attacks on ECDs.

Points with a high probability of attack in ECD systems include: 

*   Devices with vulnerabilities/weaknesses in
    *   storage firmware
    *   application software
    *   physical interface
    *   web interface
    *   network services
    *   insecure default settings
    *   outdated components
    *   insecure update mechanisms
*   Communication channels that connect ECD components with one another
*   Applications and software

#### Supply chain

ECDs make supply chain vulnerabilities even worse. These attacks often involve compromised software being installed in a certain ECD, such as a router or a camera however it can also be a piece of hardware placed or modified to change a device’s behaviour.

Supply chain types of attacks pose a significant threat since the compromised software or device can present a single point of a security breach for several devices.

#### Personal connected devices on enterprise network 

Due to the proliferation of IoTs private ones are increasingly brought into the offices by employees with the possibility of being connected to the enterprise network. It is likely that these devices could be targeted to gain access to the enterprise network.

## Bots{ .article-section }

An increasing number of bots comprise compromised IoT devices.

In 2016 the Mirai malware infected IP cameras and basic home routers, creating a botnet that was used to take out the Doman Name System (DNS) provider Dyn.

The Mirai malware targets IoT devices to turn them into botnets capable of launching DDoS attacks. Once infected with Mirai, computers continually search the internet for vulnerable IoT devices and then use known default usernames and passwords to log in, infecting them with malware.

According to documents leaked in 2020 by Digital Revolution – a Russian hacking group –, the Russian domestic intelligence agency FSB is working on creating an IoT botnet inspired by the Mirai botnet with each infected device in the botnet reprogrammed to carry out password attacks on other devices in order to keep the botnet alive and growing. The planned main targets would be security cameras and network video recorders.

###### **About this article**

###### This post is based on an article from the NCSC UK. To read the full version of this article click [here.](https://www.ncsc.gov.uk/report/organisational-use-of-enterprise-connected-devices)