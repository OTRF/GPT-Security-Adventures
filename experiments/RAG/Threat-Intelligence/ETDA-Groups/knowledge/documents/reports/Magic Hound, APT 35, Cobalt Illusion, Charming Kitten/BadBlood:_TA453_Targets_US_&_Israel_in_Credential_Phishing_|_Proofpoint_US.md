# Reference for threat actor for "Magic Hound, APT 35, Cobalt Illusion, Charming Kitten"

**Title**: BadBlood: TA453 Targets US & Israel in Credential Phishing | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/threat-insight/badblood-ta453-targets-us-and-israeli-medical-research-personnel-credential

## Content































































BadBlood: TA453 Targets US & Israel in Credential Phishing | Proofpoint US









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
                                    BadBlood: TA453 Targets US and Israeli Medical Research Personnel in Credential Phishing Campaigns 
                              

 












BadBlood: TA453 Targets US and Israeli Medical Research Personnel in Credential Phishing Campaigns 





Share with your network!








 March 30, 2021


                Joshua Miller and the Proofpoint Threat Research Team
  
        

 Overview
In late 2020, TA453, an Iranian-nexus threat actor, launched a credential phishing campaign targeting senior medical professionals who specialize in genetic, neurology, and oncology research in the United States and Israel. TA453 (aka CHARMING KITTEN and PHOSPHORUS) has historically aligned with Islamic Revolutionary Guard Corps (IRGC) collection priorities, targeting dissidents, academics, diplomats, and journalists. This latest campaign, dubbed BadBlood, is a deviation from the group’s usual activity. [1,2,3] While this campaign may represent a shift in TA453 targeting overall, it is also possible it may be the result of a specific short term intelligence collection requirement. BadBlood is aligned with an escalating trend of medical research being increasingly targeted by threat actors.
Proofpoint researchers have named this campaign BadBlood based on the medical focus and continued geopolitical tensions between Iran and Israel.
Credential Phishing Campaign 
In this December 2020 campaign, TA453 used an actor-controlled Gmail account that masqueraded as a prominent Israeli physicist. The account (zajfman.daniel[@]gmail.com) sent messages with the subject "Nuclear weapons at a glance: Israel" and contained social engineering lures relating to Israeli nuclear capabilities. These malicious emails contained a link to the TA453-controlled domain 1drv[.]casa. When clicked, the URL leads to a landing site spoofing Microsoft's OneDrive service along with an image of a PDF document logo titled CBP-9075.pdf.

Figure 1: TA453 Landing Site with PDF Document Logo
When a user attempts to view and download the PDF document, 1drv[.]casa delivers a forged Microsoft login page which attempts to harvest user credentials. Attempting to use any other hyperlink in the webpage results in the same redirect to the same forged Microsoft login page, except for the "Create one!" link. This tab leads to the legitimate Microsoft Outlook “Sign Up” page at hxxps://signup.live[.]com.

Figure 2: TA453 Credential Harvesting Page at 1drv[.] casa
Once an email is entered by the user and “Next” is clicked, the page prompts for a password.
Once a user enters their credentials, they are then redirected to Microsoft’s OneDrive where the benign "Nuclear weapons at a glance: Israel" document is hosted.

Figure 3: Microsoft OneDrive TA453 Benign Document
At this time, it does not appear 1drv[.]casa conducts any sort of multi-factor authentication bypass. Although Proofpoint does not currently have further visibility into how TA453 used any credentials obtained from this specific campaign, public reporting from CERTFA indicates TA453 has previously used harvested credentials to exfiltrate email inbox contents.[4] In select prior campaigns, Iranian-aligned actors, including TA453, have used compromised accounts for further phishing.[5]
Targeting
TA453 targeted less than 25 senior professionals at a variety of medical research organizations located in the US and Israel. Proofpoint analysis of the targets’ publicly available research efforts and resumes indicate TA453 targeted individuals with a background in either genetics, oncology, or neurology. These medical professionals appear to be extremely senior personnel at a variety of medical research organizations. Additionally, TA453 targeting Israeli organizations and individuals is consistent with increased geopolitical tensions between Israel and Iran during 2020. [6]
At this time, Proofpoint cannot conclusively determine the motivation of actors conducting these campaigns. As collaboration for medical research is often conducted informally over email, this campaign may demonstrate that a subset of TA453 operators have an intelligence requirement to collect specific medical information related to genetic, oncology, or neurology research. Alternatively, this campaign may demonstrate an interest in the patient information of the targeted medical personnel or an aim to use the recipients' accounts in further phishing campaigns. While this campaign may represent a shift in TA453 targeting overall, it is also possible it may be an outlier, reflective of a specific priority intelligence tasking given to TA453.
Attribution
While Proofpoint cannot independently attribute TA453 to the IRGC, the tactics and techniques observed in BadBlood continue to mirror those used in historic TA453 campaigns and the overall targeting of TA453 campaigns detected by Proofpoint appear to support IRGC intelligence collection priorities.[7]
In 2019, the US Department of Justice indicted four Iranian individuals for using social media and credential phishing emails to conduct malicious computer intrusions on behalf of the IRGC.[8] Private industry reporting identified this activity as part of CHARMING KITTEN in both 2017 and 2019.[9,10] In early 2019, Microsoft reported TA453 was abusing well known email brands to conduct spear phishing operations against government agencies, political targets, and journalists on behalf of the Iranian government.[11]
Related Infrastructure
While investigating this campaign, Proofpoint Threat Research identified other domains attributed to TA453 with high confidence based on network infrastructure components, campaign timing, and similarity in lure documents. Both Proofpoint and VirusTotal telemetry indicated additional actor-controlled domains were used in TA453 campaigns attempted to compromise more traditional TA453 targets with a similar attack-chain in late December 2020. Finally, the provided lure documents at the end of the attack chain share similar, national security themes, including Congressional Research Reports, think tank publications, and other policy minded documents. While researchers were not able to directly correlate all of these domains with phishing campaigns, we judge this activity to be consistent with the BadBlood campaign.

