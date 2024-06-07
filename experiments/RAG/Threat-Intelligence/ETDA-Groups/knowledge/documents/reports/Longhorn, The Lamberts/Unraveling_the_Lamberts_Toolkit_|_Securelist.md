# Reference for threat actor for "Longhorn, The Lamberts"

**Title**: Unraveling the Lamberts Toolkit | Securelist

**Source**: https://securelist.com/unraveling-the-lamberts-toolkit/77990/

## Content















Unraveling the Lamberts Toolkit | Securelist


































































Solutions for:

Home Products
Small Business 1-50 employees
Medium Business 51-999 employees
Enterprise 1000+ employees
 



















by Kaspersky


CompanyAccount
Get In Touch
Dark mode off
EnglishRussianSpanish













Solutions



Hybrid Cloud SecurityLearn More
Internet of Things & Embedded SecurityLearn More
Threat Management and DefenseLearn More
Industrial CybersecurityLearn More
Fraud PreventionLearn More



Other solutions
Blockchain Security
Kaspersky for Security Operations Center


Industries



National CybersecurityLearn More
Industrial CybersecurityLearn More
Finance Services CybersecurityLearn More
Healthcare CybersecurityLearn More
Transportation CybersecurityLearn More
Retail CybersecurityLearn More



Other Industries
Telecom Cybersecurity
Blockchain Security
View all


Products



KasperskyEndpoint Security for BusinessLearn More
KasperskyEndpoint Detection and Response (EDR)Learn More
KasperskyEDR OptimumLearn More
KasperskyAnti Targeted Attack PlatformLearn More
KasperskyManaged Detection and ResponseLearn More
KasperskySandboxLearn More



Other Products
Kaspersky Security for Mail Server
Kaspersky Security for Internet Gateway
Kaspersky Embedded Systems Security
Kaspersky Hybrid Cloud Security for AWS
Kaspersky Hybrid Cloud Security for Azure
View All


Services



KasperskyCybersecurity ServicesLearn More
KasperskyAdaptive Online TrainingLearn More
KasperskyPremium SupportLearn More
KasperskyThreat IntelligenceLearn More
KasperskyAPT Intelligence ReportingLearn More
KasperskyTargeted Attack DiscoveryLearn More



Other Services
Kaspersky Professional Services
Kaspersky Incident Response
Kaspersky Cybersecurity Training
Kaspersky Incident Communications
Kaspersky Security Awareness
View All


Resource Center

Case Studies
White Papers
Datasheets
Technologies
MITRE ATT&CK

About Us

Transparency
Corporate News
Press Center
Careers
Innovation Hub
Sponsorship
Policy Blog
Contacts

GDPR
 





Subscribe
 Dark mode off
Login


Securelist menu

EnglishRussianSpanish
Existing Customers

Personal

My Kaspersky
Renew your product
Update your product
Customer support

Business

KSOS portal
Kaspersky Business Hub
Technical Support
Knowledge Base
Renew License


Home

Products
Trials&Update
Resource Center

Business

Small Business (1-50 employees)
Medium Business (51-999 employees)
Enterprise (1000+ employees)


Securelist
Threats

Financial threats
Mobile threats
Web threats
Secure environment (IoT)
Vulnerabilities and exploits
Spam and Phishing
Industrial threats

Categories

APT reports
Incidents
Research
Malware reports
Spam and phishing reports
Publications
Kaspersky Security Bulletin

Archive
All Tags
APT Logbook
Webinars
Statistics
Encyclopedia
Threats descriptions
KSB 2021

About Us

Company
Transparency
Corporate News
Press Center
Careers
Sponsorships
Policy Blog
Contacts

Partners

Find a Partner
Partner Program
















Content menu
Close













Subscribe













by Kaspersky

 Dark mode off




ThreatsThreats

APT (Targeted attacks)
Secure environment (IoT)
Mobile threats
Financial threats
Spam and phishing
Industrial threats
Web threats
Vulnerabilities and exploits


CategoriesCategories

APT reports
Malware descriptions
Security Bulletin
Malware reports
Spam and phishing reports
Security technologies
Research
Publications


Other sections

Archive
All tags
Webinars
APT Logbook
Statistics
Encyclopedia
Threats descriptions
KSB 2023


 











 

APT reports

Unraveling the Lamberts Toolkit 

APT reports

11 Apr 2017

  minute read								
















Table of Contents





