# Reference for threat actor for "Bluenoroff, APT 38, Stardust Chollima"

**Title**: TA444: APT Startup Aimed at Acquisition (of Your Funds) | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/threat-insight/ta444-apt-startup-aimed-at-your-funds

## Content

































































TA444: APT Startup Aimed at Acquisition (of Your Funds) | Proofpoint US









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
                                    TA444: The APT Startup Aimed at Acquisition (of Your Funds)
                              

 












TA444: The APT Startup Aimed at Acquisition (of Your Funds)





Share with your network!








 January 25, 2023


                Greg Lesnewich and the Proofpoint Threat Research Team
  
        

 
Key Takeaways
TA444 is a North Korea state-sponsored threat actor that tested numerous infection methods in 2022 with varying degrees of success.
TA444 is a unicorn among state-aligned actors as its primary operations are financially motivated, and their infection chains are often a microcosm of the cybercrime threat landscape at large. 
While TA444 has been active in its current form of targeting cryptocurrencies since at least 2017, the group has adopted an upstart mentality during the latter stages of 2022. 
Overview
In the world of tech startups, luminaries and charlatans alike boast of the value of rapid iteration, testing products on the fly, and failing forward. TA444, a North Korea-sponsored advanced persistent threat group, has taken these mantras to heart. TA444, which overlaps with public activity called APT38, Bluenoroff, BlackAlicanto, Stardust Chollima, and COPERNICIUM, is likely tasked with generating revenue for the North Korean regime. That tasking has historically involved the targeting of banks to ultimately funnel cash to the Hermit Kingdom or handlers abroad. More recently, TA444 has turned its attention, much like the tech industry, to cryptocurrency. While we do not know if the group has ping pong tables or kegs of some overrated IPA in its workspace, TA444 does mirror the startup culture in its devotion to the dollar and to the grind. 
Fail Fast with File Type Variations
Back in its infant interest with blockchain and cryptocurrency, TA444 had two main avenues of initial access: an LNK-oriented delivery chain and a chain beginning with documents using remote templates. These campaigns were typically referred to as DangerousPassword, CryptoCore, or SnatchCrypto. In 2022, TA444 continued to use both methods, but had also tried its hand at other file types for initial access. Despite having not heavily relied on macros in previous campaigns, TA444 seemed to mirror the cybercrime landscape in the summer and fall, attempting to find additional file types to stuff its payloads into.
It is unclear if the threat actor had a hackathon to generate these ideas, but we believe some of the (dramatized) conversations may have sounded like this:
          MSI Installer files? Let’s give it a shot but try a few varieties and see what sticks!
          Virtual Hard Drive? TA580 used it to drop Bumblebee, why don’t we have a VHD chain?
          ISOs to bypass MoTW? If the market wants it, let’s give it to them!
          Compiled HTML? What are we, TA406? Eh, give it a try anyway!
We can experiment all we want but we must keep up with our CageyChameleon and Astraeus quotas to meet our OKRs!
Equally as surprising as the variance in delivery methods is the lack of a consistent payload at the end of the delivery chains. When other financially-oriented threat actors test delivery methods, they tend to load their traditional payloads; this is not the case with TA444. This suggests that there is an embedded, or at least a devoted, malware development element alongside TA444 operators.
What’s Our Go-to-Market?
To convince victims to click on malicious links, TA444 has a complete marketing strategy to increase its chances of new ARR (Annual Recurring Revenue). It all starts with crafting lure content that may be of interest or necessity to the target. These can include analyses of cryptocurrency blockchains, job opportunities at prestigious firms, or salary adjustments.

