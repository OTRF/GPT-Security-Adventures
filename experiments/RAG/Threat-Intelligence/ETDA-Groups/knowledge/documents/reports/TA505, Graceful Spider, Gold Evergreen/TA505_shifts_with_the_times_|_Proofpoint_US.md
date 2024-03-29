# Reference for threat actor for "TA505, Graceful Spider, Gold Evergreen"

**Title**: TA505 shifts with the times | Proofpoint US

**Source**: https://www.proofpoint.com/us/threat-insight/post/ta505-shifts-times

## Content





























































TA505 shifts with the times | Proofpoint US









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
                                    TA505 shifts with the times
                              

 












TA505 shifts with the times





Share with your network!








 June 08, 2018


                Proofpoint Staff
  
        

 Overview
In September 2017, Proofpoint researchers detailed the history and ongoing activities of an actor we track as TA505. Throughout 2016 and 2017, TA505 was among the most prolific financially motivated actors we follow, regularly distributing massive malicious spam campaigns bearing diverse payloads ranging from Jaff ransomware to The Trick banking Trojan. TA505 was behind many of the Dridex campaigns that plagued organizations in 2015 and introduced Locky ransomware in 2016, bringing unprecedented scale to malicious spam distribution. Since we wrote our original TA505 profile, the actor has continued to explore the use of new malicious attachments and new payloads. In 2018, though, the scale and regularity of their campaigns decreased, while the diversity of payloads has increased. Given the importance of this actor in the email threat landscape we wanted to revisit our profile and update it with the latest activity from TA505.
For additional historical information on TA505, read our Actor Profile.
Activity since September 2017
Locky - September/October
By the fourth quarter of 2017, TA505 was still sending very high-volume campaigns primarily distributing Locky ransomware. As in the preceding months, TA505 pivoted through various attachment types to deliver the malicious payload. For the last half of September and the first half of October, the group primarily used VBScript files compressed in 7-Zip archives to distribute Locky Affiliate ID 3 (Affid=3). 7-Zip files are not natively supported in Microsoft Windows and require the installation of 7-Zip software; recipients also needed to execute the VBScript after installing 7-Zip and decompressing the attachments. While this combination of files is somewhat unusual for attachment campaigns and requires more user interaction than many, most researchers expect that TA505 was using new vectors to bypass protections put in place by organizations saturated with Locky-bearing messages over the previous year.
Geo-targeted Locky and The Trick - October
On October 10, TA505 introduced their first geo-targeted campaign dropping either Locky or The Trick banking Trojan. In this campaign, HTML files were attached to emails inquiring about the status of an invoice. When users opened the HTML attachments to view the fake invoice, embedded JavaScript downloaded The Trick banking Trojan with gtag "mac1" if the victim appeared to reside in the UK, Australia, Luxembourg, Ireland, or Belgium. All other victims received Locky (Affid=3 with file extension “.ykcol”).

Figure 1: Lure email with .html attachment, October 10, 2017

Figure 2: .html attachment with JavaScript that downloads the final payload, October 10, 2017
TA505 sent several similar campaigns in mid-October with VBScript compressed in 7-Zip files that also downloaded either Locky or The Trick. By late October, the actor switched to Microsoft Word attachments that abused Dynamic Data Exchange (DDE) to download either Locky or Locky and The Trick in several more geo-targeted campaigns. This was the first time that we observed TA505 abusing DDE, a legitimate feature in Microsoft Office that became a regular part of multiple threat actors’ toolkits in Q4 2017. Recipients of these emails, which also used simple lures with attached fake invoices, needed to open the Microsoft Word attachments and click through a security dialog (Figure 3) to download the malware.

Figure 3: DDE confirmation associated with late-October campaigns
Embedded .lnk and .vbs - November
On October 31, TA505 sent two campaigns, both using .lnk files embedded in Microsoft Word documents. As shown in Figure 4, recipients must open the attached Word document, enable editing, and then execute the .lnk file by double clicking an image in the document. They must further confirm that they want to open the .lnk file (Figure 5), which, in turn, downloads an intermediate downloader. This downloader then downloads either Locky or The Trick depending on location. Despite the number of steps involved, TA505 relies on light social engineering in the email and lure as well as end user conditioning to proceed through the scheme and infect their PC with malware.

