# Reference for threat actor for "GCMAN"

**Title**: APT-style bank robberies increase with Metel, GCMAN and Carbanak 2.0 attacks | Securelist

**Source**: https://securelist.com/apt-style-bank-robberies-increase-with-metel-gcman-and-carbanak-2-0-attacks/73638/

## Content















APT-style bank robberies increase with Metel, GCMAN and Carbanak 2.0 attacks | Securelist


































































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

APT-style bank robberies increase with Metel, GCMAN and Carbanak 2.0 attacks 

APT reports

08 Feb 2016

  minute read								








 

Authors




GReAT




Computer Incidents Investigation Department






Introduction
In late 2014, Kaspersky Lab researchers made a worrying prediction: financially-motivated cyber-criminals would adopt sophisticated tactics and techniques from APT groups for use in bank robberies.
Just a few months later, in February 2015, we announced the discovery of Carbanak, a cyber-criminal gang that used custom malware and APT techniques to steal millions of dollars while infecting hundreds of financial institutions in at least 30 countries.
Since then, we have seen an increase in these covert, APT-style attacks that combine the use of reconnaissance, social engineering, specialized malware, lateral movement tools and long-term persistence to steal money from financial institutions (particularly ATMs and money transfer systems).
In summer 2015, a #bank in #Russia lost millions of rubles in a one night #bankingAPT #TheSAS2016Tweet
Today at the Security Analyst Summit (SAS 2016), Kaspersky Lab is announcing the discovery of two new gangs engaged in APT-style bank robberies – Metel and GCMAN – and the reemergence of the Carbanak group with new targets in its sights.
In 2015, Kaspersky Lab researchers conducted Incident Response for 29 organizations located in Russia and infected by these three groups.
Due to the active nature of law enforcement investigations and non-disclosure agreements with victim organizations, Kaspersky Lab cannot provide extensive details of the attacks. Kaspersky Lab is releasing crucial Indicators of Compromise (IOCs) and other data to help organizations search for traces of these attack groups in their corporate networks (see below).
The story of Metel – ATM balance rollbacks
In summer 2015, a bank in Russia discovered it had lost millions of rubles in a single night through a series of strange financial transactions. The bank’s clients were making withdrawals from ATMs belonging to other banks and were able to cash out huge sums of money while their balances remained untouched. The victim bank didn’t realize this until it tried to recoup the money withdrawn from the other banks’ ATMs.
During our incident response, we discovered the solution to this puzzle: Metel, a modular malware program also known as Corkow.
The malware, used exclusively by the Metel group, infected the bank’s corporate network via e-mail and moved laterally to gain access to the computers within the bank’s IT systems.
Having gained access to the bank operator’s money-processing system, the gang pulled off a clever trick by automating the rollback of ATM transactions. This meant that money could be stolen from ATM machines via debit cards while the balance on the cards remained the same, allowing for multiple transactions at different ATM machines.

Encrypted configuration for Metel malware plugins

Our investigations revealed that the attackers drove around several cities in Russia, stealing money from ATMs belonging to different banks. With the automated rollback in place the money was instantly returned to the account after the cash had been dispensed from the ATM. The group worked exclusively at night, emptying ATM cassettes at several locations.
GCMAN group planted cron script into #bank server, stealing $200/min #bankingAPT #TheSAS2016Tweet
In all, we discovered Metel in more than 30 financial institutions, but Kaspersky Lab’s incident responders were able to clean the networks before any major damage could be done. It is highly likely that this threat is far more widespread and we urge financial institutions around the world to scan their networks for signs of the Metel malware.
The Metel criminal group is still active. At the moment, we don’t have any information about any victims outside Russia.

GCMAN – penetration testing tools gone bad
A second group, which we call GCMAN because the malware is based on code compiled on the GCC compiler, emerged recently using similar techniques to the Metel Group to infect banking institutions and attempt to transfer money to e-currency services.
The initial infection mechanism is handled by spear-phishing financial institution targets with e-mails carrying a malicious RAR archive to. Upon opening the RAR archive, an executable is started instead of a Microsoft Word document, resulting in infection.

