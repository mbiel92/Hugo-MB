+++
lang="en-GB"
title="Man in the Middle Attacks & Mitigation"
date="2022-07-12"
author="Eugene Wypior"
image="/blog/MITM-1.png"
tags=['ABC security','messaging security']
+++

## What is a Man in the Middle attack?{ .article-section }

Man in the Middle attack is a type of cyber attack where an attacker intercepts and relays messages between two parties who believe they are communicating with each other.

MITM attacks pose a serious threat to online security because the attacker can capture and manipulate sensitive data, like login credentials, account details or credit card numbers in real-time. Depending on the attacker’s intentions they can passively eavesdrop on the communication or actively change the content of the information they intercept.

 An exemplary MITM attack could follow these steps:

1.  An attacker installs a packet sniffer to detect insecure network traffic
2.  Once the user logs into the insecure website, the attacker sends them to a fake website
3.  The fake website mimics the original website and collects all pertinent user data that the attacker uses on the original website

 Cybercriminals conduct MITM attacks in a variety of ways and two typical phases can be distinguished:

#### **Interception**

This is the phase where the attacker places themselves in the way of the information flow exchange.

The simplest and most common way is **WiFi eavesdropping**. Here, the malicious actor sets up a free, not password-protected WiFi hotspot available to the public. Should a victim connect to the internet this way, the hacker has full information on all data exchanged online by the victim. This is an example of a **passive interception**.

 **Active interception** methods include:

*   IP spoofing – where the attacker creates Internet Protocol (IP) packets with a false source IP address, impersonating another computer system or disguising the sender’s identity. It is the most common method of session hijacking.
*   ARP spoofing – Address Resolution Protocol (ARP) is used to link the Internet Protocol (IP) address of a device on a Local Area Network (LAN) to a Media Access Control (MAC) address for the sake of communication between the devices. These linked pairs are stored in an ARP table. Spoofing occurs when the attacker, who gained access to the LAN makes a change in the table, substituting his MAC address with an existing one thus linking it with the IP address of a legitimate user on the network.
*   DNS spoofing – these attacks exploit vulnerabilities in Domain Name Servers (DNS), allowing for corruption of the DNS’s data (fake data is introduced into the DNS resolver’s cache hence an alternative name for this type of attack is ‘cache poisoning’), causing the name server to return the incorrect IP address and thus directing the unaware user to a website different than the intended one.
*   Email hijacking – is a specific type of spoofing where an attacker gains access to the victim’s email account (usually through phishing or social engineering) and silently monitors the email traffic in order to use the information contained for malicious purposes. There are many ways this method can benefit the attacker from taking over other victims’ online accounts to sending the victim a false call to pay a bill or similar. The best way to protect oneself from this type of attack is Two Factor Authentication (2FA).

#### **Decryption**

Once traffic has been intercepted, most likely it is encrypted using the Secure Sockets Layer (SSL) protocol and needs to be decrypted.

To decrypt traffic data, the attacker can use one of the following methods 

*   HTTPS spoofing – here the attacker presents a fake certificate to the victim’s browser after the initial connection request to a secure site is made enabling them to access any data entered by the victim before it is passed to the application.
*   SSL stripping – the attacker downgrades the communication between the client and the server into an unencrypted format by intercepting the TLS authentication sent from the client to the server. The hacker sends an unencrypted version of the application’s site to the user while maintaining the secure session with the application thus making the entire session visible to the hacker.
*   SSL hijacking

## How to prevent Man in the Middle attacks?{ .article-section }

*   Don’t connect to unverified hotspots which offer a free internet connection. Remember – if you are not paying for the product, you are the product.
*   Pay attention to browser notifications warning of unsafe websites.
*   Logging out of applications when not in use.
*   Not using public networks for conducting sensitive transactions (such as banking).