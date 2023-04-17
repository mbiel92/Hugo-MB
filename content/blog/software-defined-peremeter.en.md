+++
lang="en-GB"
title="Software Defined Perimeter"
date="2022-03-14"
author="Eugene Wypior"
image="/blog/SDP-2.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

A Software Defined Perimeter (SDP) is a network security architecture that uses user authentication and network segmentation in order to grant access to resources based on the principle of authentication first, access later. SDP is a way of implementing the Zero Trust Network Access which is the main technology associated with Zero Trust Architecture.

Contrary to having a human-defined perimeter with static, open ports leading to various access solutions the Software Defined Perimeter’s default state is that of all the ports closed to all incoming traffic from anyone. In this way, the organisation becomes invisible online as it does not publish any services or makes information available to the outside, making it impossible for hackers to gather information during the reconnaissance phase of the Cyber Kill Chain model. Users who want to access the desired resources within the perimeter must first authenticate at a public, off-site location that is not part of the corporate network. Only after doing so access is granted and a port is dynamically opened by software. Unlike a traditional open port, an SDP-operated port is specific for that user, from a particular location at a specific time and to a specific destination within the corporate network, while the organisation remains hidden, seemingly off-line to the rest of the world. By the time the connection is accepted to the corporate network, it has already been legitimated and authenticated. Amongst its many benefits, SDP solves the issue which emerged with the surge in IP addresses and the perimeter loss in cloud environments, which weaken location-based security, providing connection-based security instead.

####  **SDP architecture and the way it works**

A simple SDP architecture can comprise of

an SDP Client (Initiating Host),

an SDP Controller and

an SDP Gateway

The SDP Client is normally software installed on the endpoint which usually handles the device verification and the tunnel setup to the SDP Gateway.

The SDP Controller functions as a trust broker between the client and the back-end resource. The SDP Controller link with an Identity Management solution to authenticate and check authorisation for any given request. The controller also sets up an encrypted tunnel between the clients and the remote resource. Access is provided only for a specific resource the client is requesting and has authorisation for. In addition to verifying and authorising the user, the controller also verifies the Client’s device making sure that it is running up-to-date software, checks for malware infections and performs other security inspections.

The SDP Gateway grants access to the requested resource. Once the gateway confirms with the controller that the client can access a given resource, the connection to the application is allowed.

For the duration of the connection, the SDP Client and SDP Gateway communicate with the SDP Controller and exchange information. If at any time during the connection the client’s key is compromised or invalidated, or their machine is showing signs of being compromised the connection is immediately blocked off and all visibility to applications or servers on the network is cut off.

SDP inventor – Cloud Security Alliance – claims that SDP mitigates the most common network-based attacks, including server scanning, DoS, SQL Injection, operating system and application vulnerability exploits, man-in-the-middle, pass-the-hash, or pass-the-ticket.

###### **About this article**

This article was based on a couple of video presentations which you can watch [here](https://www.youtube.com/watch?v=DenGhmqExw8) and [here](https://www.youtube.com/watch?v=_yGGZj9wkaU).

And the entry on SDP on [Wikipedia](https://en.wikipedia.org/wiki/Software-defined_perimeter).
