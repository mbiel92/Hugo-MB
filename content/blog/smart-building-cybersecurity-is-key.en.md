+++
lang="en-GB"
title="Smart Buildings – Cybersecurity is key"
date="2019-04-24"
author="Łukasz Dudkowski"
image="/blog/Cyberbezpieczenstwo_smart_building-1.jpg"
tags=['smartbuilding', 'proptech']
+++

Today’s buildings are more than concrete, steel and glass: they are structures filled with ctechnology readyutting edge technology designed to aid business activity 24 hours a day, all year round. These are intelligent buildings equipped with advanced technological solutions to optimise their functioning and provide the highest level of comfort to their users.

The specialist software used in such structures manages, controls, monitors and supports almost every field of activity, from managing the flow of people, through video surveillance as well as monitoring temperature and air conditioning, to the control of lighting, elevators and parking systems. **The growing number of manufacturers and available solutions, along with the creation of the IoT, caused the emergence of increasingly more serious threats to cybersecurity.**

#### **As modern technology progresses, it is important to consider the following issues related to Smart Building cybersecurity**

*   Is there a sufficient startegy in place in case of a malfunction in access control?
*   Would you still be safe if you lost access to your video surveillance system?
*   Is there a plan of action in case someone remotely switches off the lights in your building?
*   What would the consequences of faults in the cooling system be in server rooms or warehouses in which temperature-sensitive goods are stored?

**It’s high time to consider these issues and prepare accordingly!**

![](/blog/Cyberbezpieczenstwo_smart_building-1.jpg)

**This article will discuss:**

*   What are Smart Buildings, what are their characteristics and what systems do they use?,
*   examples of hacker attacks targerting Smart Buildings,
*   the risks associated with Smart Buildings and examples of ineffective security measures,
*   the most common causes of attacks on Smart Buildings,
*   who is responisble for Smart Building cybersecurity?
*   what are the consequences of not providing effecitve security measures for Smart Buildings?
*   how to improve Smart Building cybersecurity?

**Find out more about this topic:**

