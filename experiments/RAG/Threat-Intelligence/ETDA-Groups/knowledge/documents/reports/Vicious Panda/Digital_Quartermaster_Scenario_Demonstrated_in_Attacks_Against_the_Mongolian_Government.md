# Reference for threat actor for "Vicious Panda"

**Title**: Digital Quartermaster Scenario Demonstrated in Attacks Against the Mongolian Government

**Source**: https://unit42.paloaltonetworks.com/digital-quartermaster-scenario-demonstrated-in-attacks-against-the-mongolian-government/

## Content

























Digital Quartermaster Scenario Demonstrated in Attacks Against the Mongolian Government




































































 



































Menu






Tools
ATOMs
Security Consulting
About Us
Under Attack?
 












Digital Quartermaster Scenario Demonstrated in Attacks Against the Mongolian Government


33,158
 people reacted

16
  13  min. read



Share 


















 







          By Josh Grunzweig, Robert Falcone and Bryan Lee 
March 14, 2016 at 1:00 PM
Category: Government, Threat Prevention, Unit 42
Tags: BBSRAT, cmstar, Digital Quartermaster, Mongolia



 


This post is also available in: 
    日本語 (Japanese)Unit 42 has collected multiple spear phishing emails, weaponized document files, and payloads that targeted various offices of the Mongolian government during the time period of August 2015 and February 2016. The phishing emails and document files leveraged a variety of geopolitically sensitive subject matters as attractive lures, such as events in Beijing, the Dalai Lama, North Korea relations, the Zika virus, and various legitimate appearing announcements. As we began to analyze and tear down the various samples we collected, we found significant overlaps with previously reported and documented adversary groups, attack campaigns, and their toolsets, exemplifying the concept of the Digital Quartermaster.

The concept of the Digital Quartermaster is not a particularly new one; it is the idea that there is a group, or groups whose mission is to supply and maintain malicious tools in support of cyber espionage operations. The existence of a Digital Quartermaster has been discussed within the intelligence community for some time, but it is not often that sufficient overlaps exist between what appear to be separate toolsets to confidently claim this idea is indeed in use. The data Unit 42 has collected and analyzed however, does strongly point to the possibility that while there may be multiple operations groups, a Digital Quartermaster may be the one supplying and maintaining the tools used.
Attack Analysis
While investigating new BBSRAT instances discovered using the AutoFocus tool, Unit 42 was able to collect additional samples, weaponized documents, and phishing emails uploaded to VirusTotal between August 2015 through February 2016. Each of the samples collected via WildFire and VirusTotal contained significant overlaps in tactics used, tools used, as well as infrastructure for command and control channels. In addition, a large majority of the samples gathered from VirusTotal were uploaded from a single entity in Mongolia.
The attacks themselves followed a consistent playbook throughout the observed timeframe; using weaponized Microsoft Word documents initially containing an exploit for only CVE-2012-0158, appearing to use the highly popular ‘Tran Duy Linh’ toolkit, then adding in an additional exploit for CVE-2014-1761 in the three newest samples we collected. The newer documents containing exploits for both vulnerabilities appeared to use a publically available PoC authored by ‘HCL’, with little to no modifications made. All of the weaponized documents except two executed the Cmstar loader or a lightly modified variant of Cmstar onto the victim host while displaying a decoy document or a legitimate appearing document that is generated and presented to the user to make it appear that the weaponized document that had been executed was indeed, legitimate. Once Cmstar was loaded onto the victim hosts, it would attempt to retrieve a final payload. Unfortunately, at the time of analysis, we were unable to retrieve the majority of the payloads the Cmstar loaders were attempting to download, but those that were available were variants of BBSRAT. The two samples not using Cmstar simply had BBSRAT embedded directly into to the weaponized document.
Furthermore, examining the data from August indicates that this campaign had started earlier and the adversary may have already achieved initial footholds, due to the use of what appears to be compromised legitimate email accounts from within the Mongolian government.
Attack Timeline

Attack Details



SHA256
5beb50d95c1e720143ca0004f5172cb8881d75f6c9f434ceaff59f34fa1fe378


Date
8/12/2015


Filename
Ялалтын баярын ар дахь улс төр.doc (Victory in the back of the government)


Vulnerability Targeted
CVE-2012-0158


Tools Used
Cmstar


