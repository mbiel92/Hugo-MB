+++
lang="en-GB"
title="Common Attack Vectors in the Cloud"
date="2022-03-01"
author="Eugen Wypiór"
image="/blog/CAVC.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Once a threat actor breaches the security of a cloud environment (see
our post from last week on Common Cloud Vulnerabilities) it can freely
use its resources allowing for scaling the attacks and wiping traces.
According to the 2021 IBM Security X-Force Cloud Threat Landscape Report
the most common uses of these resources are:

-   To deliver malware (including ransomware)
-   To execute command-and-control attacks
-   Deployment of cryptominers

### **1. Malware prefers containers**

Improperly configured Docker containers prone to compromise are a
sought-after destination for many malware types, which shift their
targeting from generic Linux systems in favour of Docker containers. The
most common Docker attacks are host or registry based and running
container attacks. In case of host attacks, it is possible to compromise
a host server when port 2375 (or 2376) of the daemon Docker is exposed
without authentication. Registries allow DevOps to make ready-made
images available to systems. Successfully reaching a registry allows a
hacker to extract the images contained therein being able to obtain
sensitive information such as authentication keys, passwords, or
certificates. The opposite action is also possible, where an attacker
rewrites or pushes an image containing a backdoor to the information
system.

The main malware types which were found affecting Dockers were XoRDDOS,
Groundhog, Tsunami as well as botnet malware.

Other types of containers, such as Windows or Kubernetes were also
observed to be exploited. The first one was by Siloscape malware, the
latter by TeamTNT.

The Kubernetes containers were especially targeted when operating within
corporate environments as they can provide an attacker with initial
access to one component of the infrastructure and subsequently allow for
lateral movement thus providing access to desired resources.

### **2. Cryptominers through misconfigured image containers**

From the four most common malware types -- banking trojan, botnet,
miner, and ransomware -- it is the mining malware that shows the highest
percentage of code update/alteration compared to the year before with
nearly 7% of code being new.

Cryptominers remain the top hacker's aim with the use of malicious
Docker images. Once an image is created and access to a Docker daemon
gets compromised, the threat actor will use the image to generate a new
container already containing the infected image.

### **3. Command-and-Control moves to the cloud**

On top of using the cloud environment to host malicious payloads threat
actors also increasingly use it to hold their Command-and-Control
backend for their activities. They do it to avoid signature-based
detections as top-level domains of cloud service providers are usually
trusted by most network scanning services. This enables threat actors to
avoid certain security controls by blending into regular network
traffic.

This is not a new practice, but the trend has grown over 2021 seeing
more cloud-based solutions of this type. The types of application can
include chat or YouTube video descriptions, possibly hiding dubious
network traffic as licit activity.

###### **About this article**

This article was based on the 2021 IBM Security X-Force Cloud Threat Landscape Report. To read the full report click [here.](https://www.ibm.com/downloads/cas/WMDZOWK6)