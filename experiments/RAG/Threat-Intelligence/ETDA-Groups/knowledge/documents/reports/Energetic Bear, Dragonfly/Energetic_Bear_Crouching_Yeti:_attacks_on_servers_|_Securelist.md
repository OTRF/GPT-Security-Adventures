# Reference for threat actor for "Energetic Bear, Dragonfly"

**Title**: Energetic Bear/Crouching Yeti: attacks on servers | Securelist

**Source**: https://securelist.com/energetic-bear-crouching-yeti/85345/

## Content















Energetic Bear/Crouching Yeti: attacks on servers | Securelist



































































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

Energetic Bear/Crouching Yeti: attacks on servers 

APT reports

23 Apr 2018

  minute read								
















Table of Contents





Attack victimsWaterholeScanned resourcesToolset usedUtilitiesMalicious php filesModified sshdActivity of the attackers on compromised serversConclusionAppendix I – Indicators of CompromiseFilenames and PathsTools*PHP files:LogsPHP file hashesYara rulesAppendix II – Shell script to check a server for toolsShell script for DebianShell script for Centos 






 

Authors




Kaspersky ICS CERT





Energetic Bear/Crouching Yeti is a widely known APT group active since at least 2010. The group tends to attack different companies with a strong focus on the energy and industrial sectors. Companies attacked by Energetic Bear/Crouching Yeti are geographically distributed worldwide with a more obvious concentration in Europe and the US. In 2016-2017, the number of attacks on companies in Turkey increased significantly. 
The main tactics of the group include sending phishing emails with malicious documents and infecting various servers. The group uses some of the infected servers for auxiliary purposes – to host tools and logs. Others are deliberately infected to use them in waterhole attacks in order to reach the group’s main targets. 
Recent activity of the group against US organizations was discussed in a US-CERT advisory, which linked the actor to the Russian government, as well as an advisory by the UK National Cyber Security Centre. 
This report by Kaspersky Lab ICS CERT presents information on identified servers that have been infected and used by the group. The report also includes the findings of an analysis of several webservers compromised by the Energetic Bear group during 2016 and in early 2017.
Attack victims
The table below shows the distribution of compromised servers (based on the language of website content and/or the origins of the company renting the server at the time of compromise) by countries, attacked company types and the role of each server in the overall attack scheme. Victims of the threat actor’s attacks were not limited to industrial companies.
Table 1. Compromised servers



Country
Description
Role in the attack


Russia
Opposition political website
Waterhole


Real estate agency
Auxiliary (collecting user data in the waterhole attack)


Football club
Waterhole


Developer and integrator of secure automation systems and IS consultant
Waterhole


Developers of software and equipment
Auxiliary (collecting user data in the waterhole attack, tool hosting)


Investment website
Auxiliary (collecting user data in the waterhole attack)


Ukraine
Electric power sector company
Waterhole


Bank
Waterhole


UK
Aerospace company
Waterhole


Germany
Software developer and integrator
Waterhole


Unknown
Auxiliary (collecting user data in the waterhole attack)


Turkey
Oil and gas sector enterprise
Waterhole


Industrial group
Waterhole


Investment group
Waterhole


Greece
Server of a university
Auxiliary (collecting user data in the waterhole attack)


USA
Oil and gas sector enterprise
Waterhole


Unknown
Affiliate network site
Auxiliary (collecting user data in the waterhole attack)



Waterhole
All waterhole servers are infected following the same pattern: injecting a link into a web page or JS file with the following file scheme: file://IP/filename.png.

The link is used to initiate a request for an image, as a result of which the user connects to the remote server over the SMB protocol. In this attack type, the attackers’ goal is to extract the following data from the session:

user IP,
user name,
domain name,
NTLM hash of the user’s password.

It should be noted that the image requested using the link is not physically located on the remote server.
Scanned resources
Compromised servers are in some cases used to conduct attacks on other resources. In the process of analyzing infected servers, numerous websites and servers were identified that the attackers had scanned with various tools, such as nmap, dirsearch, sqlmap, etc. (tool descriptions are provided below).
Table 2. Resources that were scanned from one of the infected servers



