# Reference for threat actor for "Gorgon Group"

**Title**: 
	Gorgon APT targeting MSME sector in India 

**Source**: https://www.seqrite.com/blog/gorgon-apt-targeting-msme-sector-in-india/

## Content





	Gorgon APT targeting MSME sector in India 










 































































SEARCH




News
Security
Products
About Seqrite
 






















Blog






News
Security
Products
About Seqrite
 












 Home  /  APT • Cybersecurity • Uncategorized  /  Gorgon APT targeting MSME sector in India				






10
August
2020



					Gorgon APT targeting MSME sector in India				
Written by Pavankumar Chaudhari


 


  APT, Cybersecurity, Uncategorized





 
Estimated reading time: 5 minutesFrom the past few months, we have been monitoring cyber-threats on MSME [Micro, Small and Medium Enterprises] sector within India. MSME sector is considered to be the backbone of the Indian economy. MSME employs around 40% of the country’s workforce, contributing nearly 45% to manufacturing output and 40% of exports. Staring at a major financial resource crunch, MSME’s are worst affected due to the ongoing COVID-19 pandemic.
We observed one similar wave on MSME in late April 2020 — it was a phishing campaign luring victims with COVID-19 themed maldocs. From this campaign, one prominent file was:



FileName
face mask order.doc


MD5
4FC5BA9426E9191AAB4E694E7E703E13


SHA-1
B5EBAF2F5AF220FE1B1DE5433C2E39FF16B0C0B4


SHA-256
2022D9CC42ED2838DAA442561107C29297BDDB88B36222345C10B39164E66819


Prevalence
300+




