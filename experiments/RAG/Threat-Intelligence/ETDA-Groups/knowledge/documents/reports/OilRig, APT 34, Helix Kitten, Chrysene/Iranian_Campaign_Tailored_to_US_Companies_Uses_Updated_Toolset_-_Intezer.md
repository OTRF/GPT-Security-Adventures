# Reference for threat actor for "OilRig, APT 34, Helix Kitten, Chrysene"

**Title**: Iranian Campaign Tailored to US Companies Uses Updated Toolset - Intezer

**Source**: https://intezer.com/blog-new-iranian-campaign-tailored-to-us-companies-uses-updated-toolset/

## Content













Iranian Campaign Tailored to US Companies Uses Updated Toolset - Intezer






















































































 





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
 








New Iranian Campaign Tailored to US Companies Utilizes an Updated ToolsetWritten by Paul Litvak and Michael Kajiloti - 30 January 2020

 





























Share article







Get Free AccountJoin NowIntroduction
Our researchers Paul Litvak and Michael Kajilolti have discovered a new campaign conducted by APT34 employing an updated toolset. Based on uncovered phishing documents, we believe this Iranian actor is targeting Westat employees, or United States organizations hiring Westat services.
Westat is a United States-based company that “provides research services to agencies of the U.S. Government, as well as businesses, foundations, and state and local governments”. One example of the services Westat offers is a survey for federal workers, which leads us to believe this attack may target Westat customers.
Official Westat response: “Westat understands that in their effort to identify threats and malware, Intezer has identified a malicious file that uses the Westat name and logo. This file was not created by, hosted by, or sent from Westat, and is likely the result of a bad actor stealing the Westat brand name and logo. Our cybersecurity team is working with Intezer and others to fully understand the nature of this report. We will continue to monitor the situation and respond accordingly.”
APT34 Background
APT34 (also known as OilRig or Helix Kitten) is a cluster of Iranian government-backed cyber espionage activities that has been active since 2014. The group is known to target various international organizations, mainly in the Middle East. Among their targeted industries are government agencies, financial services, energy and utilities, telecommunications, and oil and gas.
More light was shed on this group in April 2019 as leaks emerged from a mysterious individual with the pseudonym “Lab Dookhtegan”. This individual exposed data belonging to victims of this group, together with source code of hacking tools and data about previous APT34 operations; including IP addresses and domains where the group hosted web shells related to past operations.
Most recently, FireEye exposed a spear-phishing operation conducted by APT34, which enabled us to connect this operation to this Iranian actor due to similarities in the techniques and tools employed in both campaigns.
Initial Vector
In late January 2020, we discovered a file named survey.xls that was designed to look like an employee satisfaction survey tailored to either Westat employees or Westat customers.
At first the spreadsheet appeared to be blank. Only once the victim enables macros, the survey is displayed to the user and the malicious VBA code begins to execute.

survey.xls
The embedded VBA code unpacks a zip file into a temporary folder, extracts a “Client update.exe” executable file and installs it to “C:Users<User>valsClient update.exe”.
“Client update.exe” is actually a highly modified version of the TONEDEAF malware, which we named TONEDEAF 2.0. Finally, the crtt function creates a scheduled task “CheckUpdate” that runs the unpacked executable five minutes after being infected by it, as well as on future log-ons.


Survey.xls VBA Code
Both the extracted VBA code and the functionality of the code look similar to the one analyzed in the FireEye report:
APT34 VBA Code from the FireEye Report
In addition, we found a similar document labelled as “Employee satisfaction survey.xls” containing the same survey as the previous document.
Employee Satisfaction survey.xls
However, it’s important to highlight that the code page field of this document is Arabic as can be seen when examining its file metadata, denoting the preferred language installed on the document author’s version of Microsoft Excel:

Employee Satisfaction survey.xls Metadata
TONEDEAF 2.0
At first glance, “Client update.exe” seems like a completely new backdoor malware. However, further examination reveals it’s most likely a highly modified version of the previously seen TONEDEAF backdoor. TONEDEAF is a backdoor that communicates with its Command and Control server via HTTP in order to receive and execute commands. It was mentioned in FireEye’s recent report about an ongoing APT34 operation, as one of the group’s custom tools. We have named the new variant TONEDEAF 2.0.
TONEDEAF 2.0 is an advanced version of TONEDEAF, serving the same purpose as the original, but with a revamped C2 communication protocol and a substantially modified code base. In contrast to the original TONEDEAF, TONEDEAF 2.0 contains solely arbitrary shell execution capabilities, and doesn’t support any predefined commands. It’s also more stealthy and contains new tricks such as dynamic importing, string decoding, and a victim deception method.
New Tricks
Upon execution the backdoor checks whether it was executed with “…” as an argument, which is the way it’s configured to execute by the scheduled task, as part of the proper infection chain.
In the case it’s executed without the correct argument, such as by launching it via a double click, it will display a blank GUI Window to the user. This is most likely intended to serve as a deception method, to make the malware appear like a legitimate (alibiet broken) application titled “Bee”.

GUI Window Used for Deception
TONEDEAF 2.0 also attempts to be more stealthy than its predecessor by hiding many of the interesting API imports it uses. The names of these APIs, and the DLLs that contain them, are stored as encoded strings and are decoded and resolved on demand during runtime.

