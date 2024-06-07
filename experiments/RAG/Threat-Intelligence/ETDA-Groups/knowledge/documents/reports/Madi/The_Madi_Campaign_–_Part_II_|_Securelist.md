# Reference for threat actor for "Madi"

**Title**: The Madi Campaign – Part II | Securelist

**Source**: https://securelist.com/the-madi-campaign-part-ii-53/33701/

## Content















The Madi Campaign – Part II | Securelist


































































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

The Madi Campaign – Part II 

APT reports

26 Jul 2012

  minute read								








 

Authors




GReAT





In our previous blogpost, we discussed the Madi campaign, uncovered through joint research with our partner Seculert (http://blog.seculert.com/2012/07/mahdi-cyberwar-savior.html).
In this blogpost, we will continue our analysis with information on the Madi infrastructure, communications, data collection, and victims.
The Madi infrastructure performs its surveillance operations and communications with a simple implementation as well. Five command and control (C2) web servers are currently up and running Microsoft IIS v7.0 web server along with exposed Microsoft Terminal service for RDP access, all maintaining identical copies of the custom, C# server manager software. These servers also act as the stolen data drops. The stolen data seems to be poorly organized on the server side, requiring multiple operators to log in and investigate the data per each of the compromised systems that they are managing over time.
The services at these IP addresses have been cycled through by the operators for unknown reasons. There does not appear to be a pattern to which malware reports to which server just yet. According to sinkhole data and other reliable sources, the approximate locations of Madi victims are distributed mainly within the Middle East, but some are scattered lightly throughout the US and EU. It seems that some of the victims are professionals and academia (both students and staff) running laptops infected with the Madi spyware, travelling throughout the world:

Here is an approximate global map representing the approximate location of Madi victims, dependent on GeoIP data. While the overwhelming percentage of Madi victims in the middle east is not best visualized in this graphic, it helps to understand the Madi reach:

Some related domains not under our sinkhole were quickly sinkholed by other security groups the day after our post. But the problem with the timing and approach by these newcomers is that the spyware and downloaders currently active do not “speak” with those domains, for the most part. Instead, they speak directly with the web servers running according to their hard-coded IP addresses, avoiding any DNS name resolution. To help with this process, the malware authors built update functionality into the downloaders. If they were switching their pool of infected systems to another domain or IP address, a Madi downloader or infostealer would communicate with its assigned C2 server and then retrieve the IP or domain of its new C2, store the new locator in a plain text file on the drive, and then switch over and begin communicating with the new C2. This approach also seems crude in comparison to other resilient cybercrime infrastructure.
When source IP addresses are examined from systems checking in to the C2 by hand and matched up with their ASN, the most activity is clearly coming from within Iran:
Iran 84%
Pakistan 6%
US 3%
IL 1%
UAE <1%
Saudi Arabia <1%
We distributed the largest collection of related samples so far to multiple vendors and incident response handlers. Only a couple of vendors have responded in kind with only a few binaries that are new to our collection. Accordingly, these numbers are the most accurate that research has to offer at this point, even as new Madi samples are uploaded to our backend services:

C2 locators hard-coded into Madi downloaders
A timeline of new activity can be scoped out for the group, with the greatest number of related downloaders created by the developers in December 2011, Feb and March of 2012, followed by June of 2012. Also, the oldest Madi trojan currently in the collection was created in Sept. 2011, most likely during the testing phase of the project. The domain that it reports to was created on August 10, 2011.

This information tends to make sense, as other researchers discussed privately that spear-phishing campaign volumes appeared to be heaviest in February 2012, but this information was collected from the targets outside of Iran. We don-t know about any sort of activity intensity timeline within Iran, although the trends above may help inform those questions.
We also know that the infostealers are a much smaller pool of code, and were released on a separate timeline. We have discovered five months in which the Madi infostealers were created, and the matching URL that they communicated with for instructions and to upload victim screenshots, keylogged data, stolen documents and contracts:

In addition to the information we presented here, our partner Seculert posted their own analysis of the Madi C2 infrastructure here: http://blog.seculert.com/2012/07/mahdi-numbers-and-flame-connection.html.
Note: On July 25, we received a new variant of Madi which connects to a new C2 server in Canada. We are still investigating it and the data from this post does not include this new C2 server.






Adobe
Adobe PDF
APT
Malware Statistics
Microsoft
Microsoft Windows
Targeted attacks



Authors




GReAT





The Madi Campaign – Part II 
 Your email address will not be published. Required fields are marked *Name * 
Email * 

  




Cancel 

Δ 





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




 


APT annual review: What the world’s threat actors got up to in 2020 






 


Cyberthreats to financial organizations in 2021 






 


Advanced Threat predictions for 2021 






 


Ghimob: a Tétrade threat actor moves to infect mobile devices 






 


APT trends report Q3 2020 









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



























