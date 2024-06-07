# Threat actor: Emissary Panda, APT 27, LuckyMouse, Bronze Union

**UUID**: e67091ab-cbea-4d73-984d-e4b29f6c48a9

**First seen**: 2010

**Source last modified**: 2023-10-12

## Threat actor aliases

Emissary Panda (CrowdStrike), APT 27 (Mandiant), LuckyMouse (Kaspersky), Bronze Union (Secureworks), TG-3390 (SecureWorks), TEMP.Hippo (Symantec), Budworm (Symantec), Group 35 (Talos), ATK 15 (Thales), Iron Tiger (Trend Micro), Earth Smilodon (Trend Micro), Red Phoenix (PWC), ZipToken (?)

## Description

Threat Group-3390 is a Chinese threat group that has extensively used strategic Web compromises to target victims. The group has been active since at least 2010 and has targeted organizations in the aerospace, government, defense, technology, energy, and manufacturing sectors.

Emissary Panda has some overlap with {{Turbine Panda, APT 26, Shell Crew, WebMasters, KungFu Kittens}} and possibly {{UNC215}}.

This actor worked together with {{TA428}} in Operation StealthyTrident.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Aerospace, Aviation, Defense, Education, Embassies, Government, Manufacturing, Technology, Telecommunications, Think Tanks

## Observed attacked countries where victims operate in

Australia, Canada, China, Germany, Hong Kong, India, Iran, Israel, Japan, Mongolia, Philippines, Russia, Spain, South Korea, Taiwan, Thailand, Tibet, Turkey, UK, USA, Middle East

## Observed usage of tools

Antak, ASPXSpy, China Chopper, Gh0st RAT, gsecdump, HTTPBrowser, HTran, Hunter, HyperBro, Mimikatz, Nishang, OwaAuth, PlugX, ProcDump, PsExec, SysUpdate, TwoFace, Windows Credentials Editor, ZXShell, Living off the Land

## Reported hacking operations

2010: Operation “Iron Tiger”
Operation Iron Tiger is a targeted attack campaign discovered to have stolen trillions of data from defense contractors in the US, including stolen emails, intellectual property, strategic planning documents – data and records that could be used to destabilize an organization.
https://github.com/CyberMonitor/APT_CyberCriminal_Campagin_Collections/blob/master/2015/2015.09.17.Operation_Iron_Tiger/wp-operation-iron-tiger.pdf

2015: Penetration of networks for industrial espionage
Designated as Threat Group 3390 and nicknamed “Emissary Panda” by researchers, the hacking group has compromised victims’ networks largely through “watering hole” attacks launched from over 100 compromised legitimate websites, sites picked because they were known to be frequented by those targeted in the attack.
https://arstechnica.com/information-technology/2015/08/newly-discovered-chinese-hacking-group-hacked-100-websites-to-use-as-watering-holes/

2017-07: Operation “PZChao”
The past few years have seen high-profile cyber-attacks shift to damaging the targets’ digital infrastructures to stealing highly sensitive data, silently monitoring the victim and constantly laying the ground for a new wave of attacks.
This is also the case of a custom-built piece of malware that we have been monitoring for several months as it wrought havoc in Asia. Our threat intelligence systems picked up the first indicators of compromise in July last year, and we have kept an eye on the threat ever since.
https://labs.bitdefender.com/2018/02/operation-pzchao-a-possible-return-of-the-iron-tiger-apt/

2018-03: Campaign targeting a national data center in the Central Asia
The choice of target made this campaign especially significant – it meant the attackers gained access to a wide range of government resources at one fell swoop. We believe this access was abused, for example, by inserting malicious scripts in the country’s official websites in order to conduct watering hole attacks.
https://securelist.com/luckymouse-hits-national-data-center/86083/

2018-04: Operation “SpoiledLegacy”
We have been monitoring a campaign targeting Vietnamese government and diplomatic entities abroad since at least April 2018.
https://securelist.com/apt-trends-report-q1-2019/90643/

2019-04: In April 2019, Unit 42 observed the Emissary Panda (AKA APT27, TG-3390, Bronze Union, Lucky Mouse) threat group installing webshells on Sharepoint servers to compromise Government Organizations of two different countries in the Middle East.
https://unit42.paloaltonetworks.com/emissary-panda-attacks-middle-east-government-sharepoint-servers/

2019 Summer: Operation “DRBControl”
https://documents.trendmicro.com/assets/white_papers/wp-uncovering-DRBcontrol.pdf

2020: APT27 Turns to Ransomware
https://shared-public-reports.s3-eu-west-1.amazonaws.com/APT27+turns+to+ransomware.pdf

2020: Iron Tiger APT Updates Toolkit With Evolved SysUpdate Malware
https://www.trendmicro.com/en_us/research/21/d/iron-tiger-apt-updates-toolkit-with-evolved-sysupdate-malware-va.html

2020-03: Is APT27 Abusing COVID-19 To Attack People ?!
https://marcoramilli.com/2020/03/19/is-apt27-abusing-covid-19-to-attack-people/

2020-04: Investigation with a twist: an accidental APT attack and averted data destruction
https://www.ptsecurity.com/ww-en/analytics/pt-esc-threat-intelligence/incident-response-polar-ransomware-apt27/

2020-06: Operation “StealthyTrident”
ESET researchers discovered that chat software called Able Desktop, part of a business management suite popular in Mongolia and used by 430 government agencies in Mongolia.
https://www.welivesecurity.com/2020/12/10/luckymouse-ta428-compromise-able-desktop/
https://decoded.avast.io/luigicamastra/apt-group-targeting-governmental-agencies-in-east-asia/

2021-03: Exchange servers under siege from at least 10 APT groups
https://www.welivesecurity.com/2021/03/10/exchange-servers-under-siege-10-apt-groups/

2021-03: German government warns of APT27 activity targeting local companies
https://therecord.media/german-government-warns-of-apt27-activity-targeting-local-companies/

2022-04: Budworm: Espionage Group Returns to Targeting U.S. Organizations
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/budworm-espionage-us-state

2022-05: LuckyMouse uses a backdoored Electron app to target MacOS
https://blog.sekoia.io/luckymouse-uses-a-backdoored-electron-app-to-target-macos/

2022-07: Iron Tiger’s SysUpdate Reappears, Adds Linux Targeting
https://www.trendmicro.com/en_us/research/23/c/iron-tiger-sysupdate-adds-linux-targeting.html

2022-08: Iron Tiger Compromises Chat Application Mimi, Targets Windows, Mac, and Linux Users
https://www.trendmicro.com/en_us/research/22/h/irontiger-compromises-chat-app-Mimi-targets-windows-mac-linux-users.html

2023-08: Budworm: APT Group Uses Updated Custom Tool in Attacks on Government and Telecoms Org
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/budworm-tool-update-telecoms-govt

## Reported counter operations against threat actor