An Overview of the LambertsThe Lamberts in Brief – from Black to GrayBlack LambertBlue LambertGreen LambertWhite LambertPink LambertGray LambertTimelineCodenames and Popular Culture Referenced in LambertsConclusions 






 

Authors




GReAT



An Overview of a Color-coded Multi-Stage Arsenal


Yesterday, our colleagues from Symantec published their analysis of Longhorn, an advanced threat actor that can be easily compared with Regin, ProjectSauron, Equation or Duqu2 in terms of its complexity.
Longhorn, which we internally refer to as “The Lamberts”, first came to the attention of the ITSec community in 2014, when our colleagues from FireEye discovered an attack using a zero day vulnerability (CVE-2014-4148). The attack leveraged malware we called ‘BlackLambert’, which was used to target a high profile organization in Europe.
Since at least 2008, The Lamberts have used multiple sophisticated attack tools against high-profile victims. Their arsenal includes network-driven backdoors, several generations of modular backdoors, harvesting tools, and wipers. Versions for both Windows and OSX are known at this time, with the latest samples created in 2016.
Although the operational security displayed by actors using the Lamberts toolkit is very good, one sample includes a PDB path that points to a project named “Archan~1” (perhaps ‘Archangel’). The root folder on the PDB path is named “Hudson”. This is one of the very few mistakes we’ve seen with this threat actor.
While in most cases the infection vector remains unknown, the high profile attack from 2014 used a very complex Windows TTF zero-day exploit (CVE-2014-4148).
Kaspersky Lab products successfully detect and eradicate all the known malware from the Lamberts family. For more information please contact: intelreports@kasperskycom
An Overview of the Lamberts

Figure 1. Lamberts discovery timeline
The first time the Lambert family malware was uncovered publicly was in October 2014, when FireEye posted a blog about a zero day exploit (CVE-2014-4148) used in the wild. The vulnerability was patched by Microsoft at the same time. We named the malware involved ‘Black Lambert’ and described it thoroughly in a private report, available to Kaspersky APT Intel Reports subscribers.
The authors of Black Lambert included a couple of very interesting details in the sample, which read as the following: toolType=wl, build=132914, versionName = 2.0.0. Looking for similar samples, we were able to identify another generation of related tools which we called White Lambert. While Black Lambert connects directly to its C&C for instructions, White Lambert is a fully passive, network-driven backdoor.





Black Lambert
White Lambert


Implant type
Active
Passive


toolType
wl
aa (“ArchAngel”)


build
132914
113140


versionName
2.0.0
5.0.2




Internal configuration similarities in Black and White Lambert
White Lambert runs in kernel mode and intercepts network traffic on infected machines. It decrypts packets crafted in a special format to extract instructions. We named these passive backdoors ‘White Lambert’ to contrast with the active “Black Lambert” implants.
Looking further for any other malware related to White Lambert and Black Lambert, we came by another generation of malware that we called Blue Lambert.
One of the Blue Lambert samples is interesting because it appears to have been used as second stage malware in a high profile attack, which involved the Black Lambert malware.
Looking further for malware similar to Blue Lambert, we came by another family of malware we called Green Lambert. Green Lambert is a lighter, more reliable, but older version of Blue Lambert. Interestingly, while most Blue Lambert variants have version numbers in the range of 2.x, Green Lambert is mostly in 3.x versions. This stands in opposition to the data gathered from export timestamps and C&C domain activity that points to Green Lambert being considerably older than the Blue variant. Perhaps both Blue and Green Lamberts have been developed in parallel by two different teams working under the same umbrella, as normal software version iterations, with one seeing earlier deployment than the other.
Signatures created for Green Lambert (Windows) have also triggered on an OS X variant of Green Lambert, with a very low version number: 1.2.0. This was uploaded to a multiscanner service in September 2014. The OS X variant of Green Lambert is in many regards functionally identical to the Windows version, however it misses certain functionality such as running plugins directly in memory.
Kaspersky Lab detections for Blue, Black, and Green Lamberts have been triggered by a relatively small set of victims from around the world. While investigating one of these infections involving White Lambert (network-driven implant) and Blue Lambert (active implant), we found yet another family of tools that appear to be related. We called this new family Pink Lambert.
The Pink Lambert toolset includes a beaconing implant, a USB-harvesting module and a multi-platform orchestrator framework which can be used to create OS-independent malware. Versions of this particular orchestrator were found on other victims, together with White Lambert samples, indicating a close relationship between the White and Pink Lambert malware families.
By looking further for other undetected malware on victims of White Lambert, we found yet another apparently related family. The new family, which we called Gray Lambert is the latest iteration of the passive network tools from the Lamberts’ arsenal. The coding style of Gray Lambert is similar to the Pink Lambert USB-harvesting module, however, the functionality mirrors that of White Lambert. Compared to White Lambert, Gray Lambert runs in user mode, without the need for exploiting a vulnerable signed driver to load arbitrary code on 64-bit Windows variants.
Connecting all these different families by shared code, data formats, C&C servers, and victims, we have arrived at the following overarching picture:

