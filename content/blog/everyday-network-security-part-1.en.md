+++
lang="en-GB"
title="Everyday Network Security – Part 1"
date="2022-05-31"
author="Eugene Wypior"
image="/blog/ENS_1-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

It will probably come as no surprise and is common knowledge by now that every klick you make online can be watched, logged, analysed, aggregated, and sold for profit. Depending on where you live, ‘Big Brother’ can use this information truly oppressively, and malicious actors can misuse it for nefarious activities.

One of the areas of keeping your information secure and preventing prying eyes from collecting too much information about you is properly configuring and using your network connection. This is part 1 of hints on how to connect your devices securely to the internet, including configuring routers and setting up VPN.

**Use a VPN**

Using a reputable, paid-for VPN can prevent sites you visit from logging your real IP address, limit the data your Internet Service Provider (ISP) can collect, and increase your protection when using public WiFi.

Bear in mind though, that not all VPNs are equal, and you should inform yourself well before you choose a service. Some VPN providers keep logs and can even sell them to third parties which in principle outdoes the whole purpose of a VPN. So, choose a VPN with a good reputation and one that does not keep logs.

You can also configure a VPN on your router, firewall, or home server. This will encrypt traffic from all your devices en block without the need to set up a VPN on each of them individually. Such an approach reduces the chance of IP leaks, VPN app crashes and provides VPN access to devices that don’t support VPN clients such as TVs, Smart Hubs, or IoT devices.

It is important, if possible when using a VPN to only use the DNS server of your chosen VPN provider or secure service. For OpenVPN, you can add _block-outside-dns_ to your config file (which will have the extension _.ovn_ or _.conf_ ).

**Change the router’s password**

Default router passwords are publicly available, making it possible for anyone within the reception area to be able to connect. You should also use the most secure authentication protocol for connecting to your WiFi. By default, most modern routers will provide you with a WPA2 or WPA3 option which is currently the most secure. Additionally, ensure your password is strong. There are a few approaches to making a strong password – the general rule is for the password not to be a single word that can be found in a dictionary – for example, you can either make a string of 12+ alphanumeric characters or join three random words.

**Keep your router firmware up to date**

It is important to have the latest firmware installed on your router. Manufacturers release firmware updates to fix security vulnerabilities, implement new standards or add new features to improve the performance of the equipment. This helps the device to be exploited by malicious actors through an unpatched vulnerability. Some newer routers will provide updates automatically. To check for and install an update manually you have to log in to the router management panel. This can usually be done by navigating to 192.168.0.1 or 192.168.1.1 and entering the admin credential which is normally displayed on the back of your router, finding the relevant menu options, and following the instructions displayed.

**Secure DNS** 

Use DNS-over-HTTPS (DoH) which performs DNS resolution via the HTPS protocol, encrypting data between you and your DNS resolver. Although DoH is not perfect, it does remove the need for trust.

**Avoid the free router from your ISP**

Usually, the routers provided for free by your ISP are cheap versions manufactured in bulk with insecure propriety firmware that does not receive regular security updates. Consider swapping it for an open-source router or commercial router with secure firmware.

**Whitelist MAC addresses**

You can prevent unknown devices from connecting to your network by whitelisting MAC addresses in your router settings. This will disable connection from unwanted sources even if they know your credentials. This method is not 100% bullet-proof and malicious actors may be able to work around it by cloning their address to appear the same as one of your trusted devices, but it adds an extra step for them to take.

**Change the router’s local IP address**

It is possible for a malicious script in your web browser to exploit a cross-site scripting vulnerability, access known vulnerable routers at their local IP address, and tamper with them (known as CSRF attack). To help you protect from some of these automated attacks, change your router’s local default IP address (usually 192.168.0.1 or similar).