Figure 1. Example TA444 email lure using salary adjustment themes.
TA444 has abused email marketing tools like SendInBlue and SendGrid to engage with its target audience. These serve as redirectors to either cloud-hosted files or connect the victim directly to TA444 infrastructure. Additionally, the use of such links removes some stigma from the user of clicking on an unknown link, as marketing links will not necessarily get called out by phishing training.
Like other entities in the tech and cryptocurrency space, someone in TA444’s organization oversees socials. This is a very strong component of TA444’s practice, as the threat actor has continued to use LinkedIn to engage with victims prior to delivering links to malware. Proofpoint has observed this group demonstrating workable understandings of English, Spanish, Polish, and Japanese.
Test in Prod
In early December 2022, Proofpoint researchers observed a significant deviation from normal TA444 operations via a relatively basic credential harvesting campaign. A TA444 C2 domain sent OneDrive phishing emails rife with typos to a wide variety of targets in the United States and Canada, spanning several verticals including education, government, and healthcare, in addition to financial verticals. The lure emails enticed users to click a SendGrid URL which redirected to a credential harvesting page. The deviation in TA444’s targeting and volume of messages made us thoroughly analyze the campaign to both understand the activity, but also challenged our assumptions about the group. This spam wave alone nearly doubled the total volume of TA444 email messages we had observed in our data during 2022, so we were concerned about false positive detection, as well as understanding a potential change in TA444 objectives.   
The from header used the term Admin and the target domain name, but all used the same envelope-from email address (admin[@]sharedrive[.]ink) and subject (Invoice spelled with a lowercase L).

Figure 2. TA444 phishing email that deviated from expected themes and targeting.
The SendGrid URLs are used to redirect targets to the domain superiorexhbits[.]com which uses common phishing tactics such as loading the victim's iconography via the logo-rendering service ClearBit. This sprawling credential harvesting activity is a deviation from normal TA444 campaigns, which typically involve the direct deployment of malware. In fact, this same domain was observed serving a TA444 VHD containing Cur1Agent on the same day.
Proofpoint attributed this campaign with moderate to moderately high confidence based on the exclusivity of TA444 infrastructure. Other domains hosted on that IP match previous TA444 typo squats. The emails also had valid DMARC and SPF records, indicating that the sender has control of that domain. Proofpoint cannot rule out that the TA444 server was compromised by another actor to send the phishing links. It is also possible that TA444, like other North Korean actors such as Andariel, has begun its own moonlighting operations. If this occurred, we would anticipate seeing tool and infrastructure re-use as well as continued deviation of targeting away from major cryptocurrency and financial institutions.
The Culture is the Foundation
While TA444 has experimented with new lines of production, their core families still carry the brunt of their infections. The CageyChameleon (aka CabbageRAT) family has expanded its functionality but still operates as a victim-profiling framework, exfiltrating running processes and host information while setting up the potential to launch subsequent tooling loaded from the command-and-control server. The lure LNKs used to initiate execution are still often titled Password.txt.lnk.

Figure 3. Decrypted CageyChameleon data exfiltration.
Similarly, TA444 has stayed the course with its infrastructure deployments and document content, effectively reusing lure iconography in second-stage macro-laden files and borrowing content directly from entities it is spoofing. First stage remote template files have adapted to not only download the second-stage macro (tracked as Astraeus by Proofpoint) but the first stage now contains an obfuscated Cardinal backdoor, as noted by PWC and Kaspersky.

