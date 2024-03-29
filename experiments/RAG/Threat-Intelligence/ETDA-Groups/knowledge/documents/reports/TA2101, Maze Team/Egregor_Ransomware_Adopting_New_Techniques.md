# Reference for threat actor for "TA2101, Maze Team"

**Title**: Egregor Ransomware Adopting New Techniques

**Source**: https://blog.morphisec.com/egregor-ransomware-adopting-new-techniques

## Content






Egregor Ransomware Adopting New Techniques














































































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






















Egregor Ransomware Adopting New Techniques

Posted by
Michael Gorelik on February 11, 2021

Find me on:

LinkedIn
Twitter 










Tweet
















Introducing egregor ransomware
Egregor is considered to be one of the most prolific ransomware threat groups. Yet it gained this reputation in a very short time due to its uncompromising double extortion methodology.

In this report, we will provide a detailed and anonymized coverage of Egregor ransomware's tactics, techniques, and procedures (TTPs) following an incident response activity that was conducted at the end of November 2020.  
The goal of this report is to shed light on some very different techniques for initial access, persistence, and exfiltration than what is typically reported on with respect to the Egregor group. In this report, you will not find any indication of Qbot or Cobalt Strike beacons.
Though we are not going to provide an exact attribution, you will find evidence in the report that may indicate a connection to the Revil group. We will provide evidence such as upload accounts, download links, and services that can result in additional community wide research which hopefully can lead to further conclusions.
We invite the research community to share additional insights that may correlate with the published IOCs.
Technical Introduction
Any incident response involving business compromise usually starts with the end - the impact. When the impact is ransomware, incident investigation is particularly difficult as it is done in parallel to containment activities.
This investigation wasn’t different from most that involve ransomware: 

The AD is compromised and the ransomware is deployed directly from the AD.
A search and mapping of suspicious connections to the AD are correlated to legitimate activities and connections of privileged users. RDP, pass the hash, and other techniques are taken into account.
Compromised credentials or/and a lateral movement chain is established and patient zero is identified. Obviously, if logs exist, SIEM, event viewers, VPN, AV, and other logs are considered.
In the case of ransomware, the customer would usually like to know what was exfiltrated to be able to calculate business continuity risks.
In the last stage, victims like to have a recommendation report for corrective actions that can be applied to the network.

Our incident investigation revealed that the Egregor threat group most probably exploited a VPN vulnerability to access the internal network from a Tor exit node. The attackers then scanned the network while looking for a vulnerable server. They quickly identified and exploited a second vulnerability on an old 2003 application server. This application server became our patient zero. The attackers then moved laterally between file share, application, virtualization, update, and secondary AD servers until they infiltrated to the AD. Next, they exfiltrated data through known services such as MegaUpload directly from the AD. As a final step, they encrypted the network. 

A number of interesting and unique details will be mentioned in this report:

The upload account credentials and the additional file share services
Persistence through known legitimate remote control services 
Download multiple versions of the ransomware while bypassing enterprise AV solution
The use of AES.ONE for ransomware download
Connection to Revil through Lalartu

Download the report "An Analysis of the Egregor Ransomware" for the rest of our analysis. 















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































































