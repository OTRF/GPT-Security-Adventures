# Reference for threat actor for "Molerats, Extreme Jackal, Gaza Cybergang"

**Title**: TA402 Uses Complex IronWind Infection Chains to Target Middle East-Based Government Entities  | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/threat-insight/ta402-uses-complex-ironwind-infection-chains-target-middle-east-based-government

## Content
































































TA402 Uses Complex IronWind Infection Chains to Target Middle East-Based Government Entities  | Proofpoint US









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
                                    TA402 Uses Complex IronWind Infection Chains to Target Middle East-Based Government Entities 
                              

 












TA402 Uses Complex IronWind Infection Chains to Target Middle East-Based Government Entities 





Share with your network!








 November 14, 2023


                Joshua Miller and the Proofpoint Threat Research Team 
  
        

 Key takeaways 
From July through October 2023, Proofpoint researchers observed TA402 engage in phishing campaigns that delivered a new initial access downloader dubbed IronWind. The downloader was followed by additional stages that consisted of downloaded shellcode.  
During the same period, TA402 adjusted its delivery methods, moving from using Dropbox links to using XLL and RAR file attachments, likely to evade detection efforts.  
This threat actor has consistently engaged in extremely targeted activity, pursuing less than five organizations with any single campaign. They have also maintained a strong focus on government entities based in the Middle East and North Africa.  
Proofpoint has tracked TA402 since 2020. Our researchers assess the threat actor is a Middle Eastern advanced persistent threat (APT) group that historically has operated in the interests of the Palestinian Territories and overlaps with public reporting on Molerats, Gaza Cybergang, Frankenstein, and WIRTE.  
Overview 
In mid-2023, Proofpoint researchers first identified TA402 (Molerats, Gaza Cybergang, Frankenstein, WIRTE) activity using a labyrinthine infection chain to target Middle Eastern governments with a new initial access downloader Proofpoint has dubbed IronWind. From July through October 2023, TA402 utilized three variations of this infection chain—Dropbox links, XLL file attachments, and RAR file attachments—with each variant consistently leading to the download of a DLL containing the multifunctional malware. In these campaigns, TA402 also pivoted away from its use of cloud services like Dropbox API, which Proofpoint researchers observed in activity from 2021 and 2022, to using actor-controlled infrastructure for C2 communication.  
As of late October 2023, Proofpoint researchers had not observed any changes in targeting by   TA402, an APT group that historically has operated in the interests of the Palestinian Territories, nor identified any indications of an altered mandate despite the current conflict in the region. It remains possible that this threat actor will redirect its resources as events continue to unfold.   
Campaign details and IronWind 
July 2023 Activity: In July 2023, Proofpoint researchers observed the first of TA402’s new, more convoluted infection chain as compared to prior campaign activity from 2021 and 2022 (Figures 1 and 2).  

Figure 1. TA402 infection chain used from November 2021 to January 2022.  

