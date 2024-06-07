# Reference for threat actor for "Platinum"

**Title**: PLATINUM (cybercrime group) - Wikipedia

**Source**: https://en.wikipedia.org/wiki/PLATINUM_(cybercrime_group)

## Content




PLATINUM (cybercrime group) - Wikipedia


























Jump to content







Main menu





Main menu
move to sidebar
hide



		Navigation
	


Main pageContentsCurrent eventsRandom articleAbout WikipediaContact usDonate





		Contribute
	


HelpLearn to editCommunity portalRecent changesUpload file





Languages

Language links are at the top of the page.



















Search











Search





























Create account

Log in








Personal tools





 Create account Log in





		Pages for logged out editors learn more



ContributionsTalk




























Contents
move to sidebar
hide




(Top)





1PLATINUM's techniques



Toggle PLATINUM's techniques subsection





1.1Intel Exploit









2Security







3See also







4References

















Toggle the table of contents







PLATINUM (cybercrime group)



Add languages





Add links











ArticleTalk





English

















ReadEditView history







Tools





Tools
move to sidebar
hide



		Actions
	


ReadEditView history





		General
	


What links hereRelated changesUpload fileSpecial pagesPermanent linkPage informationCite this pageGet shortened URLDownload QR codeWikidata item





		Print/export
	


Download as PDFPrintable version

























From Wikipedia, the free encyclopedia


China-based hacker group
PLATINUM is the name given by Microsoft to a cybercrime collective active against governments and related organizations in South and Southeast Asia.[1] They are secretive and not much is known about the members of the group.[2] The group's skill means that its attacks sometimes go without detection for many years.[1]
The group, considered an advanced persistent threat, has been active since at least 2009,[3] targeting victims via spear-phishing attacks against government officials' private email addresses, zero-day exploits, and hot-patching vulnerabilities.[4][5] Upon gaining access to their victims' computers, the group steals economically sensitive information.[1]
PLATINUM succeeded in keeping a low profile until their abuse of the Microsoft Windows hot patching system was detected and publicly reported in April 2016.[2] This hot patching method allows them to use Microsoft's own features to quickly patch, alter files or update an application, without rebooting the system altogether, this way, they can maintain the data they have stolen while masking their identity.[2]
In June 2017, PLATINUM became notable for exploiting the serial over LAN (SOL) capabilities of Intel's Active Management Technology to perform data exfiltration.[6][7][8][9][10][11][12][13]


PLATINUM's techniques[edit]
PLATINUM has been known to exploit web plugins, at one point infiltrating the computers of several Indian government officials 2009, using a website that provided an email service.[clarification needed][1]
Once in control of a target's computer, PLATINUM actors can move through the target's network using specially built malware modules.  These have either been written by one of the multiple teams working under the Platinum group umbrella, or they could have been sold through any number of outside sources that Platinum has been dealing with since 2009.[1]
Because of the diversity of this malware, the versions of which have little code in common, Microsoft's investigators have taxonomised it into families.[1]
The piece of malware most widely used by PLATINUM was nicknamed Dispind by Microsoft.[1] This piece of malware can install a keylogger, a piece of software that records (and may also be able to inject) keystrokes.[citation needed]
PLATINUM also uses other malware like "JPIN" which installs itself into the %appdata% folder of a computer so that it can obtain information, load a keylogger, download files and updates, and perform other tasks like extracting files that could contain sensitive information.[1]
"Adbupd" is another malware program utilised by PLATINUM, and is similar to the two previously mentioned. It is known for its ability to support plugins, so it can be specialised, making it versatile enough to adapt to various protection mechanisms.[1]

Intel Exploit[edit]
In 2017, Microsoft reported that PLATINUM had begun to exploit a feature of Intel CPUs.[14] The feature in question is Intel's AMT Serial-over-LAN (SOL), which allows a user to remotely control another computer, bypassing the host operating system of the target, including firewalls and monitoring tools within the host operating system.[14]

Security[edit]
Microsoft advises users to apply all of their security updates to minimize vulnerabilities and to keep highly sensitive data out of large networks.[1] Because PLATINUM targets organizations, companies and government branches to acquire trade secrets, anyone working in or with such organizations can be a target for the group.[15]

See also[edit]
Intel AMT § Known vulnerabilities and exploits
Titanium (malware)
References[edit]


