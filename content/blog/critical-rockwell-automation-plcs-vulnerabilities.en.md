+++
lang="en-GB"
title="Critical ROCKWELL AUTOMATION PLCs vulnerabilities"
date="2022-05-11"
author="Eugene Wypior"
image="/blog/Rockwell-61-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++



On the last day of March this year, CISA released two industrial Controls System Advisories (CSAs) describing vulnerabilities affecting numerous versions of Rockwell’s Logix Controllers and several versions of its Studio 5000 Logix Designer application.

The first vulnerability (CVE-2022-1161), with a severity rating of 10, allows an attacker with the ability to modify a user program to change the user program code on some ControlLogix, CompactLogix, and GuardLogix Control systems without it being visible to the programmer of the PLC. The reason for this stems from the fact that the executable file – the bytecode that the controller actually executes – and the source code (the text code entered by the user) are stored in two separate locations on the PLC. This allows the malicious actor to modify the bytecode without changing the source code and the PLC doesn’t have an integrated safety mechanism that would check that these two are matching. As a result, an engineer looking at the text code will only be able to see that code and not the altered code actually being executed without any indication of change.

To mitigate this vulnerability CISA advises to:

*   Recompile and download the user program code
*   Put controller mode switch into Run position (and if this is impractical there is an alternative suggestion)
*   Implement CIP Security to help unauthorised connections when properly deployed

For a full list of mitigations refer to the advisory (link below the text)

It’s worth mentioning here that these PLCs are among the most commonly used ones in almost all verticals including automotive, food & beverage and oil &gas.

The other vulnerability (CVE-2022-1159), with a severity rating of 7.7, refers to Rockwell’s software used by engineers to program its PLCs, the Rockwell Studio 5000 Logix Designer. It allows an attacker with administrative access, to inject malicious code during the compilation process. Such code can then be executed on a PLC without triggering any alert.

There is no direct mitigation for this vulnerability, however a detection method is available to determine if the user program residing in the controller is identical to what was downloaded. And to leverage the detection capabilities users are directed to upgrade to more recent versions of the software and firmware of a range of PLCs.

For a full list of mitigations refer to the advisory (link below the text)

In both cases the common mitigation is to adhere to general security guidelines for a comprehensive defence-in-depth strategy.

Although these are vulnerabilities, they enable attackers to achieve a result similar to that achieved by either a Stuxnet or a Triton type attack – to change the logic flow in a PLC and have it execute a concealed bytecode while letting the engineers believe that a normal code was executed.