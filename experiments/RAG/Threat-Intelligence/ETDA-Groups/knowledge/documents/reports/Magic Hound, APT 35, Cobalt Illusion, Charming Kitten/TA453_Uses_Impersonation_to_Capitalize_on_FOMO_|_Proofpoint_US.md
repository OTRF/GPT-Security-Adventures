# Reference for threat actor for "Magic Hound, APT 35, Cobalt Illusion, Charming Kitten"

**Title**: TA453 Uses Impersonation to Capitalize on FOMO | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/threat-insight/ta453-uses-multi-persona-impersonation-capitalize-fomo

## Content

































































TA453 Uses Impersonation to Capitalize on FOMO | Proofpoint US









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
                                    Look What You Made Me Do: TA453 Uses Multi-Persona Impersonation to Capitalize on FOMO
                              

 












Look What You Made Me Do: TA453 Uses Multi-Persona Impersonation to Capitalize on FOMO





Share with your network!








 September 13, 2022


                Joshua Miller, Kyle Eaton and Alexander Rausch
  
        

 
Key Takeaways
In mid-2022, TA453 deployed a social engineering impersonation technique informally called Multi-Persona Impersonation in which the threat actor uses at least two actor-controlled personas on a single email thread to convince targets of the legitimacy of the campaign.
This is an intriguing technique because it requires more resources be used per target—potentially burning more personas—and a coordinated approach among the various personalities in use by TA453.
This is the latest in TA453's evolution of its techniques and can be mitigated in large part by potential targets, such as those specializing in Middle Eastern affairs or nuclear security, by being cautious when they receive outreach from unexpected sources, even those that appear legitimate.
Overview
As a great songwriter once penned, "everyone needs a friend." No APT this year has been taking this sentiment more to heart than the Iran-aligned espionage threat actor TA453. Throughout late 2021 and through 2022, Proofpoint researchers have observed TA453, which overlaps with activity tracked as Charming Kitten, PHOSPHORUS, and APT42, continually innovating its approach in a quest to fulfill its intelligence priorities. In late June 2022, this evolution resulted in campaigns utilizing what Proofpoint informally calls Multi-Persona Impersonation (MPI), a subset of Impersonation noted in Proofpoint's Email Fraud Taxonomy framework. In MPI, TA453 takes their targeted social engineering to a new level, targeting researchers with not just one actor-controlled persona but multiple. This technique allows TA453 to leverage the psychology principle of social proof to prey upon its targets and increase the authenticity of the threat actor's spear phishing. Proofpoint has previously observed this technique from advanced business email compromise actors such as TA2520 (Cosmic Lynx).
It is important to note that for the purposes of this blog, Proofpoint refers to each of the TA453 personas by the sender name. While Proofpoint has previously observed TA453 using compromised email accounts to send phishing emails, Proofpoint has no specific indication that these spoofed individuals were victimized by TA453. Additionally, Proofpoint regularly sees TA453 pair the same spoofed person with different actor-controlled email addresses. 
Typical TA453 Activity
In what Proofpoint researchers consider a standard TA453 campaign, the threat actor masquerades as an individual, such as a journalist or policy adjacent individual, working to collaborate with the intended target. Historically, TA453 has targeted academics, policymakers, diplomats, journalists, and human rights workers. Benign conversations that eventually lead credential harvesting links are hallmarks of TA453 activity. Proofpoint has observed limited instances of TA453 deploying malware.
In almost all cases, TA453 would engage in one-to-one conversations with their targets but this changed in mid-2022.
Times are Changing: TA453's Multiple Personalities
Proofpoint researchers observed a shift in TA453's approach starting in June 2022. In this first campaign (Figure 1), TA453 started the conversation masquerading as "Aaron Stein, Director of Research at FRPI." The actor included a variety of questions intended to generate a dialogue about Israel, the Gulf States, and the Abraham Accords. While these questions are generally meant to establish a pretext for sending a follow-up credential harvesting link or to deliver a malicious document, it is also possible they represent intelligence questions tasked to TA453. 
In the email, TA453's "Aaron Stein" launched the threat actor's use of Multi-Persona Impersonation (MPI) by referring to and including a "Richard Wike, director of global attitudes research at PEW Research Center" on the CC line.

Figure 1. TA453 email posing as an "Aaron Stein, Director of Research at FRPI."
A day after the initial email, "Richard Wike" responded (Figure 2) to the email thread likely in an attempt to establish the veracity of the request and solicit a response from the target. In this case, no malicious documents or links were observed. 

Figure 2. TA453 follow-up email using another persona.
Bringing Up BadBlood: In late June 2022, TA453 reached out to a target specializing in genome research as "Harald Ott" and cc'd two other actor-controlled accounts, "Claire Parry, Assistant Director at the Centre for Universal Health in Chatham House's Global Health Programme" and "Dr. Andrew Marshall, chief editor of Nature Biotechnology," which made this impersonation attempt a three to one MPI using organ regeneration as a lure. When the target replied to the initial email, "Harald" delivered a OneDrive link that downloaded a malicious Word doc named Ott-Lab 371.docx. The SHA256 for the file is f6456454be8cb77858d24147b1529890cd06d314aed70c07fc0b5725ac84542b. Proofpoint assesses this document represents the latest iteration of TA453's exploitation of Remote Template Injection previously reported by PwC. The template and its macros, dubbed Korg by Proofpoint, will be discussed later in this report. 

