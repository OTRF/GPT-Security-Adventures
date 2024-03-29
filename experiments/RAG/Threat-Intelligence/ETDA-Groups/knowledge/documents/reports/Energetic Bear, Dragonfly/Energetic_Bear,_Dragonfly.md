# Threat actor: Energetic Bear, Dragonfly

**UUID**: a1492ea6-162c-46a9-a2d5-9618641b5ab2

**First seen**: 2010

**Source last modified**: 2023-06-22

## Threat actor aliases

Energetic Bear (CrowdStrike), Dragonfly (Symantec), Crouching Yeti (Kaspersky), Group 24 (Talos), Koala Team (iSight), Iron Liberty (SecureWorks), TG-4192 (SecureWorks), Electrum (Dragos), ATK 6 (Thales), ITG15 (IBM), Bromine (Microsoft), Ghost Blizzard (Microsoft)

## Description

Dragonfly is a cyberespionage group that has been active since at least 2011. They initially targeted defense and aviation companies but shifted to focus on the energy sector in early 2013. They have also targeted companies related to industrial control systems.

According to Kaspersky, Crouching Yeti has been operating since at least 2010 and has infected roughly 2,800 targets in 38 countries, and in industries as diverse as education and pharmaceuticals.

A similar group emerged in 2015 and was identified by Symantec as {{Berserk Bear, Dragonfly 2.0}}. There is debate over the extent of the overlap between Dragonfly and Dragonfly 2.0, but there is sufficient evidence to lead to these being tracked as two separate groups.

## Sponsor type and motivation

**Sponsor**: State-sponsored, GRU

**Motivation**: Sabotage and destruction


## Country of origin

Russia

## Observed attacked sectors where victims operate in

Aviation, Construction, Defense, Education, Energy, Industrial, IT, Manufacturing, Oil and gas, Pharmaceutical

## Observed attacked countries where victims operate in

Canada, France, Germany, Greece, Italy, Norway, Poland, Romania, Russia, Serbia, Spain, Turkey, UK, Ukraine, USA

## Observed usage of tools

Commix, CrackMapExec, Dirsearch, Dorshel, Goodor, Havex RAT, Hello EK, Heriplor, Impacket, Industroyer, Inveigh, Karagany, LightsOut EK, Listrix, nmap, PHPMailer, PsExec, SMBTrap, sqlmap, Subbrute, Sublist3r, Sysmain, Wpscan, WSO

## Reported hacking operations

2013-02: Spam campaign
The Dragonfly group has used at least three infection tactics against targets in the energy sector. The earliest method was an email spear phishing campaign, which saw selected executives and senior employees in target companies receive emails containing a malicious PDF attachment. Infected emails had one of two subject lines: “The account” or “Settlement of delivery problem”.
https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/Dragonfly_Threat_Against_Western_Energy_Suppliers.pdf

2013-06: Watering Hole Attacks using Lightsout
In June 2013, the attackers shifted their focus to watering hole attacks. They compromised a number of energy-related websites and injected an iframe into each of them. This iframe then redirected visitors to another compromised legitimate website hosting the Lightsout exploit kit. This in turn exploited either Java or Internet Explorer in order to drop Oldrea or Karagany on the victim’s computer.

2013-09: Watering Hole Attacks using Hello
In September 2013, Dragonfly began using a new version of this exploit kit, known as the Hello exploit kit. The landing page for this kit contains JavaScript which fingerprints the system, identifying installed browser plugins. The victim is then redirected to a URL which in turn determines the best exploit to use based on the information collected.

2013: Trojanized software
The most ambitious attack vector used by Dragonfly was the compromise of a number of legitimate software packages. Three different ICS equipment providers were targeted and malware was inserted into the software bundles they had made available for download on their websites.

2014-02: LightsOut EK Targets Energy Sector
Late last year, the story broke that threat actors were targeting the energy sector with Remote Access Tools and Intelligence gathering malware.  It would seem that the attackers responsible for this threat are back for more.  This particular APT struck late February between 2/24-2/26.
https://www.zscaler.com/blogs/research/lightsout-ek-targets-energy-sector

2015-12: Attack on Energy Companies in the Ukraine
According to a statement posted this week on the official website of the Ukrainian security service SBU, Russian special services allegedly planted malware on the networks of several regional power companies. The malicious software is said to have been discovered by employees of the SBU.
The SBU said the attackers also flooded the targeted companies’ technical support phone lines. The agency removed the malware and launched an investigation.
Just before Christmas, power outages were reported in the Ivano-Frankivsk Oblast region of Ukraine. The outages were blamed on outsiders who remotely tampered with automatic control systems. The power company responsible for the region also reported that its call center suffered a technical failure caused by a barrage of calls.
https://ssu.gov.ua/sbu/control/uk/publish/article?art_id=170951&cat_id=39574

2016: This report by Kaspersky Lab ICS CERT presents information on identified servers that have been infected and used by the group. The report also includes the findings of an analysis of several webservers compromised by the Energetic Bear group during 2016 and in early 2017.
https://securelist.com/energetic-bear-crouching-yeti/85345/

2016-12: Power outage at Ukrenergo in the Ukraine
Preliminary findings indicate that workstations and Supervisory Control and Data Acquisition (SCADA) systems, linked to the 330 kilowatt sub-station “North”, were influenced by external sources outside normal parameters, Ukrenergo said in comments emailed to Reuters.
https://www.reuters.com/article/us-ukraine-cyber-attack-energy-idUSKBN1521BA
https://dragos.com/wp-content/uploads/CrashOverride-01.pdf
https://dragos.com/wp-content/uploads/CRASHOVERRIDE.pdf

2017-04: Breach of EirGrid in the UK
The breach of the Vodafone network allowed the hackers to create a type of wiretap known as Generic Routing Encapsulation (GRE) to tunnel into EirGrid’s Vodafone router located in Shotton.
https://www.independent.ie/irish-news/statesponsored-hackers-targeted-eirgrid-electricity-network-in-devious-attack-36005921.html

2017-05: Watering Hole Attack on Turkish critical infrastructure
Through our web crawling network, we were able to determine that a website belonging to a Turkish energy company was being used in a watering hole attack targeting people associated with Turkish critical infrastructure. Compromised via a supply chain attack, the site was injected with SMB credential-harvesting malware.
https://www.riskiq.com/blog/labs/energetic-bear/

2020-03: Breach of San Francisco airport
https://www.zdnet.com/article/russian-state-hackers-behind-san-francisco-airport-hack/

2020-09: The Russian state-sponsored APT actor has targeted dozens of SLTT government and aviation networks, attempted intrusions at several SLTT organizations, successfully compromised network infrastructure, and as of October 1, 2020, exfiltrated data from at least two victim servers.
https://us-cert.cisa.gov/ncas/alerts/aa20-296a

## Reported counter operations against threat actor

2020-10: Six Russian GRU Officers Charged in Connection with Worldwide Deployment of Destructive Malware and Other Disruptive Actions in Cyberspace
https://www.justice.gov/opa/pr/six-russian-gru-officers-charged-connection-worldwide-deployment-destructive-malware-and



