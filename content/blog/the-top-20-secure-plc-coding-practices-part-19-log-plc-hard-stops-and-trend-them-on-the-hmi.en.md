+++
lang="en-GB"
title="The Top 20 Secure PLC Coding Practices. Part 19 – Log PLC hard stops and trend them on the HMI"
date="2021-01-26"
author="Eugene Wypior"
image="/blog/PLC-p19-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

### **Store PLC hard stop events from faults or shutdowns for retrieval by HMI alarm systems to consult before PLC restarts. Time sync for more accurate data.** 

**Security Objective**

**Target Group**

Monitoring

Integration / Maintenance Service Provider

> ### Guidance

Fault events indicate why a PLC shuts down so that the issue can be addressed before a restart. 

Some PLCs may have error codes from the last case where the PLC faulted or shut down improperly. Record those errors and then clear them. It might be a good idea to report those errors to the HMI as informational data or perhaps to a syslog server, if those features and that infrastructure exist. 

Most PLCs also have some kind of first scan feature that generates events. It is a behavior that nearly all PLC equipment has in some form. It is basically one or more flags or a designated routine that is executed on the first scan of a PLC after it “wakes up.” This First Scan should be logged and tracked. 

> ### Why? 

**Beneficial for …?**

**Why?**

**Security**

Logs enable troubleshooting in case of an incident. Before a PLC becomes operational, especially after having experienced problems, it is important to ensure it is trustworthy. 

**Reliability** 

Logs are also good sources for debugging if the event was not caused maliciously. 

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

In the next article of The Top 20 Secure PLC Coding Practices series, you will find out about monitoring PLC memory usage and trending it on the HMI .

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