*   [Identification and mitigation of cyber risks for Smart Buildings](https://seqred.pl/en/smart-building-cybersecurity/)
*   [Smart Buildings – nearly 40 percent of systems attacked by malware](https://seqred.pl/en/smart_building_report/)
*   [Can Building Management Systems be Potential Attack Vectors for Industrial Control Systems?](https://seqred.pl/en/can-building-management-systems-be-potential-attack-vectors-for-industrial-control-systems/)

> What is a Smart Building?
> -------------------------

A Smart Building is a structure utilising innovative solutions in IT, OT (Operational Technology) and IoT (Internet of Things). The main types of buildings that contain smart building systems or elements thereof are: office buildings, shopping malls, airports, hotels, and public institutions.

Turning a structure into a Smart Building is becoming an economic necessity for any company wishing to keep up with its competition. The benefits of introducing smart building solutions include reduced operating costs, increased energy efficiency and environmental performance, comprehensive user support, and higher functionality.

### The components of a typical Smart Building system include:

**1. BMS (Building Maintenance System)** – building management system that ensures control and surveillance of the following systems: building automation, light control, media consumption, etc.

**2. Security systems** – the system of CCTV video surveillance, access control systems, alarm and intrusion detection systems, fire alarm systems, voice evacuation systems ;

**3. Network infrastructure** (wired and wireless) supporting additional systems;

**4. Everyday activity support systems:** parking lot systems, elevator control, visitor registration support, information booths etc.

**5. IoT devices.**

Smart uildings make full use of progress in IoT and IT solutions. The access to innovative methods in data exchange such as: cloud computing, remote access, external analytics, and network sharing is constantly leading to the emergence of more and more advanced solutions.

**However, technological progress has led to the emergence of cyber threats, with previously isolated systems being exposed to the world.**

> Smart Building cybersecurity
> ----------------------------

What springs to mind when you hear the term “cybersecurity”? Perhaps your first thought is of the security of your bank account, social media accounts, personal data, or IT devices. An analysis of attacks on Smart Buildings reveals the astonishing lack of awareness about possible threats, and how much is yet to be done to protect against them.

### Examples of hacker attacks on Smart Building systems. It does happen!

**– 2013 – Google building: a critical vulnerability was found in the BMS NiagaraAX system**, allowing the acquisition of administrator-level access to Google’s headquarters’ systems in Australia.

![](/blog/wyk1-1.jpg)

**– 2017 – global [ransomware-type](https://seqred.pl/en/ransomware/) attacks on numerous targets**, including several hospitals in the US: Kentucky Methodist Hospital, Chino Valley Medical Center and Desert Valley Hospital.

**– February 7th 2019 – Safety Detective Safety Detective reported unprotected browser access to BMS systems produced by RDM in 319 establishments around the world,** including ten hospitals in the United Kingdom.

In the following articles on the topic of Smart Building cybersecurity, we will illustrate the scale of the threats and the issue of liability, related to the lack of security or insufficient protection of such structures.

### What is the scale of risks associated with Smart Buildings?

Building Management Systems (BMS) exchange data using standardised communication protocols developed for solutions associated with building automation, such as:

*   BACnet
*   KNX/EIB
*   LONworks

One of the key parts of effective building automation system security is the awareness that the aforementioned protocols were created in the 1980s and 1990s, when functionality, not security, was the main focus. Initially, copper twisted pair cables were the standard medium of transmission; other media such as Ethernet or wireless connection only caught on later. This meant that devices which previously formed an isolated system became exposed to an internal IT network or even directly to the Internet.

During the initial stages of development of protocols for building automation, nobody could have foreseen that the pace of the technological progress would be so rapid. Even more importantly, it was impossible to predict that systems based on BACnet, KNX, LON, or Modbus protocols would become elements in structures as complex as Smart Buildings.

### Shodan – the identification of insecure hosts

A substantial risk of hacker attacks on Smart Buildings is posed by the fact that their systems and devices are accessible from the Internet. Potential targets may be identified with the help of [Shodan.](https://seqred.pl/en/shodan-improved/) It is an engine used for scanning the Internet and displaying all available hosts that match previously specified criteria. Most attacks or vulnerability analyses start from the identification of a host.

An example set of results for a port number reserved for the BACnet protocol: 47808

![](/blog/Shodan.png)

![](/blog/Shodan_Polska.png)

On a global scale

On a national scale

This does not mean that all devices that are detectable through the Shodan website are directly vulnerable to attacks or have vulnerabilities that are known. The tool is only the starting point for an analysis; if a vulnerability is detected, it can also identify the potentially compromised devices.

### Devices and systems are often published to the internet with insufficient security

The incident mentioned in part one involving 319 BMS systems (manufactured by RDM) responsible for the cooling installations was greatly facilitated by data available through the Shodan portal. Entering the right queries and analysing the data obtained made it possible to identify potentially unsecure systems. These could be accessed using the default login and password, and in some cases even without the need for logging in. Although the issue was reported over 3 months ago, some of these systems still remain vulnerable.

**An example of accessible cooling system without the need to log in**

![](/blog/2019/05/01_00.jpg)

### What elements of building automation systems are accessible from the Internet?

These may include the web interfaces of BMS systems that allow remote access to the building and the management thereof:

![](/blog/2019/05/04_01.jpg)

![](/blog/05.png)

This type of systems is accessible provided that you know the IP address and the web server port. You also need to know the access data for your account.

As evidenced by research cases and reports, it is possible to log in to some of these systems using the default login and password. Moreover, some systems contain known vulnerabilities in terms of cybersecurity, which may leave them open to attacks.

Using the right queries and criteria, it is also possible to identify BMS systems based on the BACnet protocol, which allows the user to view elements of the system, or even change the value of some of its objects with no further authorisation:

![](/blog/02_01.jpg)

View of object for a BACnet system

![](/blog/03_01.jpg)

A map of a BACnet network

**Accessibility from the Internet is only one of the possible vectors of an attack. What else may increase the risk?**

> Main causes of attacks on Smart Building systems:
> -------------------------------------------------

The most common causes of attacks on Smart Building systems are:

*   failure to comply with “good practices” and recommendations provided by the manufacturers of the devices,
*   human error in system configuration and management,
*   vulnerabilities identified in devices (also due to the use of Open Source components),
*   lack of adequate security measures in network infrastructure,
*   lack of concern for the fact that key protocols and technologies used in Smart Building structures are “insecure by design”,
*   combining solutions from different manufacturers and providers,
*   lack of adequate regulations in the “Bring Your Own Device” policy, which opens additional channels for attack,
*   the fact that a Smart Building system may be endangered even if it is not the direct target. following attacks on the other components of the structure to which it may be connected (intranet networks, IT architecture, etc.).

**Potential sources of risk to Smart Building systems**

[![](/blog/Smart_Building_Sources_of_Potential_Threats.jpg)](/blog/Smart_Building_Sources_of_Potential_Threats.jpg)

> Who is responsible for Smart Building’s cybersecurity?
> ------------------------------------------------------

In analysing the life cycle of a building, one needs to consider its stages and the entities involved in the emergence of a Smart Building system and its utilisation.

At the stage of construction, this means the investor, the general contractor, the numerous subcontractors and the integrators, responsible both for Smart Building systems and its support systems. At the stage of utilisation, the group also includes the administration, the companies responsible for technical maintenance, the local IT team, the lessees and external entities.

This leads to several key questions:

*   Given the complexity of the situation, who verifies the building’s readiness and utility in terms of cybersecurity?
*   Were the matters of cybersecurity taken into account at the stage of designing Smart Building solutions?
*   Was cybersecurity taken into account as a factor in the selection of specific devices and manufacturers?
*   Did the process of building acceptance testing include cybersecurity tests of the entire system?

**The lifecycle of a Smart Building**

![](/blog/mart_Building_liability.jpg)

> What are the threats and what potential consequences can they lead to?
> ----------------------------------------------------------------------

The crucial elements of a Smart Building system are: automation systems, access control systems and visual surveillance systems. A security breach even in one of them could bring negative consequences, for instance:

*   **loss of sensitive data**: the loss of confidential business information, leak of personal data, potential loopholes for fraud and extortion,
*   **less comfort for users**: the loss of control over the functioning of selected systems, e.g. lighting, heating, a decrease in productivity,
*   **disturbance in the building’s operations**: this includes many possible scenarios, from issues with functionality (evacuation, use of elevators), to the physical destruction of the utilised systems and threats to the life or health of the people inside the building,
*   **loss of company image/ credibility**: the loss of trust from clients, potential drops in revenue, a weaker position for the company,
*   **legal consequences**: pecuniary fines, potential lawsuits, the risk of termination of contracts.

> Five ways you can improve Smart Buildings’ cybersecurity:
> ---------------------------------------------------------

**1\.** **Know your building and its limitations** – a knowledge of the architecture, the solutions used and, most of all, the key areas of activity related to Smart Building systems provides the proper perspective for thinking about cybersecurity.

**2\.** **Avoid “plug and play” solutions for cybersecurity** – developing cybersecurity needs to be a “tailor-made’ process attuned to the specific threats associated with your structure.

**3\.** **Adopt a broad perspective in looking at IT issues** – matters of cybersecurity should involve all the entities associated with IT – the IT department, managers, solutions providers, maintenance companies etc.

**4\.** **Estimate the potential consequences of an attack** – plan your solutions in accordance with the services rendered by you or your lessees.

**5\.** **Be prepared for attacks** – consider and develop procedures and scenarios to be used in the event of a hacker attack. Define the methods and priorities of restoring system functionality.

