# Reference for threat actor for "Molerats, Extreme Jackal, Gaza Cybergang"

**Title**: SAS 2019: The APT criminal group Gaza cybergang | Kaspersky official blog

**Source**: https://www.kaspersky.com/blog/gaza-cybergang/26363/

## Content








SAS 2019: The APT criminal group Gaza cybergang | Kaspersky official blog





















































































Solutions for:Home Products
Small Business 1-50 employees
Medium Business 51-999 employees
Enterprise 1000+ employees
 











Kaspersky official blog



My Account

My Kaspersky
My Products / Subscriptions
My Orders




SolutionsHybrid Cloud SecurityLearn moreInternet of Things & Embedded SecurityLearn moreThreat Management and DefenseLearn moreIndustrial CyberSecurityLearn moreKaspersky Fraud PreventionLearn moreOther solutionsKaspersky for Security Operations CenterIndustriesNational CybersecurityLearn moreIndustrial CybersecurityLearn moreFinance Services CybersecurityLearn moreHealthcare CybersecurityLearn moreTransportation CybersecurityLearn moreRetail CybersecurityLearn moreOther industriesTelecom CybersecurityBlockchain SecurityView allProductsKaspersky Endpoint Security for BusinessLearn moreKaspersky Endpoint Detection and ResponseLearn moreKaspersky Endpoint Detection and Response OptimumLearn moreKaspersky Anti Targeted Attack PlatformLearn moreKaspersky Managed Detection and ResponseLearn moreKaspersky SandboxLearn moreOther ProductsKaspersky Security for Mail ServerKaspersky Security for Internet Gateway NEWKaspersky Embedded Systems SecurityKaspersky Hybrid Cloud Security for AWSKaspersky Hybrid Cloud Security for AzureView allServicesCybersecurity ServicesLearn moreKaspersky Adaptive Online TrainingLearn moreKaspersky Premium Support (MSA)Learn moreKaspersky Threat IntelligenceLearn moreKaspersky APT Intelligence ReportingLearn moreKaspersky Targeted Attack DiscoveryLearn moreOther ServicesKaspersky Professional ServicesKaspersky Incident ResponseKaspersky Cybersecurity TrainingKaspersky Incident CommunicationsKaspersky Security AwarenessView allResource CenterCase StudiesWhite PapersDatasheetsTechnologiesMITRE ATT&CKAbout UsTransparencyCorporate NewsPress CenterCareersInnovation HubSponsorshipPolicy BlogContactsGDPRBlog

Business
News
Privacy
Products
Special Projects
Technology
Threats
Tips
RSS
Newsletter subscription


Secure Futures











 





Solutions for:

Home

Security Solutions

Kaspersky Premium
Kaspersky Plus
Kaspersky Standard
View All Solutions
Privacy & Kids
Kaspersky Safe Kids
Kaspersky VPN Secure Connection
Kaspersky Password Manager

Renew Licence
Support
Trials&Update

Business

Small Business (1-50 employees)
Medium Business (51-999 employees)
Enterprise (1000+ employees)


Search blog posts
Blog

Business 
News 
Privacy 
Products 
Special Projects 
Technology 
Threats 
Tips 
RSS

About us

About company
Transparency
Corporate News
Press Center
Careers
Sponsorships
Policy blog
Contacts

Partners

Find a Partner
Partners

My Account

Personal

My Kaspersky
Renew your product

Business

KSOS portal
Kaspersky Business Hub
Renew your License















Search








 SAS

The Gaza cybergang and its SneakyPastes campaign 
A cybergang that specializes in cyberespionage, with its campaign mostly limited to the Middle East and countries in central Asia.







Kaspersky Team




April 10, 2019




 





At our Kaspersky Security Analyst Summit (SAS) conference we traditionally speak about APT attacks: It was there that we first published info about Slingshot, Carbanak, and Careto. Targeted attacks are running as high as ever, and this year was no exception: At SAS 2019 in Singapore we spoke about an APT criminal group called the Gaza cybergang.
Rich armory
The Gaza cybergang specializes in cyberespionage, with its campaign mostly limited to the Middle East and countries in central Asia. At the center of its focus are politicians, diplomats, journalists, activists, and the region’s other politically active citizens.
In terms of the number of attacks we registered from January 2018 through January 2019, the targets located within the Palestinian territories were very comfortably in the lead. Quite a few infection attempts also fell on Jordan, Israel, and Lebanon. In its attacks, the gang uses methods and tools of varying complexity degrees.
Our experts have identified three subgroups in the cybergang. We have already covered two of those. One was the author of the Desert Falcons campaign, and the other was behind the tailored attacks known as Operation Parliament.
Now it’s time to talk about the third, which we call MoleRATs. The group is armed with relatively simple tools, but that doesn’t make its SneakyPastes campaign (named for its active use of pastebin.com) less dangerous.
 SneakyPastes 