Figure 2. An overview of connections between the Lambert families
The Lamberts in Brief – from Black to Gray
Below, we provide a small summary of all the Lamberts. A full description of all variants is available to subscribers of Kaspersky APT Reports. Contact intelreports@kaspersky.com
Black Lambert
The only known sample of Black Lambert was dropped by a TTF-exploit zero day (CVE-2014-4148). Its internal configuration included a proxy server which suggests the malware was created to work in a very specific network configuration, inside the victim’s network.
An internal description of Black Lambert indicates what appears to be a set of markers used by the attackers to denote this particular branch: toolType=wl, build=132914, versionName = 2.0.0.




Hash
Description


683afdef710bf3c96d42e6d9e7275130
generic loader (hdmsvc.exe)


79e263f78e69110c09642bbb30f09ace
winlib.dll, final payload (toolType=wl)




Blue Lambert
The Blue Lambert implants contain what appear to be version numbers in the 2.x range, together with project/operation codename sets, which may also indicate codenames for the victims or campaigns.

Figure 4. Blue Lambert configuration in decrypted form, highlighting internal codenames
Known codenames include TRUE CRIME (2.2.0.2), CERVELO YARDBIRD (2.6.1.1), GAI SHU (2.2.0.5), DOUBLESIDED SCOOBYSNACK (2.3.0.2), FUNNELCAKE CARNIVAL (2.5.0.2), PROSPER SPOCK (2.0.0.2), RINGTOSS CARNIVAL (2.4.2.2), COD FISH (2.2.0.0), and INVERTED SHOT (2.6.2.3).
Green Lambert
Green Lambert is a family of tools deeply related to Blue Lambert. The functionality is very similar, both Blue and Green are active implants. The configuration data shares the same style of codenames for victims, operations, or projects.

Figure 5. Green Lambert configuration block (decrypted) highlighting internal codenames
The Green Lambert family is the only one where non-Windows variants have been found. An old version of Green Lambert, compiled for OS X was uploaded from Russia to a multiscanner service in 2014. Its internal codename is HO BO (1.2.0).
The Windows versions of Green Lambert have the following code names: BEARD BLUE (2.7.1), GORDON FLASH (3.0), APE ESCAPE (3.0.2), SPOCK LOGICAL (3.0.2), PIZZA ASSAULT (3.0.5), and SNOW BLOWER (3.0.5).
Interestingly, one of the droppers of Green Lambert abused an ICS software package named “Subway Environmental Simulation Program” or “SES”, which has been available on certain forums visited by engineers working with industrial software. Similar techniques have been observed in the past from other threat groups, for instance, trojanized Oracle installers by the Equation group.
White Lambert
White Lambert is a family of tools that share the same internal description as Black Lambert. Known tool types, builds, and version names include:

ToolType “aa”, protocol 3, version 7, versionName 5.0.2, build 113140
ToolType “aa”, protocol 3, version 7, versionName 5.0.0, build 113140
ToolType “aa”, protocol 3, version 6, versionName 4.2.0, build 110836M
ToolType “aa”, protocol 3, version 5, versionName 3.2.0

One of the White Lambert samples is interesting because it has a forgotten PDB path inside, which points to “Archan~1l” and “Hudson”. Hudson could point to a project name, if the authors name their projects by rivers in the US, or, it could also be the developer’s first name. The truncated (8.3) path “archan~1” most likely means “Archangel”. The tool type “aa” could also suggest “ArchAngel”. By comparison, the Black Lambert tool type “wl” has no known meaning.

White Lambert samples run in kernel mode and sniff network traffic looking for special packets containing instructions to execute. To run unsigned code in kernel mode on 64-bit Windows, White Lambert uses an exploit against a signed, legitimate SiSoftware Sandra driver. The same method was used before by Turla, ProjectSauron, and Equation’s Grayfish, with other known, legitimate drivers.
Pink Lambert
Pink Lambert is a suite of tools initially discovered on a White Lambert victim. It includes a beaconing implant, partially based on publicly available source code. The source code on top of which Pink Lambert’s beaconing implant was created is “A Fully Featured Windows HTTP Wrapper in C++”.

