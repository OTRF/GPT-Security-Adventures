# Threat actor: Inception Framework, Cloud Atlas

**UUID**: 7849ff33-1be0-4715-89b1-3adcb182561a

**First seen**: 2012

**Source last modified**: 2024-01-16

## Threat actor aliases

Inception Framework (Symantec), Cloud Atlas (Kaspersky), Oxygen (Microsoft), ATK 116 (Thales), Blue Odin (PWC), The Rocra (?)

## Description

(Symantec) Researchers from Blue Coat Labs have identified the emergence of a previously undocumented attack framework that is being used to launch highly targeted attacks in order to gain access to, and extract confidential information from, victims’ computers. Because of the many layers used in the design of the malware, we’ve named it Inception—a reference to the 2010 movie “Inception” about a thief who entered peoples’ dreams and stole secrets from their subconscious. Targets include individuals in strategic positions: Executives in important businesses such as oil, finance and engineering, military officers, embassy personnel and government officials. The Inception attacks began by focusing on targets primarily located in Russia or related to Russian interests, but have since spread to targets in other locations around the world.  The preferred malware delivery method is via phishing emails containing trojanized documents.

• Initially targeted at Russia, but expanding globally
• Masterful identity cloaking and diversionary tactics
• Clean and elegant code suggesting strong backing and top-tier talent
• Includes malware targeting mobile devices: Android, Blackberry and iOS
• Using a free cloud hosting service based in Sweden for command and control

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

Russia

## Observed attacked sectors where victims operate in

Aerospace, Defense, Embassies, Energy, Engineering, Financial, Government, Oil and gas, Research

## Observed attacked countries where victims operate in

Afghanistan, Armenia, Austria, Azerbaijan, Belarus, Belgium, Brazil, Congo, Cyprus, France, Georgia, Germany, Greece, India, Indonesia, Iran, Italy, Jordan, Kazakhstan, Kenya, Kyrgyzstan, Lebanon, Lithuania, Malaysia, Moldova, Morocco, Mozambique, Oman, Pakistan, Paraguay, Portugal, Qatar, Romania, Russia, Saudi Arabia, Slovenia, South Africa, Suriname, Switzerland, Tajikistan, Tanzania, Turkey, Turkmenistan, Uganda, Ukraine, UAE, USA, Uzbekistan, Venezuela, Vietnam

## Observed usage of tools

Inception, Lastacloud, PowerShower, VBShower, many 0-day exploits

## Reported hacking operations

2012-10: Operation “RedOctober”
In October 2012, Kaspersky Lab’s Global Research & Analysis Team initiated a new threat research after a series of attacks against computer networks of various international diplomatic service agencies. A large scale cyber-espionage network was revealed and analyzed during the investigation, which we called “Red October” (after famous novel “The Hunt For The Red October”).
https://securelist.com/red-october-diplomatic-cyber-attacks-investigation/36740/#8

2014-05: Hiding Behind Proxies
Since 2014, Symantec has found evidence of a steady stream of attacks from the Inception Framework targeted at organizations on several continents. As time has gone by, the group has become ever more secretive, hiding behind an increasingly complex framework of proxies and cloud services.
https://www.symantec.com/blogs/threat-intelligence/inception-framework-hiding-behind-proxies

2014-08: Operation “Cloud Atlas”
In August 2014, some of our users observed targeted attacks with a variation of CVE-2012-0158 and an unusual set of malware. We did a quick analysis of the malware and it immediately stood out because of certain unusual things that are not very common in the APT world.
https://securelist.com/cloud-atlas-redoctober-apt-is-back-in-style/68083/

2018-10: This blog describes attacks against European targets observed in October 2018, using CVE-2017-11882 and a new PowerShell backdoor we’re calling POWERSHOWER due to the attention to detail in terms of cleaning up after itself, along with the malware being written in PowerShell.
https://unit42.paloaltonetworks.com/unit42-inception-attackers-target-europe-year-old-office-vulnerability/

2019: During its recent campaigns, Cloud Atlas used a new “polymorphic” infection chain relying no more on PowerShower directly after infection, but executing a polymorphic HTA hosted on a remote server, which is used to drop three different files on the local system.
https://securelist.com/recent-cloud-atlas-activity/92016/

2022-02: Cloud Atlas targets entities in Russia and Belarus amid the ongoing war in Ukraine
https://research.checkpoint.com/2022/cloud-atlas-targets-entities-in-russia-and-belarus-amid-the-ongoing-war-in-ukraine/

2023-12: Cyber-espionage group Cloud Atlas targets Russian companies with war-related phishing attacks
https://therecord.media/cloud-atlas-targets-russian-orgs-war-phishing

## Reported counter operations against threat actor