^ a b c d e f g h i j "PLATINUM Targeted attacks in South and Southeast Asia (PDF)" (PDF). Windows Defender Advanced Threat Hunting Team (Microsoft). 2016. Retrieved 2017-06-10.

^ a b c Osborne, Charlie. "Platinum hacking group abuses Windows patching system in active campaigns | ZDNet". ZDNet. Retrieved 2017-06-09.

^ Eduard Kovacs (2017-06-08). ""Platinum" Cyberspies Abuse Intel AMT to Evade Detection". SecurityWeek.Com. Retrieved 2017-06-10.

^ Eduard Kovacs (2016-04-27). ""Platinum" Cyberspies Abuse Hotpatching in Asia Attacks". SecurityWeek.Com. Retrieved 2017-06-10.

^ msft-mmpc (2016-04-26). "Digging deep for PLATINUM – Windows Security". Blogs.technet.microsoft.com. Retrieved 2017-06-10.

^ Peter Bright (2017-06-09). "Sneaky hackers use Intel management tools to bypass Windows firewall". Ars Technica. Retrieved 2017-06-10.

^ Tung, Liam (2014-07-22). "Windows firewall dodged by 'hot-patching' spies using Intel AMT, says Microsoft". ZDNet. Retrieved 2017-06-10.

^ msft-mmpc (2017-06-07). "PLATINUM continues to evolve, find ways to maintain invisibility – Windows Security". Blogs.technet.microsoft.com. Retrieved 2017-06-10.

^ Catalin Cimpanu (2017-06-08). "Malware Uses Obscure Intel CPU Feature to Steal Data and Avoid Firewalls". Bleepingcomputer.com. Retrieved 2017-06-10.

^ Juha Saarinen (2017-06-08). "Hackers abuse low-level management feature for invisible backdoor - Security". iTnews. Retrieved 2017-06-10.

^ Richard Chirgwin (2017-06-08). "Vxers exploit Intel's Active Management for malware-over-LAN. Platinum attack spotted in Asia, needs admin credentials". The Register. Retrieved 2017-06-10.

^ Christof Windeck (2017-06-09). "Intel-Fernwartung AMT bei Angriffen auf PCs genutzt | heise Security". Heise.de. Retrieved 2017-06-10.

^ "PLATINUM activity group file-transfer method using Intel AMT SOL | Windows Security Blog | Channel 9". Channel9.msdn.com. 2017-06-07. Retrieved 2017-06-10.

^ a b "Platinum hacker group uses Intel AMT", Tad Group, 2017-09-25

^ Liu, Jianhong (2017-07-15). Comparative Criminology in Asia. Springer. ISBN 9783319549422.


vteHacking in the 2010s
← 2000s
Timeline
2020s →
Major incidents2010
Operation Aurora (publication of 2009 events)
Australian cyberattacks
Operation Olympic Games
Operation ShadowNet
Operation Payback
2011
Canadian government
DigiNotar
DNSChanger
HBGary Federal
Operation AntiSec
PlayStation network outage
RSA SecurID compromise
2012
LinkedIn hack
Stratfor email leak
Operation High Roller
2013
South Korea cyberattack
Snapchat hack
Cyberterrorism Attack of June 25
2013 Yahoo! data breach
Singapore cyberattacks
2014
Anthem medical data breach
Operation Tovar
2014 celebrity nude photo leak
2014 JPMorgan Chase data breach
2014 Sony Pictures hack
Russian hacker password theft
2014 Yahoo! data breach
2015
Office of Personnel Management data breach
Hacking Team
Ashley Madison data breach
VTech data breach
Ukrainian Power Grid Cyberattack
SWIFT banking hack
2016
Bangladesh Bank robbery
Hollywood Presbyterian Medical Center ransomware incident
Commission on Elections data breach
Democratic National Committee cyber attacks
Vietnam Airport Hacks
DCCC cyber attacks
Indian Bank data breaches
Surkov leaks
Dyn cyberattack
Russian interference in the 2016 U.S. elections
2016 Bitfinex hack
2017
SHAttered
2017 Macron e-mail leaks
WannaCry ransomware attack
Westminster data breach
Petya and NotPetya
2017 Ukraine ransomware attacks
Vault7 data breach
Equifax data breach
Deloitte breach
Disqus breach
2018
Trustico
Atlanta cyberattack
SingHealth data breach
2019
Sri Lanka cyberattack
Baltimore ransomware attack
Bulgarian revenue agency hack
WhatsApp snooping scandal
Jeff Bezos phone hacking incident
Hacktivism
Anonymous
associated events
CyberBerkut
GNAA
Goatse Security
Lizard Squad
LulzRaft
LulzSec
New World Hackers
NullCrew
OurMine
PayPal 14
RedHack
Teamp0ison
 TDO 