Figure 6. “A Fully Featured Windows HTTP Wrapper” by shicheng
Other tools in the Pink Lambert suite include USB stealer modules and a very complex multi-platform orchestrator.
In a second incident, a Pink Lambert orchestrator was found on another White Lambert victim, substantiating the connection between the Pink and White Lamberts.
Gray Lambert
Gray Lambert is the most recent tool in the Lamberts’ arsenal. It is a network-driven backdoor, similar in functionality to White Lambert. Unlike White Lambert, which runs in kernel mode, Gray Lambert is a user-mode implant. The compilation and coding style of Gray Lambert is similar to the Pink Lambert USB stealers. Gray Lambert initially appeared on the computers of victims infected by White Lambert, which could suggest the authors were upgrading White Lambert infections to Gray. This migration activity was last observed in October 2016.
Some of the known filenames for Gray Lambert are mwapi32.dll and poolstr.dll – it should be pointed though that the filenames used by the Lamberts are generally unique and have never been used twice.
Timeline
Most of the Blue and Green Lambert samples have two C&C servers hardcoded in their configuration block: a hostname and an IP address. Using our own pDNS as well as DomainTools IP history, we plotted the times when the C&C servers were active and pointing to the same IP address as the one from the configuration block.
Unfortunately, this method doesn’t work for all samples, since some of them don’t have a domain for C&C. Additionally, in some cases we couldn’t find any pDNS information for the hostname configured in the malware.
Luckily, the attackers have made a few mistakes, which allow us to identify the activity times for most of the other samples. For instance, in case when no pDNS information was available for a subdomain on top of the main C&C domain, the domain registration dates were sufficient to point out when the activity began. Additionally, in some cases the top domain pointed to the same IP address as the one from the configuration file, allowing us to identify the activity times.
Another worthwhile analysis method focuses on the set of Blue Lambert samples that have exports. Although most compilation timestamps in the PE header appear to have been tampered (to reflect a 2003-2004 range), the authors forgot to alter the timestamps in the export section. This allowed us to identify not just the activity / compilation timestamps, but also the method used for faking the compilation timestamps in the PE header.
It seems the algorithm used to tamper with the samples was the following: subtract 0x10 from the highest byte of timestamp (which amounts to about 8 and half years) and then randomize the lowest 3 bytes. This way we conclude that for Blue Lamberts, that original compilation time of samples was in the range of 2012-2015.
Putting together all the various families, with recovered activity times, we come to the following picture:

Figure 8. A timeline of activity for known Lamberts
As it can be seen from the chart above, Green Lambert is the oldest and longest-running in the family, while Gray is the newest. White, Blue and Pink somehow overlap in deployment, with Blue replacing Green Lambert. Black Lambert was seen only briefly and we assume it was “retired” from the arsenal after being discovered by FireEye in 2014.
Codenames and Popular Culture Referenced in Lamberts
The threat group(s) behind the Lambert toolkits have used a large number of codenames extensively throughout their projects. Some of these codenames are references to old computer games, Star Trek, and cartoons, which is very unusual for high profile APT groups. We really enjoyed going through the backstories of these codenames and wanted to provide them below for others to enjoy as well.
For instance, one of the Green Lambert versions has the internal codename “GORDON FLASH”, which can also be read as “FLASH GORDON”. Flash Gordon is the hero of a space opera adventure comic strip created by and originally drawn by Alex Raymond. It was first published in 1934 and subsequently turned into a popular film in 1980.

Flash Gordon poster
A ‘Funnel cake’ is a regional food popular in North America at carnivals, fairs, sporting events, and seaside resorts. This explains the codename “FUNNELCAKE CARNIVAL”:

Figure 9. A typical funnel cake
Spock and Prosper obviously refers to Star Trek, the well-known science fiction television series created by Gene Roddenberry. Cdr. Spock is a half-Vulcan, half-human character, portrayed by Leonard Nimoy. “Live long and prosper” is the traditional Vulcan greeting in the series.

Leonard Nimoy as “Spock” displaying the traditional Vulcan greeting “Live long and prosper”
Ringtoss is a game that is very popular at carnivals in North America.

