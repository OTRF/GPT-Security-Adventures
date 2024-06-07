# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: BazaFlix: BazaLoader Fakes Movie Streaming Service | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/threat-insight/bazaflix-bazaloader-fakes-movie-streaming-service

## Content































































BazaFlix: BazaLoader Fakes Movie Streaming Service | Proofpoint US









      Skip to main content
    







Products
Solutions
Partners
Resources
Company











English (Americas)
English (Europe, Middle East, Africa)
English (Asia-Pacific)
Español
Deutsch
Français
Italiano
Português
日本語
한국어



Login

Support Log-in
Digital Risk Portal
Email Fraud Defense
ET Intelligence
Proofpoint Essentials
Sendmail Support Log-in


Contact






Aegis Threat Protection PlatformDisarm BEC, phishing, ransomware, supply chain threats and more.
Sigma Information Protection PlatformDefend your data from careless, compromised and malicious users.
Identity Threat Defense PlatformPrevent identity risks, detect lateral movement and remediate identity threats in real time.
Intelligent Compliance PlatformReduce risk, control costs and improve data visibility to ensure compliance.
Premium ServicesLeverage proactive expertise, operational continuity and deeper insights from our skilled experts.





Email Security and Protection
Email Protection
Email Fraud Defense
Secure Email Relay
Threat Response Auto-Pull
Sendmail Open Source
Essentials for Small Business

Advanced Threat Protection
Targeted Attack Protection in Email
Threat Response
Emerging Threats Intelligence

Security Awareness Training
Assess
Change Behavior
Evaluate


Information Protection
Enterprise Data Loss Prevention (DLP)
Insider Threat Management
Intelligent Classification and Protection
Endpoint Data Loss Prevention (DLP)
Email Data Loss Prevention (DLP)
Email Encryption
Data Discover

Cloud Security
Isolation
Cloud App Security Broker
Web Security


Identity Threat Detection and Response
Spotlight
Shadow


Compliance and Archiving
Automate
Capture
Patrol
Track
Archive
Discover
Supervision


Premium Services
Managed Email Threat Protection
Managed Information Protection
Managed Security Awareness
Managed Abuse Mailbox
Recurring Consultative Services
Technical Account Managers
Threat Intelligence Services
People-Centric Security Program






  New threat protection solution bundles with flexible deployment options 
  AI-powered protection against BEC, ransomware, phishing, supplier risk and more with inline+API or MX-based deployment
Learn More






Solutions by Topic


Combat Email and Cloud ThreatsProtect your people from email and cloud threats with an intelligent and holistic approach.
Change User BehaviorHelp your employees identify, resist and report attacks before the damage is done.
Combat Data Loss and Insider RiskPrevent data loss via negligent, compromised and malicious insiders by correlating content, behavior and threats.
Modernize Compliance and ArchivingManage risk and data retention needs with a modern compliance and archiving solution.
Protect Cloud AppsKeep your people and their cloud apps secure by eliminating threats, avoiding data loss and mitigating compliance risk.


Prevent Loss from RansomwareLearn about this growing threat and stop attacks by securing today’s top ransomware vector: email.
Secure Microsoft 365Implement the very best security and compliance solution for your Microsoft 365 collaboration suite.
Defend Your Remote Workforce with Cloud EdgeSecure access to corporate resources and ensure business continuity for your remote workers.
Authenticate Your EmailProtect your email deliverability with DMARC.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.




Solutions by Industry

Federal Government
State and Local Government
Higher Education
Financial Services
Healthcare
Mobile Operators
Internet Service Providers
Small and Medium Businesses






Partner Programs


Channel PartnersBecome a channel partner. Deliver Proofpoint solutions to your customers and grow your business.
Archive Extraction PartnersLearn about Proofpoint Extraction Partners.
Global System Integrator (GSI) and Managed Service Provider (MSP) PartnersLearn about our global consulting and services partners that deliver fully managed and integrated solutions.


Technology and Alliance PartnersLearn about our relationships with industry-leading firms to help protect your people, data and brand.
Social Media Protection PartnersLearn about the technology and alliance partners in our Social Media Protection Partner program.
Proofpoint Essentials Partner ProgramsSmall Business Solutions for channel partners and MSPs.




Partner Tools

