+++
lang="en-GB"
title="Everyday Network Security – Part 2"
date="2022-06-07"
author="Eugene Wypior"
image="/blog/ENS_2-1.png"
tags=['ABC security','IT security', 'OT security', 'PLC security']
+++

Continuing from last week on the topic of making a network secure for everyday use, the following recommendations are worth considering:

## **Manage your SSID**{ .article-section }

**Change your network name**

SSID stands for Service Set Identifier and for the sake of simplicity we can call it the WiFi name, i.e. the name assigned to your router. This name is usually set by the manufacturer and usually is a generic name of a type of router.

It is advisable to update the router name (which in the case of a home with a single router equals the name of the home network) in a way that does not identify its owner. Avoid using your name, flat number, address or the device brand or model in the network’s name.

Changing the network name does not increase the network’s security per se but it carries a message for a potential network attacker that the router is more conscientiously administered than routers using generic defaults.

**Opt out of router listings**

Another security concern are websites listing WiFis’ names – such as Wiggle. It is done using apps on portable devices, that scan, log and publish WIFis’ SSIDs. This can be prevented by adding \_nomap to the end of your SSID.

**Hide your SSID**

You can also hide your SSID from displaying publically however finding hidden networks is a simple task.

### **Disable WPS**

WiFi Protected Setup (WPS) is a router function allowing for an easy method of connecting devices to the router without the need for entering a long WiFi password. The WPS mode can usually be activated using a dedicated button on the router, entering an 8-digit PIN or tapping an NFC (Near Field Connection) enabled device. It is convenient, but WPS is notorious for major security issues, allowing an attacker to bypass the password, and gain easy access to the network. It is thus strongly recommended to disable the function the least and best, obtaining a router without the WPS function altogether.

### **Disable UPnP**

Universal Plug and Play allows applications to automatically forward a port on the router, saving the hassle of forwarding ports manually. However, it has a long history of security issues and so it is recommended to turn this feature off.

### **Use a guest network for guests**

Do not give access to your primary WiFi network to visitors, as it allows them and their device to interact with all the devices on your network – printers, IoT/smart home devices, storage attached to the network, etc. Even if it is someone you trust, and they themselves may have no malicious intentions, you cannot guarantee that their device has not been compromised in some way.

Some routers are equipped with the function of enabling a separate ‘guest’ network, which provides isolation and is able to expire after a given time frame. 

### **Change your router’s default IP address**

Altering your router admin panel’s default IP address makes it more difficult for malicious scripts in your web browser to target local IP addresses. It also adds an extra step for potential hackers trying to break into your local network.

### **Kill unused processes and services on your router**

Services such as Telnet or SSH (Secure Shell) that provide command-line access to devices should never be exposed to the internet and should also be disabled on the local network unless they are actually needed. This follows the good practice of disabling any service that is not used to reduce the attack surface.

### **Don’t keep ports open**

Close any open ports on your router that are not needed. Open ports provide an easy entrance for hackers. You can use a port scanner or a web service to help with this task.

### **Disable remote management**

Most routers offer a ‘remote access’ feature, allowing you to access the admin web interface from a remote location using your username and password. This greatly increases the attack surface and opens your network up to a host of threats. Therefore you should take great care when accessing your router’s admin panel remotely, ensuring you always log out or use Incognito mode. Ideally, you don’t access your router remotely and have this function disabled. You can even take it a step further to disable the admin interface over WiFi and be only able to modify the router’s settings using a direct Ethernet connection (this might not be possible on some modern mesh-based routers).

### **Manage range correctly**

It is not uncommon for users to want to o maximise the range of their WiFi. This is often needed to be able to use a WiFi with a single point in a large house or wanting to extend the signal to areas such as workshops, garages or gardens. But in the case of smaller spaces, such as a flat, and with neighbours living in close proximity, you increase your attack surface when your WiFi signal can be picked up across the street. It is prudent to carefully configure your networks and device antennas to provide coverage only within your usage area.

### **Disable WiFi on all devices**

Connecting to even a secure WiFi network increases your attack surface. So, if you are truly security conscious disable your home WiFi and connect each device via Ethernet, and turn off WiFi on your phone and use a USB-C/Lightenong to Ethernet cable. This will protect you against WiFi exploits.