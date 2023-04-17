+++
lang="en-GB"
title="Industrial Network Security Architecture - Network Segmentation"
date="2022-03-28"
author="Eugen Wypiór"
image="/blog/INSA_ns-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

The idea of network segmentation is an old concept in IT environments.
It began as a way to improve network performance and bandwidth. Recently
network segmentation is used proactively as a part of network security
architecture. Segmenting the network into separate zones allows them to
be individually and independently controlled, monitored, and protected.

 In the realm of Operational Technology, this is especially important
due to the specific nature of the operational environment and is
reflected within the ISA/IEC 62443-3-3 SR5.1 RE1: "SR5.1 RE1 -- Physical
network segmentation: The control system shall provide the capability to
physically segment control system networks from non-control system
networks and to physically segment critical control system networks from
non-critical system networks".

 To implement this standard for Industrial Automation and Control
Systems (IACS) the following criteria should be taken into
consideration:

 

#### 1. Safety Instrumented System and Functions (SIS & SIF)

In automation environments safety applies to applications that
potentially could harm people and assets. If a safety-related Industrial
Control System (ICS) is present it must be isolated from the other
equipment on the plant network.

 

#### 2. Communication in the automation environment

Factory equipment that belongs to the same automation application and
ICS have to be placed in the same zone as the communication protocols
required for industrial processes exchanged between the controller and
the device are subject to strict requirements in terms of delay --
counted in microseconds -- and jitter. Accidently assigning them to
different zones can lead to equipment malfunction or output problems.

 

#### 3. Functional relationship

A production process usually requires a range of equipment functioning
closely together with interdependent processes. Such groups of machines
should be grouped in a dedicated zone with the same security
requirements.

 

#### 4. Risk homogenous zones

Following the ISA/IEC-62443 standards, critical devices (as identified
during the relevant risk assessment) must be assigned to their own
security zone. And devices tagged with the same security level can be
grouped and connected into the same zone.

 

## **Industrial network layers**{ .article-section }

 

To prevent unauthorised and malicious access through lateral movement,
the industrial network (OT) has to be separated from the enterprise part
of the network (IT).

In the ISA/IEC-62443-3-3 this is defined as "Protection against
intentional violation using simple means with low resources, generic
skills and low motivation" and is equivalent to security level 2 (SL2).

 To achieve this the following architecture is recommended:

 

#### 1. Cell layer

 The cell layer is the bottom layer of the industrial network
architecture. Its topology will be determined by the intended
application. Where redundancy is not required, a line, tree, or star
model can be implemented. For critical industrial processes, a
redundancy topology will be necessary, e.g., a ring that will require
the use of managed switches to support the redundancy protocols.
Typically, a cell groups devices belonging to the same machine or
functional group. Where additional devices of non-automation nature are
to be connected to a cell, this should be done using a VLAN, to separate
these devices from the devices in the cell and so the VLAN must be
secured by the cell protection firewall which acts as a secure gateway
for all traffic.

 

#### 2. Aggregation layer

 This layer groups multiple cells and machines involved in the same
production process into dedicated aggregation networks. The main purpose
of this layer is to act as a connection point between the cell and the
backbone layer. It is advisable to use the redundancy topology here with
network devices able to transfer traffic at rates of several gigabits
per second with high port density. Devices performing additional
functions such as wireless access points and network monitoring systems
can be connected here.

 

#### 3. Backbone layer

 The backbone layer is the focal point of the industrial network. It
secures redundant connectivity to the aggregation layers, the industrial
data centre, the industrial DMZ, and the enterprise network. It is
essential to use firewalls between the aggregation layer and the
backbone layer as well as between all the elements of the backbone layer
and on the threshold of the enterprise network.

###### **About this article**

This article was inspired by a Siemens publications. You can read the full text by clicking [here.](https://new.siemens.com/global/en/products/automation/industrial-communication/industrial-network-solutions/white-paper-industrial-network-security-architecture.html)