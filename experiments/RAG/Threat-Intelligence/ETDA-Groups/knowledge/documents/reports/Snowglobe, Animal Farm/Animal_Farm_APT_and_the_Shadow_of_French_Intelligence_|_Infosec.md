# Reference for threat actor for "Snowglobe, Animal Farm"

**Title**: Animal Farm APT and the Shadow of French Intelligence | Infosec

**Source**: https://resources.infosecinstitute.com/animal-farm-apt-and-the-shadow-of-france-intelligence/

## Content



















Animal Farm APT and the Shadow of French Intelligence | Infosec


















Boot camps & training


Awareness & anti-phishing


Community

























Topics















Certification Prep















Cyber Work















About us






























Back




Industry insights




Phishing




Hacking




Capture the flag (CTF)




Professional development




Security awareness




Penetration testing




Cyber ranges




General security




Management & compliance




Malware analysis




MITRE ATT&CK™




News




Application security




Digital forensics




View all











Back




(ISC)² CISSP




(ISC)² CCSP




(ISC)² CAP




Cisco CCNA




CMMC




CompTIA A+




CompTIA Network+




CompTIA Security+




CompTIA CySA+




CompTIA PenTest+




CompTIA CASP+




EC-Council CEH




ISACA CDPSE




ISACA CGEIT




ISACA CISA




ISACA CISM




ISACA CRISC




Microsoft Azure




PMP




View all











Back




Cyber Work Podcast




Cyber Work Live











Back




Contact us




Contributors














Topics


Threat Intelligence


Animal Farm APT and the Shadow of French Intelligence









Threat Intelligence
Animal Farm APT and the Shadow of French Intelligence





July 8, 2015 by
Pierluigi Paganini


Babacar and Casper
Almost every government is working to improve its cyber-capabilities. The majority of them already have in their arsenal powerful espionage malware and hacking platforms. We read about the techniques and tactics implemented by a number of APT groups from China, Russia, Iran and belonging to the Five Eyes (US, UK, Australia, New Zealand, Canada) Intelligence Agencies.
Early in 2015, security researchers detected a new strain of malware, dubbed Babar, that they consider as a malicious code developed by French intelligence. According to the experts, Babar malware was used by the General Directorate for External Security (DGSE), which is the France's external intelligence agency, for surveillance and cyber espionage purposes.




 



The spyware is also dubbed Snowglobe by the Canadian Intelligence agency CSEC, it was spyware designed to collect victims' e-mails.
The General Directorate for External Security is controlled by the French ministry of Defense. It is in charge of intelligence activities for the national security. The Casper malware was discovered by Canadian malware researchers that linked it to the French Intelligence.
Babar is considered by the experts powerful spyware that is capable of eavesdropping on online conversations held via popular messaging platforms, including Skype, MSN and Yahoo messenger, as well as logging keystrokes and monitoring the activity of the victim on the Internet.
Security experts have collected evidence of the use of Babar to spy on several Iranian organizations, including nuclear research institutes and universities. Babar was also used by threat actors to spy on European financial institutions. The name Babar first appeared in one of the documents leaked by the NSA whistleblower Edward Snowden, the slides were made by the Canadian intelligence agency and linked Babar to the French Government.

Figure 1 - CSEC slides leaked by Snowden
The documents confirm the presence of the France's intelligence services behind an e-mail spying campaign started in November 2009 that was aimed at Iran's nuclear program. According to the French newspaper Le Monde, the hackers hit many other targets, including a Canadian media outlet.
 "Canadian secret service suspect indeed their French counterparts of being behind a vast computer piracy operation, which would have begun in 2009 and still continue thanks to a spy implant," states Le Monde.

