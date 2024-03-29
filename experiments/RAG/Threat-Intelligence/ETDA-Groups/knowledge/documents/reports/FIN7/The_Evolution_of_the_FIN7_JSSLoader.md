# Reference for threat actor for "FIN7"

**Title**: The Evolution of the FIN7 JSSLoader

**Source**: https://blog.morphisec.com/the-evolution-of-the-fin7-jssloader

## Content






The Evolution of the FIN7 JSSLoader
















































































ON-DEMAND WEBINAR: Morphisec's Top 10 Security Predictions - Outlook into 2024























Support
Partners
Contact Us













Products

Product Overview
Morphisec for Windows Endpoints
Morphisec for Windows Servers & Workloads
Morphisec for Linux Server Protection
Morphisec Vulnerability Visibility & Prioritization
Incident Response Services
About Moving Target Defense

Solutions

By Industry

Finance
Hedge Funds
Healthcare
Technology
Manufacturing
Legal
K-12 Education
SMB

By Use Case

Microsoft Defender AV
Microsoft Defender for Endpoint
Virtual Desktop Protection
Cloud Workload Protection
Remote Employee Security
Ransomware Prevention
Virtual Patching and Compliance
Supply Chain Attack Protection
Browser Attack Protection


Company

About Us
News & Events
Careers

Resources

Blog
Learning Center
Customer Stories 




































Products

Products
Product Overview
Morphisec for Windows Endpoints
Morphisec for Windows Servers & Workloads
Morphisec for Linux Server Protection
Morphisec Vulnerability Visibility & Prioritization
Incident Response Services
About Moving Target Defense

Solutions

Solutions
By Industry

Finance
Hedge Funds
Healthcare
Technology
Manufacturing
Legal
K-12 Education
SMB

By Use Case

Microsoft Defender AV
Microsoft Defender for Endpoint
Virtual Desktop Protection
Cloud Workload Protection
Remote Employee Security
Ransomware Prevention
Virtual Patching and Compliance
Supply Chain Attack Protection
Browser Attack Protection


Company

Company
About Us
News & Events
Careers

Resources

Resources
Learning Center
Customer Stories 

Blog
Support
Partners
Contact Us



































Cybersecurity Blog
Cybersecurity News, Threat Research, and more from the Team Spearheading the Evolution of Endpoint Security






















The Evolution of the FIN7 JSSLoader

Posted by
Arnold Osipov on January 4, 2021

Find me on:

LinkedIn
Twitter 










Tweet
















This report has been updated with assistance from the cybersecurity community.
Morphisec Labs has been tracking FIN7 (Carbanak Group) activity for the past several years. Morphisec’s ability to collect rich forensic data from memory has provided unique visibility into multiple FIN7 campaigns that our researchers were proud to share with MITRE and the InfoSec community at large. Fin7 is a well-funded financially motivated cybercrime group. Their advanced techniques and tactics were even emulated in the third round of the MITRE ATT&CK evaluations.

This report presents an attack chain that was intercepted and prevented within a customer’s network in December 2020, then will focus on a component from a typical FIN7 attack chain - JSSLoader. Though JSSLoader is well known as a minimized .NET RAT, not many details have been publicly available with respect to various capabilities such as exfiltration, persistence, auto-update, malware downloading, and more. Furthermore, in the many occasions where JSSLoader is mentioned, there are few details on the complete attack chain. The following provides a never before seen technical analysis of this infamous group’s JSSLoader as part of an end to end attack.
FIN7 JSSLOADER Technical Analysis
Below is an example of a typical phishing campaign that may lead to a FIN7 JSSLoader compromise as well as to other malwares such as QBOT; the traffic is then redirected through BlackTDS traffic distribution system. In this example an email is being sent from “Natural Health Sherpa” with an invoice to pay from Quickbooks.

Figure 1: A typical phishing campaign
Clicking the invoice link leads to a private Sharepoint directory that stores an archive file containing a VBScript (later changed to WSF-Windows Script File).

 
Figure 2: The private Sharepoint directory.
Shortly after this phishing campaign “Natural Health Sherpa” posted this on social media.

Figure 3: Natural Health Sherpa's message on social media.
This VBScript downloads and executes the next stage’s VBScript in memory. This second stage was recently introduced. The in-memory script downloads and writes a .NET module (JSSLoader) on disk, then executes the module through a scheduled task with a newly introduced timeout delay to bypass attack chain monitoring.
It is worth mentioning that the early versions of the VB scripts have a strong resemblance to the ongoing QBOT campaign that may lead to an Egregor compromise.
The JSSLoader is a RAT (Remote Access Trojan) with multiple capabilities that were introduced over time. These various capabilities are documented throughout this report. In the specific attack chain that was recently intercepted, the RAT typically executes a Takeout script which is responsible for the reflective loading and execution of a Carbanak.
Not surprisingly, the C2 hosting provider is a company named FranTech Solutions, which has been used before by the FIN7 group.
Download the complete report for details on the various capabilities of this ever-evolving RAT, as well as an analysis of the complete attack chain in which it is leveraged.
Note: Morphisec CTO Michael Gorelik contributed to this analysis.















Subscribe to our blog
Stay in the loop with industry insight, cyber security trends, and cyber attack information and company updates.






























Search Our Site





























Recent Posts














Posts by Tag



Moving Target Defense (127)


Cyber Security News (123)


Morphisec Labs (111)


Threat Research (60)


Threat Post (59)


Morphisec News (52)


Automated Moving Target Defense (8)


Defense-in-Depth (6)


in-memory attacks (6)


Gartner (4)


runtime attacks (4)


Legacy security (3)


Linux cyber security (3)


advanced threat defense (3)


threat and vulnerability management (3)


ChatGPT (2)


Gartner endpoint protection (2)


Ransomware (2)


financial cybersecurity (2)


patch management (2)


Anti-tampering (1)


Evasive loader (1)


Fileless malware (1)


Gartner Emerging Tech (1)


Healthcare cybersecurity (1)


IoT security (1)


Securing IoT devices (1)


Server security (1)


See all



























Products

Product Overview
Morphisec for Windows Endpoints
Morphisec for Windows Servers & Workloads
Morphisec for Linux Server Protection
Morphisec Vulnerability Visibility & Prioritization
Incident Response Services
About Moving Target Defense

Solutions By Industry

Banking & Finance
Hedge Funds
Healthcare
Technology
Manufacturing
Legal
K-12 Education
SMB

Solutions by Use Case

Microsoft Defender for Endpoint
Microsoft Defender AV
Virtual Desktop Protection
Ransomware Protection
Supply Chain Attack Protection
Cloud Workload Protection
Remote Employee Security
Virtual Patching & Compliance
Browser Attack Protection







Company

About Us
News & Events
Careers

Blog
Support
Partners
Contact Us
Privacy & Legal
Contact Sales
Inquire via Azure














© 2023 Morphisec Ltd. | All rights reserved































