Become a Channel Partner
Channel Partner Portal








Resource LibraryFind the information you're looking for in our library of videos, data sheets, white papers and more.
BlogKeep up with the latest news and happenings in the ever‑evolving cybersecurity landscape.
PodcastsLearn about the human side of cybersecurity. Episodes feature insights from experts and executives.
New Perimeters MagazineGet the latest cybersecurity insights in your hands – featuring valuable knowledge from our own industry experts.


Threat GlossaryLearn about the latest security threats and how to protect your people, data, and brand.
EventsConnect with us at events to learn how to protect your people and data from ever‑evolving threats.
Customer StoriesRead how Proofpoint customers around the globe solve their most pressing cybersecurity challenges.
WebinarsBrowse our webinar library to learn about the latest threats, trends and issues in cybersecurity.




Security Hubs

Get free research and resources to help you protect against threats, build a security culture, and stop ransomware in its tracks.

Threat Hub
CISO Hub
Cybersecurity Awareness Hub
Ransomware Hub
Insider Threat Management Hub









About ProofpointProofpoint is a leading cybersecurity company that protects organizations' greatest assets and biggest risks: their people.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.
CareersStand out and make a difference at one of the world's leading cybersecurity companies.


News CenterRead the latest press releases, news stories and media highlights about Proofpoint.
Privacy and TrustLearn about how we handle data and make commitments to privacy and other regulations.
Environmental, Social, and GovernanceLearn about our people-centric principles and how we implement them to positively impact our global community.




Support

Access the full range of Proofpoint support services.
Learn More











 




BlogThreat Insight
                                    BazaFlix: BazaLoader Fakes Movie Streaming Service 
                              

 












BazaFlix: BazaLoader Fakes Movie Streaming Service 





Share with your network!








 May 26, 2021


                Selena Larson and Matthew Mesa
  
        

 Key Findings 

BazaLoader affiliates continue to use elaborate infection chains requiring significant victim interaction to distribute BazaLoader malware. 
Emails directed the victim to call a customer service line which sent them to a website containing malicious content. 
The threat actor created a robust fake movie streaming service called BravoMovies, complete with fake movie titles as a landing page. 
Overview
Proofpoint researchers identified a BazaLoader campaign requiring significant human interaction to execute and install the BazaLoader backdoor. The threat actor leveraged phone-based customer service representatives to direct victims to unknowingly download and install the malware. This campaign is representative of a broader trend leveraged by the BazaLoader threat actors using call centers as part of an intricate attack chain. 
The entertainment-themed campaign was first observed in early May 2021 and masqueraded as a streaming entertainment service, complete with a slick website featuring fake movies. The campaign demonstrates an inversely proportional relationship between successful infection rates and asking people to complete complicated steps – the more steps required by the user, the less likely they are to complete the attack chain. However, despite being counterintuitive, the techniques used by the threat actors in this, and similar, campaigns help bypass fully automated threat detection systems. Additionally, leveraging a streaming service cancellation lure preys on a growing trend of users cancelling online entertainment following major growth in the industry during 2020. 
Campaign Details
BazaLoader is a downloader written in C++ that is used to download and execute additional modules. Proofpoint first observed BazaLoader in April 2020. It is currently used by multiple threat actors and frequently serves as a loader for disruptive malware including Ryuk and Conti ransomware. Proofpoint assesses with high confidence there is a strong overlap between the distribution and post-exploitation activity of BazaLoader and threat actors behind The Trick malware, also known as Trickbot.
Infection Chain

In the recent BazaLoader campaign, messages purport to be from various senders with subjects such as:
Your trial period M0012064753012345 is going to be expired soon. Thankfully you made a decision to stick with us!
Demo stage is expired! Your account #M0272028060812345 will be automatically transferred to premium plan!

Figure 1: Initial BazaLoader email masquerading as an entertainment streaming service
The emails contain phone numbers and references to the "BravoMovies" company. The messages purport to inform the target their credit card will be charged unless they cancel their subscription to the service. If the user calls the phone number provided in the email, a customer service representative will verbally guide the user to the company's alleged website. The website is a convincing representation of a movie and television streaming service. The threat actors used fake movie posters obtained from various open-source resources including an advertising agency, the creative social network Behance, and the book “How to Steal a Dog.”