Country
(based on the content)
Description


Russia
Non-profit organization


Sale of drugs


Travel/maps


Resources based on the Bump platform (platform for corporate social networks) – non-profit organization, social network for college/university alumni, communication platform for NGOs, etc.


Business – photographic studio


Industrial enterprise, construction company


Door manufacturing


Cryptocurrency exchange


Construction information and analysis portal


Personal website of a developer


Vainah Telecom IPs and Subnets (Chechen Republic)
Various Chechen resources (governmental organizations, universities, industrial enterprises, etc.)


Web server with numerous sites (alumni sites, sites of industrial and engineering companies, etc.)


Muslim dating site


Brazil
Water treatment


Turkey
Hotels


Embassy in Turkey


Software developer


Airport website


City council website


Cosmetics manufacturer


Religious website


Turktelekom subnet with a large number of sites


Telnet Telecom subnet with a large number of sites


Georgia
Personal website of a journalist


Kazakhstan
Unknown web server


Ukraine
Office supplies online store


Floral business


Image hosting service


Online course on sales


Dealer of farming equipment and spare parts


Ukrainian civil servant’s personal website


Online store of parts for household appliance repair


Timber sales, construction


Tennis club website


Online store for farmers


Online store of massage equipment


Online clothes store


Website development and promotion


Online air conditioner store


Switzerland
Analytical company


US
Web server with many domains


France
Web server with many domains


Vietnam
Unknown server


International
Flight tracker



The sites and servers on this list do not seem to have anything in common. Even though the scanned servers do not necessarily look like potential final victims, it is likely that the attackers scanned different resources to find a server that could be used to establish a foothold for hosting the attackers’ tools and, subsequently, to develop the attack.
Part of the sites scanned may have been of interest to the attackers as candidates for hosting waterhole resources.
In some cases, the domains scanned were hosted on the same server; sometimes the attackers went through the list of possible domains matching a given IP.
In most cases, multiple attempts to compromise a specific target were not identified – with the possible exception of sites on the Bump platform, flight tracker servers and servers of a Turkish hotel chain.
Curiously, the sites scanned included a web developer’s website, kashey.ru, and resources links to which were found on this site. These may have been links to resources developed by the site’s owner: www.esodedi.ru, www.i-stroy.ru, www.saledoor.ru
Toolset used
Utilities
Utilities found on compromised servers are open-source and publicly available on GitHub:

Nmap – an open-source utility for analyzing the network and verifying its security.
Dirsearch — a simple command-line tool for brute forcing (performing exhaustive searches of) directories and files on websites.
Sqlmap — an open-source penetration testing tool, which automates the process of identifying and exploiting SQL injection vulnerabilities and taking over database servers.
Sublist3r — a tool written in Python designed to enumerate website subdomains. The tool uses open-source intelligence (OSINT). Sublist3r supports many different search engines, such as Google, Yahoo, Bing, Baidu and Ask, as well as such services as Netcraft, Virustotal, ThreatCrowd, DNSdumpster and ReverseDNS. The tool helps penetration testers to collect information on the subdomains of the domain they are researching.
Wpscan — a WordPress vulnerability scanner that uses the blackbox principle, i.e., works without access to the source code. It can be used to scan remote WordPress sites in search of security issues.
Impacket — a toolset for working with various network protocols, which is required by SMBTrap.
SMBTrap — a tool for logging data received over the SMB protocol (user IP address, user name, domain name, password NTLM hash).
Commix — a vulnerability search and command injection and exploitation tool written in Python.
Subbrute – a subdomain enumeration tool available for Python and Windows that uses an open name resolver as a proxy and does not send traffic to the target DNS server.
PHPMailer – a mail sending tool.

In addition, a custom Python script named ftpChecker.py was found on one of the servers. The script was designed to check FTP hosts from an incoming list.
Malicious php files
The following malicious php files were found in different directories in the nginx folder and in a working directory created by the attackers on an infected web servers:



File name
Brief description
md5sum
Time of the latest file change (MSK)
Size, bytes


ini.php
wso shell+ mail
f3e3e25a822012023c6e81b206711865
2016-07-01 15:57:38
28786


