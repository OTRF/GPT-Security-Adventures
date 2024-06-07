# Threat actor: Chafer, APT 39

**UUID**: d7f937b7-b50b-4022-bca1-9e403ffefe45

**First seen**: 2014

**Source last modified**: 2021-11-02

## Threat actor aliases

Chafer (Symantec), APT 39 (Mandiant), Remix Kitten (CrowdStrike), Cobalt Hickman (SecureWorks), TA454 (Proofpoint), ITG07 (IBM)

## Description

(FireEye) APT39 was created to bring together previous activities and methods used by this actor, and its activities largely align with a group publicly referred to as “Chafer.” However, there are differences in what has been publicly reported due to the variances in how organizations track activity. APT39 primarily leverages the SEAWEED and CACHEMONEY backdoors along with a specific variant of the POWBAT backdoor. While APT39’s targeting scope is global, its activities are concentrated in the Middle East. APT39 has prioritized the telecommunications sector, with additional targeting of the travel industry and IT firms that support it and the high-tech industry.

APT39’s focus on the telecommunications and travel industries suggests intent to perform monitoring, tracking, or surveillance operations against specific individuals, collect proprietary or customer data for commercial or operational purposes that serve strategic requirements related to national priorities, or create additional accesses and vectors to facilitate future campaigns. Government entities targeting suggests a potential secondary intent to collect geopolitical data that may benefit nation-state decision making. Targeting data supports the belief that APT39’s key mission is to track or monitor targets of interest, collect personal information, including travel itineraries, and gather customer data from telecommunications firms.

## Sponsor type and motivation

**Sponsor**: State-sponsored, Rana Intelligence Computing Company

**Motivation**: Information theft and espionage


## Country of origin

Iran

## Observed attacked sectors where victims operate in

Aviation, Engineering, Government, High-Tech, IT, Shipping and Logistics, Telecommunications, Transportation

## Observed attacked countries where victims operate in

Israel, Jordan, Kuwait, Saudi Arabia, Spain, Turkey, UAE, USA, Middle East

## Observed usage of tools

Antak, ASPXSpy, EternalBlue, HTTPTunnel, MechaFlounder, Metasploit, Mimikatz, nbtscan, Non-sucking Service Manager, OilRig, Plink, POWBAT, pwdump, Rana, Remcom, Remexi, SafetyKatz, SEAWEED, UltraVNC, Windows Credentials Editor, Living off the Land, SMB hacking tools

## Reported hacking operations

2017: Chafer appears to have been undeterred by its exposure in 2015 and continued to be very active during 2017, using seven new tools, rolling out new infrastructure, and attacking nine new target organizations in the region. The group hit organizations in Israel, Jordan, the United Arab Emirates, Saudi Arabia, and Turkey.
Sectors targeted included airlines; aircraft services; software and IT services companies serving the air and sea transport sectors; telecoms services; payroll services; engineering consultancies; and document management software.</br />Outside of the Middle East, Symantec has also found evidence of attacks against one African airline and attempts to compromise an international travel reservations firm.
https://www.symantec.com/blogs/threat-intelligence/chafer-latest-attacks-reveal-heightened-ambitions

2018-02: Turkish Government Targeting
This new secondary payload is Python-based and compiled into executable form using the PyInstaller utility. This is the first instance where Unit 42 has identified a Python-based payload used by these operators. We’ve also identified code overlap with OilRig’s Clayside VBScript but at this time track Chafer and OilRig as separate threat groups. We have named this payload MechaFlounder for tracking purposes.
https://unit42.paloaltonetworks.com/new-python-based-payload-mechaflounder-used-by-chafer/

2018 Autumn: Spying on Iran-based foreign diplomatic entities
Throughout the autumn of 2018 we analyzed a long-standing (and still active at that time) cyberespionage campaign that was primarily targeting foreign diplomatic entities based in Iran. The attackers were using an improved version of Remexi in what the victimology suggests might be a domestic cyberespionage operation.
https://securelist.com/chafer-used-remexi-malware/89538/

2018: Bitdefender researchers have found attacks conducted by this actor in the Middle East region, dating back to 2018. The campaigns were based on several tools, including “living off the land” tools, which makes attribution difficult, as well as different hacking tools and a custom built backdoor.
https://www.bitdefender.com/files/News/CaseStudies/study/332/Bitdefender-Whitepaper-Chafer-creat4491-en-EN-interactive.pdf

## Reported counter operations against threat actor

2020-09: Treasury Sanctions Cyber Actors Backed by Iranian Intelligence Ministry
https://home.treasury.gov/news/press-releases/sm1127



