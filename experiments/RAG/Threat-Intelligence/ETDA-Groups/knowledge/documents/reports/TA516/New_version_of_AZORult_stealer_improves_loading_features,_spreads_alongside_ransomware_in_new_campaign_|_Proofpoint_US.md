# Reference for threat actor for "TA516"

**Title**: New version of AZORult stealer improves loading features, spreads alongside ransomware in new campaign | Proofpoint US

**Source**: https://www.proofpoint.com/us/threat-insight/post/new-version-azorult-stealer-improves-loading-features-spreads-alongside

## Content





























































New version of AZORult stealer improves loading features, spreads alongside ransomware in new campaign | Proofpoint US









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
                                    New version of AZORult stealer improves loading features, spreads alongside ransomware in new campaign
                              

 












New version of AZORult stealer improves loading features, spreads alongside ransomware in new campaign





Share with your network!








 July 30, 2018


                Proofpoint Staff
  
        

 Overview
AZORult is a robust information stealer & downloader that Proofpoint researchers originally identified in 2016 as part of a secondary infection via the Chthonic banking Trojan. We have since observed many instances of AZORult dropped via exploit kits and in fairly regular email campaigns as both a primary and secondary payload.
Recently, AZORult authors released a substantially updated version, improving both on its stealer and downloader functionality. It is noteworthy that within a day of the new update appearing on underground forums, a prolific actor used the new version in a large email campaign, leveraging its new capabilities to distribute Hermes ransomware. It is always interesting to see malware campaigns where both a stealer and ransomware are present, as this is less common [1], and especially disruptive for recipients who initially may have credentials, cryptocurrency wallets, and more stolen before losing access to their files in a subsequent ransomware attack.
AZORult Forum Advertisement
On July 17, a major update to the AZORult credential stealer and downloader was advertised on an underground forum. The change log for the new version -- Version 3.2 -- is shown below. The conditional loader feature, based on the presence of cookies, cryptocurrency wallets, and other parameters, is particularly noteworthy.
**************
Change log text:
UPD v3.2
[+] Added stealing of history from browsers (except IE and Edge)
[+] Added support for cryptocurrency wallets: Exodus, Jaxx, Mist, Ethereum, Electrum, Electrum-LTC
[+] Improved loader. Now supports unlimited links. In the admin panel, you can specify the rules for how the loader works. For example: if there are cookies or saved passwords from mysite.com, then download and run the file link[.]com/soft.exe. Also there is a rule "If there is data from cryptocurrency wallets" or "for all"
[+] Stealer can now use system proxies. If a proxy is installed on the system, but there is no connection through it, the stealer will try to connect directly (just in case)
[+] Reduced the load in the admin panel.
[+] Added to the admin panel a button for removing "dummies", i.e. reports without useful information
[+] Added to the admin panel guest statistics
[+] Added to the admin panel a geobase
**************
Campaign Analysis
On July 18, 2018, one day after the AZORult update above was announced, we observed a campaign delivering thousands of messages targeting North America that used the new version of AZORult. The messages used employment-related subjects such as “About a role” and “Job Application”. The attached documents used file names in the format of “firstname.surname_resume.doc”.

Figure 1: Email used in the July 18 campaign
The documents in this campaign were password-protected. The password was included in the body of the original email and, in this case, was ‘789’, as visible in Figure 1 above. This technique is an attempt to evade various antivirus engines, since the document itself is not malicious until the password is entered successfully. Once potential victims enter the password, they also need to enable macros for the document to download AZORult, which in turn downloads the Hermes 2.1 ransomware payload.

Figure 2: Document attachment used in the July 18 campaign
We attribute this campaign to an actor we track as TA516. In 2017 we presented research on TA516 and ways in which this actor used documents with similar resume lures to download banking Trojans or a Monero miner. Improved means of stealing cryptocurrency wallets and credentials in the new version of AZORult might also provide a connection to TA516’s demonstrated interests in cryptocurrencies.
Malware Analysis
Once the recipient opens the password-protected document and enables the embedded macros, the macros download AZORult. While there were many code changes to the malware, we focused on analyzing the updated command and control (C&C) communication protocol.
The following POST is an initial client-to-server communication, where the client sends an initial checkin request and the server responds with data XOR-encoded with a 3-byte key (The XOR key in this case was \x0d0ac8). If we decode this data, the server response begins with a base64-encoded configuration block.

