+++
lang="en-GB"
title="‘Denonia’ – the first cryptominer built for AWS Lambda"
date="2022-04-19"
author="Eugene Wypior"
image="/blog/Screenshot-2022-04-19-at-11.36.49.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

On the 6th April, CADO Security reported on its finding of the first known case of a cryptominer malware designed specifically to run in the AWS Lambda environment.

The malware is written in Go and CADO believes it contains a customised variant of the XMRig mining software, along with some other unknown functions.

It was named ‘Denonia’ by the CADO team after the domain it communicates with (gw.denonia.xyz) using newer address resolution techniques for command and control (C2) traffic designed to evade typical detection measures and virtual access controls making it difficult to detect.

Matt Muir, security researcher with CADO states that his team has not identified how Denonia is deployed yet. He believes it might be a question of compromising access credentials and then manually planting the malware into compromised Lambda environments. In response to the original article AWS issued a statement, part of which reads:

“_The software described by the researcher does not exploit any weakness in Lambda or any other AWS service. Since the software relies entirely on fraudulently obtained account credentials, it is a distortion of facts to even refer to it as malware because it lacks the ability to gain unauthorized access to any system by itself. What’s more, the researchers even admit that this software does not access Lambda–and that when run outside of Lambda in a standard Linux server environment, the software performed similarly.”_

The reference to Linux comes as result of the research team analysing the malicious code in a vanilla Amazon Linux sandbox environment where the code continued to execute. The team believed that this is because the Lambda serverless environment is abstracted from the underlying Linux infrastructure and the malware was fooled into believing it is operating in Lambda (after adjusting the necessary environment variables).

### **Mitigations**

The fact that the analysis of the malicious code didn’t reveal a way in which it spreads and so far, the only explanation is that it does so by means of compromised credentials, resource configuration and customer function code & libraries is a good thing. It means that following basic cybersecurity hygiene procedures can protect us from contracting this unwanted piece of cryptomining technology.

To protect your AWS account from unauthorised access remember to abide by the following:

*   Don’t use your root access to manage day to day tasks on the account. Create and admin user account to manage daily tasks instead.
*   Safely lock away your root access credentials.
*   Use a strong AWS root account password.
*   Enable Multi Factor Authentication (MFA) on your AWS root account.
*   If you have an access key for your AWS root account, delete it or, if you must keep it, change it regularly.
*   Never share your AWS root credentials or access with anyone.
*   Use TLS 1.2 or later to communicate with your AWS resources.

AWS also provides a range of tools to monitor and audit Lambda functions such as Amazon CloudWatch which monitors Lambda functions on your behalf, Amazon Cloud Trail, AWS X-Ray and AWS Config. When properly used these tools help you monitor the Lambda environment and help detect anomalies in its operations.