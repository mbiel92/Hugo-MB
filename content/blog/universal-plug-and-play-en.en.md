+++
lang="en-GB"
title="Universal Hack and Play"
date="2019-12-15"
author="Michał Niwicki"
image="/blog/UPnP_Universal_Plug_and_Play.jpg"
tags=['IT security', 'upnp']
+++

**UPnP (Universal Plug and Play** – plug it in and it works) is a protocol that allows direct communication between computers and network devices. It is used in dozens of home appliances and enables devices such as computers, printers, TV sets, WiFi routers, robot vacuums, game consoles, and even microwave ovens or fridges to mutually detect one another’s presence and establish a connection to configure or exchange information. For the end-user, this technology simplifies configuration and access to their own data and services used; it also automates all these processes.

One of the advantages of UPnP is the ability to configure port mappings and IP addresses on the router following the requirements of the applications opened in the intranet. Unfortunately, even though the dangers associated with this kind of solution have been known for years now, many network administrators trivialise this threat and leave the UPnP service active in the routers.

![](/blog/UPnP_Universal_Plug_and_Play.jpg)

> What is UPnP for and how does it work
> =====================================

The majority of private users on the Internet do not connect their devices directly to the global network, they use a router instead, which allows the computers from a private network to access the Internet with the use of a single IP address (the router’s address). This translation process is called NAT (Network Address Translation).

If we want an application running behind a NAT to be accessible from the Internet, we have to map an external port on an inside IP address and the port number on the router. This operation requires administrative privileges. However, when the administrator had already turned on the UPnP service on the router, the application can send port mapping requests to the router without the requirement to log into the router’s administration panel.

**Sample query**

<?xml version=”1.0″?>  
<s:Envelope xmlns:s=”http://schemas.xmlsoap.org/soap/envelope/” s:encodingStyle=”http://schemas.xmlsoap.org/soap/encoding/”>  
<s:Body>  
<u:AddPortMapping xmlns:u=”urn:schemas-upnp-org:service:WANIPConnection:1″>  
<NewRemoteHost></NewRemoteHost>  
<NewExternalPort>18080</NewExternalPort>  
<NewProtocol>TCP</NewProtocol>  
<NewInternalPort>8080</NewInternalPort>  
<NewInternalClient>192.168.1.100</NewInternalClient>  
<NewEnabled>1</NewEnabled>  
<NewPortMappingDescription>Kamera IP</NewPortMappingDescription>  
<NewLeaseDuration>0</NewLeaseDuration>  
</u:AddPortMapping>  
</s:Body>  
</s:Envelope>

> UPnP – where are the threats?
> -----------------------------

First of all, any device operating on the intranet, the console of which we can log in from the Internet, gives us access to resources behind NAT. NAT does not protect from accessing a remote console if it can be shared with the help of UPnP.

Looking at the SOAP envelope, which calls upon the router service, we could ask ourselves the question: is it possible for us to give any values to fill in the port number and IP address fields instead of those used by our application? Unfortunately we can! This way, any service working behind the NAT, such as the multimedia server’s network share, the Internet camera’s web interface, the printer, or even the administration panel of the router itself, can be made accessible from any computer in the intranet. All you have to do is send a single http request.

![](/blog/UPnP_Universal_Plug_and_Play-2.jpg)

Unfortunately, this is not all. It turns out that some software running on routers prioritises the UPnP configuration above the static port mapping. As a result, a service that was made accessible on purpose can be replaced with another service, one that doesn’t necessarily run within the intranet network.

![](/blog/UPnP_Universal_Plug_and_Play_2.jpg)

Moreover, one of the more popular open-source firmware allows the ports to be mapped by the UPnP service in such a way that the requests directed to a machine running in a demilitarised zone will be redirected to an artificial dummy host.

> How to live with UPnP?
> ----------------------

We have to remember that NAT does not serve as network protection. The apparent sense of security and the belief that what is “behind NAT” is not available from the Internet is wrong and dangerous. The UPnP service, if it remains running on the edge router, becomes a threat to the intranet resources. Moreover, all the exercises described above were performed while an on router firewall was turned on. The safest solution is turning off the UPnP. If this solution is not available, you can reduce the risk of attack on particular machines by looking through the UPnP mapping table in the administration panel of the router and by limiting the access of services to those specific machines within the intranet.