Figure 3: Initial client beacon followed by the encoded server response

Figure 4: Initial client beacon followed by the server response (decoded by us manually) 
As Figure 4 shows, there is a base64 string (configuration block) included in the server response between the “<c>” and “</c>” tags. It decodes to the following, revealing cryptocurrency strings of interest:
++++-+++++
F      123    %DSK_23% *wallet*.txt,*seed*.txt,*btc*.txt,,*key*.txt,*2fa*.txt,*2fa*.png,*2fa*.jpg,*auth*.jpg,*auth*.png,*crypto*.txt,*coin*.txt,*poloniex*,*kraken*,*okex*,*binance*,*bitfinex*,*gdax*,*private*.txt,*upbit,**bcex*,*bithimb*,*hitbtc*,*bitflyer*,*kucoin*,*huobi*,*wallet.json*       10     +      -     
I      <REMOVED, IP ADDRESS OF THE INFECTED CLIENT>:<COUNTRY OF THE INFECTED CLIENT>
We can also see another encoded block after the base64 string  (only the beginning of the block is shown for brevity). This is yet another XOR-encoded data block, where the key is 4 bytes. Decoding this second encoded data block reveals additional configuration information and executable files such as mozglue.dll, nssdbm3.dll, softokn3.dll, ucrtbase.dll, or vcruntime140.dll. While the purpose of these executables is not known, we do not see any reason to send these other than to perhaps delay reverse engineering and analysis.
Next, after the initial exchange between the infected machine and the C&C server, the infected machine sends a report containing the stolen information. Again the report is XOR-encoded with the same 3-byte key; a portion of  the decoded version is shown in Figure 5. The stolen information is organized into sections:
info: basic computer information such as Windows version and computer name
pwds: this section contains stolen passwords (not confirmed)
coks: cookies or visited sites
file: contents of the cookies files and a file containing more system profiling information including machine ID, Windows version, computer name, screen resolution, local time, time zone, CPU model,  CPU count,  RAM, video card information, process listing of the infected machine, and software installed on the infected machine.

Figure 5: A report of stolen information sent by the infected machine (only a snippet is shown here)
Finally, after the initial beaconing, receiving a configuration, and exfiltrating stolen information from the infected machine, AZORult may download the next payload. For example, in the campaign described at the beginning of this post, AZORult downloads Hermes 2.1 ransomware  after it exfiltrates the victim’s data and credentials.
Conclusion
As in legitimate software development, malware authors regularly update their software to introduce competitive new features, improve usability, and otherwise differentiate their products. The recent update to AZORult includes substantial upgrades to malware that was already well-established in both the email and web-based threat landscapes. It is noteworthy that within a day of the new update appearing on underground forums, a prolific actor used the new version in a large email campaign, leveraging its new capabilities to distribute Hermes ransomware.
The potential impact of this type of attack is considerable:
The campaigns sent thousands of messages
AZORult malware, with its capabilities for credential and cryptocurrency theft, brings  potential direct financial losses for individuals as well as the opportunity for actors to establish a beachhead in affected organizations
Additional direct financial losses and business disruption via infection with Hermes ransomware.
References
[1] https://www.malware-traffic-analysis.net/2017/01/27/index2.html
[2] https://malware.dontneedcoffee.com/2018/03/CVE-2018-4878.html#gf-sundown
[3] https://www.proofpoint.com/us/threat-insight/post/threat-actors-using-legitimate-paypal-accounts-distribute-chthonic-banking
Indicators of Compromise (IOCs)

IOC


IOC Type


Description


ccf1f4d83023c51a75ba008cbd25167c2a1e55f6a8617fe004b63dcd4acc0de4


SHA-256


Malicious document


hxxp://205.185.121[.]209/azo.exe


URL


Document payload (AZORult)


3809394dceddbe1419e964cd08397e5fed4a0bbefc8be466f33614bac8794243


SHA-256


AZORult


hxxp://briancobert[.]com/index.php


URL


AZORult C&C


hxxp://205[.]185.121[.]209/5.exe


URL


AZORult payload (Hermes)


6071511eea15d5b1d9d8bf9803ad71b3fe65c455b77d683a3aaf887fa54cb447


SHA-256


Hermes
 

ET and ETPRO Suricata/Snort/ClamAV Signatures
2025885 || ET TROJAN AZORult Variant.4 Checkin






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

 







 

