Figure 2 -Canadian -Intelligence - Operation Snowglobe
The presentation concludes with the revelation that CSEC agency has also detected a more sophisticated version of the Babar agent, dubbed Snowman, which is under analysis.
The slides were prepared in 2011 and shared among the Intelligence agencies belonging to the Five Eyes.
Snowglobe was detected in operation against targets in Canada, Spain, Greece, Norway, Ivory Coast and Algeria, but the main target appeared to be in Iran. The hackers were focusing on the country's foreign ministry, the Atomic Energy Organization of Iran, the Iran University of Science and Technology and two Tehran schools heavily involved in nuclear research, Malek-E-Ashtar University of Technology and Imam Hussein University.
The authors of the slides speculate that the French intelligence targeted Greece because it is "possibly associated with [the] European Financial Association," and also Algeria and Ivory Coast because they are former French colonies.
"The memo outlines circumstantial evidence that led CSEC to conclude that Snowglobe was a French intelligence operation." Continues LeMonde.
The researcher at CSEC are skeptical of possible financial motivation of the attackers, the exclude cyber-crime rings as the responsible of the campaign. Analysts noted that the malware author left his username amid the computer coding: "Titi," a French diminutive or "colloquial term for a small person."
On March 2015, malware researchers spotted a new strain of malware, dubbed Casper, which is spyware designed to track Internet users for surveillance purpose. The malware was hosted on a compromised website belonging to the Syrian Government (at http://jpic.gov.sy/) it was a complex agent able to exploit two zero-day flaws to infect victims.
Both the exploits were hosted on a Syrian website, launched in 2011 by the Syrian Ministry of Justice that was designed as an online platform for citizens to complain about law and order violations. Experts believe it was designed to target Syrian dissidents complaining about the government. The site was hacked in September 2013 by a group using the twitter account @olivertuckedout that raised the reaction of the hacking group known as the Syrian Electronic Army. 

Figure 4 - olivertuckedout announced the hack of the Syrian Server

Figure 5 - SEA replied @olivertuckedout
"In mid-April we detected two new SWF exploits. After some detailed analysis it was clear they didn't use any of the vulnerabilities that we already knew about. We sent the exploits off to Adobe and a few days later got confirmation that they did indeed use a 0-day vulnerability that was later labeled as CVE-2014-0515. The vulnerability is located in the Pixel Bender component, designed for video and image processing." reported an analysis published by Kaspersky Lab.
The experts at Kaspersky noticed that both exploits were professionally designed, but while one of them is standard and can infect practically any vulnerable computer, the second exploit (include.swf) only works on computers where Adobe Flash Player 10 ActiveX and Cisco MeetingPlace Express Add-In are installed. The authors used the Flash Player Pixel Bender component, which Adobe no longer supports, as the attack vector and remain active for longer. This means that threat actors were running surgical espionage campaigns.
Casper malware was used by threat actors in the wild to target systems, spy on them, and drop other advanced persistent malware.
"According to the report, which Motherboard reviewed in advance, Casper was hosted on a hacked Syrian government website in April of last year. The incident caught the attention of some security researchers because the attackers used two zero-day vulnerabilities to infect victims" states a blog post published by the Motherboard news portal.
The report published by Motherboard confirms that the Casper malware was designed by a French APT group, likely a state-sponsored hacking crew.
Casper was used to run several espionage campaigns over the last few years and its authors had access to two zero-day exploits that were used in a sample detected by malware researchers in April 2014.
Casper is not common malware; security researchers speculate it requested a significant effort for its development in term of resource and financial investment, a prerogative of Government-built malware.
Babar, Casper, and Evil Bunny have the same root
Malware specialists have discovered several similarities between the source code of Casper and Babar, the researchers speculate that they were "likely" developed by the same team of coders. The experts discovered much more, both agents appear as the product of a common hacking platform developed by French Intelligence that was used to distribute other malicious code, including the Evil Bunny. In December 2014, the security firm Cyphort Labs firm detected another sophisticated malware dubbed EvilBunny that implements a very complex evasion technique.
To establish that the same development team has worked on Bunny, Babar, and Casper the experts focused the analysis on the identification of unusual stubs of code or algorithms implemented by all the malware in the arsenal of the Animal Farm APT.
EvilBunny is written in C++ and is able to detect installed antivirus and other defensive solutions. It includes a Lua 5.1 interpreter, which allows the spyware to execute Lua scripts and change its behavior at runtime.
The experts discovered that EvilBunny is able to receive commands from the C&C server at least in three different ways, via HTTP, through a downloaded database file or as a scheduled task.
The EvilBunny malware was initially delivered through a malicious PDF document, exploiting CVE-2011-4369. Once compromised the target the malware is loaded onto the system and infects the PC with EvilBunny malware.
"The malware is dubbed 'EvilBunny' and is designed to be an execution platform for Lua scripts injected by the attacker." According to the new report written by Joan Calvet, a malware researcher at anti-virus maker ESET, the EvilBunny together with other hacking tools, like the NBOT tool, suggested ties to the French Intelligence.

Figure 6 - Comparison between NBOT code and Caper code
"We have reasons to believe that French intelligence has been using—or is even still using—at least four different malware families," Marion Marschalek, another researcher who worked with Calvet and Paul Rascagneres in investigating the malware, told Motherboard.
The Animal Farm is a very prolific malware factory; Casper is just the latest tool in order of time belonging to the arsenal of the Animal Farm group. Security researchers believe Casper has been active since at least 2009 or 2010.
"Other security researchers agree that Casper, perhaps named after the famous cartoon "friendly ghost," was likely created by the French government and its spying agency the General Directorate for External Security (DGSE). They refer to the hacking group as the "Animal Farm" because of each malware's animal-like and cartoon-inspired names." continues the Motherboard.
Experts at ESET firm collected the following evidence that suggests the involvement of the same development team for the malware used by the Animal Farm group:


Casper hides its calls to API functions by using a hash calculated from the functions' names, rather than the names themselves, a technique implemented by other malware on the Animal Farm, including NBOT and Babar.


Casper, Bunny, Babar, and NBOT gather information about the running antivirus solution in a similar way. The computer the SHA-256 hash of the first word of the antivirus name.


Casper generates delimiters for its HTTP requests by filling a specific format string with the results of calls to the GetTickCount API function. The same code is present in some NBOT samples.


Costin Raiu, the director of the Global Research and Analysis Team at Kaspersky Labs, confirmed that his company has been tracking the Animal Farm since 2013, the popular expert has no doubts about the involvement of a government for the development of the malicious code used by the APT group.
"When you have such a large-scale operation going on for several years using multiple zero-days without any kind of financial outcome,"Raiu told Motherboard, "it's obvious that it's a nation-state sponsored—it has to be."
France's Defense Ministry did not respond to Motherboard's requests for comment.
Another character from the cartoons … this time it's Dino Malware
Security experts at ESET have recently discovered a new sophisticated malware dubbed Dino that experts believe linked to the arsenal of the Animal Farm ATP group.
The researcher that discovered and analyzed Dino, the new strain of malware used by the so-called "Animal Farm", explained that it was detected for the first time in March 2014 when French media released a new collection of Snowden's slides describing a campaign dubbed "Operation Snowglobe."
Several security firms, including ESET, Cyphort and G DATA, have analyzed in details the malware belonging the Animal Farm APT. Below a list of the reports they published:


Casper, a stealthy first-stage implant, documented by ESET in last March


Bunny, a Lua-based backdoor, documented by Marion Marschalek (Cyphort)


Babar, an espionage platform, also analyzed by Marion Marschalek


The arsenal of the Animal Farm includes Babar, EvilBunny, and Casper, but the list is long and NBot, Tafacalou (TFC / Transporter) and Dino are other malicious code used by the APT.
ESET published a detailed analysis of the Dino malware, the ESET researcher Joan Calvet has detected a single sample of Dino in the wild that was used in an attempt to infect a target in Iran in 2013.
"Dino is so hard to find because the group behind the Animal Farm is really good at targeting people precisely, and we basically miss a lot of their samples," Calvet told
Dino is a modular malware, a number of components allow it to carry out several tasks, the agent is able to execute commands sent by C2C servers and Windows batch commands.
The malware is also able to search for specific files, upload files to the command and control (C&C) server, and download further files from the control architecture. The experts noticed that Dino can also schedule commands to be executed at a specified time, it is also able to kill processes and uninstall the malicious code from the infected system to avoid leave traces of its presence.
Experts at Kaspersky explained that the Tafacalou malware is used by the Animal Farm APT to serve further sophisticated spyware like Babar and Dino.
The researchers discovered several similarities between the code of the Dino malware and other threats from the Animal Farm malware families. The experts highlighted that the developers of these malware families are French speakers.
The amount of shared code between Dino and the other Animal Farm malware is significant and leaves no doubt that Dino belongs to Animal Farm's arsenal. Below the list of shared features provided by the experts at ESET:


At the very beginning of Dino execution, the current process name is checked against process names used by some sandboxes, the feature allows it to avoid the execution in testing environments.



Figure 7 - Dino checks to avoid execution in virtualized environments.


The call to API functions is hidden with the same hashing mechanisms implemented by other malware on the Animal Farm APT. The hash is calculated from the function's name and used to look for the address of the API function.


The Dino's custom file system – the so-called ramFS – is present in several droppers used by Animal Farm.


The output of Dino's sysinfo command looks like an updated version of the "beacon" from the SNOWBALL implant described in the leaked CSE slides – part of operation SNOWGLOBE, which led to the discovery of Babar:


"Dino's binary contains a resource whose language code value is 1036. The original purpose of this language code is to allow developers to provide resources (menus, icons, version information…) fordifferent locations in the world in the corresponding language. Interestingly, when a developer does not manually specify the language code, the compiler sets it to the language of the developer's machine. So, which language corresponds to the value 1036, or 0x40c in hexadecimal? French (France)." states the report published by the ESET.
Another anomaly discovered by researchers is the presence in the file path of the word "arithmetique," which is French for "arithmetic."arithmetique," which is French for "arithmetic."
Experts at ESET explained that the Dino malware, differently for other codes used by the Animal Farm APT, doesn't implement sophisticated anti-analysis techniques.
Conclusion
The information presented in this post reviews the findings of the reports prepared by the principal security firms that confirm the existence of a state-sponsored hacking group behind the Animal Farm APT.
All the malicious codes share a large amount of code and appear developed by the same pool of experts. The malware is very sophisticated and their development requested for sure a significant effort. The analysis of Babar in the documents prepared by the Canadian CSEC indicates that the group is active at least since 2009, and the availability of zero-day exploits is another element that led the experts to consider the Anima Farm a Government-backed actor.
In the following table explains the principal malware that security experts linked to the group of Animal Farm.








Malware
Function
Further info

Casper
Stealthy first-stage implant
Casper was used against Syrian targets in April 2014, which makes it the most recent malware from this group publicly known at this time. Casper has been active since at least 2009 or 2010.

Evil Bunny
Backdoor
The malware is written in C++, multi-threaded, aims to detect installed anti-virus- and firewall solutions and accepts a vast number of different control commands.

Babar
Spyware that infects Windows desktop machines and exfiltrates data, including instant messenger conversations, browsers, and office application data.
The security firm Cyphort Labs firm detected it in December 2014. It implements a very complex evasion technique.

NBot
Backdoor


Dino
Spyware
Dino is a modular malware, researchers discovered a number of components that allows it to carry out several tasks.

Tafacalou
Backdoor
Malware used in a first stage of attack that was used to load further malware including the Evil Bunny.

Is the France intelligence behind Animal Farm?
It's difficult to confirm it, despite the malware share the same features, the attribution is not simple, despite many experts speculate in the involvement of the France Intelligence.
References
http://securityaffairs.co/wordpress/34462/intelligence/babar-casper-french-intelligence.html
http://securityaffairs.co/wordpress/38204/cyber-crime/dino-malware-animal-farm.html
http://motherboard.vice.com/read/meet-casper-yet-another-malware-likely-created-by-france-for-surveillance
http://www.cyphort.com/evilbunny-malware-instrumented-lua/
http://www.cyphort.com/babar-suspected-nation-state-spyware-spotlight/
http://www.theglobeandmail.com/news/national/french-spy-software-targeted-canada-report/article17608109/
http://www.welivesecurity.com/2015/03/05/casper-malware-babar-bunny-another-espionage-cartoon/
http://www.lemonde.fr/international/article/2014/03/21/la-france-suspectee-de-cyberattaque_4387232_3210.html
http://www.welivesecurity.com/2015/06/30/dino-spying-malware-analyzed/




 



http://www.welivesecurity.com/2015/03/05/casper-malware-babar-bunny-another-espionage-cartoon/


Posted: July 8, 2015






Pierluigi Paganini

View Profile





Pierluigi is member of the ENISA (European Union Agency for Network and Information Security) Threat Landscape Stakeholder Group, member of Cyber G7 Workgroup of the Italian Ministry of Foreign Affairs and International Cooperation, Professor and Director of the Master in Cyber Security at the Link Campus University. He is also a Security Evangelist, Security Analyst and Freelance Writer. 
Editor-in-Chief at "Cyber Defense Magazine", Pierluigi is a cyber security expert with over 20 years experience in the field, he is Certified Ethical Hacker at EC Council in London. The passion for writing and a strong belief that security is founded on sharing and awareness led Pierluigi to find the security blog "Security Affairs" recently named a Top National Security Resource for US.
Pierluigi is a member of the "The Hacker News" team and he is a writer for some major publications in the field such as Cyber War Zone, ICTTF, Infosec Island, Infosec Institute, The Hacker News Magazine and for many other Security magazines.












 




In this Series



Animal Farm APT and the Shadow of French Intelligence


Dark Web hacking tools: Phishing kits, exploits, DDoS for hire and more


Dependency confusion: Compromising the supply chain


BendyBear: A shellcode attack used for cyberespionage


ATP group MontysThree uses MT3 toolset in industrial cyberespionage


BlackBerry exposes threat actor group BAHAMUT: Cyberespionage, phishing and other APTs


Top 9 cybercrime tactics, techniques and trends in 2020: A recap


KashmirBlack botnet targets WordPress, Joomla and other popular CMS platforms


BAHAMUT: Uncovering a massive hack-for-hire cyberespionage group


Linux security and APTs: Identifying threats and reducing risk


Top 6 ransomware strains to watch out for in 2020


2020 Verizon data breach investigations report: Summary and key findings for security professionals


How hackers use CAPTCHA to evade automated detection


The State of Ransomware 2020: Key findings from Sophos & Malwarebytes


Dark web fraud: How-to guides make cybercrime too easy


Top 6 malware strains to watch out for in 2020


Top Cybersecurity Predictions for 2020


Malware spotlight: What is click fraud?


What does dark web monitoring really do?


ThreatMetrix Cybercrime Report: An interview


Are dark web monitoring services worth it?


Cybercrime and the underground market [Updated 2019]


Verizon DBIR 2019 analysis


Common causes of large breaches (Q1 2019)


The Magecart Cybercrime Group Is Threatening E-Commerce Websites Worldwide


Russian Cyberspies Target 2018 U.S. Midterm Elections


The Increasing Threat of Banking Trojans and Cryptojacking


Leaders’ Meetings: A Privileged Target for Hackers


Fraud as a Service (FaaS): Everything You Need to Know


All about SamSam Ransomware


The Decline of Ransomware and the Rise of Cryptocurrency Mining Malware


Mechanics Behind Ransomware-as-a-Service


The Art of Fileless Malware


ZLAB MALWARE ANALYSIS REPORT: RANSOMWARE-AS-A-SERVICE PLATFORMS


Which Are the Most Exploited Flaws by Cybercriminal Organizations?


5 New Threats Every Organization Should be Prepared for in 2018


Memcrashed: The Dangerous Trend Behind the Biggest DDoS Attack Ever


Open source threat intelligence tools & techniques


Global Cost of Cybercrime on the Rise


An Enterprise Guide to Using Threat Intelligence for Cyber Defense


The Five Largest Ransomware Attacks of 2017


Intellectual Property Crimes in the Dark Web


Top 5 Smartest Malware Programs


Is Russian Intelligence Using Tainted Software to Access Corporate and Government Networks?


Vault 7 Leaks: Inside the CIA's Secret Kingdom (July-August 07)


DragonFly 2.0: The Alleged Nation-State Actor Hits the Energy Sector Again


Russian APT Groups Continue Their Stealthy Operations


Massive Petya Attack: Cybercrime or Information Warfare?


SAP SECURITY FOR CISO: SAP Attacks and Incidents


Role of Threat Intelligence in Business World


WikiLeaks Vault 7 Data Leak: Another Earthquake in the Intelligence Community





Related Bootcamps



ISACA CISA Training Boot Camp


(ISC)² CISSP® Training Boot Camp


Incident Response & Network Forensics Training Boot Camp


CompTIA Security+ Training Boot Camp








 



Get certified and advance your career


Exam Pass Guarantee
Live instruction
CompTIA, ISACA, (ISC)², Cisco, Microsoft and more!





                        View Certifications
                    


 



















Threat Intelligence

Dark Web hacking tools: Phishing kits, exploits, DDoS for hire and more












August 03, 2021
Dan Virgillito




















Threat Intelligence

Dependency confusion: Compromising the supply chain












June 03, 2021
Pedro Tavares




















Threat Intelligence

BendyBear: A shellcode attack used for cyberespionage












June 02, 2021
Pedro Tavares




















Threat Intelligence

ATP group MontysThree uses MT3 toolset in industrial cyberespionage












March 18, 2021
Greg Belding





 






































Topics



Hacking




Penetration testing




Cyber ranges




Capture the flag




Malware analysis




Professional development




General security




News




Security awareness




Phishing




Management, compliance & auditing




Digital forensics




Threat intelligence




DoD 8570



View all topics

Certifications



CISSP




CCSP




CGEIT




CEH




CCNA




CISA




CISM




CRISC




A+




Network+




Security+




CASP+




PMP




CySA+




CMMC




Microsoft Azure



View all certifications

Careers



IT auditor




Cybersecurity architect




Cybercrime investigator




Penetration tester




Cybersecurity consultant




Cybersecurity analyst




Cybersecurity engineer




Cybersecurity manager




Incident responder




Information security auditor




Information security manager



View all careers

Company



Contact us




About us




Work at Infosec




Newsroom




Partner program







Infosec, part of Cengage Group — ©2023 Infosec Institute, Inc.




Trademarks


Privacy