DOUBLESIDED SCOOBYSNACK is likely a reference to an NFL Lip Reading video featuring Adrian Peterson that went viral in mid-2013. According to the urban dictionary, it is also used to denote a sexual game in which the participants are dressed as Scooby-Doo and his master.
Ape Escape (also known as Saru Get You (サルゲッチュ Saru Getchu) in Japan) is a series of video games made by SCE Japan Studio, starting with Ape Escape for PlayStation in 1999. The series often incorporates ape-related humor, unique gameplay, and a wide variety of pop culture references; it is also notable for being the first game to make the DualShock or Dual Analog controller mandatory.

Ape Escape
INVERTED SHOT is likely a reference to a mixed martial arts move also known as an ‘Imanari roll takedown’, named after Masakazu Imanari who popularized the grappling technique. It consists of a modified Brazilian jiu-jitsu granby roll that places the fighter in inverted guard position while taking the opponent down to the mat.
GAI and SHU (as used in Green Lambert OS X) are characters from the Guilty Crown anime series. Gai Tsutsugami (恙神 涯 Tsutsugami Gai) is the 17-year-old resourceful and charismatic leader of the “Funeral Parlor” resistance group, while Shu Ouma (桜満 集 Ōma Shū) is the 17-year-old main protagonist of Guilty Crown.

Figure 10. Main characters of Guilty Crown with Shu Ouma in the middle.
Conclusions
The Lamberts toolkit spans across several years, with most activity occurring in 2013 and 2014. Overall, the toolkit includes highly sophisticated malware, which relies on high-level techniques to sniff network traffic, run plugins in memory without touching the disk, and leverages exploits against signed drivers to run unsigned code on 64-bit Windows.
To further exemplify the proficiency of the attackers leveraging the Lamberts toolkit, deployment of Black Lambert included a rather sophisticated TTF zero day exploit, CVE-2014-4148. Taking that into account, we classify the Lamberts as the same level of complexity as Regin, ProjectSauron, Equation and Duqu2, which makes them one of the most sophisticated cyber espionage toolkits we have ever analysed.
Considering the complexity of these projects and the existence of an implant for OS X, we assume that it is highly possible that other Lamberts also exist for other platforms, such as Linux. The fact that in the vast majority of cases the infection method is unknown probably means there are still a lot of unknown details about these attacks and the group(s) leveraging them.
As usual, defense against attacks such as those from the Lamberts/Longhorn should include a multi-layered approach. Kaspersky products include special mitigation strategies against the malware used by this group, as well as the many other APT groups we track. If you are interested in reading more about effective mitigation strategies in general, we recommend the following articles:

Strategies for mitigating APTs
How to mitigate 85% of threats with four strategies

We will continue tracking the Lamberts and sharing new findings with our intel report subscribers, as well as with the general public. If you would like to be the first to hear our news, we suggest you subscribe to our intel reports.
Kaspersky Lab products successfully detect and eradicate all the known malware from the Lamberts family.
For more information about the Lamberts, please contact: intelreports@kaspersky.com






APT
Backdoor
Malware Descriptions
Targeted attacks
Zero-day vulnerabilities



Authors




GReAT





Unraveling the Lamberts Toolkit 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







anonymous 


							Posted on							April 18, 2017. 8:31 pm 



Hudson is probably from hudson-ci (original name of the jenkins ci) not from the river. The workspace directory would also fit.
Reply 








Mike 


							Posted on							February 14, 2019. 5:45 pm 