UGNazi
Ukrainian Cyber Alliance
Advancedpersistent threats
Bureau 121
Charming Kitten
Cozy Bear
Dark Basin
DarkMatter
Elfin Team
Equation Group
Fancy Bear
GOSSIPGIRL (confederation)
Guccifer 2.0
Hacking Team
Helix Kitten
Iranian Cyber Army
Lazarus Group (BlueNorOff) (AndAriel)
NSO Group
Numbered Panda
PLA Unit 61398
PLA Unit 61486
PLATINUM
Pranknet
Red Apollo
Rocket Kitten
Stealth Falcon
Syrian Electronic Army
Tailored Access Operations
The Shadow Brokers
Yemen Cyber Army
Individuals
George Hotz
Guccifer
Jeremy Hammond
Junaid Hussain
Kristoffer von Hassel
Mustafa Al-Bassam
MLT
Ryan Ackroyd
Sabu
Topiary
Track2
The Jester
Major vulnerabilitiespublicly disclosed
Evercookie (2010)
iSeeYou (2013)
 Heartbleed (2014)
Shellshock (2014)
POODLE (2014)
Rootpipe (2014)
Row hammer (2014)
SS7 vulnerabilities (2014)
JASBUG (2015)
Stagefright (2015)
DROWN (2016)
Badlock (2016)
Dirty COW (2016)
Cloudbleed (2017)
Broadcom Wi-Fi (2017)
EternalBlue (2017)
DoublePulsar (2017)
Silent Bob is Silent (2017)
KRACK (2017)
ROCA vulnerability (2017)
BlueBorne (2017)
Meltdown (2018)
Spectre (2018)
EFAIL (2018)
Exactis (2018)
Speculative Store Bypass (2018)
Lazy FP state restore (2018)
TLBleed (2018)
SigSpoof (2018)
Foreshadow (2018)
Dragonblood (2019)
Microarchitectural Data Sampling (2019)
BlueKeep (2019)
Kr00k (2019)
Malware2010
Bad Rabbit
 Black Energy 2
SpyEye
Stuxnet
2011
Coreflood
Alureon
Duqu
Kelihos
Metulji botnet
Stars
2012
Carna
Dexter
FBI
Flame
Mahdi
Red October
Shamoon
2013
CryptoLocker
DarkSeoul
2014
Brambul
 Black Energy 3
Carbanak
Careto
DarkHotel
Duqu 2.0
FinFisher
Gameover ZeuS
Regin
2015
Dridex
Hidden Tear
Rombertik
TeslaCrypt
2016
Hitler
Jigsaw
KeRanger
MEMZ
Mirai
Pegasus
Petya and NotPetya
X-Agent
2017
BrickerBot
Kirk
LogicLocker
Rensenware
Triton
WannaCry
XafeCopy
2018
VPNFilter
2019
Grum
Joanap
NetTraveler
R2D2
Tinba
Titanium
ZeroAccess botnet





Retrieved from "https://en.wikipedia.org/w/index.php?title=PLATINUM_(cybercrime_group)&oldid=1198114185"
Categories: 2017 in computingCybercrimeHacking in the 2010sCriminal advanced persistent threat groupsHidden categories: Articles with short descriptionShort description matches WikidataWikipedia articles needing clarification from October 2017All articles with unsourced statementsArticles with unsourced statements from October 2017






 This page was last edited on 23 January 2024, at 01:24 (UTC).
Text is available under the Creative Commons Attribution-ShareAlike License 4.0;
additional terms may apply.  By using this site, you agree to the Terms of Use and Privacy Policy. Wikipedia® is a registered trademark of the Wikimedia Foundation, Inc., a non-profit organization.


Privacy policy
About Wikipedia
Disclaimers
Contact Wikipedia
Code of Conduct
Developers
Statistics
Cookie statement
Mobile view













Toggle limited content width







