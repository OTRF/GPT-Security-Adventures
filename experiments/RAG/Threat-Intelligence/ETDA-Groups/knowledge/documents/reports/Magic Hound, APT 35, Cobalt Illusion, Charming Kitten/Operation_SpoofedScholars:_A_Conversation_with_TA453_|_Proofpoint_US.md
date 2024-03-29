# Reference for threat actor for "Magic Hound, APT 35, Cobalt Illusion, Charming Kitten"

**Title**: Operation SpoofedScholars: A Conversation with TA453 | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/threat-insight/operation-spoofedscholars-conversation-ta453

## Content

































































Operation SpoofedScholars: A Conversation with TA453 | Proofpoint US









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
                                    Operation SpoofedScholars: A Conversation with TA453
                              

 












Operation SpoofedScholars: A Conversation with TA453





Share with your network!








 July 13, 2021


                Joshua Miller, Crista Giering, & the Threat Research Team
  
        

 Key Takeaways 
TA453, an Iranian-state aligned actor, masqueraded as British scholars to covertly target individuals of intelligence interest to the Iranian government in what Proofpoint has dubbed Operation SpoofedScholars.  
The email conversations were benign until TA453 provided a link to a compromised website hosting a credential harvesting page.  
The use of a legitimate but actor-compromised website is an increase in sophistication compared to TA453’s historical Tactics, Techniques, and Procedures of using actor-controlled credential phishing websites. 
Proofpoint has worked with the appropriate authorities to conduct victim notification. 
Overview 
Masquerading as UK scholars with the University of London’s School of Oriental and African Studies (SOAS), the threat actor TA453 has been covertly approaching individuals since at least January 2021 to solicit sensitive information. The threat actor, an APT who we assess with high confidence supports Islamic Revolutionary Guard Corps (IRGC) intelligence collection efforts, established backstopping for their credential phishing infrastructure by compromising a legitimate site of a highly regarded academic institution to deliver personalized credential harvesting pages disguised as registration links. Identified targets included experts in Middle Eastern affairs from think tanks, senior professors from well-known academic institutions, and journalists specializing in Middle Eastern coverage. 
These connection attempts were detailed and extensive, often including lengthy conversations prior to presenting the next stage in the attack chain. Once the conversation was established, TA453 delivered a “registration link” to a legitimate but compromised website belonging to the University of London’s SOAS radio. The compromised site was configured to capture a variety of credentials. Of note, TA453 also targeted the personal email accounts of at least one of their targets. In subsequent phishing emails, TA453 shifted their tactics and began delivering the registration link earlier in their engagement with the target without requiring extensive conversation. This operation, dubbed SpoofedScholars, represents one of the more sophisticated TA453 campaigns identified by Proofpoint. 
 
Chatting with TA453 
In early 2021, a TA453 persona, “Dr.Hanns Bjoern Kendel, Senior Teaching and Research Fellow at SOAS University in London,” used email address hannse.kendel4[@]gmail.com to solicit conversations with targets. The following is a brief summary of an example conversation observed by Proofpoint Threat Research: 
TA453 sent an initial email trying to entice the target with a prospective invitation to an online conference on “The US Security Challenges in the Middle East.” TA453 strived to connect with the individual via phone to discuss the invitation; however, after the target hedged and emphatically stated that they wanted a written proposal with the details, TA453 acquiesced with conference specifics. After a little back and forth that verified the target’s interest, TA453 provided a detailed invitation to the fake conference (Figure 1). The conversation concluded with TA453 attempting to get the target to connect via videoconferencing. 
 
