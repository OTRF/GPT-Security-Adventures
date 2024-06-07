# Reference for threat actor for "Pinchy Spider, Gold Southfield"

**Title**: After Russian arrests, REvil ransomware implants persist

**Source**: https://blog.reversinglabs.com/blog/after-russian-arrests-revil-rolls-on

## Content






After Russian arrests, REvil ransomware implants persist






























  <img  height="1" width="1" style="display:none" src="https://www.facebook.com/tr?id=1076912843267184&amp;ev=PageView&amp;noscript=1"> 





































New! The Buyer’s Guide to Software Supply Chain Security

          Download Now!
        


WEBINAR: Know When Your Software Is Malware | The New Era of Software Supply Chain Security

          REGISTER NOW
        


ReversingLabs is the #1 Alternative to VirusTotal

          Learn Why
        



























Solutions





Software Supply Chain Security 

Spectra Assure for Procurement


Spectra Assure for Build & Release



Automate Soc Support 

Triage


Incident Response


SIEM/SOAR


Protect Cloud File Shares



Optimize Threat Hunting 

Ransomware Feed


Malware Lab


Threat Hunting


Sandbox


Email


EDR


Threat Intelligence Platform


Threat Intelligence Platform for Microsoft Sentinel







Product & Technology





Product & Technology 

Titanium Platform


Spectra Assure for Software Supply Chain Security


ReversingLabs Threat Intelligence


ReversingLabs Elastic Threat Infrastructure


ReversingLabs Threat Analysis & Hunting


Free: Open Source Yara Rules


Integrations






Why RL?



Partners





Partners 

Become A Partner


Value Added Partners


Marketplaces



Alliances 

ReversingLabs And Synopsys







Resources





Resources 

Blog


Content Library


Webinars


Software Deconstruction Demo Series


ReversingGlass: Concepts Explained


ConversingLabs Podcast


From the Labs: YARA Rules


DEMO Videos


Learning with ReversingLabs







Company





Company 

About Us


Leadership


Careers


Series B Investment


Company News



Events 

Events



Press 

Press Releases


In the News






Demo




Contact Us


Support


Login


Blog


Developer Portal


Search

















































ReversingLabs Blog




















Threat Research

 | 
January 26, 2022 


After Russian arrests, REvil ransomware implants persist

Almost two weeks after Russian authorities claimed to have dismantled the REvil ransomware group with a string of arrests, evidence for a reduction in the availability of REvil implants has yet to appear.








Blog Author

Paul Roberts, Cyber Content Lead at ReversingLabs. Read More...




























Almost two weeks after Russian authorities orchestrated high profile arrests of cyber criminals affiliated with the notorious ransomware group, there has been little change in the availability of malicious files and implants associated with the group, ReversingLabs data shows.In fact, detections of files and other software modules associated with the REvil ransomware increased modestly in the week following the arrests by Russia’s FSB intelligence service. That contrasts with statements by the Russian government, which characterized the arrests by the Federal Security Services (FSB) as a decisive action against REvil (aka “Sodinokibi”) after which the group “ceased to exist.” With key operators no longer active, indisposed or simply taking a vacation, the availability of REvil implants has not declined, recent data suggests. However, the continued existence of such implants may also indicate shortcomings in how security industry identifies and tracks malware families or other attackers benefitting from the misidentification.The Russian government announced the arrests of 14 alleged REvil/Sodinokibi members on January 14. At the time, the move was interpreted as a friendly gesture to the West, which has long called for Russia to take action against a long list of criminal ransomware groups that operate from within the country.

In a statement the Russian government claimed that the arrests by the Russian FSB were at the behest of the United States. They came after the U.S. President Joe Biden called on Russia’s President, Vladimir Putin, to crack down on REvil and other ransomware groups operating from within Russia.
Whatever their geopolitical impact, the recent arrests have not led to a noticeable change in detections of REvil malicious files as of this writing. While this fits with a pattern in which REvil ransomware operations appear resilient in the face of efforts to take down the group,  further research that needs to be done to explain the data.
REvil Goes Whaling
First identified in 2019 after it branched off from the GandCrab ransomware group, REvil initially targeted smaller organizations like dentists offices and local governments who lacked dedicated IT and information security teams. Attacks came by way of known vulnerabilities in common platforms like Oracle Weblogic and the Pulse Secure VPN. However, that shifted in 2020, as the REvil group shifted its business model: launching fewer attacks on larger organizations that were capable of paying its multi-million dollar ransoms.To target more sophisticated firms, REvil has also shifted its strategy from commodity attacks like phishing emails to sophisticated campaigns targeting third party software providers, such as the recent REvil attack on the Kaseya IT management software.You can see this shift to more targeted, lower volume activity if you look at the graph (below) of historic REvil activity. Detections of REvil linked modules drops steeply in late 2019 from more than 500 samples a day to a much lower level of activity - a pattern of activity that has held firm ever since.

