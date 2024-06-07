# Reference for threat actor for "Icefog, Dagger Panda"

**Title**: The Icefog APT Hits US Targets With Java Backdoor | Securelist

**Source**: https://securelist.com/the-icefog-apt-hits-us-targets-with-java-backdoor/58209/

## Content















The Icefog APT Hits US Targets With Java Backdoor | Securelist



































































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

The Icefog APT Hits US Targets With Java Backdoor 

APT reports

14 Jan 2014

  minute read								








 

Authors



 Vitaly Kamluk



 Igor Kuznetsov



 Costin Raiu





In September 2013, we published our extensive analysis of Icefog, an APT campaign that focused on the supply chain – targeting government institutions, military contractors, maritime and ship-building groups.
Icefog, also known as the “Dagger Panda” by Crowdstrike’s naming convention, infected targets mainly in South Korea and Japan. You can find our Icefog APT analysis and detailed report here.
Since the publication of our report, the Icefog attackers went completely dark, shutting down all known command-and-control servers. Nevertheless, we continued to monitor the operation by sinkholing domains and analysing victim connections. During this monitoring, we observed an interesting type of connection which seemed to indicate a Java version of Icefog, further to be referenced as “Javafog”.
Meet “Lingdona”
The Icefog operation has been operational since at least 2011, with many different variants released during this time. For Microsoft Windows PCs, we identified at least 6 different generations:

The “old” 2011 Icefog – sends stolen data by e-mail; this version was used against the Japanese House of Representatives and the House of Councillors in 2011.
Type “1” “normal” Icefog – interacts with command-and-control servers via a set of “.aspx” scripts.
Type “2” Icefog – interacts with a script-based proxy server that redirects commands from the attackers to another machine.
Type “3” Icefog – a variant that uses a certain type of C&C server with scripts named “view.asp” and “update.asp”
Type “4” Icefog – a variant that uses a certain type of C&C server with scripts named “upfile.asp”
Icefog-NG – communicates by direct TCP connection to port 5600

In addition to these, we also identified “Macfog”, a native Mac OS X implementation of Icefog that infected several hundred victims worldwide.
By correlating registration information for the different domains used by the malware samples, we were able to identify 72 different command-and-control servers, of which we managed to sinkhole 27.
One interesting domain in particular was “lingdona[dot]com”, which expired in September 2013 and we took over in October 2013. Here’s what the original contact information looked like:





Domain Name: LINGDONA.COM
Registrant Contact:
lin ming hua
lin ming kevistin@qq.com
telephone: +86.031185878412
fax: +86.031185878412
fuzhoushi Fuzhou Shi Fujian Sheng 412141
CN




12345678

Domain Name: LINGDONA.COMRegistrant Contact:lin ming hualin ming kevistin@qq.comtelephone: +86.031185878412fax: +86.031185878412fuzhoushi Fuzhou Shi Fujian Sheng 412141CN




The domain was originally hosted in Hong Kong, at IP 206.161.216.214 and 103.20.195.140, and appeared suspicious because of the registration data, which seemed to match other known Icefog domains. As soon as we sinkholed it, we observed a number of suspicious connections, almost every 10 seconds:





69.59.x.x www.lingdona.com - [26/Oct/2013:23:59:39 +0000] "POST /news/latestnews.aspx?title=2.0_1593925273 HTTP/1.1" 404 345 "-" "Java/1.7.0_25"
69.59.x.x www.lingdona.com - [26/Oct/2013:23:59:45 +0000] "POST /news/latestnews.aspx?title=2.0_1593925273 HTTP/1.1" 404 345 "-" "Java/1.7.0_25"
38.100.x.x www.lingdona.com - [26/Oct/2013:23:59:48 +0000] "GET /news/latestnews.aspx?title=1.1_1254592001 HTTP/1.1" 404 345 "-" "Java/1.7.0_40"
38.100.x.x www.lingdona.com - [26/Oct/2013:23:59:58 +0000] "GET /news/latestnews.aspx?title=1.1_1254592001 HTTP/1.1" 404 345 "-" "Java/1.7.0_40"




1234

69.59.x.x www.lingdona.com - [26/Oct/2013:23:59:39 +0000] "POST /news/latestnews.aspx?title=2.0_1593925273 HTTP/1.1" 404 345 "-" "Java/1.7.0_25"69.59.x.x www.lingdona.com - [26/Oct/2013:23:59:45 +0000] "POST /news/latestnews.aspx?title=2.0_1593925273 HTTP/1.1" 404 345 "-" "Java/1.7.0_25"38.100.x.x www.lingdona.com - [26/Oct/2013:23:59:48 +0000] "GET /news/latestnews.aspx?title=1.1_1254592001 HTTP/1.1" 404 345 "-" "Java/1.7.0_40"38.100.x.x www.lingdona.com - [26/Oct/2013:23:59:58 +0000] "GET /news/latestnews.aspx?title=1.1_1254592001 HTTP/1.1" 404 345 "-" "Java/1.7.0_40"




Interestingly, the User-Agent string indicated the client could be a Java application, however, this was unusual because all other Icefog variants used regular IE User-Agent strings.
 
Finding the sample
While we suspected there was a malware sample in the wild connecting to the domain “lingdona[dot]com”, we didn’t have a copy of that particular Icefog trojan.
Luck seemed to strike when we came by a JSUNPACK submission that appeared quite interesting.

In November 2012, someone submitted an interesting URL to the public JSUNPACK service which was hosted on the “sejonng[dot]org” server, a known Icefog domain. It also appeared to reference “starwars123[dot]net”, another known Icefog domain.
Most interestingly, the HTML page references a Java applet “policyapplet.jar” with a long hexadecimal string parameter named “jar”. Unfortunately, we were not able to recover the “policyapplet.jar” file, which was most likely a Java exploit. Decoding the hexadecimal string, we found another Java applet with the following information:





Size: 8697 bytes
MD5: d26af487534c1d575e747ff240ee6357




12

Size: 8697 bytesMD5: d26af487534c1d575e747ff240ee6357




Later, we discovered the extracted applet was also uploaded to a virus scanning service around the same time.
 
The Javafog
The “jar” applet caught our attention so we analysed to determine how it works.
The JAR format uses ZIP compression to store the data in compact form. The ZIP header uses timestamps to track when files were added to the archive. This helps understanding when the JAR file could have been created. Here is ZIP directory information from the applet:





Date Time Attr Size Compressed Name
---------- --- ------ ------ ------------
2012-10-30 16:47:50 ..... 129 115 META-INF/MANIFEST.MF
2012-10-30 16:47:50 ..... 259 206 META-INF/B8228E45.SF
2012-10-30 16:47:50 ..... 5365 3610 META-INF/B8228E45.RSA
2010-10-29 22:44:06 ..... 7726 4226 JavaTool.class




123456

Date Time Attr Size Compressed Name---------- --- ------ ------ ------------2012-10-30 16:47:50 ..... 129 115 META-INF/MANIFEST.MF2012-10-30 16:47:50 ..... 259 206 META-INF/B8228E45.SF2012-10-30 16:47:50 ..... 5365 3610 META-INF/B8228E45.RSA2010-10-29 22:44:06 ..... 7726 4226 JavaTool.class




This means that the JAR file was most likely created on 30th November 2012, while the main class JavaTool.class was compiled two years before that, on 29th November 2010.
Upon startup, it tries to register itself as a startup entry to achieve persistence. The module writes a registry value to ensure it is automatically started by Windows:





[HKEY_CURRENT_USERsoftwaremicrosoftwindowscurrentversionrun]
JavaUpdate=%TEMP%update.jar




12

[HKEY_CURRENT_USERsoftwaremicrosoftwindowscurrentversionrun]JavaUpdate=%TEMP%update.jar




It is worth noting that the module does not copy itself to that location. It is possible that the missing file “policyapplet.jar” contains the parts of the installation routine.

Next, it enters a loop where it keeps calling its main C&C function, with a delay of 1000ms. The main loop contacts the well known Icefog C&C server – “www.lingdona[dot]com/news” and interacts with it.

First of all, it sends the full system information profile, which the attackers can use to determine if the victim is “interesting” or has any real value. Here’s a PCAP of the conversation:

In the screenshot above, “title=2.0_1651809722” indicates a unique victim ID that is computed by hashing the hostname. This can be used by the operators to uniquely identify the victim and send commands to it.
As a reply to the uploaded system information, the backdoor expects an “order”, which can have different values:
Command Description:

upload_* – Upload a local file specified after the command to the C&C server by URL “%C&C server URL%/uploads/%file name%”. Uploaded data is encrypted with a simple XOR operation with key 0x99.
cmd_UpdateDomain – Migrate to a new C&C server URL specified after the command. The new URL is also written to the file “%TEMP%update.dat”
cmd_* – Execute the string specified after the command using “cmd.exe /c”. The results are uploaded to the C&C server by URL “%C&C server URL%/newsdetail.aspx?title=2.0_%host name%”.
Besides the above, the backdoor doesn’t do much else. It allows the attackers to control the infected system and download files from it. Simple, yet very effective.

 
Geography of victims
One might wonder what is the purpose of something like the Javafog backdoor. The truth is that even at the time of writing, detection for Javafog is extremely poor (3/47 on VirusTotal). Java malware is definitively not as popular as Windows PE malware, and can be harder to spot.
During the sinkholing operation for the “lingdona[dot]com” domain, we observed 8 IPs for three unique victims of Javafog, all of them in the United States. Interestingly, during the observation period, two of the victims updated the Java version from “Java/1.7.0_25” to “Java/1.7.0_45”.
Based on the IP address, one of the victims was identified as a very large American independent Oil and Gas corporation, with operations in many other countries.
As of today, all victims have been notified about the infections. Two of the victims have removed it already.
Conclusions
With Javafog, we are turning yet another page in the Icefog story by discovering another generation of backdoors used by the attackers.
In one particular case, we observed the attack commencing by exploiting a Microsoft Office vulnerability, followed by the attackers attempting to deploy and run Javafog, with a different C&C. We can assume that based on their experience, the attackers found the Java backdoor to be more stealthy and harder to notice, making it more attractive for long term operations. (Most Icefog operations being very short – the “hit and run” type).
The focus on the US targets associated with the only known Javafog C&C could indicate a US-specific operation run by the Icefog attackers; one that was planned to take longer than usual, such as, for instance, long term collection of intelligence on the target. This brings another dimensions to the Icefog gang’s operations, which appear to be more diverse than initially thought.






APT
Icefog
Java
Targeted attacks
Vulnerabilities and exploits



Authors



 Vitaly Kamluk



 Igor Kuznetsov



 Costin Raiu





The Icefog APT Hits US Targets With Java Backdoor 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







Wlliam Saqusaqu 


							Posted on							August 24, 2014. 12:07 am 



Thank you for the hard work in updating stakeholders
Reply 








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




 


In search of the Triangulation: triangle_check utility 






 


Operation Triangulation: iOS devices targeted with previously unknown malware 






 


Copy-paste heist or clipboard-injector attacks on cryptousers 






 


How to train your Ghidra 






 


TOP 10 unattributed APT mysteries 









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



