Figure 2: BravoMovies landing page
When the user visits the site mentioned, navigates to the Frequently Asked Questions component of the website, and follows the directions to unsubscribe via the “Subscribtion” page, they will be directed to the download of an Excel Sheet. 

Figure 3: FAQ page with cancellation instructions

Figure 4: Fake subscription cancellation page
The Excel sheet contains macros that, if enabled, will download BazaLoader.

Figure 5: Malicious Excel Sheet 
At this time, Proofpoint has not observed the second-stage payload in this campaign. 
Related Campaigns 
Proofpoint has observed BazarLoader threat actors using the method of phone-based customer service representatives to direct malicious downloads since February 2021. Security researchers have dubbed this method “BazarCall”. Proofpoint has previously observed BazaLoader email threat campaigns requiring significant human interaction in order to execute the malware. The previous campaigns included subscription pharmaceutical services and lingerie and flower orders. 
Additionally, Proofpoint researchers have observed similar infection chains leading to the distribution of The Trick instead of BazaLoader. By leveraging attack chains that require a lot of human interaction, threat actors can bypass some automated threat detection services that only flag on malicious links or attachments in email. Proofpoint anticipates the threat actors behind BazaLoader and The Trick will continue to use these techniques in future campaigns. 
Conclusion
Using entertainment subscription themes may be a timely and effective method for convincing users to engage with the email content and follow-on malicious documents. During the COVID-19 pandemic in 2020, subscriptions to online streaming services skyrocketed, surpassing one billion users globally last year. But according to recent 2021 data, consumers are using fewer services while churning through free subscriptions and cancelling when their trials run out. BazaLoader threat actors are taking advantage of this human behavior trend in the identified campaign. 
Indicators of Compromise

IOC


IOC Type


Description


First Observed


urbancinema[.]net


Domain


Landing Page


2021-05-05


bravomovies[.]net


Domain


Landing Page


2021-05-01


bvcinema[.]net


Domain


Landing Page


2021-05-06


47.91.77[.]83


IP


BravoMovies Website Host


2021-05-05


8.209.65[.]249


IP


BravoMovies Website Host


2021-05-01


8.209.92[.]183


IP


BravoMovies Website Host


2021-05-04


8.209.75[.]180


IP


BravoMovies Website Host


2021-05-04


8.211.4[.]26


IP


BravoMovies Website Host


2021-05-06


8.211.6[.]4


IP


BravoMovies Website Host


2021-05-06


8.209.67[.]183


IP


BravoMovies Website Host


2021-05-10


47.91.74[.]88


IP


BravoMovies Website Host


2021-05-15


176.111.174[.]60


IP


BazaLoader Excel Payload Host


2021-05-04


hxxps://18.237.242[.]195/g1_262/bt_64_g1_262


URL


BazaLoader C2


2021-05-04


hxxp://noise1[.]xyz/campo/n/o


URL


BazaLoader Excel Payload


2021-05-04


9663dc275239aa93ceccedae7a0d54e10def18dd177d231264a323a4175a23d4


SHA256


BazaLoader Hash


2020-04-25

 
ET Signatures: 
 
2033033 - ET TROJAN BazaLoader CnC Activity  
2033034 - ET TROJAN Observed Malicious SSL Cert






Previous Blog Post


Next Blog Post







Subscribe to the Proofpoint Blog

























About


Overview
Why Proofpoint
Careers
Leadership Team
News Center
Nexus Platform
Privacy and Trust




Threat Center


Threat Hub
Cybersecurity Awareness Hub
Ransomware Hub
Threat Glossary
Threat Blog








Products


Email Security & Protection
Advanced Threat Protection
Security Awareness Training
Cloud Security
Archive & Compliance
Information Protection
Product Bundles




Resources


White Papers
Webinars
Data Sheets
Events
Customer Stories
Blog
Free Trial








Connect


+1-408-517-4710
Contact Us
Office Locations
Request a Demo




Support


Support Login
Support Services
IP Address Blocked?
















Facebook
Twitter
linkedin
Youtube





English (US)
English (UK)
English (AU)
Español
Deutsch
Français
Italiano
Português
日本語
한국어





© 2024. All rights reserved.
            Terms and conditions
Privacy Policy
Sitemap

 







 

