The cybersecurity firm Symantec analyzed Vault 7 documents and found some of the described software closely matched cyberattacks by “Longhorn,” which it had monitored since 2014. Symantec had previously suspected that “Longhorn” was government-sponsored and had tracked its usage against 40 targets in 16 countries.[
Reply 





















Table of Contents





An Overview of the LambertsThe Lamberts in Brief – from Black to GrayBlack LambertBlue LambertGreen LambertWhite LambertPink LambertGray LambertTimelineCodenames and Popular Culture Referenced in LambertsConclusions 





GReAT webinars






																		13 May 2021, 1:00pm								
GReAT Ideas. Balalaika Edition 





Boris Larin



Denis Legezo










																		26 Feb 2021, 12:00pm								
GReAT Ideas. Green Tea Edition 





John Hultquist



Brian Bartholomew



Suguru Ishimaru



Vitaly Kamluk



Seongsu Park



Yusuke Niwa



Motohiko Sato










																		17 Jun 2020, 1:00pm								
GReAT Ideas. Powered by SAS: malware attribution and next-gen IoT honeypots 





Marco Preuss



Denis Legezo



Costin Raiu



Kurt Baumgartner



Dan Demeter



Yaroslav Shmelev










																		26 Aug 2020, 2:00pm								
GReAT Ideas. Powered by SAS: threat actors advance on new fronts 





Ivan Kwiatkowski



Maher Yamout



Noushin Shabab



Pierre Delcher



Félix Aime



Giampaolo Dedola



Santiago Pontiroli










																		22 Jul 2020, 2:00pm								
GReAT Ideas. Powered by SAS: threat hunting and new techniques 





Dmitry Bestuzhev



Costin Raiu



Pierre Delcher



Brian Bartholomew



Boris Larin



Ariel Jungheit



Fabio Assolini












From the same authors




 


Coyote: A multi-stage banking Trojan abusing the Squirrel installer 






 


FakeSG campaign, Akira ransomware and AMOS macOS stealer 






 


Advanced threat predictions for 2024 






 


Stealer for PIX payment system, new Lumar stealer and Rhysida ransomware 






 


Updated MATA attacks industrial companies in Eastern Europe 









Subscribe to our weekly e-mails
The hottest research right in your inbox




Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ








In the same category




 


HrServ – Previously unknown web shell used in APT attack 






 


Modern Asian APT groups’ tactics, techniques and procedures (TTPs) 






 


A cascade of compromise: unveiling Lazarus’ new campaign 






 


How to catch a wild triangle 






 


StripedFly: Perennially flying under the radar 






 















Latest Posts




 



Malware descriptions

Cracked software beats gold: new macOS backdoor stealing cryptowallets 





Sergey Puzan










 



Kaspersky Security Bulletin

Dark web threats and dark market predictions for 2024 





Sergey Lozhkin



Anna Pavlovskaya



Kaspersky Security Services










 



Research

A lightweight method to detect potential iOS malware 





Maher Yamout










 



Research

Operation Triangulation: The last (hardware) mystery 





Boris Larin












Latest Webinars





 




Technologies and services



												11 Dec 2023, 4:00pm					
60 min

The Future of AI in cybersecurity: what to expect in 2024






Vladimir Dashchenko



Victor Sergeev



Vladislav Tushkanov



Dennis Kipker











 




Threat intelligence and IR



												30 Nov 2023, 4:00pm					
70 min

Responding to a data breach: a step-by-step guide






Anna Pavlovskaya











 




Cyberthreat talks



												14 Nov 2023, 4:00pm					
60 min

2024 Advanced persistent threat predictions






Igor Kuznetsov



David Emm



Marc Rivero



Dan Demeter



Sherif Magdy











 




Cyberthreat talks



												09 Nov 2023, 5:00pm					
60 min

Overview of modern car compromise techniques and methods of protection






Alexander Kozlov



Sergey Anufrienko












Reports







HrServ – Previously unknown web shell used in APT attack 

In this report Kaspersky researchers provide an analysis of the previously unknown HrServ web shell, which exhibits both APT and crimeware features and has likely been active since 2021.








Modern Asian APT groups’ tactics, techniques and procedures (TTPs) 

Asian APT groups target various organizations from a multitude of regions and industries. We created this report to provide the cybersecurity community with the best-prepared intelligence data to effectively counteract Asian APT groups.








A cascade of compromise: unveiling Lazarus’ new campaign 

We unveil a Lazarus campaign exploiting security company products and examine its intricate connections with other campaigns








How to catch a wild triangle 

How Kaspersky researchers obtained all stages of the Operation Triangulation campaign targeting iPhones and iPads, including zero-day exploits, validators, TriangleDB implant and additional modules.








 









Subscribe to our weekly e-mails
The hottest research right in your inbox





Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe











Δ








 











ThreatsThreats

APT (Targeted attacks)
Secure environment (IoT)
Mobile threats
Financial threats
Spam and phishing
Industrial threats
Web threats
Vulnerabilities and exploits


CategoriesCategories

APT reports
Malware descriptions
Security Bulletin
Malware reports
Spam and phishing reports
Security technologies
Research
Publications


Other sections

Archive
All tags
Webinars
APT Logbook
Statistics
Encyclopedia
Threats descriptions
KSB 2023


 









© 2024 AO Kaspersky Lab. All Rights Reserved.
Registered trademarks and service marks are the property of their respective owners.



Privacy Policy
License Agreement
Cookies












Subscribe to our weekly e-mails
The hottest research right in your inbox



Email*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

 
 Subscribe










Δ



