REvil retreat in July? Think again
Throughout that period, REvil has had a number of apparent brushes with death, only to reappear stronger than ever. In mid July, for example, reports circulated that servers associated with the REvil group disappeared from the Internet shortly after President Biden called on his Russian counterpart to reign in the group following two, high-profile attacks attributed to REvil: the attack on JBS, a major meat processor in the United States in June, followed by the attack on managed services provider Kaseya in early July. A known leader of the group, who uses the handle “Unknown,” also disappeared from the group’s underground forums at around that time, according to reports, suggesting that REvil was ‘on the run’ from authorities.
Data from the ReversingLabs platform tells a slightly different story. Yes, there was a 47% decline in daily REvil implant detections from the second half of July through the first half of August, from 87 new REvil implants (608 per week) to 46 (322 per week). However, that reduced level of REvil detections was above the daily average detection rate of 37 implants a day (259 per week) for the second half of 2021. 
(Note: ReversingLabs platform identifies a wide range of unique modules that track malware campaigns launched against customers. In general, the higher the number of modules we detect, the more active the threat. As with all digital evidence, however, exceptions are the rule. Among other things, false flag operations or deliberately misleading implant characteristics can lead to false conjectures. ReversingLabs is continuing to monitor the REvil activity and will share more information in future write-ups.)

A big takedown…then a reboot
Then, in October, REvil faced a much more serious threat: a coordinated offensive led by Western governments to take its infrastructure down. Among other things, the operation shuttered Happy Blog, the group’s website where data stolen from victims was leaked in an effort to compel payment of the ransom. Reports at the time spoke of governments “turning the tables” on REVil and the group being “shoved offline.”However, data from ReversingLabs suggests the actual impact on REvil ransomware operations was small. Average daily REvil/Sodinokibi detections declined 49%, from 43 new REvil implants per day (307 per week) in late-September to an average of just 22 new REvil implants per day (150 per week) by mid-October, which correlates with the coordinated government “takedown. However, by the middle of November, average daily REvil/Sodinokibi file detections rebounded to 47 new REvil implants per day (326 per week). That suggests, once again, that the takedown of REvil/Sodinokibi had only a temporary impact on the prevalence of REvil implants.

