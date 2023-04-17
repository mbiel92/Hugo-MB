+++
lang="en-GB"
title="Data Privacy, Data Security, Vol. III 2"
date="2021-11-23"
author="Eugen Wypiór"
image="/blog/Data-Privacy-Security-NP4-2.png"
tags=['ABC security','IT security', 'response&recovery']
+++

## Browser hardening{ .article-section }

There are many layers at which you can improve your security and
privacy. Apart from the layer of the operating system and its settings,
the layer of applications, the next important layer is the browser used.
Browsers are a window into the users' minds and a possible entry into
their system (computer). That's why it is important to take care of the
privacy and security settings on the browser used. But privacy and
security are a sliding scale. The level of privacy and security a user
will want to maintain will depend on their individual privacy and
security model (requirements). This means that not all people have to
and as result will have the same level of security and privacy. The
below information is presented for the user to make their own assessment
as to which of the options presented best serve their needs. The process
presented is one called hardening and can be applied to any device with
adjustable settings. As the word suggests, one can make the desired
device as hard (or think -- resistant to exploitation or leaking private
information) as one wishes within the given parameters. In this case, we
will look at the Firefox browser to see what can be done, to improve the
privacy and security of its user.

## **Browser Settings**{ .article-section }

Starting with the General setting -- always allow for automatic updates
to install. This will allow Firefox (or any other browser) to be always
up to date with the most recent releases of security patches, and thus
provide the user with the best protection against potential exploits.

![](/blog/Screenshot-2021-11-22-at-18.30.30-1024x487.png)

In the next step, set your home page to a privacy-oriented search engine
such as DuckDuckGo. You will find it in the Search option of the
Settings menu.

![](/blog/Screenshot-2021-11-22-at-18.33.58-1024x304.png)

Disable all forms of suggestions in the Omnibox.

![](/blog/Screenshot-2021-11-22-at-19.27.29-1024x470.png)

By default, Firefox comes with a Standard setting in the Enhanced
Tracking Protection section of the Privacy & Security settings. Change
it to a Strict setting for improved tracking protection. Some websites
might not display or work correctly with this setting. In such instance,
temporarily lower your protection by reverting to Standard setting
option.

![](/blog/Screenshot-2021-11-22-at-19.41.15-1024x799.png)

To enhance your security, disable password management done by your
browser. Login details stored in the browser can be accessed in case the
computer is hacked remotely. It also allows anybody to access the user's
personal information on any service they are logged in to.

![](/blog/Screenshot-2021-11-22-at-19.31.29-1-1024x419.png)

Set the browser to never remember history. This and some of the
following steps can be also achieved by using the browser in the Private
mode.

![](/blog/Screenshot-2021-11-22-at-19.51.20-1024x337.png)

Remove cookies and site data when Firefox is closed.

![](/blog/Screenshot-2021-11-22-at-19.54.44-1024x359.png)

Block pop-up windows and limit as many permissions as possible.

![](/blog/Screenshot-2021-11-22-at-20.01.05-1024x638.png)

Disable any data collection done by Mozilla.

![](/blog/Screenshot-2021-11-22-at-20.03.18-1024x555.png)

Make sure you are not signed into any Firefox account to sync your
settings.

![](/blog/Screenshot-2021-11-22-at-20.04.50-1-1024x479.png)

Enable HTTPS-only mode.

HTTPS secures your connection using an SSL certificate and thus encrypts
your traffic.

HTTPS-only mode enforces HTTP requests to become HTTPS.

![](/blog/Screenshot-2021-11-22-at-20.10.58-1024x489.png)

## **Browser Add-ons**{ .article-section }

Even with all the above settings set this way, Firefox will still
collect a certain amount of data about you and your online activities.
To minimize this further, exceptionally, third-party help in the form of
add-ons is required.

The first Firefox add-on to be mentioned here is **uBlock Origin**, an
Open-Source ad and content blocker. The advantage of this add-on over
other similar ones is that uBlock Origin does not whitelist companies
who pay money to show ads.

![](/blog/Screenshot-2021-11-22-at-20.21.31-1024x418.png)

Next on the list to increase your privacy while using Firefox is the
Privacy Badger add-on. It blocks spy ads and invisible trackers.

![](/blog/Screenshot-2021-11-22-at-20.25.24-1024x385.png)

WebRTC leak is a vulnerability inherent in web browsers. It causes your
IP address to be visible while using VPN. Both uBlock Origin and Privacy
Badger have the option to fix WebRTC leaks.

If you want to take your privacy protection even further, you might want
to install the Decentraleyes add-on. It protects you from third-party
tracking through large, centralised, content deliverers such as
Google-hosted libraries.

![](/blog/Screenshot-2021-11-22-at-22.46.22-1024x425.png)

And for those, who really want to make sure they don't leave any trace
on the web and would like to become next to invisible, they might want
to try such Firefox add-ons as Cookie AutoDelete, CanvasBlocker, or
NoScript Security Script.

Most of the add-ons mentioned here are also available for Chrome, often
under the same name.

## Do you require help with hardening of your IT or OT system?{ .article-section }

[SEQRED [offers assistance in providing comprehensive security solutions
for IT and OT systems. It offers services in the areas of Security
Audits, Network Segmentation, Mobile Device Security, Cloud Security,
and many others.

To discuss your requirements, contact SEQRED at
[\[email protected\]](/cdn-cgi/l/email-protection)

###### **About this guide**

The idea for this article was inspired mainly by a presentation by Techlore which you can watch [here.](https://www.youtube.com/watch?v=NXsC1j7wIQE&list=PL3KeV6Ui_4CayDGHw64OFXEPHgXLkrtJO&index=21)