Figure 3. Screenshot of TA453 using one of its cc'd personas to further the ruse targeting a medical researcher.
While the targeting of medical personnel, specifically those involved in genome research, is not a frequent area of focus for TA453, it is not the first time this actor has demonstrated an interest in this type of research. In December 2020, TA453 conducted a phishing campaign targeting medical researchers, as detailed in Proofpoint's BadBlood blog.
Group Project: In June 2022, TA453's "Carroll Doherty" persona reached out to a prominent academic involved in nuclear arms control about a possible US versus Russia clash. This campaign ended up representing an evolution of TA453's MPI technique as the persona did not stop at reaching out to just one target but reached out to two targets at the same university. "Carroll" also cc'd three other TA453 personas on the email: "Daniel Krcmaric," "Aaron Stein," and "Sharan Grewal."

Figure 4. Timeline of TA453's Group Project email campaign.
One of the targets responded initially to the outreach email but then ghosted "Carroll." After the target failed to respond for a little over a week, "Carroll" kindly provided a OneDrive link to the article referenced in the original email (Figure 5). The link downloaded a document titled “The possible US-Russia clash.docx" SHA256: 16a961475a88313478bc2406d6b442be9809e64ea9e2a4754debcce9200cf36b. 


Figure 5. Screenshots of "Carroll" persona sending the target a malicious OneDrive link and password.
"Carroll" sent the password separately and followed up with the target to let them know the document is secure because it cannot be read without the password. Four days later, one of the cc'd TA453 personas, "Aaron Stein," dropped "Carroll" from the email thread, apologized to the target, and resent the same OneDrive link and password (Figure 6). 

Figure 6. A cc'd TA453 persona attempting to convince a target of the legitimacy of the campaign.
Similar to the document sent by "Harald," this document also used remote template injection to download Korg. 
Korg—TA453's Latest Remote Template Injection 
As noted above, some of TA453's campaigns delivered OneDrive links that hosted malicious documents. The documents are the latest version of the TA453 remote template injection documents discussed by PwC in July 2022. The password protected documents downloaded the macro enabled template documents from 354pstw4a5f8.filecloudonline[.]com. Proofpoint observed multiple campaigns reusing that specific filecloudonline[.]com host. The downloaded template, dubbed Korg by Proofpoint, has three macros: Module1.bas, Module2.bas, and ThisDocument.cls. The macros collect information such as username, list of running processes along with the user's public IP from my-ip.io and then exfiltrates that information using the Telegram API. 
At this time, Proofpoint has only observed the beaconing information and has not observed any follow-on exploitation capabilities. The lack of code execution or command and control capabilities within the TA453 macros is abnormal. Proofpoint judges that infected users may be subject to additional exploitation based on the software identified on their machines. 
Attribution
Proofpoint continues to assess that TA453 operates in support of the Islamic Revolutionary Guard Corps (IRGC). This assessment is based on a variety of evidence, including overlaps in unit numbering between Charming Kitten reports and IRGC units as identified by PwC, the US Department of Justice indictment of Monica Witt and IRGC-affiliated actors, and analysis of TA453 targeting compared to reported IRGC-IO priorities. 
Proofpoint tracks multiple subgroups of TA453 differentiated primarily by victimology, techniques, and infrastructure. Some subgroups in their typical campaigns will engage in benign conversations with targets for weeks before delivering malicious links. Conversely, another subgroup tends to immediately send a malicious link in the initial email. 
While the mere presence of specific indicators does not definitively condemn an email as TA453, indicators of a possible TA453-linked persona include:
Use of Gmail, Outlook, Hotmail, or AOL email address instead of institutional email  
Including other "personal email accounts" in the conversation
Replying to blank email 
Asking to collaborate on research about issues relating to the Middle East
Offering a Zoom call (often resulting in a credential harvesting link)
Sending unsolicited collaboration "draft" attachments
Conclusion 
All threat actors are in constant states of iterating their tools, tactics, and techniques (TTPs), advancing some while deprecating others. The use of MPI by TA453, while the group's latest technique, is likely to continue to evolve and morph as this group hunts for intelligence in support of the IRGC. Proofpoint researchers have already started to observe this potential next step with TA453 attempting to send a blank email, then respond to the blank email all while including all their "friends" on the CC line. This is likely the threat actor's attempt at bypassing security detection. 
Researchers involved in international security, particularly those specializing in Middle Eastern studies or nuclear security, should maintain a heightened sense of awareness when receiving unsolicited emails. For example, experts that are approached by journalists should check the journalist’s or their publication’s website to see if the email address belongs to them.






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

 







 

















