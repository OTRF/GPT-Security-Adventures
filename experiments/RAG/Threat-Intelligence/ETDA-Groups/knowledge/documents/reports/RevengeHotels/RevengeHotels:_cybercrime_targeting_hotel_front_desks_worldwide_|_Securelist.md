# Reference for threat actor for "RevengeHotels"

**Title**: RevengeHotels: cybercrime targeting hotel front desks worldwide | Securelist

**Source**: https://securelist.com/revengehotels/95229/

## Content















RevengeHotels: cybercrime targeting hotel front desks worldwide | Securelist




































































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

RevengeHotels: cybercrime targeting hotel front desks worldwide 

APT reports

28 Nov 2019

  minute read								








 

Authors




GReAT





RevengeHotels is a targeted cybercrime malware campaign against hotels, hostels, hospitality and tourism companies, mainly, but not exclusively, located in Brazil. We have confirmed more than 20 hotels that are victims of the group, located in eight states in Brazil, but also in other countries such as Argentina, Bolivia, Chile, Costa Rica, France, Italy, Mexico, Portugal, Spain, Thailand and Turkey. The goal of the campaign is to capture credit card data from guests and travelers stored in hotel systems, as well as credit card data received from popular online travel agencies (OTAs) such as Booking.com.
The main attack vector is via email with crafted Word, Excel or PDF documents attached. Some of them exploit CVE-2017-0199, loading it using VBS and PowerShell scripts and then installing customized versions of RevengeRAT, NjRAT, NanoCoreRAT, 888 RAT and other custom malware such as ProCC in the victim’s machine. The group has been active since 2015, but increased its attacks in 2019.
In our research, we were also able to track two groups targeting the hospitality sector, using separate but similar infrastructure, tools and techniques. PaloAlto has already written about one of them. We named the first group RevengeHotels, and the second ProCC. These groups use a lot of social engineering in their attacks, asking for a quote from what appears to be a government entity or private company wanting to make a reservation for a large number of people. Their infrastructure also relies on the use of dynamic DNS services pointing to commercial hosting and self-hosted servers. They also sell credentials from the affected systems, allowing other cybercriminals to have remote access to hotel front desks infected by the campaign.
We monitored the activities of these groups and the new malware they are creating for over a year. With a high degree of confidence, we can confirm that at least two distinct groups are focused on attacking this sector; there is also a third group, though it is unclear if its focus is solely on this sector or if carries out other types of attacks.
Not the quotation you’re expecting
One of the tactics used in operations by these groups is highly targeted spear-phishing messages. They register typo-squatting domains, impersonating legitimate companies. The emails are well written, with an abundance of detail. They explain why the company has chosen to book that particular hotel. By checking the sender information, it’s possible to determine whether the company actually exists. However, there is a small difference between the domain used to send the email and the real one.
An email sent to a hotel supposedly from an attorney’s office
This spear-phishing message, written in Portuguese, has a malicious file attached misusing the name of a real attorney office, while the domain sender of the message was registered one day before, using a typo-squatting domain. The group goes further in its social engineering effort: to convince the hotel personnel about the legitimacy of their request, a copy of the National Registry of Legal Entities card (CNPJ) is attached to the quotation.
The attached file, Reserva Advogados Associados.docx (Attorneys Associates Reservation.docx), is a malicious Word file that drops a remote OLE object via template injection to execute macro code. The macro code inside the remote OLE document contains PowerShell commands that download and execute the final payload.
PowerShell commands executed by the embedded macro
In the RevengeHotels campaign, the downloaded files are .NET binaries protected with the Yoda Obfuscator. After unpacking them, the code is recognizable as the commercial RAT RevengeRAT. An additional module written by the group called ScreenBooking is used to capture credit card data. It monitors whether the user is browsing the web page. In the initial versions, back in 2016, the downloaded files from RevengeHotels campaigns were divided into two modules: a backdoor and a module to capture screenshots. Recently we noticed that these modules had been merged into a single backdoor module able to collect data from clipboard and capture screenshots.
In this example, the webpage that the attacker is monitoring is booking.com (more specifically, the page containing the card details). The code is specifically looking for data in Portuguese and English, allowing the attackers to steal credit card data from web pages written in these languages.
Title searched by the malware in order to capture the screen contents
In the ProCC campaigns, the downloaded files are Delphi binaries. The backdoor installed in the machine is more customized than that used by RevengeHotels: it’s developed from scratch and is able to collect data from the clipboard and printer spooler, and capture screenshots. Because the personnel in charge of confirming reservations usually need to pull credit card data from OTA websites, it’s possible to collect card numbers by monitoring the clipboard and the documents sent to the printer.
Screenshot is captured when the user copies something to the clipboard or makes a print request
A bad guy’s concierge
According to the relevant underground forums and messaging groups, these criminals also infect front desk machines in order to capture credentials from the hotel administration software; they can then steal credit card details from it too. Some criminals also sell remote access to these systems, acting as a concierge for other cybercriminals by giving them permanent access to steal new data by themselves.
Access to hotel booking systems containing credit card details is sold by criminals as a service
Some Brazilian criminals tout credit card data extracted from a hotel’s system as high quality and reliable because it was extracted from a trusted source, i.e., a hotel administration system.
Message sent to an underground channel selling data extracted from hotel systems
Guests and victims
The majority of the victims are associated with the hospitality sector. Based on the routines used, we estimate that this attack has a global reach. However, based on our telemetry data, we can only confirm victims in the following countries:
Victims confirmed in Argentina, Bolivia, Brazil, Chile, Costa Rica, France, Italy, Mexico, Portugal, Spain, Thailand and Turkey
Based on data extracted from Bit.ly statistics, we can see that potential victims from many other countries have at least accessed the malicious link. This data suggests that the number of countries with potential victims is higher than our telemetry has registered.
Victims per country based on data from a malicious Bit.ly link from the RevengeHotels campaign
A safe stay
RevengeHotels is a campaign that has been active since at least 2015, revealing different groups using traditional RAT malware to infect businesses in the hospitality sector. While there is a marked interest in Brazilian victims, our telemetry shows that their reach has extended to other countries in Latin America and beyond.
The use of spear-phishing emails, malicious documents and RAT malware is yielding significant results for at least two groups we have identified in this campaign. Other threat actors may also be part of this wave of attacks, though there is no confirmation at the current time.
If you want to be a savvy and safe traveler, it’s highly recommended to use a virtual payment card for reservations made via OTAs, as these cards normally expire after one charge. While paying for your reservation or checking out at a hotel, it’s a good idea to use a virtual wallet such as Apple Pay, Google Pay, etc. If this is not possible, use a secondary or less important credit card, as you never know if the system at the hotel is clean, even if the rooms are…
All Kaspersky products detect this threat as:

HEUR:Backdoor.MSIL.Revenge.gen
HEUR:Trojan-Downloader.MSIL.RevengeHotels.gen
HEUR:Trojan.MSIL.RevengeHotels.gen
HEUR:Trojan.Win32.RevengeHotels.gen
HEUR:Trojan.Script.RevengeHotels.gen


Indicators of compromise (IoCs)
Reference hashes:

74440d5d0e6ae9b9a03d06dd61718f66
e675bdf6557350a02f15c14f386fcc47
df632e25c32e8f8ad75ed3c50dd1cd47
a089efd7dd9180f9b726594bb6cf81ae
81701c891a1766c51c74bcfaf285854b

For a full list of IoCs as well as the YARA rules and intelligence report for this campaign, please visit the Kaspersky Threat Intelligence Portal: https://tip.kaspersky.com/






Brazil
Cyber espionage
RAT Trojan
Spear phishing
Targeted attacks
Vulnerabilities and exploits



Authors




GReAT





RevengeHotels: cybercrime targeting hotel front desks worldwide 
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



