Figure 4. TA444 first-stage lure document themes.
Security researchers have observed TA444 deploying an impressive set of post-exploitation backdoors in its history, including msoRAT, Cardinal (default.rdp), the Rantankba suite, CHEESETRAY, and DYEPACK, as well as passive backdoors, virtualized listeners, and browser extensions to facilitate theft.
Attribution
Proofpoint clusters TA444 activities based on malware lineage, behavioral heuristics and traits of first-stage tooling meant to fool targeted users, distinctive infrastructure usage, and targeting of financial entities, along with other factors. Historic TA444 operations, such as the 2016 Bangladesh Bank heist and targeting of cryptocurrency entities, have been linked to the North Korean government by the United States.
The United States Treasury Department levied sanctions against two coin mixing services, Tornado Cash and BlenderIO, for allowing TA444 operators to launder over $120 million of cryptocurrency stolen from intrusions into various bridge and exchange entities. The US Federal Bureau of Investigation attributed the heist of a major cryptocurrency bridge to APT38, a group which heavily overlaps with TA444, where funds were later mixed in BlenderIO. This attribution underlines how reliant TA444 is on the cryptocurrency ecosystem to steal funds, create an avenue to launder them, and cash out. Recent TA444 activity highlights how willing the adversary is to adapt their methods to continue to profit from its intrusions, and new services will like aide them in their efforts, even if unintentionally.
Conclusion
While we may poke fun at its broad campaigns and ease of clustering, TA444 is an astute and capable adversary that is willing and able to defraud victims for hundreds of millions of dollars. TA444 and related clusters are assessed to have stolen nearly $400 million dollars’ worth of cryptocurrency and related assets in 2021. In 2022, the group surpassed that value in a single heist worth over $500 million, gathering more than $1 billion during 2022. North Korea, like other cryptocurrency enthusiasts, has weathered the declining value of cryptocurrencies, but remains engaged in its efforts to use cryptocurrency as a vehicle to provide usable funds to the regime.
ET Signatures
2043279- ET MALWARE TA444 Related Domain in DNS Lookup (updatezone .org)
2043280- ET MALWARE TA444 Related Domain in DNS Lookup (autoprotect .com .de)
2043281- ET MALWARE TA444 Related Domain in DNS Lookup (autoprotect .gb .net)
2043282- ET MALWARE TA444 Related Domain in DNS Lookup (azure-security .online)
2043283- ET MALWARE TA444 Related Domain in DNS Lookup (azure-security .site)
2043284- ET MALWARE TA444 Related Domain in DNS Lookup (hoststudio .org)
2043285- ET MALWARE TA444 Related Domain in DNS Lookup (thecloudnet .org)
2037802- ET MALWARE TA444 Related Domain in DNS Lookup (documentworkspace .io)
2037803- ET MALWARE TA444 Related Domain in DNS Lookup (fclouddown .co)
2037804- ET MALWARE TA444 Related Domain in DNS Lookup (googlesheet .info)
2037883- ET MALWARE TA444 Related Domain in DNS Lookup (inst .shconstmarket .com)
2037884- ET MALWARE TA444 Related Domain in DNS Lookup (web .shconstmarket .com)
2037885- ET MALWARE TA444 Related Domain in DNS Lookup (wordonline .cloud)
2038542- ET MALWARE Observed DNS Query to TA444 Domain (cooporatestock .com)
2038543- ET MALWARE Observed DNS Query to TA444 Domain (finxiio .com)
2038544- ET MALWARE Observed DNS Query to TA444 Domain (1drvmicrosoft .com)
2038546- ET MALWARE Observed DNS Query to TA444 Domain (ledger-cloud .com)
2038547- ET MALWARE Observed DNS Query to TA444 Domain (globiscapital .co)
2038548- ET MALWARE Observed DNS Query to TA444 Domain (wpsonline .co)
2038709- ET MALWARE Observed DNS Query to TA444 Domain (wps .wpsonline .co)
2038710- ET MALWARE Observed DNS Query to TA444 Domain (documentshare .info)
2038711- ET MALWARE Observed DNS Query to TA444 Domain (unchained-capital .co)
2038712- ET MALWARE Observed DNS Query to TA444 Domain (cloud .globiscapital .co)
2038713- ET MALWARE Observed DNS Query to TA444 Domain (shconstmarket .com)
2038714- ET MALWARE Observed DNS Query to TA444 Domain (stablehouses .info)
2038715- ET MALWARE Observed DNS Query to TA444 Domain (edit .wpsonline .co)
2038716- ET MALWARE Observed DNS Query to TA444 Domain (bankofamerica .us .org)
2038717- ET MALWARE Observed DNS Query to TA444 Domain (salt1ending .com)
2038718- ET MALWARE Observed DNS Query to TA444 Domain (cloud .jbic .us)
2038720- ET MALWARE Observed DNS Query to TA444 Domain (share .anobaka .info)
2038721- ET MALWARE Observed DNS Query to TA444 Domain (vote .anobaka .info)
2038722- ET MALWARE Observed DNS Query to TA444 Domain (cloud .wpic .ink)
2038762- ET MALWARE Observed DNS Query to TA444 Domain (careersbankofamerica .us)
2038763- ET MALWARE Observed DNS Query to TA444 Domain (mufg .tokyo)
2038764- ET MALWARE Observed DNS Query to TA444 Domain (azure-protect .online)
2038785- ET MALWARE Observed DNS Query to TA444 Domain (azure-protection .cloud)
2038786- ET MALWARE Observed DNS Query to TA444 Domain (bankofamerica .nyc)
2038787- ET MALWARE Observed TA444 Domain (bankofamerica .nyc in TLS SNI)
2038788- ET MALWARE Observed TA444 Domain (azure-protection .cloud in TLS SNI)
2038789- ET MALWARE Observed TA444 Domain (careersbankofamerica .us in TLS SNI)
2038790- ET MALWARE Observed TA444 Domain (azure-protect .online in TLS SNI)
2038791- ET MALWARE Observed TA444 Domain (mufg .tokyo in TLS SNI)
2038845- ET MALWARE Observed DNS Query to TA444 Domain (cloud .tptf .ltd)
2038846- ET MALWARE Observed DNS Query to TA444 Domain (careers .bankofamerica .nyc)
2038847- ET MALWARE Observed DNS Query to TA444 Domain (bankofamerica .offerings .cloud)
2038848- ET MALWARE Observed DNS Query to TA444 Domain (bankofamerica .tel)
2038849- ET MALWARE Observed DNS Query to TA444 Domain (cloud .mufg .uk)
2038850- ET MALWARE Observed TA444 Domain (cloud .tptf .ltd in TLS SNI)
2038851- ET MALWARE Observed TA444 Domain (bankofamerica .tel in TLS SNI)
2038852- ET MALWARE Observed TA444 Domain (cloud .mufg .uk in TLS SNI)
2038853- ET MALWARE Observed TA444 Domain (bankofamerica .offerings .cloud in TLS SNI)
2038854- ET MALWARE Observed TA444 Domain (careers .bankofamerica .nyc in TLS SNI)
2038919- ET MALWARE Observed DNS Query to TA444 Domain (docuprivacy .com)
2038920- ET MALWARE Observed DNS Query to TA444 Domain (share .anobaka .info)
2038921- ET MALWARE Observed DNS Query to TA444 Domain (privacysign .org)
2038922- ET MALWARE Observed DNS Query to TA444 Domain (ms .onlineshares .cloud)
2038923- ET MALWARE Observed DNS Query to TA444 Domain (team .msteam .biz)
2038924- ET MALWARE Observed DNS Query to TA444 Domain (mizuhogroup .us)
2038925- ET MALWARE Observed DNS Query to TA444 Domain (docs .azurehosting .co)
2038926- ET MALWARE Observed DNS Query to TA444 Domain (tptf .fund)
2038927- ET MALWARE Observed DNS Query to TA444 Domain (perseus .bond)
2038928- ET MALWARE Observed DNS Query to TA444 Domain (smbcgroup .us)
2038929- ET MALWARE Observed DNS Query to TA444 Domain (tptf .cloud)
2038936- ET MALWARE Observed TA444 Domain (tptf .fund in TLS SNI)
2038937- ET MALWARE Observed TA444 Domain (docs .azurehosting .co in TLS SNI)
2038938- ET MALWARE Observed TA444 Domain (team .msteam .biz in TLS SNI)
2038939- ET MALWARE Observed TA444 Domain (share .anobaka .info in TLS SNI)
2038940- ET MALWARE Observed TA444 Domain (smbcgroup .us in TLS SNI)
2038941- ET MALWARE Observed TA444 Domain (perseus .bond in TLS SNI)
2038942- ET MALWARE Observed TA444 Domain (docuprivacy .com in TLS SNI)
2038943- ET MALWARE Observed TA444 Domain (privacysign .org in TLS SNI)
2038944- ET MALWARE Observed TA444 Domain (mizuhogroup .us in TLS SNI)
2038945- ET MALWARE Observed TA444 Domain (ms .onlineshares .cloud in TLS SNI)
2038946- ET MALWARE Observed TA444 Domain (tptf .cloud in TLS SNI)
2038987- ET MALWARE TA444 Related Domain in DNS Lookup (onlinecloud .cloud)
2039041- ET MALWARE TA444 Domain in DNS Lookup (mufg .ink)
2039042- ET MALWARE TA444 Domain in DNS Lookup (mufg .us .org)
2039043- ET MALWARE Observed TA444 Domain (mufg .ink in TLS SNI)
2039044- ET MALWARE Observed TA444 Domain (mufg .us .org in TLS SNI)
2039808- ET MALWARE TA444 Domain in DNS Lookup (gdocshare .one)
2039809- ET MALWARE Observed TA444 Domain (gdocshare .one in TLS SNI)
2039823- ET MALWARE TA444 Domain in DNS Lookup (sharedrive .ink)
2039824- ET MALWARE TA444 Domain in DNS Lookup (dnx .capital)
2039825- ET MALWARE Observed TA444 Domain (sharedrive .ink in TLS SNI)
2039826- ET MALWARE Observed TA444 Domain (dnx .capital in TLS SNI)






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

 







 

