Description
Two spear-phishing emails originating from likely compromised account 'altangadas@energy.gov.mn' targets multiple other Mongolian government officials. The subject and file attachment are titled 'Ялалтын баярын ар дахь улс төр' (Victory in the back of the government). CVE-2012-0158 exploit used, dropping new variant of Cmstar. The dropped decoy document talks about a Russian festival known as 'Victory Day' and Mongolian's participation in this event.








SHA256
10090692ff40758a08bd66f806e0f2c831b4b9742bbf3d19c250e778de638f57


Date
8/28/2015


Filename
Бээжин хотод цэргийн ёслолын жагсаал.doc (Military ceremonial parade in Beijing)


Vulnerability Targeted
CVE-2012-0158


Tools Used
Cmstar


Description
Spear-phishing email originating from 'ganbat_g@bpo.gov.mn'. A single target is discovered in the collected sample. Subject and filename are titled 'Бээжин хотод цэргийн ёслолын жагсаал' (Military ceremonial parade in Beijing). CVE-2012-0158 exploit used, dropping new variant of Cmstar. The decoy document contains a flight itinerary from Ulaanbaatar, Mongolia to Beijing, China.








SHA256
44dbf05bc81d17542a656525772e0f0973b603704f213278036d8ffc999bb79a


Date
9/15/2015