Figure 1: Trend for Gorgon APT sample
Technical Details
Victims received an email with attached zip “face mask order.zip” which contained the aforementioned maldoc responsible to drop malware into the victim machine. The attack begins after opening “face mask order.doc”.  This RTF is weaponized with exploit which triggers CVE-2017-11882 vulnerability to execute arbitrary code.
Figure 2: Process Infection Chain
CVE-2017-11882 Analysis:
Malicious rtf document contains two malicious ole objects.
Figure 3: RTF Objects
The tools extracts the ole objects from RTF file. OLE object (#0) is a VBScript file (i.e. ServerCrypted.vbs script) and object (#2) contains Equation Editor Exploit and command to execute file “CmD.exe /C cscript %tmp%\ServerCrypted.vbs”.
The OLE object (#0) is an executable file (i.e. ServerCrypted.vbs script) as shown in figure 4.
Figure 4: Embedded VBScript
The class name for this object (#2) is Equation.3 the exploit (CVE-2017-11882) as shown in the below image.
Figure 5: RTF contents
It also contains the command to run ServerCrypted.vbs script as shown in below figure 6.
Figure 6: RTF contents
CVE-2017-11882 is present in the Microsoft Office Equation Editor (EQNEDT32.EXE) component. The attacker can successfully exploit a stack buffer overflow vulnerability in the equation editor component of MS Office and execute arbitrary code. The root cause of this vulnerability is copy unbounded string of FONT name defined within a FONT record structure of Equation Editor OLE object data.
The below figure shows the stack buffer overflow scenario while copying the font name into a locally created buffer.
Figure 7: Stack buffer overflow scenario
In this case, the function will return “back” to 0x430c12, which is the address of WinExec, and the argument is the “font name” and command which the attacker wants to execute.
Figure 8: Return address, overwritten with WinExec
VBScript Analysis:
After successful exploitation, cmd.exe is executed with commands:
“/c cscript %tmp%\ServerCrypted.vbs >> AC”
This command creates a cscript.exe process to execute code in ServerCrypted.vbs. VBScript file was already dropped in %temp% folder by WinWord process. Below Figure shows the VBScript code. As shown in figure 9 and figure 10, actors used some AV-vendors names in function names, variable names, and strings.  This VBScript is responsible to execute two processes, cmd.exe and powershell.exe. Figure 10 shows the obfuscated PowerShell script.
Figure 9: Contents of ServerCrypted.vbs
Figure 10: Contents of ServerCrypted.vbs
PowerShell Analysis:
Figure 11 shows the de-obfuscated PowerShell script.
As shown below, the script downloads two files with a .jpg extension. First file “15882060891.jpg” is a PowerShell script which contains encoded injector DLL written in C#, as shown in figure 12. This DLL is loaded in-memory by PowerShell. In this script, actors used some interesting names of class and function of injector DLL like FlorianRoth and Cyb3rOps.  Florian Roth is a well-known security researcher and  CTO of Nextron Systems. Cyb3rOps is his twitter handle name. The second file which is downloaded by PowerShell is “15882060892.jpg”, is an encoded agent tesla payload. This payload is injected in Windows native binary RegAsm.exe.
Figure 11: Decoded PowerShell script
Below is encoded data of hxxp://www[.]m9c[.]net/uploads/15882060891.jpg. This is a PowerShell code and encoded injector DLL data.
Figure 12: Contents of 15882060891.jpg
After decoding PE header of injector DLL can be seen.
Figure 13: Decoded data of 15882060891.jpg
Below figure shows contents of hxxp://www[.]m9c[.]net/uploads/15882060892.jpg. It is the encoded data of the final payload.
Figure 14: Contents of 15882060892.jpg
Final Payload – Agent Tesla:
Below figure shows injected Agent Tesla payload in RegAsm.exe.
Figure 15: Injected payload
Agent Tesla is a well-known keylogger and infostealer written in DotNet. This malware steals information from a variety of applications like Web Browsers, Email Clients, FTP Clients, Messenger applications, VPN clients, etc. and can also take screenshots of the system. All stolen data is exfiltrated over SMTP.
We have already explored and analysed Agent Tesla in our last couple of blogs:
https://www.seqrite.com/blog/advance-campaign-targeting-manufacturing-and-export-sectors-in-india/
https://www.seqrite.com/blog/coronavirus-themed-campaign/
Conclusion
Most TTPs shared above, have been seen on several occasions in the last few years. Looking at malware, C2 and technique execution, Quick Heal correlates this campaign on MSME sector to Gorgon group [a.k.a. Subaat]. All members of the Gorgon cyber-criminal group purport to have Pakistan-based interests/connections. Recently, another Gorgon campaign was uncovered a few months back which used the same commodity malware RATs to accomplish their objective.
Given the global impact of COVID-19, threat actors will likely continue to use COVID-19-themed emails to deliver malware broadly in support of their objectives. Considering this trend, we encourage Micro, Small and Medium Enterprises to apply extra scrutiny to COVID-19-related emails containing attachments. Though large organizations, critical government infrastructures, and others have somewhat built resilience to such cyber threats; but MSME still needs to cover-up and remain extra vigilant with a robust strategy to mitigate risks.
Threat Protection
Our Seqrite and Quick Heal line of products protect against top cyber threats including Microsoft Office Memory Corruption Vulnerability (CVE-2017-11882) and variants of Agent Tesla RAT. Our advanced signature-less behaviour-based detection successfully blocks Agent Tesla variants.
Quick Heal advises users to exercise ample caution and avoid opening attachments & clicking on web links in unsolicited emails. Users should also keep their Operating System updated and have a full-fledged security solution installed on all devices.
While organizations with appropriate spam filtering, proper system administration, and up-to-date Windows hosts have a much lower risk of infection, we further encourage organizations to validate the installation of the Microsoft patch for CVE 2017-11882.
Quick Heal’s research team is proactively monitoring all campaigns targeting MSME’s and working relentlessly to ensure the safety of our customers
Subject matter experts:

Kalpesh Mantri
Bajrang Mane
Pavankumar Chaudhari

 


 

  Previous PostAV-Test certifies Seqrite EPS as the top product for Windows, yet...Next Post  All you need to know about Application Programming Interface (API... 



 




About Pavankumar Chaudhari



 
                                                            Pavankumar is associated with Quick Heal Technologies as a Technical Lead (Research and Development) and is also a part of Vulnerability Research and Analysis Team....                                                        
Articles by Pavankumar Chaudhari »



Related Posts 






Cyber Security in Automotive Supply Chain: Challenges and Solutions



February 8, 2024










Traversing the Cyber Threat Terrain in 2024: Insights, Expert Guidance, and Collective Resilience



February 8, 2024










Navigating India’s Data Protection Landscape: A SEQRITE Perspective



January 29, 2024





No Comments

Leave a Reply.Your email address will not be published.  Cancel reply 
Name * 
Email * 


Leave this field empty











CAPTCHA Code
Comments * 

 












SEARCH


Popular Posts

 Operation RusticWeb targets Indian Govt: From Rust-based malware to Web-service exfiltration December 21, 2023
 All About XDR and Its Many Capabilities January 18, 2024
 Navigating India’s Data Protection Landscape: A SEQRITE Perspective January 29, 2024


Featured Authors  


Seqrite
Follow us for the latest updates and insights related to security for...
Read more..

 


Sanjay Katkar
Sanjay Katkar is the Joint Managing Director of Quick Heal Technologies...
Read more..

 


Mahua Chakrabarthy
A tea connoisseur who firmly believes that life is too short for dull content....
Read more..

 Stay Updated!


Email*  










Topicsapt (13)
Cyber-attack (32)
cyber-attacks (56)
cyberattack (13)
cyberattacks (13)
Cybersecurity (306)
cyber security (26)
Cyber threat (29)
cyber threats (44)
Data (11)
data breach (50)
data breaches (27)
data loss (28)
data loss prevention (33)
data protection (21)
data security (13)
DLP (49)
Encryption (16)
endpoint security (103)
Enterprise security (16)
Exploit (12)
firewall (11)
GDPR (11)
hackers (11)
IoT (10)
malware (66)
malware attack (23)
malware attacks (12)
MDM (25)
Microsoft (14)
Network security (18)
Patch Management (12)
phishing (19)
Ransomware (62)
ransomware attack (30)
ransomware attacks (30)
ransomware protection (13)
security (10)
Seqrite (27)
Seqrite Encryption (27)
Seqrite EPS (33)
Seqrite Services (16)
UTM (34)
Vulnerability (16)
windows (11)
 









ProductsHawkkWatch MDR
Seqrite MSSP Portal
HawkkScan
HawkkProtect
HawkkHunt XDR
HawkkEye
HawkkEye Endpoint Security Cloud
HawkkEye mSuite
HawkkEye Workspace
Endpoint Security (EPS)
Unified Threat Management
Antivirus for Linux
 

ResourcesWhite Papers
Datasheets
Threat Reports
Manuals
Case Studies
 

About UsCompany Overview
Leadership
Why choose SEQRITE?
Awards & Certifications
Newsroom
 

ArchivesBy Date
By Category
 




Email*  





















						© 2024 Quick Heal Technologies Ltd.						Cookie Policies
Privacy Policies









         Our website uses cookies. Cookies enable us to provide the best experience possible and help us understand how visitors use our website. By browsing this website, you agree to our cookie policy.
Close

