Once inside the network, the GCMAN group uses legitimate and penetration testing tools such as Putty, VNC, and Meterpreter for lateral movement. Our investigation revealed an attack where the group then planted a cron script into bank’s server, sending financial transactions at the rate of $200 per minute. A time-based scheduler was invoking the script every minute to post new transactions directly to upstream payment processing system. This allowed the group to transfer money to multiple e-currency services without these transactions being reported to any system inside the bank.

Decompiled code of GCMAN malware that is responsible for connecting to CnC
In a stroke of luck, the financial institutions discovered the suspicious activity on their network in time to neutralize the threat and cancel the transactions.
One interesting observation is that the real attack happened approximately 18 months before it was discovered. The group used an MS SQL injection in commercial software running on one of bank’s public web services, and about a year and a half later, they came back to cash out. During that time they poked 70 internal hosts, compromised 56 accounts, making their way from 139 attack sources (TOR and compromised home routers).
We discovered that about two months before the incident someone was trying different passwords for an admin account on a banking server. They were really persistent but doing it only three times a week and then only on Saturdays, in an effort to stay under the radar.
Kaspersky Lab’s research team responded to three financial institutions in Russia that were infected with the GCMAN malware. It is likely that this threat is far more widespread and we urge banks to sweep their networks for signs of this cyber-criminal group.
Carbanak 2.0: new targets beyond banks
After our exposure of the Carbanak group exactly a year ago, the group disappeared for about five months, leading us to believe that the operation was disbanded. However, in September last year, our friends at CSIS published a blog detailing a new Carbanak variant affecting one of its customers.
In December 2015, we confirmed that the group was still active. Kaspersky Lab discovered signs of Carbanak in two institutions – a telecommunications company and a financial institution.

Executable files founded in SHIM during Carbanak incident response
One interesting characteristic of Carbanak 2.0 is a different victim profile. The group has moved beyond banks and is now targeting the budgeting and accounting departments in any organization of interest to them, using the same APT-style tools and techniques.

In one remarkable case, the Carbanak 2.0 gang used its access to a financial institution that stores information about shareholders to change the ownership details of a large company. The information was modified to name a money mule as a shareholder of the company, displaying their IDs. It’s unclear how they wanted to make use of this information in future.
#Carbanak gang is now targeting budgeting & accounting departments #bankingAPT #TheSAS2016Tweet
Kaspersky Lab products successfully detect and block the malware used by the Carbanak 2.0, Metel and GCMAN threat actors with the following detection names:

Trojan-Dropper.Win32.Metel
Backdoor.Win32.Metel
Trojan-Banker.Win32.Metel
Backdoor.Win32.GCMan
Backdoor.Win64.GCMan
Trojan-Downloader.Win32.GCMan
Trojan-Downloader.Win32.Carbanak
Backdoor.Win32.Carbanak

Kaspersky Lab urges all organizations to carefully scan their networks for the presence of Carbanak, Metel and GCMAN and, if detected, to disinfect their systems/computers/networks and report the intrusion to law enforcement.
All this information has been made available to customers of our APT intelligence reporting service and they received the indicators of compromise and context information as soon as they became available.
Indicators of Compromise (IOC) are available here:
Metel
GCMAN
Carbanak 2.0
For more about the measures to be taken against these Bank Busters and similar offensives, read this article in the Kaspersky Business Blog.







APT
ATM attacks
Cybercrime
TheSAS2016
Trojan Banker



Authors




GReAT




Computer Incidents Investigation Department





APT-style bank robberies increase with Metel, GCMAN and Carbanak 2.0 attacks 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 







kevin_borys 


							Posted on							February 10, 2016. 10:04 am 



surprising and interesting technique of atm ..
This is stealing thieves!
Reply 








Gerald Steck 


							Posted on							April 11, 2016. 8:28 pm 



What can I do if I have knowledge of Carbanak attack in which I was hacked along with a 170,000.00 bank account by this group via iPhone, OnStar.
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



























