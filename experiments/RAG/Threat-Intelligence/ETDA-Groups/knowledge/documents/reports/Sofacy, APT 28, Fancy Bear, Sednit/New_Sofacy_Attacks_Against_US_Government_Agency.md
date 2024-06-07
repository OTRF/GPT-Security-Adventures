# Reference for threat actor for "Sofacy, APT 28, Fancy Bear, Sednit"

**Title**: New Sofacy Attacks Against US Government Agency

**Source**: https://unit42.paloaltonetworks.com/unit42-new-sofacy-attacks-against-us-government-agency/

## Content

























New Sofacy Attacks Against US Government Agency




























































 



































Menu






Tools
ATOMs
Security Consulting
About Us
Under Attack?
 












New Sofacy Attacks Against US Government Agency


45,655
 people reacted

4
  7  min. read



Share 


















 







          By Robert Falcone and Bryan Lee 
June 14, 2016 at 5:00 AM
Category: Unit 42
Tags: APT28, Carberp, Ministry of Foreign Affairs, Sofacy, Trojan



 


This post is also available in: 
    日本語 (Japanese)The Sofacy group, also known as APT28, is a well-known threat group that frequently conducts cyber espionage campaigns. Recently, Unit 42 identified a spear phishing e-mail from the Sofacy group that targeted the United States government. The e-mail was sent from a potentially compromised account belonging to the Ministry of Foreign Affairs of another government entity and carried the Carberp variant of the Sofacy Trojan. The developer implemented a clever persistence mechanism in the Trojan, one which had not been observed in previous attacks. The focus of this blog will be on the attacks and the infrastructure associated with Sofacy using the new persistence mechanism as a correlation point.