mysql.php
wso shell+ mail
f3e3e25a822012023c6e81b206711865
2016-06-12 13:35:30
28786


opts.php
wso shell
c76470e85b7f3da46539b40e5c552712
2016-06-12 12:23:28
36623


error_log.php
wso shell
155385cc19e3092765bcfed034b82ccb
2016-06-12 10:59:39
36636


code29.php
web shell
1644af9b6424e8f58f39c7fa5e76de51
2016-06-12 11:10:40
10724


proxy87.php
web shell
1644af9b6424e8f58f39c7fa5e76de51
2016-06-12 14:31:13
10724


theme.php
wso shell
2292f5db385068e161ae277531b2e114
2017-05-16 17:33:02
133104


sma.php
PHPMailer
7ec514bbdc6dd8f606f803d39af8883f
2017-05-19 13:53:53
14696


media.php
wso shell
78c31eff38fdb72ea3b1800ea917940f
2017-04-17 15:58:41
1762986



In the table above:

Web shell is a script that allows remote administration of the machine.
WSO is a popular web shell and file manager (it stands for “Web Shell by Orb”) that has the ability to masquerade as an error page containing a hidden login form. It is available on GitHub:

https://github.com/phpFileManager/WSO
Two of the PHP scripts found, ini.php and mysql.php, contained a WSO shell concatenated with the following email spamming script:
https://github.com/bediger4000/php-malware-analysis/tree/master/db-config.php
All the scripts found are obfuscated.


One of the web shells was found on the server under two different names (proxy87.php and code29.php). It uses the eval function to execute a command sent via HTTP cookies or a POST request:


Modified sshd
A modified sshd with a preinstalled backdoor was found in the process of analyzing the server.
Patches with some versions of backdoors for sshd that are similar to the backdoor found are available on GitHub, for example:
https://github.com/jivoi/openssh-backdoor-kit
Compilation is possible on any OS with binary compatibility.
As a result of replacing the original sshd file with a modified one on the infected server, an attacker can use a ‘master password’ to get authorized on the remote server, while leaving minimal traces (compared to an ordinary user connecting via ssh).
In addition, the modified sshd logs all legitimate ssh connections (this does not apply to the connection that uses the ‘master password’), including connection times, account names and passwords. The log is encrypted and is located at /var/tmp/.pipe.sock.

Activity of the attackers on compromised servers
In addition to using compromised servers to scan numerous resources, other attacker activity was also identified.
After gaining access to the server, the attackers installed the tools they needed at different times. Specifically, the following commands for third-party installations were identified on one of the servers:

apt install traceroute
apt-get install nmap
apt-get install screen
git clone https://github.com/sqlmapproject/sqlmap.git

Additionally, the attackers installed any packages and tools for Python they needed.
The diagram below shows times of illegitimate logons to one of the compromised servers during one month. The attackers checked the smbtrap log file on working days. In most cases, they logged on to the server at roughly the same time of day, probably in the morning hours:

In addition, in the process of performing the analysis, an active process was identified that exploited SQL injection and collected data from a database of one of the victims.
Conclusion
The findings of the analysis of compromised servers and the attackers’ activity on these servers are as follows:

With rare exceptions, the group’s members get by with publicly available tools. The use of publicly available utilities by the group to conduct its attacks renders the task of attack attribution without any additional group ‘markers’ very difficult.
Potentially, any vulnerable server on the internet is of interest to the attackers when they want to establish a foothold in order to develop further attacks against target facilities.
In most cases that we have observed, the group performed tasks related to searching for vulnerabilities, gaining persistence on various hosts, and stealing authentication data.
The diversity of victims may indicate the diversity of the attackers’ interests.
It can be assumed with some degree of certainty that the group operates in the interests of or takes orders from customers that are external to it, performing initial data collection, the theft of authentication data and gaining persistence on resources that are suitable for the attack’s further development.

