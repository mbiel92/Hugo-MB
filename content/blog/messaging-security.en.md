+++
lang="en-GB"
title="Secure Messaging"
date="2019-06-20"
author="@tals0n0r"
image="/blog/SecureMessaging-1.png"
tags=['ABC security', 'messaging security']
+++

Messaging is a part of the everyday life of almost all of us.

And as a form of digital communication, it is subject to security issues applying to other forms of this kind of communication.

Here are some hints to improve your security in this area

### **Only use fully end-to-end encrypted messages preferably operated by reputable open-source platforms**

Messages encrypted end-to-end are encrypted on the sender’s device and only decrypted once they reach the intended recipient. Should such a message be intercepted by a third party, it will be not possible for them to read it. Nor is it possible to read it on servers where it is stored.

When it comes to the encryption itself, only open-source applications allow for independent examination and audit of the encryption method. This allows establishing whether the encryption protocol does not allow for any backdoors, vulnerabilities, or other security issues. Therefore, unfortunately, proprietary applications cannot be trusted for communicating sensitive information. Also, in open-source ecosystems bugs are reported in a transparent way and usually fixed quickly. And version histories can show who added what and when. It is worth mentioning, that no piece of software is guaranteed totally bug-free and as result never fully secure or private – so being open source is still no guarantee that it is safe, but it is managed in a transparent way by design.

When going for an open-source encrypted messaging app ensure it is actively maintained and backed by reputable developers or at least be fully clear about where funding originates from and what their revenue model is. It should also have undergone an independent code audit, with its results publicly published.

### **Check the security settings**

Enable security settings in the app, including contact verification, security notifications and encryption. Make sure to disable optional non-security features such as read receipt, last online and typing notification. Should the application support cloud sync for either backup or for access through a desktop or web app companion, disable it as it increases the attack surface.

### **Ensure your recipient’s environment is secure and your recipient verified**

Although you might be following all the good practices regarding secure messaging it will come to no good if the people you are communicating with don’t do the same – as you know the system can only be as secure as its weakest link. So, take time to educate and inform the participants in your conversation, about good security practices – share with them about secure authentication, device encryption, network security, and malware prevention.

Always ensure you are talking with the intended recipient, and that they have not been compromised. One way of doing this is to use an app that supports contact verification. This is a very useful feature that enables users to trust the destination and ensure the conversation has not been hijacked.

The risk of compromise is higher in a group chat, rising exponentially the more participants are in a group. There is also a higher chance that an adversary is lurking among the members and can go unnoticed. Therefore, occasionally check that all participants are legitimate and ensure only trusted members have admin privileges. Additionally, it’s worth mentioning that with some messaging apps (especially if one of the participants is using an older version) not all group chats are encrypted.

### **Create a safe environment for communication**

There are several factors to the security of digital communications. These factors include the devices of the communicating parties, the ISP, the national gateway or government logging, the messaging provider, and the servers. You can help to minimise the risk inherent to these factors by keeping your devices up to date, avoiding malware, watching out for phishing attacks, relying on trustworthy services, creating strong passwords and 2Fam using encryption and helping those with whom you communicate do the same.

### **Defang URLs**

Sending links via WhatsApp, Slack, Apple Messenger, Wire, Facebook, and other services can unintentionally expose your personal information. This is because when a thumbnail or preview is generated (on the client-side) and therefore causes your IP, user-agent, and device info to be logged. This broadcasts to the website owner that you are discussing that website. One way around this is to defang the URL you are forwarding/sending – e.g. https://www.example.com => hxxps://www\[.\]example\[.\]com. You can also use VPN to help protect your IP.

### **Enable ephemeral messages**

The physical security of your device cannot always be relied upon. The feature of self-destructing messages allows for your messages to automatically delete after a set amount of time that you can vary from weeks all the way down to just a few seconds. This means that even if your device is lost, stolen, or seized an adversary will only have access to the most recent communications. Unlike remote erase, disappearing messages does not require your device to be remotely accessible or have a signal.

### **Avoid SMS**

Although very common and convenient but not secure, susceptible to threats, such as interception, sim swapping, manipulation, and malware. If you chose to use SMS, encrypt it before sending it.

### **Watch out for trackers**

A tracker is a piece of software meant to collect data about you or your usage. Be wary of messaging applications with trackers, as the detailed usage statistics they collect are often very evasive and can sometimes reveal your identity as well as personal information that you would otherwise not intend to share. You can check how many, and which trackers a given app uses, by searching it in [Exodus Privacy](https://reports.exodus-privacy.eu.org/en/).

### **Beware of jurisdiction**

The jurisdictions where the organisation running the messenger app is based, and data is hosted should also be considered. As in some territories, organisations are forced to comply with local government regulations, which can require them to keep logs of all users’ interactions and metadata, or hand over encryption keys. Where possible, avoid Five Eyes and other International Cooperatives, and countries with poor respect for user privacy such as China, Russia, Singapore and Malaysia.

### **Ensure forward secrecy is supported**

Opt for a platform that implements forward secrecy. This is where your app generates a new encryption key for every message. It means that if your adversary has obtained the private encryption key from one party, they will not be able to use it to decrypt any previously captured messages.

### **Consider a decentralised platform**

If all data flows through a central provider, you must trust them with your data and meta-data. You cannot verify that the system running is authentic without back doors, and they may be subject to local laws, court orders, or censorship, and if that provider ceases to operate, the entire network will be unavailable for that duration. Whereas with a decentralized system, there are no central servers to compromise, and no single point of failure. It cannot be raided, shut down, or forced to turn over data. Some decentralized platforms also route traffic through the Tor network, which provides an additional layer of anonymity and security.