# Reference for threat actor for "TA505, Graceful Spider, Gold Evergreen"

**Title**: TA505 targets the US retail industry with personalized attachments | Proofpoint US

**Source**: https://www.proofpoint.com/us/threat-insight/post/ta505-targets-us-retail-industry-personalized-attachments

## Content





























































TA505 targets the US retail industry with personalized attachments | Proofpoint US









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
                                    TA505 targets the US retail industry with personalized attachments
                              

 












TA505 targets the US retail industry with personalized attachments





Share with your network!








 December 06, 2018


                Proofpoint Staff
  
        

 Overview
Since November 15, 2018, Proofpoint began observing email campaigns from a specific actor targeting large retail chains, restaurant chains and grocery chains, as well as other organizations in the food and beverage industries. These email campaigns attempted to deliver various malware families, including Remote Manipulator System (RMS) and FlawedAmmyy, among others.
We also observed personalization of attachments in one such campaign. These attachments included the targeted company’s logo in the body of the attachment to make messages more believable.
We attributed these campaigns to TA505, the actor behind the largest Dridex and Locky ransomware campaigns of the last two years and more recently associated with distribution of remote access Trojans (RATs) and downloaders. This change in tactics -- the use of personalized attachments in moderately large campaigns combined with retail industry targeting -- arrives just in time for the holiday shopping season.
Campaign Details
On December 3, 2018, we observed a TA505 campaign targeting almost exclusively retail, grocery, and restaurant chains. This campaign distributed tens of thousands of messages. 
More interestingly, each intended target received a personalized attachment, a technique that TA505 has not previously used. The email (Figure 1) purported to be sent from a Ricoh printer and contain a scanned document. The bogus scan was actually a malicious Microsoft Word attachment (Figure 2). The document attached was unique to the targeted company, and even contained the targeted company’s logo in the document lure (blurred in the figure with a black box).
The document contains macros that, if enabled, downloaded and executed an MSI file. The execution leads to the installation of Remote Manipulator System (RMS) with a settings file that contains a custom command and control (C&C) address.

Figure 1: Email used in attempts to deliver malicious document on December 3
The lure shown in Figure 2 continues the social engineering introduced in the email, enticing recipients to enable macros so that they can view the contents of the fake scanned document.

Figure 2: Attached document with the logo blacked out and social engineering to trick recipients into enabling macros
Conclusion
TA505 has helped shape the threat landscape for years, largely because of the massive volumes associated with their campaigns through the end of 2017. When this group changes tactics, it tends to correspond to broader shifts and, throughout the year, we have seen both TA505 and a number of other actors focus on downloaders, RATs, information stealers, and banking Trojans, often in smaller, more targeted campaigns. Threat actors follow the money and, with dropping cryptocurrency values, the return on investment in better targeting, improved social engineering, and management of persistent infections now seems to be greater than that for large “smash and grab” ransomware campaigns.
Given the ongoing holiday shopping season, the clear US retail and grocery targeting associated with these campaigns, and the nature of the malware they are distributing -- RATs and backdoors -- TA505 appears poised to take advantage of increased activity in this sector through the end of the year.
Indicators of Compromise (IOCs)

IOC


IOC Type


Description


hxxp://local365office[.]com/content


URL


Document payload


9206f08916ab6f9708d81a6cf2f916e2f606fd048a6b2355a39db97e258d0883


SHA256


RMS MSI dropper


06c637ac62cab511c5c42e142855ba0447a1c8ac8ee4b0f1f8b00faa5310fe9f


SHA256


Self-extracting RAR containing RMS


609b0a416f9b16a6df9b967dc32cd739402af31566e019a8fb8abdf3cb573e30


SHA256


RMS RAT


89.144.25[.]32:5655


IP:Port


RMS RAT C&C


0F 2B 44 E3 98 BA 76 C5 F5 77 79 C4 15 48 60 7B


Certificate Serial


Serial number of the code signing certificate


DIGITAL DR


String


Subject name of the code signing certificate

 
ET and ETPRO Suricata/Snort Signatures
2812668          ETPRO POLICY Remote Utilities Access Tool Activity






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

 







 

