Figure 4: Microsoft Word document with embedded malicious .lnk file, October 31, 2017

Figure 5: Security dialog for embedded .lnk file 
Through November 9, TA505 distributed several such campaigns, sometimes two per day, largely distributing Locky. Activity for the rest of November was light, featuring only five more campaigns using embedded Visual Basic scripts in Word documents or VB Script in 7-Zip attachments to distribute The Trick, Dridex, Scarab ransomware, and GlobeImposter ransomware.
GlobeImposter - December
December saw yet another shift in payloads for TA505. Of the 34 campaigns the group sent in a month that was extremely active even by TA505 standards, 24 were distributing GlobeImposter ransomware. Like The Trick banking Trojan, GlobeImposter was a relatively low-profile, regionally focused malware strain that became a global threat when TA505 began distributing it in massive campaigns. The majority of these campaigns used malicious VBScript or JavaScript compressed in 7-Zip attachments.
The remaining ten campaigns in December distributed a range of malware including The Trick, the DreamSmasher reconnaissance tool, and Dridex.
Shifting to low-volume campaigns - January/February 2018
TA505 has typically taken some time to resume full operations after the Russian Orthodox holidays. The group is also heavily reliant on the Necurs botnet for its massive campaigns and its operators of the botnet appear to have lost control of the botnet for much of January and February. However, in previous years, Necurs disruptions resulted in complete silence from TA505. This year, the group remained active, though campaign frequency and volume were a tiny fraction of their peaks in 2017 during this period.
Rather, TA505 appeared to once again be exploring new payloads and vectors. We observed the actor send two large pharmaceutical spam campaigns via BlackTDS in February, a highly unusual move for a group focused on malicious attachments since at least 2014. We have also observed smaller campaigns distributing GandCrab ransomware, DreamSmasher, Dridex, and Quant Loader.
The slow return of Necurs-powered large campaigns - March 2018 to present
Beginning in March, TA505 launched several large campaigns, again utilizing the Necurs sending infrastructure, albeit much less frequently than in 2017. Campaigns in March and April largely delivered the FlawedAmmyy remote access Trojan (RAT), often via the intermediate Quant Loader malware. Attachments in these campaigns were frequently Zip archives containing ".url" files which, if opened and allowed by the user, downloaded Javascript via the SMB protocol. The Javascript then downloaded Quant Loader, which, in turn downloaded the FlawedAmmyy RAT. RATs are generally used in targeted attacks, begging the question how a threat actor distributing large-scale malicious spam might use such a tool.
We observed a handful of TA505 campaigns delivering FlawedAmmyy in late April and May, with the most recent occurring on June 7. While the frequency of these campaigns remains off from their normal cadence and message volumes still have not returned to 2017 levels, the trend of shifting vectors and experimentation with new techniques continues. The last two campaigns we observed from TA505 made use of .iqy attachments -- Microsoft Excel Web Query files are used to pull external data into Excel and, in these cases, the functionality was abused to download FlawedAmmyy.
Conclusion
Over the past four years, TA505 has introduced both Dridex and Locky to the threat landscape in relentless, massive email campaigns. The group also turned smaller targeted or regionally-focused malware like The Trick, GlobeImposter, and FlawedAmmyy into global phenomena. TA505 regularly changes vectors, shifts payloads, and experiments with new techniques, all apparently to bypass defenses and deliver payloads from bankers to RATs, often at a scale unmatched by other high-profile actors.
Their recent foray into large-scale distribution of RATs and intermediate loaders bears further observation as, unlike with Locky or GlobeImposter infections, victims may not realize they are infected until the group triggers additional malware installations or steals valuable data. The group’s willingness to explore new vectors, payloads, sending infrastructure, and other malicious services like BlackTDS, even when they do not have access to the Necurs spam cannon, exemplifies the adaptability of modern threat actors.






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

 







 

















