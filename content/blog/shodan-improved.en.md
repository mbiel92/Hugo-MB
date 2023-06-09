+++
lang="en-GB"
title="Shodan improved – advanced reconnaissance with Shodan"
date="2021-06-27"
author="Jakub Dzieciątko"
image="/blog/Seqred_Shodan.jpg"
tags=['cybersecurity','IT security', 'shodan']
+++

A proper reconnaissance lays the groundwork for further offensive action during security testing. The ability to search for information and to organise it in the right way could determine whether the later stages of the process will be easy, or even feasible at all.

Detecting a larger number of hosts, or services operating therein, expands the attack surface, giving the task team more leeway; it also allows the security of the analysed organisation to be verified in a more detailed manner.

Reconnaissance is crucial also in the case of sociotechnical attacks. Additional information translates to more precise spearphishing tests and better reactions during physical penetration testing.

**The present article aims to share tools that facilitate the accummulation and analysis of data acquired from the well-known Shodan search engine.**

![](/blog/Seqred_Shodan.jpg)

> What is it Shodan?
> ------------------

Shodan is a useful tool at the initial stage of testing. It allows you to quickly check how a given organisation looks like as far as the Internet is concerned.

Shodan is a search engine (often compared to Google) that indexes devices connected to the Internet and makes it possible to browse them. The special scanners it uses were created solely for the purpose of creating its own database. Each of them is constantly selecting a random public IP address, scanning a chosen port and entering the results into the databasse which is then made available and searchable.

Shodan has numerous advantages; scanning on your own does not even compare. The engine instantly finds systems that match your query in terms of vulnerability, affiliation with a given organisation, the type of protocol used, location and many other criteria. All without sending even a single ping towards the target system.

The engine is a very powerful tool, yet it does have its limitations. For instance, you may want to present the results in a form other than the browser display or the report generated by Shodan, make a more detailed query or expand the results to include your own scripts.

Shodan provides the API tool (Application Programming Interface) that allows you to send queries to its database. The free version limits the viewable results to 100 per query; paid versions (requiring a monthly subscribtion fee) have fewer limitations. There are tools that can use the API very well, e.g. the Shodan library in Python or the recon-ng. If you are not acquainted with these tools, I recommend familiarising yourself with how they work.

I did not, however, find any tool that would allow full analysis of the data acquired. Having tested many methods (including copy-pasting to Excel manually – never again), I decided to create my own tool that would offer enough flexibility in the gathering and presenentation of results.

> ShoSearch Tool – gathering data acquired from API and saving them locally
> -------------------------------------------------------------------------

The first tool deals with gathering data acquired from API and saving them locally. It uses the mongodb database, because API generates results in the JSON format, which is very easy to put in such a non-relational database. It is very simple – it takes as arguments the API key, the query and the name of the collection in which the results are to be saved.

The tool can be run several times for one and the same collection, filling it in with data pertaining to our target analysed from different angles, e.g. by making queries about vulnerable hosts in a given organisation, all hosts in a given autonomous system, ect.

![](/blog/ShoSearch.jpg)

[Download ShoSearch](https://github.com/seqred-s-a/shosearch)

> ShoView Tool – generate reports on the basis of the contents of mongodb databases
> ---------------------------------------------------------------------------------

This tool is used to generate reports on the basis of the contents of mongodb databases. Its advantage over the standard method of querying Shodan lies in the ability to use any and all filters supported by mongodb ([the full list see the mongodb files](https://docs.mongodb.com/manual/reference)).

It is therefore able to display all hosts with identified vulnerabilities (-q ‘{„vulns” : {„$exists” : true}}’), or all host with a nginx server, or to combine these filters in any way to display whatever you need for a given test.

![](/blog/ShoView.png)

The Shodan engine is, for instance, unable to filter results according to the rDNS, and some versions of API cannot filter according to vulnerability. The ShoView tool allows you to do it using mongodb filters.

Moreover, the template included in this tool highlights in red all vulnerabilities with an available exploit on exploit-db / rapid7 (metasploit). When you hover the cursor over a given vulnerability, the tool displays its description and links to further information, or, in the case of ‘red’ entries, a link to the exploit.

[Download ShoView](https://github.com/seqred-s-a/shoview)

![](/blog/Seqred_Shodan_3.png)

Proper reconnaissance allows the test team to avoid potentially dangerous oversight during testing and makes it easier to access the acquired data at a later point in time.

Aside from Shodan, a similar approach can be used in handling other tools yielding results in the JSON format.