Decoding and Resolving API Functions
C2 Communication 
The backdoor uses HTTP for C2 communication, with a custom encoding and handshake mechanisms. Messages sent by the backdoor always contain the HTTP query parameter “?ser=<6 digits>” as an identifier. The first three digits are the <server_id> and the last three are the <client_id>.  The backdoor will use one of the following two messages:
1. GET /dow?ser=<server_id><client_id>  – request message, used to obtain commands to execute from the server.
2. POST /upl?ser==<server_id><client_id>  – reply to command message, used to send the executed command’s output to the server.
Before performing the first request, the malware will generate the <client_id> derived from the environment variables %HOMEPATH% and %COMPUTERNAME% using a custom formula.
It will then send an initial GET message to the C2 using that ID.

C2 Request
One odd element about the communication is the usage of a Windows Phone User-Agent  value in the HTTP message.
During our analysis the C2 was alive but continuously replied with a 403 Forbidden HTTP error code to our requests. It’s possible that the C2 is filtering the targets since this backdoor is part of a targeted operation and our client_id parameter does not match that of one of the intended victims.
Should the C2 accept the ID, it will reply with an encoded message that contains the <server_id> and the command the backdoor needs to execute. The malware extracts the command by looking for an HTTP div element in the response with a special class name.

Parsing of C2 Response
The malware will then execute the command by prepending it with “cmd U c” and will send the output of the command back to the C2 using the POST reply message (2).
When entering the C2 via a browser, the site tries to imitate https://docs.microsoft.com/en-us/, although it fails to display it properly due to a misconfiguration with the CSS, as can be seen in the console:
manygoodnews[.]com C2 webpage
We have also observed that an SSL certificate has been recently generated that matches the domain of the C2.

SSL Certificate for the C2 Domain that was Issued One Month Ago
These findings might indicate that the attackers are in the process of transitioning into HTTPS for C2 communication, in an attempt to improve their OPSEC capabilities and avoid detection.
Traces from the Original TONEDEAF
With all of the changes and new additions, there are still enough similarities that link TONEDEAF 2.0 to the original. While the code is mostly modified, the general flow and functionality are similar. The C2 communication is different but still has similarities to its predecessor, such as the usage of three digit identifiers for both the victim and the server. However, most notably there are several places in the code where the similarity is most clear. One such place is a function that exists in both variants, which oddly enough creates a notification icon in the Windows status bar. The only notable changes are the usage of dynamic API resolution and the shortening of the notification message from “Updating” to “up”.
Specific Function Comparison
Another instance is the code that sets the working directory of the program. It appears in different stages for each variant, but is identical:
Similar Code Snippets
VALUEVAULT 2.0
We were unable to download further modules, however, we believe this operation also includes the usage of a VALUEVAULT implant. VALUEVAULT is a browser credential theft tool built in Golang, discovered by FireEye in the aforementioned APT34 operation analysis.
We found the survey.xls file uploaded to VirusTotal with a VALUEVAULT instance and a TONEDEAF 2.0 instance, uploaded from Lebanon by the same user, only a few minutes apart. This may indicate that these malware were delivered together as part of the same attack.

This VALUEVAULT takes a more minimalistic approach than its predecessor. Many functionalities and strings were stripped from the new binary in order to lower its noise. Only Chrome password dumping is now supported, although interestingly the use of the file “fsociety.dat” as a password data store under the “AppData\Roaming” directory stayed the same.

VALUEVAULT 2.0 Compilation Paths

VALUEVAULT 1.0 Compilation Paths
Furthermore, VALUEVAULT 2.0 is a 64-bit binary as opposed to VALUEVAULT 1.0 which is a 32-bit binary. These relatively minor changes were enough to create a fully undetected implant.
Conclusion
The last APT34 operation was exposed only a few months ago by FireEye, and judging by our current findings we can confidently state that the group has since evolved its operations. The technical analysis of the new malware variants reveals this Iranian government-backed group has invested substantial efforts into upgrading its toolset in an attempt to evade future detection.
The binary code from these new malware samples are now indexed in our Genetic Malware Analysis platform, Intezer Analyze. We encourage you to use our free community edition to detect and classify threats that share code with APT34 malware.
IOCs
manygoodnews[.]com
c10cd1c78c180ba657e3921ee9421b9abd5b965c4cdfaa94a58e383b45bb72ca
4c323bc11982b95266732c01645c39618550e68f25c34f6d3d79288eae7d4378
a897164e3547f0ce3aaa476b0364a200769e8c07ce825bcfdc43939dd1314bb1
20b3d046ed617b7336156a64a0550d416afdd80a2c32ce332be6bbfd4829832c
d61eecd7492dfa461344076a93fc2668dc28943724190faf3d9390f8403b6411
 Paul LitvakPaul is a malware analyst and reverse engineer at Intezer. He previously served as a developer in the Israel Defense Force (IDF) Intelligence Corps for three years. Michael KajilotiMichael is a security researcher turned product manager, who previously led the Intezer Analyze product lifecycle. He has presented his malware research at conferences such as REcon and the Chaos Communications Congress (CCC).Linux Rekoobe Operating with New, Undetected Malware SamplesIntezer Featured in IBM X-Force Threat Index














 




 


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





















































 
