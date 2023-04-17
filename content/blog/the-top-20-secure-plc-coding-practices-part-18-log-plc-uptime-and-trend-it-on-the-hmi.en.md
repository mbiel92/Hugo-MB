+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 18 – Log PLC uptime and trend it on the HMI"
date="2021-01-20"
author="Eugene Wypior"
image="/blog/PLC-p18-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Log PLC uptime to know when it’s been restarted. Trend and log uptime on the HMI for diagnostics.** 

**Security Objective**

**Target Group**

Monitoring

Integration / Maintenance Service Provider

> ### Guidance

Keep track of PLC uptime 

*   in the PLC itself (if uptime is a system variable in the PLC)
*   in the PLC itself if it has MIB-2 / any SNMP implementation
*   externally by means of e.g., SNMP 

If the PLC has SNMP with MIB-2, which is very common, the OID for uptime “sysUpTimeInstance(0)” is 1.3.6.1.2.1.1.3. Uptime resets are important indicators for PLC restarts. Make sure the HMI alerts to any sort of PLC restart. 

Uptime correlated with error codes are good diagnostics. 

> PLC restarts are also good for diagnostics in case of failures and for monitoring which PLCs are being worked on at what time. 
> 
> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

The most basic attack vector for a PLC is to force it to crash and / or restart. For many PLCs, it is not that hard to do, because many PLCs cannot cope well with unexpected inputs or too much traffic. Thus, unexpected restarts can be an indicator that the PLC encounters unusual actions. 

**Reliability** 

See security, but for non-malicious causes. 

**Maintenance** 

/

> ### References

**Standard/framework**

**Mapping**

**MITRE ATT&CK for ICS** 

**Tactic:** [TA009 – Inhibit Response Function](https://collaborate.mitre.org/attackics/index.php/Inhibit_Response_Function)

**Technique:** [T0816 – Device Restart/Shutdown](https://collaborate.mitre.org/attackics/index.php/Technique/T0816)

**ISA 62443-3-3** 

**SR 7.6:** Network and security configuration settings

**ISA 62443-4-2** 

**CR 7.6:** Network and security configuration settings

**MITRE CWE**

**CWE-778:** Insufficient Logging

> ### What’s next?

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about logging PLC hard stops and trending them on the HMI.

.

> ### Do you require help with secure coding of your PLCs?

If you have any questions or require help in securely coding your PLCs, please contact SEQRED.

SEQRED specialises in providing bespoke OT and IoT cybersecurity solutions.  
Our services cover such areas as Critical Infrastructure Protection, Cloud Services Security or Audits, and Threat Intelligence. For a full list of our services visit our services page – [https://seqred.pl/en/services/](https://seqred.pl/en/services/)

###### **About this article**

You can download the full copy of the Top 20 Secure PLC Coding Practices by clicking [here.](https://www.plc-security.com/index.html#download)

The series of these articles is written under the following license:

Copyright (c) 2021 admeritia GmbH, Langenfeld/Rheinland, Germany

Permission is hereby granted, free of charge, to any person obtaining a copy of “Top 20 Secure PLC Coding Practices” and associated documentation files, to deal in the “Top 20 Secure PLC Coding Practices” without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the “Top 20 Secure PLC Coding Practices”, and to permit persons to whom the “Top 20 Secure PLC Coding Practices” is furnished to do so, subject to the following conditions:

THE “Top 20 Secure PLC Coding Practices” IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE “Top 20 Secure PLC Coding Practices” OR THE USE OR OTHER DEALINGS IN THE “Top 20 Secure PLC Coding Practices”.

