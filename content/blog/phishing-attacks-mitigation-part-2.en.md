+++
lang="en-GB"
title="Phishing Attacks & Mitigation – part 2"
date="2022-08-22"
author="Eugene Wypior"
image="/blog/phishing-p2-1.png"
+++

According to the CISCO’s 2021 Cybersecurity threat trends report, phishing accounts for around 90% of data breaches with at least one person having clicked a phishing link in around 86% of organisations.

## **How to protect yourself from falling prey to a (spear) phishing attack?**{ .article-section }
---------------------------------------------------------------------------

There is no 100% phishing-proof recipe and not getting caught requires an approach of constant vigilance when opening and acting on received emails, texts, and voice messages (communication).

Some of the common ways of recognising a phishing email are the indicators the majority of us are familiar with by now, such as:

*   Grammar and spelling mistakes
*   Ridiculously sounding promises and assurances – such as $5M awaiting you
*   The email doesn’t call you by your name
*   The email address the message came from is different from the official one
*   The domain name they come from looks very similar to a legitimate domain name using similar-looking names or spelling tricks – such as arnazon.com

to name only the most common and obvious ones.

The following can also be indicators of a phishing attack, which when turned into a spear-phishing attack – when the email you receive is personalised by addressing you directly and possibly fortified by some other personalised information that the hacker obtained by researching you and/or your company – can turn more dangerous as it will look more genuine:

*   Urgency – you might be sent a message that has a tight deadline on it – ‘RE: Update your IT login NOW!!!’
*   Authority – the message might appear to come from a trusted authority, like your boss, colleague or a company you often use.
*   Mimicry – spear-phishers can exploit your daily habits by sending you messages at about the time you’d expect them.
*   Curiosity – Sometimes the attacker will try to entice you in – ‘Breaking news from HR’

## **Multi-layered anti-phishing defence approach**{ .article-section }

The UK National Cyber Security Centre advises a four-layer defense system against phishing attacks.

#### **Layer 1 – Make it difficult for attackers to reach your users**

– Don’t let your email addresses be a resource for attackers

Attackers ‘spoof’ trusted emails making it look like the attacker’s email comes from a reputable organisation (such as Amazon, PayPal, or yours). To mitigate this consider using one of the anti-spoofing controls:

*   DMARC – Domain-based Message Authentication, Reporting and Conformance  
    allows you to set a policy for how receiving email servers should handle email which doesn’t pass either SPF or DKIM checks. This includes untrusted emails, which should be discarded. DMARC also generates reports, which you can use to understand how your email is being handled.
*   DKIM – Domain Keys Identified Mail  
    allows you to cryptographically sign the email you send to show it’s from your domain.
*   SPF – Sender Policy Network  
    allows you to publish IP addresses that should be trusted for your domain.

– Encourage digital footprint management

Attackers use publicly available information about organisations and users to craft their spear phishing messages to make them more convincing. This information can be obtained from the company’s website and social media accounts.

This is especially crucial regarding the information relating to high-profile members of the organisation, as it can be used to prepare personalised whaling attacks.

Also, partners, contractors, and suppliers can give away sensitive information about one’s organisation online.

– Filter or block incoming phishing emails

*   Technical defenses – investing in appropriate technical and network controls to limit the amount of potentially malicious emails that employees could face to receive.
*   Avoid using a predictable structure for email addresses (e.g. [surname@organisation.com](mailto:firstname.surname@organisation.com)) – these can be easily guessed by an individual looking to target an employee they have found online.

#### **Layer 2 – Help users identify and report suspected phishing emails** 

– Carefully consider the approach to phishing training

Growing evidence shows that no one can be expected to spot all phishing emails and spear-phishing is even harder to detect. Responding to emails and clicking on links is a huge part of the modern workplace, so it’s unrealistic to expect users to always remain vigilant. So how can you improve the situation through training?

*   Be upfront with your staff that phishing messages can be hard to identify and they are not expected to be able recognise them 100% of the time.
*   Encourage a supportive environment for employees to come forward if they feel they may have responded to something that they now regard as suspicious and re-assure them that it is OK to ask for further support when something looks suspicious.
*   Make sure your employees are aware of the danger of phishing, and that it is clear, especially to those departments that may be more vulnerable to it such as customer-facing departments or staff with access to sensitive information such as IT or finance. Offer these departments additional support.
*   Make your employees aware of the common features of phishing messages such as urgency or authority leverage.

– Make it easier for users to recognise fraudulent requests

One of the ways phishing attackers work is to exploit legitimate processes such as payments. Think about which processes can be mocked by attackers and what measures can you put in place to harden them so phishing attacks are more difficult to execute.

*   Ensure staff are familiar with the regular ways procedures (for example payments) are done, so there is a better chance for them to recognise an unusual request.
*   To make processes more resistant to phishing Introduce an additional channel of communication (such as a text message, a phone call, logging into an account, or confirmation in person) to verify important email requests such as payments.
*   How will suppliers recognise emails from you as genuine? Are they expecting an email from you, and will they recognise your email address?

– Build a culture that encourages users to report phishing attempts

Creating an environment that encourages users to report phishing attempts can provide you with vital information about the types of phishing attacks used. You can also find out what types of emails get mistaken for phishing attacks, and how this might impact your organisation.

*   Have an effective reporting process in place allowing users to report a potential phishing attempt. Ensure the process is clear, simple, and convenient to use and users know their reports are being acted on.
*   Never punish those who struggle to recognise phishing messages. People who are told off for doing something will not report mistakes quickly, if at all.

#### **Layer 3 – Protect your organisation from the effects of undetected phishing emails**

As it is not always possible to stop all attacks, you should ensure you have put in place guards to minimise the impact of undetected phishing emails.

– Protect your devices from malware

Phishing emails often contain attachments with malware or links to website that carry it. Well configured devices and good endpoint defenses can stop malware from installing, even if the email is clicked.

*   Prevent attackers from using known vulnerabilities by only using supported software and devices and that they are always kept up to date with the latest patches.
*   Prevent users from accidentally installing malware from a phishing email, by limiting administrator accounts to those who need those privileges.

– Protect your users from malicious websites

*   Most current, up-to-date browsers will block known phishing and malware websites (note: this does not always apply to mobile devices).
*   If possible, run a proxy service to block any attempt to reach websites identified as hosting malware or phishing campaigns.

– Protect your accounts with effective authentication and authorisation

*   Add additional security to your login process using multi-factor authentication (MFA).
*   Consider using password managers, some of which can recognised real websites and will not autofill on fake websites.
*   Consider using alternative login mechanisms (like biometrics or smartcards) which are more challenging to steal than passwords.
*   Only provide privileged access to people who need it for their roles as the damage the attacker can cause is proportionate to the privileges assigned to the credentials stolen.
*   Have a strong password policy in place.

#### **Layer 4 – Respond quickly to incidents**

– Detect incidents quickly

*   Ensure users are familiar with the way to report incidents before they occur.
*   Use a security logging system to pick up on incidents users are not aware of.
*   Once a monitoring capability has been set up, it needs to be kept up to date to ensure it remains effective.

– Have an incident response plan

*   Ensure that your organisation knows what to do in the case of different types of incidents. For example, how will you force a password reset if the password is compromised? Who is responsible for removing malware from a device, and how will they do it?
*   Incident response plans should be practiced before an incident occurs. The best way to do this is through exercising.

###### **About this article**

###### To read the full article on phishing attacks on NCSC website click [here.](https://www.ncsc.gov.uk/guidance/phishing#section_4)