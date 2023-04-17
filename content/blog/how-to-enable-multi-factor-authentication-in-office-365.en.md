+++
lang="en-GB"
title="How to enable multi-factor authentication in Office 365"
date="2020-05-25"
author="Michał Kwiatkowski"
image="/blog/Uwierzytelnianie_wielopoziomowe.jpg"
+++

The coronavirus pandemic has forced many organisations to undergo a
rapid digital transformation and switch to a remote workforce. This
sudden change created a need for tools allowing users remote access to
company resources. Within a couple of days, business processes of many
companies have been moved online. Due to the rapidness of the changes,
not all employees have been sufficiently prepared for working remotely
and telecommunication and IT systems have not been adequately secured.
Many cybercriminals have taken advantage of the current situation,
taking quick and widespread action. A large part of their activity
consists of phishing attempts aimed at stealing login data. Thankfully,
negative impact of phishing can be avoided by the use of multi-factor
authentication.

**In this article, you will find out about:**

-   an increase in the number of phishing attacks during the Covid-19
    pandemic
-   what MFA (Multi-Factor Authentication) is
-   configurating a second factor of authentication in Office 365

[Read more: Best practices for safe and secure remote work](https://seqred.pl/en/best-practices-for-safe-and-secure-remote-work/)

## Phishing scams during the Covid-19 pandemic

Due to the ongoing pandemic and a large number of people being forced to
work from home, there has been a noticeable increase of phishing
attacks, aimed at gaining access to company assets through social media
platforms and cloud computing tools. One of the more popular ways to
achieve that is acting as an app related to Office 365. This type of an
attack requires a well falsified login page. If the victim fills the
boxes in with required information, the attacker can easily gain access
to cloud storage used by an organization and be able to tamper e.g. with
messages, files and customer or financial data of a company.

**Would everyone be able to recognise a fake login screen?**

![](/blog/phishing-falszywy-ekran-logowania.jpg)

## Multi-Factor Authentication- protection from unauthorised access

Multi-factor authentication is a recognised way of protecting your
passwords in a potential cyberattack. It includes additional means of
authentication a user has to go through before completing the login
process and accessing the system. For example, to log into Office 365,
in addition to filling in their account name and password, a user has to
enter a one-time password received in a text message.

### Various authentication factors

For authentication process to be considered „multi-factor" it must
require authentication mechanisms from more than one of these groups:

-   user-specific information: a password or an answer to a question,
-   euser-specific device or equipment: keycards, usb keys, smart-cards
    or a phone,
-   biometric authentication: retina scans, fingerprint scans, voice or
    face activated authentication (read more about biometric here),
-   location e.g. used by Google to block log in attempts form places
    which are far from a user's current location or locations not
    typical for a specific user,
-   time, e.g. creating a timeframe based on employees' work schedule,
    in which a system can be accessed.

It is important to note that the security measures listed above will not
protect a user from accidentally sharing their password in a phishing
attack. Multi-factor authentication prevents unauthorised access to data
stored in a cloud during an attack, because even with the password the
attacker will not be able to pass other steps of the log in process.

## Configuring a second factor of authentication in Office 365

Office 365, even on its most limited license, allows the user to include
its mobile app in the log in process, to provide an additional factor of
authentication.

**How to configure and activate this mechanism?**

**1.** Log in to an administrative user
account and go to the Admin center app.

[[![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja_krok-1.jpg)

**2.** Choose „Users" in the menu and click
on „Active users". When a list of registered users pops up, choose
"Multi-factor authentication" from the top of the list.

![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja_krok-2a.jpg)

**3.** You will receive a list of users along
with information on their MFA status. Before you start updating
individual users' status, click on "service settings" to adjust the
settings for the whole organization.

![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja-krok-3.jpg)

If you want to allow users to use applications with no built in
Microsoft authentication e.g. some email clients, pick the option
allowing for the creation of passwords for specific apps.

![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja-krok-4.jpg)

In the following part, we will discuss which channel you should use to
conduct further verification:

-   a phone call and a text message are the easiest and most accessible
    method, but generate additional costs with every authentication
    attempt,
-   a mobile app notification is the easiest to use for most users, but
    requires installing Microsoft Authentication,
-   using a verification code is another popular option for Microsoft as
    well as applications created by other manufacturers, e.g. Amazon or
    OVH, however it does require a hardware token or code generating
    application. These types of functionalities can be provided not only
    by the previously mentioned Microsoft Authenticator, but also other
    solutions such as Authy, AndOTP or Google Authenticator,

After making appropriate adjustments, make sure to save the changes
before you return to the list of users.

After running the multi-factor authentication mechanism for one or more
users select them from the list -- afterwards, an Enable button should
appear at the right side of the screen. After turning this option on,
when a user is logging into one of the components of Office 365, a
request for additional information will automatically pop up in the
browser, followed by the configuration creator.

The configuration process is quite simple and intuitive, however it is
considered good practice to test it on a smaller group of users. It is
important to point out that before selecting „login using the app" a
user should first complete the MFA configuration wizard . Not doing so
might result in another login page and MFA configuration wizard
resetting, which would then lead to a disruption in the log in process
as well as other potential problems.

![](/blog/Uwierzytelnianie-wieloskladnikowe-konfiguracja-krok-5.jpg)

After enabling the service, every user can adjust its settings on their
own panel.

Enabling multi-factor authentication is fairly straightforward and using
it should not be too complicated or tedious for any user. The
implementation of this security measure is worth considering if your
goal is to protect the entire organization from a loss of data.