Appendix I – Indicators of Compromise
Filenames and Paths
Tools*
/usr/lib/libng/ftpChecker.py
/usr/bin/nmap/
/usr/lib/libng/dirsearch/
/usr/share/python2.7/dirsearch/
/usr/lib/libng/SMBTrap/
/usr/lib/libng/commix/
/usr/lib/libng/subbrute-master/
/usr/share/python2.7/sqlmap/
/usr/lib/libng/sqlmap-dev/
/usr/lib/libng/wpscan/
/usr/share/python2.7/wpscan/
/usr/share/python2.7/Sublist3r/
*Note that these tools can also be used by other threat actors.
PHP files:
/usr/share/python2.7/sma.php
/usr/share/python2.7/theme.php
/root/theme.php
/usr/lib/libng/media.php
Logs
/var/tmp/.pipe.sock
PHP file hashes
f3e3e25a822012023c6e81b206711865
c76470e85b7f3da46539b40e5c552712
155385cc19e3092765bcfed034b82ccb
1644af9b6424e8f58f39c7fa5e76de51
2292f5db385068e161ae277531b2e114
7ec514bbdc6dd8f606f803d39af8883f
78c31eff38fdb72ea3b1800ea917940f
Yara rules
rule Backdoored_ssh {
strings:
$a1 = “OpenSSH”
$a2 = “usage: ssh”
$a3 = “HISTFILE”
condition:
uint32(0) == 0x464c457f and filesize<1000000 and all of ($a*)
}
Appendix II – Shell script to check a server for tools
Shell script for Debian
cd /tmp
workdir=428c5fcf495396df04a459e317b70ca2
mkdir $workdir
cd $workdir
find / -type d -iname smbtrap > find-smbtrap.txt 2>/dev/null
find / -type d -iname dirsearch > find-dirsearch.txt 2>/dev/null
find / -type d -iname nmap > find-nmap.txt 2>/dev/null
find / -type d -iname wpscan > find-wpscan.txt 2>/dev/null
find / -type d -iname sublist3r > find-sublist3r.txt 2>/dev/null
dpkg -l | grep -E \(impacket\|pcapy\|nmap\) > dpkg-grep.txt
cp /var/lib/dpkg/info/openssh-server.md5sums . #retrieve initial hash for sshd
md5sum /usr/sbin/sshd > sshd.md5sum #calculate actual hash for sshd
Shell script for Centos
cd /tmp
workdir=428c5fcf495396df04a459e317b70ca2
mkdir $workdir
cd $workdir
find / -type d -iname smbtrap > find-smbtrap.txt 2>/dev/null
find / -type d -iname dirsearch > find-dirsearch.txt 2>/dev/null
find / -type d -iname nmap > find-nmap.txt 2>/dev/null
find / -type d -iname wpscan > find-wpscan.txt 2>/dev/null
find / -type d -iname sublist3r > find-sublist3r.txt 2>/dev/null
rpm -qa | grep -E \(impacket\|pcapy\|nmap\) > rpm-grep.txt
rpm -qa –dump | grep ssh > rpm-qa-dump.txt #retrieve initial hash for sshd
sha256sum /usr/sbin/sshd > sshd.sha256sum #calculate actual sha256 hash for sshd
md5sum /usr/sbin/sshd > sshd.md5sum #calculate actual md5 hash for sshd
 Energetic Bear/Crouching Yeti: attacks on servers






APT
Backdoor
Targeted attacks
Vulnerabilities and exploits
Watering hole attacks



Authors




Kaspersky ICS CERT





Energetic Bear/Crouching Yeti: attacks on servers 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 
















Table of Contents





Attack victimsWaterholeScanned resourcesToolset usedUtilitiesMalicious php filesModified sshdActivity of the attackers on compromised serversConclusionAppendix I – Indicators of CompromiseFilenames and PathsTools*PHP files:LogsPHP file hashesYara rulesAppendix II – Shell script to check a server for toolsShell script for DebianShell script for Centos 





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




 


Threat landscape for industrial automation systems. Statistics for H1 2023 






 


Threat landscape for industrial automation systems for H2 2022 






 


The secrets of Schneider Electric’s UMAS protocol 






 


Threat landscape for industrial automation systems for H1 2022 






 


Targeted attack on industrial enterprises and public institutions 









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



























