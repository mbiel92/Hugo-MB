+++
lang="en-GB"
title="Industrial Network Security Architecture - Network Protection"
date="2020-03-30"
author="Eugen Wypiór"
image="/blog/NetworkProtection-2.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Segmenting an industrial network into a cell layer, an aggregation
layer, and a backbone layer is not enough from a cybersecurity
perspective. Such a solution is missing the necessary functions of
restriction of data exchange and the identification of authorised users.
To implement these functions additional components capable of filtering
the traffic, detecting authorised connections, and sending notifications
must be added to the network.

The need for accurate network protection and its incident audit
capability is reflected in sections SR1.1 and SR5.2. of the
ISA/IEC-62443-3.3, the flexible framework
developed by the ISA99 committee addressing and mitigating current and
future security vulnerabilities in industrial automation and control
systems (IACSs).

Section 'SR 1.1 - Human user identification and
authentication states:

'The control system shall provide the capability to identify and
authenticate all human users. This capability shall enforce such
identification and authentication on all interfaces which provide human
user access to the control system to support segregation of duties and
least privilege in accordance with applicable security policies and
procedures.'

 Section 'SR 5.2 - Zone boundary protection]' states:

'The control system shall provide the capability to monitor and control
communications at zone boundaries to enforce the compartmentalisation
defined in the risk-based zones and conduits model.'

**User and device authentication**

User and device authentication procedures are crucial for the safety of
IT and OT systems. Recently, there has been a paradigm shift in the
approach of how users are being allowed access to resources on a network
requiring access credentials. This approach falls within the concept of
'Zero Trust Network Access' and one of its most well-known
implementations when it comes to the user and device authentication is
the Software Defined Perimeter (SDP). It allows for verification and
authentication of the user and its device before they are even allowed
to access the desired network. And once access is granted, it is granted
only for the absolute necessary resources required to complete the task
at hand making it impossible for them to access or let alone see
anything else available on the network. Furthermore, shall the
authorisation credentials be removed or changed while the task is
performed, or shall their device become compromised while on task, their
access to the resource(s) is being terminated instantly. On a technical
level, this requires a user and device database containing a list of all
authorised users and their devices together with their corresponding
access rights and credentials. Such a solution will also allow for all
access requests to be logged and accounted for in the respective device
as well as in the authentication server.

**Zone boundaries traffic control**

Firewalls should only accept previously agreed ingress traffic following
the rule of whitelisting -- denying by default all but listed
connections. The firewall should also monitor the state of an active
connection and granularly assign rules to specific users.

Alternatively, to a firewall, an Intrusion Detection and/or Prevention
System can be installed to monitor the system and check traffic for
known patterns and deviations from baseline traffic as well as generate
an alarm requiring a follow-up. Or as in the case of an IPS it will
actively block suspicious or unusual activity, however, in an OT
environment where technical processes are ongoing, such solutions must
be implemented with great consideration as not to disrupt and/or
endanger the production environment.

**Centralised OT firewall management**

In large networks with many firewalls a central firewall management
system is necessary to assure consistent configuration.

###### **About this article**

This article was inspired by a Siemens publications. You can read the full text by clicking [here.](https://new.siemens.com/global/en/products/automation/industrial-communication/industrial-network-solutions/white-paper-industrial-network-security-architecture.html)