# Reference for threat actor for "TA551, Shathak"

**Title**: TA551 Uses ‘SLIVER’ Red Team Tool in New Activity | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/security-briefs/ta551-uses-sliver-red-team-tool-new-activity

## Content































































TA551 Uses ‘SLIVER’ Red Team Tool in New Activity | Proofpoint US









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
                                    Security Brief: TA551 Uses ‘SLIVER’ Red Team Tool in New Activity
                              

 












Security Brief: TA551 Uses ‘SLIVER’ Red Team Tool in New Activity





Share with your network!








 October 20, 2021


                BRYAN CAMPBELL, SELENA LARSON AND THE PROOFPOINT THREAT INSIGHT TEAM
  
        

 Proofpoint researchers identified a new campaign from the highly active cybercrime actor known as TA551 using a legitimate “Red Team & adversary simulation Framework”. The new activity demonstrates a significant departure from the previously observed activity from this group. Proofpoint assesses with high confidence the new activity could lead to ransomware infections.
TA551 is a criminal threat actor Proofpoint has tracked since 2016. It is known by other security firms as Shathak. Proofpoint assesses with high confidence TA551 gains access to stolen messages or compromised email accounts – also known as thread hijacking – which it uses in email campaigns to distribute malware. TA551 has previously distributed malware payloads such as Ursnif, IcedID, Qbot, and Emotet. This actor acts as an initial access facilitator for ransomware threat actors. Proofpoint has observed its campaigns leveraging banking trojans have led to ransomware infections. Proofpoint assesses with high confidence TA551 IcedID implants were associated with Maze and Egregor ransomware events in 2020.
On 20 October 2021, Proofpoint observed emails that appeared to be replies to previous conversations and contained password-protected zipped Word documents. The attachments ultimately lead to the download of Sliver, an open-source, cross-platform adversary simulation and red team platform. The activity demonstrated a significant departure from previous tactics, techniques, and procedures from TA551.

Figure: Thread hijacked email containing zipped Word document.
When a victim downloads the zipped attachment, they are ultimately directed to a macro-laden Microsoft Word document. If macros are enabled, SLIVER is downloaded.

Figure: Malicious Microsoft Word document directing victims to enable macros.
SLIVER is available for free online, and capabilities include information gathering, command and control (C2) functionality, token manipulation, process injection, and other features. Red teaming tools are becoming increasingly popular with cybercrime threat actors. For instance, Proofpoint observed a 161% increase in threat actor use of the red teaming tool Cobalt Strike between 2019 and 2020. Additional offensive frameworks that appear as first stage payloads used by cybercrime actors include Lemon Tree and Veil.
TA551’s use of SLIVER demonstrates considerable actor flexibility. As an established initial access broker leveraging initial access via email threat campaigns, TA551 would compromise a victim and potentially broker access to enable the deployment of Cobalt Strike and eventually ransomware. With SLIVER, TA551 actors can gain direct access and interact with victims immediately, with more direct capabilities for execution, persistence, and lateral movement. This potentially removes the reliance on secondary access.
Proofpoint observed the following indicators of compromise:

Indicator


Description


hXXp://carwaded[.]com/cbfsd/P9G7gD1E6t9w22zQj/cC9DHcTHUKJV/ugnbvdk0EInGgeCqaLEYILzxL/zes1?ref=wU4bJ1ZLhoMc8BcRMMqy&q=ELOKZymM


Document Payload


hXXp://ruwejo[.]com/upload/admin.jsp


SLIVER C2


b7cc07bfc41e61a89e961dd5826fa2b4d47a85a5b5856d50f9a57667199635b3


Document SHA256

Emerging Threats Signature
ETPRO MALWARE Sliver Framework HTTP C2 sessionInit
 
Is your organization protected against criminal threat actors? Learn about Ransomware attacks and prevention.






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

 







 

















