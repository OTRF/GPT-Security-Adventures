# Reference for threat actor for "Pacha Group"

**Title**: Linux Server Security Threatened by Threat Actor Pacha Group - Intezer

**Source**: https://www.intezer.com/blog-pacha-group-deploying-undetected-cryptojacking-campaigns/

## Content













Linux Server Security Threatened by Threat Actor Pacha Group - Intezer






















































































 





PRODUCT 






Autonomous SOC Platform
 



Intelligent automation for triage, investigation, remediation, and escalation of serious threats 








SOLUTIONS 





  



Intezer for Reported Phishing 



NEW 







 



Intezer for SentinelOne 







 



Intezer for Microsoft Defender 







 



Intezer for CrowdStrike 







 



Intezer for SOAR 







 



Intezer for Malware Sandboxing 







FOR SERVICE PROVIDERS 






Intezer for MSSP 



Discover how Intezer helps MSSPs scale 









Want to see Intezer in action? 







 
See the Product












 





LEARN 





Blog 



Read threat analyses from Intezer’s research team, step-by-step technical tutorials, and the latest product news 







Documentation 



Dig into documentation about setup, integrations, and working with Intezer’s API 







Resources 



Check out case studies, whitepapers, 
and featured videos 







Featured Case Studies 



 




				DPD Automates SOC Tier 1 Tasks with Intezer			







				Orange Cyberdefense Automates Incident Response Process with Intezer			







				Legato Security Scales Up with Intezer Autonomous SOC			















 

Product 

Autonomous SOC Platform
Intezer for Microsoft Defender
Intezer for SentinelOne
Intezer for CrowdStrike
Intezer for SOAR
Intezer Autonomous SOC for MSSP
Intezer for Malware Sandboxing
Intezer Autonomous SOC for Reported Phishing


Learn 

Blog
Resources
Docs


FAQ
Pricing
 
Log in
 Get a Demo
 Get a Demo
 








Pacha Group, A New Threat Actor Deploying Undetected Cryptojacking Campaigns on Linux ServersWritten by  Intezer - 28 February 2019

 





























Share article







Get Free AccountJoin Now 
Top Blogs



Automating Forensic Analysis for Linux Endpoints

TL;DR We just released a new version of our popular endpoint scanner for Linux machines,...
Read more



WildCard: The APT Behind SysJoker Targets Critical Sectors in Israel

Our research team has identified a new APT group, dubbed “WildCard,” initially detected through its...
Read more



FBI Takedown: IPStorm Botnet Infrastructure Dismantled

UPDATE NOVEMBER 2023: IPStorm Infrastructure Dismantled by FBI The FBI today revealed US law enforcement’s...
Read more






Key Takeaways:
• Intezer has evidence of a new threat actor, calling it Pacha Group, which has been deploying undetected cryptojacking campaigns operating from compromised servers.
• The cryptominer employed by Pacha Group, labeled Linux.GreedyAntd by Intezer, was completely undetected by all leading engines, demonstrating the sophistication of this malware.

• The malware was found on the Linux platform and is employing sophisticated evasion techniques not commonly seen in today’s Linux threat landscape.

• The cryptominer is compromising third party servers and making them part of its infrastructure to attack additional servers. It is taking a very aggressive approach to eradicate other miners by actively scanning the system to eliminate them.
Introduction:
Cryptomining malware, also known as cryptojacking or cryptocurrency mining malware, is a relatively new cyber threat. It refers to the development of software which is designed to stealthily take over a computer’s resources and use the resources to mine bitcoin without the user’s permission.
Intezer has evidence dating back to September 2018 which shows Pacha Group has been using a cryptomining malware that has gone undetected on other engines.
The new miner employed by Pacha Group, named Linux.GreedyAntd, has shown to be more sophisticated than the average Linux threat, using evasion techniques rarely seen in Linux malware. For example, when a payload is downloaded its timestamp is replaced to remain unnoticed in the file system. This technique is widely used in Windows systems but not in Linux threats. The miner also demonstrates a remarkably aggressive behavior, implementing techniques to disable or eliminate other miners to a high degree that have not been observed previously. Once in the system, Linux.GreedyAntd will kill all other miners in the server if it finds any, using the infected system for Pacha Group’s profit.
Pacha Group is believed to be of Chinese origin, and is actively delivering new campaigns, deploying a broad number of components, many of which are undetected and operating within compromised third party servers.
Technical Analysis:
Please visit https://intezer.com//blog-technical-analysis-pacha-group to view the full technical analysis and IOCs.
 IntezerCount on Intezer’s Autonomous SOC solution to handle the security operations grunt work. Cryptocurrency Cryptojacking Cryptominer Linux Linux.GreedyAntd Malware Malware Analysis Pacha Group Threat Actor Threat IntelligenceTop Five Community Uploads | February 2019Technical Analysis: Pacha Group Deploying Undetected Cryptojacking Campaigns on Linux Servers 
Recommended Articles











 
  3 

Automating Forensic Analysis for Linux Endpoints

TL;DR We just released a new version of our popular endpoint scanner for Linux...
25 January 2024











 
  12 

WildCard: The APT Behind SysJoker Targets Critical Sectors in Israel

Our research team has identified a new APT group, dubbed “WildCard,” initially detected through...
27 November 2023











 
  14 

FBI Takedown: IPStorm Botnet Infrastructure Dismantled

UPDATE NOVEMBER 2023: IPStorm Infrastructure Dismantled by FBI The FBI today revealed US law...
14 November 2023


















 




 


Youtube
 



Linkedin
 




 



Rss
 








 Count on Intezer’s Autonomous SOC solution to handle your Level 1 SOC. Leave the SOC grunt work to Intezer. 






Log In











Product 



 
Autonomous SOC Platform
Pricing
Intezer for MSSPs
 

Autonomous SOC Platform
Pricing
Intezer for MSSPs
 








Solutions 




Intelligent SOC Automation
Microsoft Defender
CrowdStrike
SentinelOne
Reported Phishing
Malware Analysis & Sandboxing
Cloud Workload Protection
Enhanced SOAR Playbooks
 

Intelligent SOC Automation
Microsoft Defender
CrowdStrike
SentinelOne
Reported Phishing
Malware Analysis & Sandboxing
Cloud Workload Protection
Enhanced SOAR Playbooks
 








Company 




About
Contact Us
Security
Partners
News
Careers
 

About
Contact Us
Security
Partners
News
Careers
 








Learn 




Blog
FAQ
Documentation
Resources
YouTube Channel
 

Blog
FAQ
Documentation
Resources
YouTube Channel
 








Featured Resources 




How Intezer Autonomous SOC Works
Maximizing Incident Response Automation for Investigations
Intezer and SOAR
Autonomous SOC Example Weekly Report
 

How Intezer Autonomous SOC Works
Maximizing Incident Response Automation for Investigations
Intezer and SOAR
Autonomous SOC Example Weekly Report
 












 



							© intezer.com 2024 All rights reserved  |  Terms of Use  |  Privacy policy 






Youtube
 



Linkedin
 



Twitter
 



Rss
 



























 Search Generic filters Exact matches only  Search in title  Search in content  Search in excerpt 





















































 