Figure 2. TA402 infection chain used in July 2023 campaign. 
TA402 engaged in a phishing campaign using a compromised Ministry of Foreign Affairs email account to target Middle Eastern government entities. The emails used an economic-themed social engineering lure ("برنامج التعاون الإقتصادي مع دول مجلس التعاون الخليجي 2023-2024" [Machine Translation: Economic cooperation program with the countries of the Gulf Cooperation Council 2023-2024"]) to deliver a Drobox link that downloaded a malicious Microsoft PowerPoint Add-in (PPAM) file. The PPAM file contained a macro that dropped three files: version.dll (IronWind), timeout.exe, and gatherNetworkInfo.vbs. Timeout.exe was used to sideload IronWind. Once sideloaded, IronWind sent an HTTP GET request to a known TA402 C2 domain, theconomics[.]net, which was hosted on 191.101.78[.]189 at the time of analysis in August 2023. Proofpoint researchers have observed TA402 leveraging Dropbox for malware delivery since at least December 2021. 
After receiving the HTTP GET request, the C2 responded with shellcode that represented the third stage of the infection chain. During Proofpoint’s analysis, the shellcode used reflective .NET loaders to conduct WMI queries. The shellcode also served as a multipurpose loader, downloading the fourth stage—a .NET executable that used SharpSploit, a .NET post-exploitation library written in C#.  
The .NET executable continued to use HTTPS POSTs and GETs to theconomics[.]net for C2 and received JSON responses. It passed authentication via a custom UserAgent string, "Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:<tag>) Gecko/<auth> Firefox/3.15" and almost certainly would have downloaded additional shellcode payloads. Based on Proofpoint analysis, this UserAgent is unique enough to be used for detection purposes. Proofpoint researchers did not observe the fifth stage at the time of analysis but took note that the last stage payload contained unused code, suggesting TA402 may be making further updates and adjustments to the malware.  
August 2023 activity: In August 2023, TA402 shifted to sending an attached XLL file to load IronWind using “قائمة الأشخاص والكيانات (المصنفة إرهابية) من قبل هيئة مكافحة غسيل الأموال وتمويل الإرهاب” as a lure instead of using a malicious PPAM file delivered via Drobox. The machine translation of the lure is as follows: “List of persons and entities (designated as terrorists) by the Anti-Money Laundering and Terrorist Financing Authority.” TA402 used the same compromised Ministry of Foreign Affairs email account observed in the July activity. As part of the initial infection process, TA402 sent a base64 encoded check in to Request Inspector—a third-party service for creating endpoints for HTTP requests—to exfiltrate some system information. 
October 2023 activity: In October 2023, TA402 shifted a portion of its infection chain yet again. This time the threat actor sent a RAR file attachment that contained a renamed version of tabcal.exe for sideloading IronWind and propsys.dll (IronWind) instead of using a malicious PPAM file delivered via Dropbox or an attached XLL file to load the malware. The delivered malware again used Request Inspector for initial check in and a new TA402 C2 domain, inclusive-economy[.]com.  
TA402 also continued to leverage a compromised Ministry of Foreign Affairs email account to send phishing emails with the lure "تقريــر وتوصيــات الـدورة (110) بخصوص الحرب على غزة,” which translates to “Report and Recommendations of the 110th Session on the War on Gaza.” Currently, TA402 only appears to be using the conflict for lure purposes. Additionally, TA402 continues to phish, indicating the conflict has not significantly disrupted the group’s operations. 
IronWind: PDB analysis  
During malware analysis, Proofpoint researchers identified TA402 had failed to sanitize the group’s PDB paths during malware development for multiple stages. A YARA rule for hunting purposes is attached at the end of this blog.  
Based on the following PDB paths, Proofpoint researchers assess with moderate confidence that the IronWind malware project name is \tornado\ and malware development is broken out by function, including IA (the IronWind dropper), stager (the stager DLL), and payloads.  
VT Stage 1: C:\Users\Win\Desktop\Reno\NewTor\27-07-2023\tornado\tornado\Payloads\BAR_33\I.A\out\IA.pdb 
July 2023 Stage 2: C:\Users\User\Desktop\tornado\Payloads\WKS_10\I.A\out\stagerx64.pdb 
August 2023 Stage 1: C:\Users\Win\Desktop\Reno\NewTor\27-07-2023\tornado\tornado\Payloads\BAR_38\I.A\out\IA.pdb 
August 2023 Stage 2: C:\Users\Win\Desktop\Reno\NewTor\NewIA-Tornado-WithStealer\Payloads\KIL_03\I.A\out\stagerx64.pdb 
Stage 4: K:\prj\WIP\C# - Payload\Client-Side\https\client-Divided\KALV\obj\Release\KALV.pdb 
Geofencing 
TA402 regularly employs geofencing techniques to make detection of its malicious activity more difficult. This aspect of the threat actor’s tactics, techniques, and procedures has remained consistent since at least 2020. Even with the more elaborate infection chains observed in 2023, TA402 continues to include URLs that will at times redirect to decoy documents hosted on legitimate document hosting platforms if the geofencing is not bypassed.   
Attribution 
Proofpoint researchers attributed the campaigns to TA402 based on tactics, techniques, and victimology. The 2023 campaigns share similarly themed lures as historical TA402 activity and retain a focus on Arabic-speaking targets located in the Middle East. Over the years, TA402 has consistently targeted government entities based in the Middle East and North Africa, at times going after the same targets repeatedly. TA402’s use of compromised Ministry of Foreign Affairs email accounts, geofencing, and decoy documents additionally contributed to the attribution. 
Proofpoint researchers also assess TA402 operates in support of Palestinian espionage objectives with a focus on intelligence collection. This is consistent with prior Proofpoint published reports on this threat actor. While Proofpoint recognizes that TA402 overlaps with a number of publicly reported threat actors, including Molerats, WIRTE, and Frankenstein, Proofpoint researchers cluster independently based on internal malware analysis and investigations.  
Conclusion 
Based on Proofpoint’s tracking of this threat actor since 2020, TA402 remains a persistent and innovative threat actor that routinely retools its attack methods and malware in support of its cyber espionage mandate. Its ongoing use of geofencing and decoy documents continues to serve its detection evasion efforts. While TA402 is an intelligence collection focused threat actor with a specific interest in Middle Eastern and North African government entities, the group could find itself under direction to adjust its targeting or social engineering lures in reaction to the ongoing Israel-Hamas conflict.  
Indicators of Compromise (IOCs) 

INDICATOR 


TYPE 


9b2a16cbe5af12b486d31b68ef397d6bc48b2736e6b388ad8895b588f1831f47  
 
5d773e734290b93649a41ccda63772560b4fa25ba715b17df7b9f18883679160  
 
19f452239dadcd7544f055d26199cb482c1f6ae5486309bde1526174e926146a  
 
A4bf96aee6284effb4c4fe0ccfee7b32d497e45408e253fb8e1199454e5c65a3  
 
26cb6055be1ee503f87d040c84c0a7cacb245b4182445e3eee47ed6e073eca47  
 
cbb89aac5a2c93a02305846f9353b013e6703813d4b6baff8eb89ee938647af3 
  
c98dc0b930ea67992921d9f0848713deaa5bba8b4ba21effd0b00595dd9ed28c  
 
ac227dd5c97a36f54e4fa02df4e4c0339b513e4f8049616e2a815a108e34552f  
 
6ab5a0b7080e783bba9b3ec53889e82ca4f2d304e67bd139aa267c22c281a368  
 
e2ba2d3d2c1f0b5143d1cd291f6a09abe1c53e570800d8ae43622426c1c4343c  
 
d8cde28cf2a5884daddf6e3bc26c80f66bc3737e426b4ba747d49d154999fbc1  
 
81fc4a5b1d22efba961baa695aa53201397505e2a6024743ed58da7bf0b4a97f  
 
3b2a6c7a39f49e790286185f2d078e17844df1349b713f278ecef1defb4d6b04  
 
7bddde9708118f709b063da526640a4132718d3d638505aafce5a20d404b2761 
 
883e035f893483b9921d054b3fa014cef90d90b10dcba7d342def8be2e98ce3c 
 
4b0a48d698240504c4ff6275dc735c8162e57f92224fb1d2d6393890b82a4206 
 
4018b462f2fcf1b0452ecd88ab64ddc5647d1857481f50fa915070f5f1858115 
 
3d80ea70b0c00d12f2ba2c7b1541f7d0f80005a38a173e6962b24f01d4a2a1de 


SHA256 


theconomics[.]net |191.101.78[.]189 


Domain | IP (C2) 


inclusive-economy[.]com 
healthcaption[.]com 


Domains 

ET Signatures 
2049153 - ET MALWARE Win32/TA402 CnC User-Agent
2049154 - ET MALWARE Win32/TA402 CnC Response M1
2049155 - ET MALWARE Win32/TA402 CnC Response M2
2049158 - ET MALWARE Win32/TA402 Checkin
2049159 - ET MALWARE Win32/TA402 Checkin M2
2049160 - ET MALWARE TA402 CnC Domain in DNS Lookup
2049161 - ET MALWARE Observed TA402 Domain in TLS SNI
2049162 - ET MALWARE TA402 CnC Domain in DNS Lookup
2049163 - ET MALWARE Observed TA402 Domain in TLS SNI
2049164 - ET MALWARE Win32/TA402 CnC Activity (POST)
2049165 - ET MALWARE Win32/TA402 CnC Activity (GET)
YARA Rule 
rule TA402_PDB 
{ meta: 
    author = "Proofpoint inc." 
    description = "Finds TA402 related PDB paths" 
    date = “2023-09-27” 
  strings: 
$pdb1 = "C:\\Users\\Win\\Desktop\\Reno\\NewTor" ascii wide  
$pdb2 = "C:\\Users\\User\\Desktop\\tornado\\" ascii wide  
$pdb3 = "K:\\prj\\WIP\\C# - Payload\\Client-Side\\https\\client-Divided\\KALV\\obj\\Release\\KALV.pdb" ascii wide  
$pdb4 = "K:\\prj\\WIP\\C# - Payload\\Client-Side" ascii wide  
  condition: 
any of them 
} 






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

 







 

