Filename
Путины урилга.doc (Putin's Invitation)


Vulnerability Targeted
CVE-2012-0158


Tools Used
Cmstar


Description
Weaponized Microsoft Word document found titled 'Путины урилга.doc' (Putin's Invitation). CVE-2012-0158 exploit used, dropping new variant of Cmstar. The following decoy image, embedded within a Word document, is displayed to the victim upon opening the malicious file.







SHA256
91ffe6fab7b33ff47b184b59356408951176c670cad3afcde79aa8464374acd3


Date
9/16/2015


Filename
1.doc


Vulnerability Targeted
CVE-2012-0158


Tools Used
Cmstar


Description
Weaponized Microsoft Word document with unknown title found. Likely delivered via spear-phishing. CVE-2012-0158 exploit used, dropping new variant of Cmstar. The decoy document, which is 13 pages in length, talks about the interference of the United States in other countries across the globe.







SHA256
6f3d4fb64de9ae61776fd19a8eba3d1d828e7e26bb89ace00c7843a57c5f6e8a


Date
9/29/2015


Filename
Далай ламыг эмч нар амрахыг зөвлөжээ.doc


Vulnerability Targeted
CVE-2012-0158


Tools Used
Cmstar


Description
Spear-phishing email originating from 'bilguun@masm.gov.mn'. Nearly two thousand recipients found to be targeted, all within the Mongolian government. Email subject and filenames titled 'Далай ламыг эмч нар амрахыг зөвлөжээ' (Dalai Lama doctors advised rest). CVE-2012-0158 exploit used, dropping new variant of Cmstar. The decoy document discusses the latest health of the Dalai Lama, as well as a number of US-based trips he made in late 2015.



 



SHA256
e88ea5eb642eaf832f8399d0337ba9eb1563862ddee68c26a74409a7384b9bb9


Date
10/2/2015


Filename
Sudalgaa avah zagvar.doc


Vulnerability Targeted
CVE-2012-0158


Tools Used
Cmstar


Description
Spear-phishing email originating from 'davaa_ayush@yahoo.com'. 'davaa_ayush@mod.gov.mn' was a target in the August 12, 2015 attack, indicating the user may have had their personal email account compromised as well. Single target found. Email subject is 'Fw:_Fwd:_@_БХЯ-наас' (Defense Ministry). Filename is titled 'Sudalgaa avah zagvar.doc', a possible Romanization of Mongolian. CVE-2012-0158 exploit used, dropping new variant of Cmstar. The decoy table provides information about the rank, class, date of birth, and experience of individuals in the Mongolian armed forces. 



  




SHA256
68f97bf3d03b1733944c25ff4933e4e03d973ccdd73d9528f4d68806b826735e


Date
10/22/2015


Filename
албанушаалтнуудын сарын цалингийнхаа 30 хувийг хасах.doc


Vulnerability Targeted
CVE-2012-0158


Tools Used
Cmstar


Description
Weaponized Microsoft Word document found titled 'Ерөнхий сайд албанушаалтнуудын сарын цалингийнхаа 30 хувийг хасах.doc' (Prime Minister albanushaaltnuudyn monthly salary minus 30%.doc). Likely delivered via spear-phishing. CVE-2012-0158 exploit used, dropping new variant of Cmstar The document discusses changes made to the salaries of government officials within the Mongolian government



 



SHA256
00ddae5bbc2ddf29954749519ecfb3978a68db6237ebea8e646a898c353053ce


Date
10/22/2015


Filename
Улс төрийн www.politik.mn сайт нээгдлээ.doc


Vulnerability Targeted
CVE-2012-0158


Tools Used
Cmstar


Description
Weaponized Microsoft Word document found titled 'Улс төрийн www.politik.mn сайт нээгдлээ.doc' (States opens state www.politik.mn site.doc). Likely delivered via spear-phishing. CVE-2012-0158 exploit used, dropping new variant of Cmstar. The decoy document dropped by the malicious file discusses a new website being launched by the Mongolian government.



 



SHA256
c2ebaf4366835e16f34cc7f0b56f8eaf80a9818375c98672bc678bb4107b4d8c


Date
10/28/2015


Filename
Unknown


Vulnerability Targeted
CVE-2012-0158


Tools Used
Cmstar


Description
Weaponized Microsoft Word document with unknown title found. Likely delivered via spear-phishing. CVE-2012-0158 exploit used, dropping new variant of Cmstar. The decoy document talks about a 2016 budget discussion in the Mongolian Parliament.







SHA256
aa86f4587423c2ff677aebae604614030f9f4d38280409501662ab4e4fe20c2a


Date
12/23/2015


Filename
СОНОРДУУЛГА.doc


Vulnerability Targeted
CVE-2012-0158


Tools Used
BBSRAT


Description
Weaponized Microsoft Word document found titled 'СОНОРДУУЛГА.doc' (Announcement). Likely delivered via spear-phishing. CVE-2012-0158 exploit used, with BBSRAT embedded. The document translates to an announcement of a loan agreement signed with foreign banks and financial institutions on October 16th, 2015.







SHA256
fc21814a5f9ed2f6bef9e15b113d00f9291a6553c1e02cc0b4c185c6030eca45


Date
1/4/2016


Filename
Өвлийн өвгөнийн үг.doc


Vulnerability Targeted
CVE-2012-0158


Tools Used
BBSRAT


Description
Weaponized Microsoft Word document found titled 'Өвлийн өвгөнийн үг.doc' (Santa's word). Likely delivered via spear-phishing. CVE-2012-0158 exploit used, with BBSRAT embedded. The decoy document, which had spacing removed for an unknown reason, provides a series of children holiday season songs and poems.



 


SHA256
7e031a04e570cddda907d0b4b7af19ce60dc481394dfb3813796ce0e6d079305

Date
2/17/2016


Filename
Хойд Солонгост хориг арга хэмжээ авна.doc


Vulnerability Targeted
CVE-2012-0158 and CVE-2014-1761


Tools Used
Cmstar and BBSRAT


Description
Weaponized Microsoft Word document found titled 'Хойд Солонгост хориг арга хэмжээ авна.doc' (North Korea sanctions). Exploits for both CVE-2012-0158 and CVE-2014-1761 used, dropping a separate, newer variant of Cmstar which downloaded BBSRAT as its final payload. The decoy document talks about a recent speech made by the South Korean President regarding sanctions made against North Korea.
 







SHA256
5c7e3cde4d286909154e9a5ee5a5d061a1f0efaa9875fb50c9073e1e8b6cfaef


Date
2/19/2016


Filename
Зика Монголд ойртсоор.doc


Vulnerability Targeted
CVE-2012-0158 and CVE-2014-1761


Tools Used
Cmstar and BBSRAT


Description
Weaponized Microsoft Word document found titled 'Зика Монголд ойртсоор' (Zika closer to Mongolia). Exploits for both CVE-2012-0158 and CVE-2014-1761 used, dropping a separate, newer variant of Cmstar which downloaded BBSRAT as its final payload. The translated Mongolian text found within the decoy document discusses how the Zika virus has been witnessed in both China and Russia, as well as other countries across the globe.







SHA256
0b0e6b40a63710b4f7e6d00d7a4a86e6db2df720fef48640ab6d9d88352a4890


Date
2/19/2016


Filename
Хятадад “Зика” вирусын хоёр дахь тохиолдол илэрчээ.doc


Vulnerability Targeted
CVE-2012-0158 and CVE-2014-1761


Tools Used
Cmstar and BBSRAT


Description
Weaponized Microsoft Word document found titled 'Хятадад “Зика” вирусын хоёр дахь тохиолдол илэрчээ' (China "Zika" viruses in two cases). Exploits for both CVE-2012-0158 and CVE-2014-1761 used, dropping a separate, newer variant of Cmstar which downloaded BBSRAT as its final payload. The dropped decoy document contains a press release dated on February 16th, 2016. The press release discusses changes made to the coal industry in inner Mongolia, The G-20 meeting in China, a five year plan for economic and social development, and two cases of the Zika virus.




The Digital Quartermaster: Tool Overlap
The tools we observed being used in this attack campaign remained consistent throughout the six months of data we were able to collect and analyze. Yet, prior to the findings in this report, none of the tools used in this campaign had been observed being used in conjunction with each other. In their 2013 report, Kaspersky theorized that NetTraveler may have had connections to the Lurid/Enfal adversaries due to some similarities in command and control infrastructure and targeting of minority groups in China, but no strong evidence was discovered since then. CMStar is a variant of Lurid discovered by us in May 2015, with similar targeting as previously observed as NetTraveler, but again, with no strong connections. BBSRAT is a relatively new Trojan we had discovered and publicized in December 2015 and had attributed it to a campaign dubbed ‘Roaming Tiger’ by ESET in 2014, which specifically appeared to target Russia and Russian speaking nation state. None of these tools have been publicly observed in use together, in a singular campaign, until now:

The initial dropper embedded in the weaponized document files were obfuscated using a subtraction cipher previously used to obfuscate strings in the NetTraveler malware family.
A BinDiff comparison of the newer Cmstar variant with a previously reported on NetTraveler sample shows an 80% code similarity
The first stage loader used in the attacks was Cmstar, or lightly modified variants. Cmstar is closely related to Lurid which is associated with the Enfal trojan
The final payload for the newest weaponized documents retrieved was BBSRAT, which was previously associated with an attack campaign called "Roaming Tiger", targeting Russia and other Russian speaking nations speaking

The one commonality that does appear amongst these seemingly different tools used by different operators is their geolocational nexus: China. In 2011, TrendMicro strongly attributed Lurid/Enfal to operators based out of China, although they stopped just short of claiming it. In Kaspersky’s 2013 report on NetTraveler, another strong attribution was made to a China-based operator. ESET’s “Roaming Tiger” reporting did not attribute the attack to any specific nation-state, but examining the command and control infrastructure and WHOIS data again suggested a China-based operator.
These facts begin to lead us to the following possible conclusions: the previous attack campaigns associated with their specific tool were all actually conducted by one, large, all encompassing operations unit. The previous attack campaigns were conducted by separate, but related operations unit with access to a common Digital Quartermaster for tools, or some combination of either scenario.
Technical Analysis of Tools Used
All of the Microsoft Word documents leveraged in these attacks used the CVE-2012-0158 and CVE-2014-1761 exploits. All of the exploit documents, in addition to targeting the same organizations and relying upon the same exploit techniques, ultimately dropped a version of the BBSRAT. A large number of the encountered samples used a new version of the Cmstar downloader to accomplish this, while some documents dropped and executed BBSRAT directly. Upon successful exploitation, the exploit documents would drop and execute a payload using one of the following techniques:

The exploit document drops and executes a file with a path of %TEMP%\xpsfiltsvcs.tmp. This file contains an original Cmstar downloader that was discussed in a previous blog post.
The 'MSOProtect.acl', 'offcln.log', and 'offcln.pip' files are dropped in the %APPDATA%\Microsoft\Office\ directory. The MSOProtect.acl file contains a new variant of the Cmstar malware family. The offcln.pip is a DLL that is responsible for opening a legitimate Microsoft Word decoy document. The offcln.log file contains a command that will open this decoy document. The offcln.log file is used by offcln.pip in order to accomplish this.
The %APPDATA%\comctl32.dll file is dropped and subsequently loaded. This file contains either a new instance of the Cmstar downloader, or a copy of the BBSRAT malware family, which was discussed by Palo Alto Networks in December 2015.

New Cmstar Downloader
The majority of the spear-phishing attachments leveraged variants of the previously discussed downloader named 'Cmstar'. Much of the functionality remained consistent in the newest variants, which were compiled in July and August of 2015. For reference, the original Cmstar downloader malware samples were compiled in February 2015.
The new samples appear to have minimal changes made, and in fact a number of the debugging statements mentioned in the original samples are seen in a number of the newest variants. The obfuscated routine that is responsible for downloading the payload has increased in size from 779 bytes to 943 bytes. This increase in size is due to additional error controls put into place. This routine is still encrypted using a single-byte XOR operation.
However, the newest Cmstar variants use a different routine to obfuscate important strings within the binary. The following code, represented in Python, accomplishes this:





def decode(data):
  out = ""
  c = 0
  for d in data:
    out += chr(ord(d) - c - 10)
    c += 1
  return out




1234567

def decode(data):  out = ""  c = 0  for d in data:    out += chr(ord(d) - c - 10)    c += 1  return out





Malware analysts may recognize this routine, as it's identical to the one witnessed in previously discussed NetTraveler samples that were found to be targeting an individual working for the Foreign Ministry of Uzbekistan in China. As witnessed in the following diagram, the new Cmstar downloader’s obfuscation routine has a 100% code match to the NetTraveler downloader previously encountered:
Figure 1 Code Overlap Between Cmstar and NetTraveler Downloaders
The following URLs were identified to be used by these Cmstar samples:

http://thbaw.ofhloe[.]com/cgl-bin/conime.cgi
http://dolimy.celeinkec[.]com/cgl-bin/upl.cgi
http://question.eboregi[.]com
http://pplime.savecarrots[.]com/cgl-bin/upsd.cgi
http://dolimy.celeinkec[.]com/bin/r0206/update.tmp

The majority of these URLs were not responsive at the time of analysis, with the exception of the last one. This returned file is an encoded executable that contains a dropper, which in turn loads BBSRAT.
BBSRAT
Much of BBSRAT's functionality has remained consistent in the newest variants. Like previous versions, the malware will build an Import Address Table at runtime and uses the following mutex to ensure a single copy of BBSRAT is running at a given time:
Global\\GlobalAcProtectMutex
Additionally, the network structure, URL pattern, and other characteristics of the malware remain consistent. BBSRAT will ensure persistence by setting the following registry key:
HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run\comctl32 - rundll32.exe %APPDATA%\comctl32.dll, Enter
The largest modification has been the addition of four commands to the command and control handler. These commands are still being researched and full functionality of them has yet to be determined. We have identified the following BBSRAT command and control servers:

cocolco[.]com
ofhloe[.]com
housejjk[.]com

Infrastructure Analysis
Mapping out the first stage command and control infrastructure for the analyzed Cmstar samples revealed an infrastructure that was most likely deployed specifically for this attack campaign:

Figure 2 Cmstar Command and Control Infrastructure
A single domain, question.erobegi[.]com, was found to be reused. This domain had previous been identified as a first stage command and control in May 2015 when we initially discovered CMStar. However, the payload was not identified at the time. The WHOIS data revealed heavy usage of resellers by the adversary, likely as an evasion technique. Analyzing the historical WHOIS data however, revealed one of the 'clean' personas used by the adversary as a registrant 'HELENEHELEN@EXCITE.CO.JP', was used to register one of the command and control domains for CMStar, celeinkec[.]com as well as one of the primary command and control domains for BBSRAT, housejjk[.]com, further supporting the links between CMStar, and BBSRAT.
The BBSRAT command and control infrastructure remained exactly the same as previously reported in December 2015:

Figure 3 BBSRAT Command and Control Infrastructure
Unfortunately, we were unable to retrieve all of the final payloads from every sample at the time of analysis. ￼One interesting fact to note is the use of the primary domain ofhloe[.]com; BBSRAT uses pagbine.ofhloe[.]com as a primary command and control, while we also observed Cmstar thbaw.ofhloe[.]com as a first stage command and control to likely retrieve BBSRAT.
Conclusion
Unit 42 often speaks of sharing threat intelligence, tools, and procedures amongst the security industry, often times pointing to the fact that the adversaries we are up against on an everyday basis are doing the exact same. Still, as a community, when we do publicize adversary groups or campaigns, there is a tendency to encapsulate each and place them in their own isolated bubbles, directly contradicting the message of sharing amongst the adversary. The reasoning behind this is not meant to be hypocritical – it is simply more straightforward for identification and ingestion purposes to be able to silo each group or campaign rather than come to the conclusion that every group or campaign is somehow related due to the sharing nature of the adversaries. We must acknowledge the fact however, that in general many attacks are related, even if they do appear significantly different or do not share the same TTPs as observed previously
The collection of data we have analyzed strongly points to the fact that a Digital Quartermaster may exist amongst the adversary. The strong overlaps within the tactics used in the toolsets as well as links in infrastructure indicate it is likely that a singular entity is responsible for deployment and maintenance of the tools used, in conjunction with a separate operator group responsible for the actual execution of the cyber espionage operations.
Palo Alto Networks customers are protected through our next-generation security platform:

WildFire successfully detects BBSRAT, Cmstar, and the weaponized documents as malicious
AutoFocus identifies the tools used under the Cmstar and BBSRAT tags
Traps actively detects and prevents exploitation of both CVE-2012-0158 and CVE-2014-1761
The C2 domains and files mentioned in this report are blocked through Threat Prevention

Indicators of Compromise
Exploit Document SHA256 Hashes
5beb50d95c1e720143ca0004f5172cb8881d75f6c9f434ceaff59f34fa1fe378
10090692ff40758a08bd66f806e0f2c831b4b9742bbf3d19c250e778de638f57
44dbf05bc81d17542a656525772e0f0973b603704f213278036d8ffc999bb79a
91ffe6fab7b33ff47b184b59356408951176c670cad3afcde79aa8464374acd3
6f3d4fb64de9ae61776fd19a8eba3d1d828e7e26bb89ace00c7843a57c5f6e8a
e88ea5eb642eaf832f8399d0337ba9eb1563862ddee68c26a74409a7384b9bb9
68f97bf3d03b1733944c25ff4933e4e03d973ccdd73d9528f4d68806b826735e
00ddae5bbc2ddf29954749519ecfb3978a68db6237ebea8e646a898c353053ce
c2ebaf4366835e16f34cc7f0b56f8eaf80a9818375c98672bc678bb4107b4d8c
aa86f4587423c2ff677aebae604614030f9f4d38280409501662ab4e4fe20c2a
fc21814a5f9ed2f6bef9e15b113d00f9291a6553c1e02cc0b4c185c6030eca45
7e031a04e570cddda907d0b4b7af19ce60dc481394dfb3813796ce0e6d079305
0b0e6b40a63710b4f7e6d00d7a4a86e6db2df720fef48640ab6d9d88352a4890
5c7e3cde4d286909154e9a5ee5a5d061a1f0efaa9875fb50c9073e1e8b6cfaef
BBSRAT SHA256 Hashes
567a5b54d6c153cdd2ddd2b084f1f66fc87587dd691cd2ba8e30d689328a673f
cd3b8e4f3a6379dc36fedf96041e292b4195d03f27221167bce7302678fb2540
BBSRAT C2 Servers
jowwln.cocolco[.]com
pagbine.ofhloe[.]com
cdaklle.housejjk[.]com
Cmstar SHA256 Hashes
c3253409cccee20caa7b77312eb89bdbe8920cdb44f3fabfe5e2eeb78023c1b8
3e2c0d60c7677d3ead690b1b6d4d7c5aaa2d218679634ac305ef3d75b5688e6a
3a7348d546d85a179f9d52ff83b20004136ee584993c23a8bfe5c168c00fbaa9
19ba40a7fa332b750c7d93385dd51bd08ee63f91cedb4ae5a93f9f33ecb38c44
4e1d59042336c3758e77c5c521f60ae262aad01bf7265581de54e869a02b65bc
Cmstar C2 Servers
http://thbaw.ofhloe[.]com/cgl-bin/conime.cgi
http://dolimy.celeinkec[.]com/cgl-bin/upl.cgi
http://question.eboregi[.]com
http://pplime.savecarrots[.]com/cgl-bin/upsd.cgi
http://dolimy.celeinkec[.]com/bin/r0206/update.tmp

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