Figure 4: Diagram of Related Infrastructure

Figure 5: Final 1drv[.]xyz Lure “Reviving The Revolutionaries Document”

Figure 6: Final 1drv[.]surf Lure Congressional Research Service Document
Outlook
While TA453 has consistently demonstrated a desire to collect and exfiltrate the email mailbox contents belonging to typical intelligence targets of the Iranian government like the Iranian diaspora, policy analysts, and educators, this TA453 campaign demonstrated a desire to target medical researchers and providers. Further detection and analysis of TA453 campaigns will likely determine whether this targeting is an outlier or if targeting has evolved to support the medical sector becoming a consistent intelligence requirement and target for TA453.
While targeting medical experts in genetics, neurology and oncology may not be a lasting shift in TA453 targeting, it does indicate at least a temporary change in TA453 collection priorities. BadBlood is aligned with an escalating trend globally of medical research being increasingly targeted by espionage motivated focused threat actors. [12]
References
[1] https://blog.certfa.com/posts/fake-interview-the-new-activity-of-charming-kitten/
[2] https://blogs.microsoft.com/on-the-issues/2020/10/28/cyberattacks-phosphorus-t20-munich-security-conference/
[3] https://www.clearskysec.com/wp-content/uploads/2020/08/The-Kittens-are-Back-in-Town-3.pdf
[4] https://blog.certfa.com/posts/charming-kitten-christmas-gift/
[5] https://carnegieendowment.org/files/Iran_Cyber_Final_Full_v2.pdf
[6] https://www.cpomagazine.com/cyber-security/hidden-cyber-war-between-israel-and-iran-spills-into-public-view-with-attacks-on-physical-infrastructure/
[7] https://www.janes.com/defence-news/news-detail/iranian-irgc-consolidates-primacy-in-intelligence-operations
[8] https://www.justice.gov/opa/press-release/file/1131726/download
[9] https://www.clearskysec.com/wp-content/uploads/2017/12/Charming_Kitten_2017.pdf   
[10] https://blogs.microsoft.com/on-the-issues/2019/10/04/recent-cyberattacks-require-us-all-to-be-vigilant
[11] https://blogs.microsoft.com/on-the-issues/2019/03/27/new-steps-to-protect-customers-from-hacking
[12] https://us-cert.cisa.gov/ncas/alerts/AA20126A
Indicators of Compromise

IOC


IOC Type


Description


1drv[.]live
 


Domain


 


1drv[.]online


Domain
 


Educational Credential Phishing Domain


1drv[.]icu
 


Domain
 


 


1drv[.]surf
 


Domain
 


 


1drv[.]xyz
 


Domain
 


 


1drv[.]cyou
 


Domain
 


 


1drv[.]casa


Domain


Medical Credential Phishing Domain


1drv[.]casa/s/AFGHJKFJelMtfZXSXSGkdsjh1


URL


Medical Credential Harvesting URL


1drv[.]icu/b/AuQWU1NEWRw1


URL


VT Sourced URL


1drv[.]surf/b/AuQWU1NEWRw9


URL


VT Sourced URL


1drv[.]xyz/b/AuQWU1NEWRw1/


URL


VT Sourced URL


1drv[.]cyou/b/AuQWU1ZEWRw5


URL


VT Sourced URL

 
[Analyst Note: List of URL IOCs is not meant to be conclusive. It is possible other variants of the URL have been delivered.]
ET Signatures 
2847882 - OneDrive Phishing Landing 2021-03-29






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

 







 

















