+++
lang="en-GB"
title="Botnet Mirai and largest Internet blackout"
date="2019-07-08"
author="Błażej Dusik"
image="/blog/Seqred_botnet_Mirai.jpg"
tags=['IT security']
+++

Let's imagine a zombie army, like those straight from the silver screen
-- a charging horde that only has one goal. This reference to a
Hollywood production can help us later understand the type of threat a
botnet poses and how large it could be -- an army of computers and other
electronic devices turned into zombies.

Let's leave cinema magic behind and come back to real life. We need to
go back to October 2016 when, as a result of the largest DDoS attack in
history, the Internet was practically switched off throughout the whole
East Coast of the US.

GitHub, Twitter, Reddit, Netflix, Airbnb, CNN, Spotify, and many others
became unreachable. Brian Krebs -- a well-known journalist writing about
computer safety -- was hit hard. According to Akami (a company that
protects against DDoS type attacks), he was the target of traffic that
reached about 650 Gigabytes per second, nearly double the amount that
the company had recorded up until then. Moreover those previous, half
lower, numbers had been enough to overwhelm most Internet services.
Meanwhile, OVH, a company providing a wide range of Internet services,
could boast about an attack of up to 1 Tbps.

![](/blog/Seqred_botnet_Mirai.jpg)

It's believed that CCTV cameras were the main family of IoT devices that
were used in the OVH attack. The cameras were not protected by a
firewall or a router using NAT what allowed them to be hacked easily.
Moreover, many IoT (Internet of Things) devices use the Universal Plug
and Play (UPnP) function which opens a router port for them to let them
access the Internet.

Mirai, the culprit of this attack, is a piece of malware designed to
attack IoT devices. You might think that this does not concern you, but
after thinking about the issue for a little longer you can conclude that
the common user is the most desired target. Our autonomous vacuum
cleaner, TV set, security camera, light bulb and even our toothbrush --
each of these items was infected by Mirai and became a bot that was
ready to be used at the whim of the cybercriminals.

## Botnet Mirai -- what it actually is and what happens?

Firstly the whole Internet is being scanned in search of services or
devices provided by a particular manufacturer. Next with the help of
defined "user:password" pairs (originally the database of such pairs is
very small, since it's only about 60 such pairs) it tries to gain access
to the device. After the infection process is successful, the bot starts
to look for other devices within the same network and then conducts a
brute force attack to infect them too. From this point onward, since our
household appliances and audio and video equipment are armed, all it
takes is for the control center to identify a target and the attack can
commence. For instance, a popular website can be flooded by a number of
requests that is impossible to deal with.

### Mirai -- the technical side of malware

-   a control center (C2 / C&C) which contains the database of all hosts
    that were taken over,
-   a receiver, which collects each bot's operations results and
    forwards them to a computer which downloads the bot to the
    vulnerable devices,
-   a downloading component which delivers the bot's binary file to the
    vulnerable devices (with the help of wget and tftp tools -- if they
    are not present in the system, it uses its own "downloader"),
-   a bot, which once activated on the infected device connects to the
    control center, scans the network in order to identify vulnerable
    devices and sends the results of the scan to the Scan Receiver
    component, which leads to more harmful code being downloaded to the
    device.

Mirai is a self-propagating virus. Each infected device works as a
scanner and tries to log into random IP addresses, while the information
about the overtaken hosts and their respective data is delivered to the
C&C.

The virus is built in such a way that it can function regardless of the
architecture, it can be x86, ARM, Sparc, PowerPC, Motorola, and the IoT
device is still vulnerable. Moreover, once the device is infected, the
bot can make it invulnerable to similar attacks, to cut out the
competition. The image of the virus in itself is small, at the same time
it uses techniques that make reverse engineering harder.

An analysis conducted by the company Symantec showed that an IoT device
is, on average, scanned every two minutes. It can be compromised even a
minute after being connected to the Internet.

### Who is responsible for all of this?

It may seem shocking that two young people, 21-year-old Paras Jha and
20-year-old Josiah White, could lead to an incident of this scale. It
seems to me that even the authors could have been unaware this could
happen. When the situation was gaining momentum and FBI agents started
to join in on the action things started to get tense, and the complete
code of the malware appeared on GitHub. From that moment onward everyone
could download the code and do with it whatever they pleased. The
publication of the code was probably meant to obscure who the creators
were so they could hide among all the people eager to test the software
on their own.

### What are the consequences?

The analysis results are clear, Mirai or its consecutive mutations have
been very active ever since their creation.

If you're the victim of the bot you don't have much to fear: your
equipment may become slower or your power consumption will rise, but
these are the biggest threats. These symptoms allow us to suspect that
we have been infected -- it's, unfortunately, hard to install antivirus
software on a vacuum cleaner or a washing machine. The only thing we can
do is to perform a factory reset and change the default passwords.

Online you can already find "commercial" offers of botnets for hire, on
YouTube there are films showing the step by step process of how to
configure a botnet.

The more worrying part, however, may be the constantly growing number of
devices that we connect to the Internet and then forget about their
existence. My personal fear is that Mirai may have only been a proof of
concept. Considering the availability of the code I can come up with
multiple scenarios of what may yet occur. Apart from the militaries of
various states, there are also hacktivists and "kids" who want to make
fast cash. We don't know if a piece of code has been created that is
lying in wait for particular circumstances, or a critical mass to be
reached, and then only its author knows what could happen.