The campaign is multistage. It begins with phishing, using letters from one-time addresses and one-time domains. Sometimes the letters contain links to malware or infected attachments. If the victim executes the attached file (or follows the link), their device receives Stage One malware programmed to activate the infection chain.
The letters, meant to quiet the reader’s vigilance, are mostly about politics. They are either records of political negotiations or addresses from some credible organizations.
Once Stage One malware is safely onboard the computer, it tries to secure its position, conceal its presence from any antivirus products, and hide the command server.
The attackers use public services (pastebin.com, github.com, mailimg.com, upload.cat, dev-point.com, and pomf.cat) for subsequent stages of the attack (including malware delivery) and, most important, for communication with the command server. Typically, they use several methods simultaneously to deliver the extracted information.
Finally, the device gets infected with RAT malware, which offers powerful capabilities. Among other things, it can freely download and upload files, launch applications, search for documents, and encrypt information.
The malware scans the victim’s computer to locate all PDF, DOC, DOCX, and XLSX files, saves them to temporary file folders, classifies, archives, and encrypts them, and finally sends them to a command server via a chain of domains.
In fact, we detect multiple tools used in this kind of attack. You can learn more about them and get more technical details from this post on Securelist.
Integrated protection against integrated threats
Our products are made to successfully combat the components used in the SneakyPastes campaign. To avoid being among its victims, follow these tips.

Teach your employees to recognize dangerous letters, both mass and targeted ones; Gaza cybergang attacks begin with phishing. Our interactive Kaspersky ASAP platform not only provides that information but also imparts the necessary skills.
Use integrated solutions built to stand up to complex and multistage attacks that may be too tough for basic antivirus products. To resist attacks at the network level, we recommend a bundle consisting of Kaspersky Anti Targeted Attack and Kaspersky Endpoint Detection and Response.
If your company employs a dedicated information security service, we recommend you subscribe to Kaspersky Lab’s closed reports, where we give detailed accounts of current cyberthreats. You can purchase a subscription by writing to intelreports@kaspersky.com


 






APT
cyberespionage
Gaza Cybergang
phishing
RAT
SAS
SAS 2019
Security Analyst Summit
trojan




 

Related





 


FinSpy: the ultimate spying tool 






 


Tomiris backdoor 
















 




Read next


Another Taj Mahal (between Tokyo and Yokohama) 
A new APT attack targets the diplomatic mission of an Asian country.




 








Pavel Shoshin




April 9, 2019










Tips






 Tips


Five cyberattacks on marketing departments 
Why cybercriminals want to attack PR and marketing staff and, crucially, how to protect your company from financial and reputational harm.









Stan Kaminsky




February 13, 2024












 Tips


Navigating the risks of online dating 
Online dating is great for those looking for love – but beware the risks!









David Buxton




February 12, 2024












 Tips


What to do when you receive unsolicited messages containing login codes 
One-time codes and two-factor authentication securely protect you from account theft. If you receive such a code or a request to enter it when you aren’t logging in, it may be an attempt to hack into your account.









Stan Kaminsky




February 8, 2024












 Tips


How to steal crypto via DNS 
Getting what you pay for: cracked macOS apps fetch malicious code from DNS records to steal crypto









Sergey Puzan




January 31, 2024













Sign up to receive our headlines in your inbox



Email Address*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

  





















Home Solutions

Kaspersky Standard
Kaspersky Plus
Kaspersky Premium
All Solutions


Small Business Products1-100 EMPLOYEES

Kaspersky Small Office Security
Kaspersky Endpoint Security Cloud
All Products


Medium Business Products101-999 EMPLOYEES

Kaspersky Endpoint Security Cloud
Kaspersky Endpoint Security for Business Select
Kaspersky Endpoint Security for Business Advanced
All Products


Enterprise Solutions1000 EMPLOYEES

Cybersecurity Services
Threat Management and Defense
Endpoint Security
Hybrid Cloud Security
All Solutions


 





Copyright © 2024 AO Kaspersky Lab. All Rights Reserved.
Privacy Policy
Anti-Corruption Policy
License Agreement B2C
License Agreement B2B
 
Contact Us About Us Partners Blog Resource Center Press Releases Sitemap  

Securelist
Eugene Personal Blog
Encyclopedia
 









 

Global













Americas
Brasil
México
United States


Africa
South Africa


Middle East
Middle East
الشرق الأوسط




Western Europe
Deutschland & Schweiz
España
France & Suisse
Italia & Svizzera
Nederland & België
United Kingdom




Eastern Europe
Polska
Türkiye
Россия (Russia)
Kazakhstan




Asia & Pacific
Australia
India
中国 (China)
日本 (Japan)


For all other countries
Global






