The Delivery
On May 28, 2016, attackers sent a spear-phishing e-mail to a U.S. government entity using an email address belonging to the Ministry of Foreign Affairs of another country. Analysis of the attack revealed a high likelihood that the sender’s email address was not spoofed and is instead a result of a compromised host or account belonging to that Ministry.
The targeted email had a subject of “FW: Exercise Noble Partner 2016”, which is a reference to a joint NATO training effort between the United States and Georgia. The email contained an RTF file as an attachment, with the filename "Exercise_Noble_Partner_16.rtf,” reflecting the same training exercise. We have also seen related delivery documents with filenames that have a Russian military theme (Putin_Is_Being_Pushed_to_Prepare_for_War.rtf and Russian anti-Nato troops.rtf), purportedly targeting organizations in Poland according to a blog published by Prevenity.
The RTF file is a weaponized document that attempts to exploit CVE-2015-1641 to drop two files to the system, specifically, "btecache.dll" and "svchost.dll". The “btecache.dll” file is a Trojan that loads and executes “svchost.dll”, which is a Carberp variant the Sofacy Trojan. Surprisingly, unlike many other espionage actors who display decoy documents after successful exploitation, this RTF document does not drop or open a decoy document after exploiting the vulnerability.
In the installation process, we observed the delivery document creating a very interesting registry key that it uses for persistence to run the Trojan. The path to the "btecache.dll" file is added to the following registry key:
Software\Microsoft\Office test\Special\Perf\: "C:\Users\[username]\AppData\Roaming\btecache.dll"
This registry key is interesting, because unlike traditional methods of maintaining persistence, it does not automatically run the “btecache.dll” file at system start up. Instead, this registry key will cause the DLL to load only when the user opens any Microsoft Office application, such as Word or Excel. This is the first time Unit 42 has seen the Sofacy group, or any other threat group for that matter, use this tactic for persistence purposes. An added benefit for the threat actor to using this specific tactic for persistence is that it requires user interaction to load and execute the malicious payload, which can cause challenges for detection in automated sandboxes.
The Carberp variant of Sofacy
The "btecache.dll" file is the loader Trojan that is responsible for loading the "svchost.dll" DLL and executing it. Both the "btecache.dll" and "svchost.dll" files contain code from the leaked Carberp source code, specifically the API resolution functions, as well as the RC2 key. The Sofacy group has used the Carberp source code in the past, specifically discussed in a blog by F-Secure, which is the reason we call this Trojan the Carberp variant.
The "svchost.dll" file contains the bulk of the functionality of this Trojan, which at a high level is a downloader that allows the threat actors to gain an initial foothold on the system. The Trojan sends network beacons to its command and control (C2) serverallowing the threat actors to identify targets of interest. The threat actors can then respond to these network beacons to download and execute additional secondary payloads on the system.
The Trojan delivered in this attack contains two network locations that it will send network beacons to, specifically “google.com” and “191.101.31.6”. These beacons are sent to the legitimate website google.com as an attempt to hide the true C2 beacons sent to the actual C2 server hosted at 191.101.31.6.  The network beacons are sent using HTTP POST requests with URLs created largely with random characters. There are two exceptions where random characters are not used to construct the URL, specifically the file extension that is randomly chosen from .xml, .pdf, .htm or .zip and the base64 encoded value at the end of the URL. The base64 encoded data is a string ("J04aLsxVhHBkr19CYr0”) hardcoded within the Trojan that it will then encrypt using a custom algorithm. Figure 1 shows an example beacon sent from the Trojan to the C2 server during analysis.

Figure 1 Network Beacon Sent from Carberp variant of Sofacy
The POST data seen in the beacon in Figure 1 is base64 encoded and encrypted using the same custom algorithm used to encrypt the data in the beacon URL. We decrypted the data to determine its purpose and found the cleartext seen in Figure 2.
,^Bid=I,;<&w@[System Process]
System
smss.exe
csrss.exe
wininit.exe
csrss.exe
winlogon.exe
services.exe
lsass.exe
lsm.exe
svchost.exe
svchost.exe
svchost.exe
svchost.exe
svchost.exe
svchost.exe
svchost.exe
spoolsv.exe
svchost.exe
taskhost.exe
userinit.exe
dwm.exe
explorer.exe
svchost.exe
cmd.exe
conhost.exe
reader_sl.exe
svchost.exe
cmd.exe
conhost.exe
SearchIndexer.exe
SearchProtocolHost.exe
SearchFilterHost.exe
SearchProtocolHost.exe
explorer.exe
svchost.exe
svchost.exe
disk=IDE\DiskMAXTOR_HARDDISK_________________________2.2.1___\5&2770a7af&0&0.0.0
build=0x7caa0e19
Figure 2 Decrypted HTTP POST Data Shows System Information
The clear text of the data sent in the network beacons contains information regarding the compromised system, as well as malware-specific information. The data is comprised of the following fields of data:
id = The serial number of the storage device
w = This parameter (whose name ‘w’ could change to any character between samples) begins with a one byte value denoting the OS version followed by a one byte value for the CPU architecture. These values are immediately followed by a new line delimited list of running processes on the system.
disk = The name of the system's hard drive, obtained from the registry key "SYSTEM\CurrentControlSet\Services\Disk\Enum\0"
build = The hardcoded build identifier for the Trojan version
inject = (Optional, not displayed in Figure 2) If the Trojan injected its code into other processes to interact with the C2 server
This callback data allows the threat actors to determine if the infected machine is a target of interest, as the beacon contains a list of running processes and the name of the storage device that could be used to filter out analysis systems or researchers. If the actors believe the system is of interest, they will respond to these network beacons to download and execute additional secondary payloads on the system. The Trojan parses the response to the beacons for two actions "Execute" and "Delete" between the tags "[file]" and "[/file]", as well as settings labeled "FileName", "PathToSave", "Rundll" and "IP" between the tags "[settings]" and "[/settings]". This allows the threat actors to download additional files to the system, execute both executables and DLLs and delete files.
The Infrastructure
The initial analyzed sample in this attack only contained a single malicious command and control location, 191.101.31.6. We have not observed this IP address used by the Sofacy group in any previous attack campaigns, and examining passive DNS data showed no other correlations to potentially related attacks. The sample also seen by Prevenity appeared to only have a single primary C2 domain, servicecdp[.]com. This domain also appears to be newly created for this specific attack campaign, with no strong links to any previous attacks.
Pivoting off the unique registry key used for persistence revealed links to a previously observed Sofacy campaign, from mid-2015. Two additional payloads with recent compile dates of March 7, 2016, were discovered using the same persistence mechanism, and analysis of those payloads revealed one primary C2 domain, munimonoce[.]com, and three secondary C2 domains, www.wscapi[.]com, www.tabsync[.]net, and storsvc[.]org. The secondary C2 domains may appear familiar, as they were widely publicized in a report from iSight Partners in July 2015 as C2 domains related to the Sofacy group aka Tsar Team.
In addition, the primary C2 domain munimonoce[.]com previously had resolved to the IP 66.172.11.207, which was previously identified as a primary C2 IP for a Sofacy payload with a compile timestamp of June 11, 2015. This particular sample also happened to use the exact same secondary C2 domains of www.wscapi[.]com, www.tabsync[.]net, and storsvc[.]org, but lacked the newly discovered persistence mechanism.

The Sofacy group often re-uses infrastructure components across multiple attack campaigns, whether to speed the flow of attacks, for a lack of available resources committed, or out of sheer laziness. In this case, the newer attack campaign appears to use newly created infrastructure, but still maintains some overlap with previous Sofacy-related C2s. We believe this overlap could possibly be due to an oversight when adapting a previous code base with the new persistence method discussed in this blog for the new attack campaign.
The threat appears to be moving toward deployment of one-off infrastructure that can make analysis of attack campaigns and correlation more challenging. This shift stresses the importance of analysts and researchers being able to pivot on all artifacts of a given attack, not simply relying on network indicators. In this case, we were able use AutoFocus to pivot on a common registry key unique to this attack campaign to quickly identify where it correlates with characteristics of previous attacks.
Conclusion
The Sofacy group continues its attack campaigns on government organizations, specifically the U.S. government in this latest spear-phishing example. The threat group added a new persistence mechanism that requires user interaction by loading its payload into Microsoft Office applications when opened, which may help the actors to evade detection. The use of this new persistence method shows the continued development of tactics and techniques employed by this threat group, often times in clever ways as we observed in this instance.
Palo Alto Networks customers are protected from the new Sofacy Carberp variant and can gather additional information using the following tools:

WildFire detection of all known samples as malicious
All known C2s are classified as malicious in PAN-DB
AutoFocus tags have been created SofacyCarberp

Indicators
Delivery Documents
03cb76bdc619fac422d2b954adfa511e7ecabc106adce804b1834581b5913bca (Exercise_Noble_Partner_16.rtf)
12572c2fc2b0298ffd4305ca532317dc8b97ddfd0a05671066fe594997ec38f5 (Putin_Is_Being_Pushed_to_Prepare_for_War.rtf and Russian anti-Nato troops.rtf)
Loader Trojans
c2551c4e6521ac72982cb952503a2e6f016356e02ee31dea36c713141d4f3785 (btecache.dll)
be1cfa10fcf2668ae01b98579b345ebe87dab77b6b1581c368d1aba9fd2f10a0 (bitsprex3.dll)
fbd5c2cf1c1f17402cc313fe3266b097a46e08f48b971570ef4667fbfd6b7301 (amdcache.dll)
Payloads
69940a20ab9abb31a03fcefe6de92a16ed474bbdff3288498851afc12a834261 (svchost.dll)
aeeab3272a2ed2157ebf67f74c00fafc787a2b9bbaa17a03be1e23d4cb273632 (clconfg.dll)
dfa8a85e26c07a348a854130c652dcc6d29b203ee230ce0603c83d9f11bbcacc (iprpp.dll)
57d230ddaf92e2d0504e5bb12abf52062114fb8980c5ecc413116b1d6ffedf1b (clconfg.dll)
Command and Control
191.101.31.6
munimonoce[.]com
wscapi[.]com
tabsync[.]net
storsvc[.]org
servicecdp[.]com

Get updates from  Palo Alto Networks!
Sign up to receive the latest news, cyber threat intelligence and research from us














Please enter your email address!







Please mark, I'm not a robot!



By submitting this form, you agree to our Terms of Use and acknowledge our Privacy Statement.




















Popular ResourcesResource Center
Blog
Communities
Tech Docs
Unit 42
Sitemap
Legal NoticesPrivacy
Terms of Use
Documents
AccountManage Subscriptions
 
Report a Vulnerability
 



© 2024 Palo Alto Networks, Inc. All rights reserved.