Figure 1. Fake conference invitation. 
Conversation Analysis 
Throughout the conversation, Proofpoint identified a few interesting themes: 
TA453 demonstrates passable English skills and is open to voice communication via videoconferencing.  
TA453 demonstrates an interest in mobile phone numbers, possibly for mobile malware or additional phishing.  
TA453 repeatedly demonstrated a desire to connect with the target in real-time. 
Personal Targeting 
In addition to Hanns’ solicitations, at least one target received a credential harvesting email to their personal email account. This attempt did not masquerade as Dr. Kendel but did still attempt to harvest credentials from the target. Currently, Proofpoint does not have more information on this specific kill chain. 
Campaign Breakdown 
Targets 
TA453 targets in Operation SpoofedScholars can be clustered into three main categories that are consistent with the IRGC’s historical collection priorities.  
Senior think tank personnel 
Journalists focused on Middle Eastern affairs 
Professors 
These groupings consistently have information of interest to the Iranian government, including, but not limited to, information about foreign policy, insights into Iranian dissident movements, and understanding of U.S. nuclear negotiations, and most of the identified targets have been previously targeted by TA453. Targeting appeared to be highly selective, with less than ten organizations targeted, according to Proofpoint data.  
Infrastructure 
Once TA453 established a time for the target to activate their invitation, the TA453 persona provided the personalized link to the intended victim. The link led to a “Webinar Control Panel” on a legitimate but compromised website belonging to University of London’s SOAS, a research institution. According to Proofpoint research, while TA453 does appear to have elevated privileges allowing them to create credential harvesting pages at soasradio[.]org, other pages on the site continue to host legitimate SOAS-affiliated content.  
TA453 strengthened the credibility of the attempted credential harvest by utilizing personas masquerading as legitimate affiliates of SOAS to deliver the malicious links. The displayed webpage (Figure 2) offers users the ability to use “OpenID” to log in with the following mail providers; Google, Yahoo, Microsoft, iCloud, Outlook, AOL, mail.ru, Email, and Facebook. The website URI was hxxps://soasradio[.]org/connect/?memberemailid= [RedactedInitials of Target]-[String of alphanumeric characters].  
 
Figure 2. SOAS displayed webpage. 
When a particular provider is clicked, a pop-up box (Figure 3) displays the actual credential phishing box. Of the options, Google, Microsoft, and Email buttons prefilled the target’s email address. Based on the variety of email providers along with TA453’s insistence that the target log on when TA453 was online, Proofpoint assesses that TA453 was planning on immediately validating the captured credentials manually. 

Figure 3. “AOL login window”   
Hanns Kendel was not the only SOAS scholar spoofed by TA453 during Operation SpoofedScholars. Months later, TA453 began spoofing Tolga Sinmazdemir, another individual associated with SOAS. These emails solicited contributions to a “DIPS Conference” and would have likely followed a similar kill chain discussed above. In mid-May, TA453 returned, using a different email (hanse.kendel4[@]gmail.com) to recruit for a webinar.  
Attribution 
As discussed previously in Proofpoint’s research on TA453’s BadBlood campaign, Proofpoint analysts cannot independently confirm that TA453 is part of the IRGC. However, the tactics and techniques used by the group and their overall targeting detected by Proofpoint is in line with IRGC intelligence collection priorities, which gives us high confidence in our assessment that TA453 operates in support of the IRGC. The IRGC, specifically the IRGC Intelligence Organization, collects intelligence and conducts operations in support of a variety of assigned responsibilities. According to the Meir Amit Intelligence and Terrorism Information Center’s November 2020 report, some of the IRGC IO’s responsibilities include foiling political subversion, combating western cultural penetration, and supporting the arrest of Iranian dual nationals. 
Likewise, attribution specifically for Operation SpoofedScholars is based on TTP similarities to previous TA453 campaigns and consistency with TA453’s historical targeting. TA453 often uses free email providers to spoof individuals familiar to their targets to increase the likelihood of successful compromise. Additionally, as previously discussed, TA453 concentrates their credential phishing to specific individuals of interest to collect intelligence through exfiltration of sensitive email and contacts or initial access for future phishing campaigns. 
Mitigation 
For specific mitigations against Operation SpoofedScholars, Proofpoint recommends investigating network traffic to soasradio[.]org, specifically URIs starting with hxxps://soasradio[.]org/connect/?memberemailid=. Additionally, emails from hanse.kendel4[@]gmail.com, hannse.kendel4[@]gmail.com, and  t.sinmazdemir32[@]gmail.com should be considered suspect and investigated.  
Broader mitigation efforts against TA453 campaigns include increased awareness and investigation of unusual communication from professional contacts. Academics, journalists, and think tank scholars should practice caution and verify the identity of the individuals offering them unique opportunities, especially if those opportunities occur virtually. Using multifactor authentication provides another layer of protection against TA453 credential harvesting.  
Conclusion 
TA453 illegally obtained access to a website belonging to a world class academic institution to leverage the compromised infrastructure to harvest the credentials of their intended targets. The use of legitimate, but compromised, infrastructure represents an increase in TA453’s sophistication and will almost certainly be reflected in future campaigns. TA453 continues to iterate, innovate, and collect in support of IRGC collection priorities. While some of the identified selectors no longer appear to be active in TA453 operations, Proofpoint assesses with high confidence that TA453 will continue to spoof scholars around the world in support of TA453’s intelligence collection operations in support of Iranian government interests. Academics, journalists, and think tank personnel should practice caution and verify the identity of the individuals offering them unique opportunities.  
ET Signature 
2033317 - ET Malware Operation SpoofedScholars Activity (GET) 






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

 







 

