Changes following FSB arrests
Which brings us to the recent arrests of alleged REvil/Sodinokibi members by Russia’s Federal Security Service (FSB). That action was heralded as a decisive strike against the group, informed by US law enforcement tips on REvil members operating out of Russia. It resulted in 14 arrests following raids on 25 addresses in the vicinity of Moscow and St Petersburg along with the seizure of computer equipment, millions in cash and cryptocurrency and luxury vehicles.
“As a result of the joint actions of the FSB and the Ministry of Internal Affairs of Russia, the organized criminal community ceased to exist, the information infrastructure used for criminal purposes was neutralized,” the Russian government said in a statement. (Translation from the original Russian via Google Translate.)
Looking at the prevalence of REvil/Sodinokibi-linked malware, it appears as if the arrests had no discernible impact, at least when measured by the  availability of REvil-linked malicious implants. Based on ReversingLags data, the seven day daily average of REvil implants actually increased following the arrests: from 26 implants a day (180 per week) after the arrests compared with an average of 24 implants a day (169 per week) in the period just before the arrests.
More time will be needed to analyze and assess the full impact of this continued stream of data, which may be influenced by other malware groups and shortcomings in how security industry tracks and identifies malware implants.
Ronnie, talk to REvil
The persistence of malicious files linked to the group raises important questions about the threat posed by REvil and other ransomware operations, and our ability to track them. Without a doubt: threat detection is an imperfect science. But the steady stream of detections of REvil/Sodinokibi malware long after alleged “takedowns” is important to understand. Cybercriminal groups thrive on gaps in enforcement, shortcomings in the security industry and the distance between official words and actions, said Andrew Yeates, a Senior Threat Researcher at ReversingLabs.
Coordinated efforts to take down infrastructure and arrest members have effected REvil/Sodinokibi’s prevalence, ReversingLabs data shows. But these organizations can recover. That is because groups like REvil function much like corporations, with much of the work of carrying out attacks and facilitating payments left to affiliates. Arrests and “takedowns” that target affiliates often leave the core ransomware group unscathed and allow development and maintenance of the ransomware platform to continue, said Yeates. 
No silver bullets
What is the moral of this story? First: we applaud law enforcement on persistence in applying pressure on ransomware gangs leading to their eventually demise. Don’t put any stock in self proclaimed “Going out of Business” declarations by the gangs themselves. Our data suggests that those shutdowns rarely materialize. We need to find ways in being able to protect ourselves and track the activity of such groups. Careful review of available data can provide some insights, but it can also uncover other areas of research that needs to performed to best understand the activity of different malware gangs and their legacy.Meanwhile, we should focus on improving internal security through programs like phishing and malware detection and as well as strong authentication. Beyond that, best practices like patch management, intrusion detection and endpoint security represent the best way to stay ahead of the continuing threats that groups like REvil pose.
“Further lobbying for global policing of cybercrime is supremely important, along with modernizing organizations’ security capabilities, awareness of the severity to board members, and education on countermeasures are the key to shifting the balance”Andrew Yeates BSc(Hons), PGCert, CISSP, ReversingLabs Senior Threat Researcher
Organizations need to build the capacity to model threats and evaluate their defenses in light of likely attacks by groups like REvil. ReversingLabs helps our customers with this problem. Our Threat Intelligence feed for ransomware uses advanced static and dynamic analysis engines to generate both network and file indicator lists. Those indicators are matched to standardized MITRE ATT&CK tags to streamline threat modeling and provide a more complete picture of cyber risk across an organization.Security engineers use these threat models to determine if there are needed detection methods missing or misconfigured within their organization. They can also signal what additional logs would be beneficial to collect or create, or if existing prevention and blocking rules are aligned with threats, or outdated and in need of tweaking or replacement.Don’t hesitate to contact us if you’d like to learn more about how we help organizations combat ransomware or to schedule a demonstration.
Clarification: January 27, 2022This blog post has been updated to indicate that ReversingLabs analysis is based on the continuous availability of REvil linked malicious implants, which may or may not be linked to the REvil ransomware gang and its affiliates. ReversingLabs continues to monitor this activity and we will share more information and insights in future write-ups as data becomes available.
Update: January 28, 2022This blog post has been further updated to emphasize that ReversingLabs data does not conclusively indicate whether or not the REvil group continues to operate and to reiterate that more time is needed to analyze threat data related to REvil and conduct other research.
 

Get up to speed on key trends and understand the landscape with The State of Software Supply Chain Security 2024. Plus: Learn about ReversingLabs Spectra Assure for software supply chain security.



Keep learning

Update your understanding: Buyer's Guide for Software Supply Chain Security
Join the Webinar: Why you need to upgrade your AppSec for the new era
Get the report and take action: The State of Supply Chain Security 2024
Join the discussion: State of Software Supply Chain Security Webinar
See Gartner's guidance on managing software supply chain risk





Tags: 
Research
Threat Research

More Blog Posts






Artificial Intelligence (AI)/Machine Learning (ML)
February 14, 2024
5 software supply chain attacks you can learn from

2023 was a big year for software security. Here are the attacks with key takeaways to help you get out in front of risk in 2024.

Read More







Company & Events
February 14, 2024
Meet the New RL Partner Program

The RL Partner Program provides resellers, distributors, consultants, MSSPs, and technology providers tools to extend RL solutions to more organizations.

Read More







AppSec & Supply Chain Security
February 13, 2024
Software supply chain security: Upgrade your AppSec for a new era

Do you trust your AppSec? Upgrade your approach with complex binary analysis — the next generation of tooling for the era of software supply chain security.

Read More

























































Topics

 All Blog Posts
 AppSec & Supply Chain Security
 Dev & DevSecOps
 Threat Research
 Security Operations
 Products & Technology
 Company & Events









Follow us

X
YouTube
LinkedIn









Subscribe
Get our blog delivered to your in-box weekly to stay up to date on key trends, analysis and best practices across threat intelligence and software supply chain security.













Special Reports




The State of Software Supply Chain Security 2024 
January 16, 2024











Latest Blog Posts


The State of Open Source Software Security
 Conversations About Threat Hunting and Software Supply Chain Security



Development Secrets
 Glassboard conversations with ReversingLabs Field CISO Matt Rose



Software Package Deconstruction: Video Conferencing Software
 Analyzing Risks To Your Software Supply Chain
























Software Supply Chain Security Hotline
If you need immediate assistance with a software supply chain security issue, you can contact us here.
sscs incident response



Blog
Webinars
Demo Videos


Events
In the News
Glossary


About Us
Careers
Contact Us















Privacy Policy | 
          Cookies
All rights reserved ReversingLabs © 2024























































