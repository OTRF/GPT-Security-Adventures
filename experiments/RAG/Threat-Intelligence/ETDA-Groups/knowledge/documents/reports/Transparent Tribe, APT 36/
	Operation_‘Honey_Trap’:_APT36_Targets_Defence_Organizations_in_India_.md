# Reference for threat actor for "Transparent Tribe, APT 36"

**Title**: 
	Operation ‘Honey Trap’: APT36 Targets Defence Organizations in India 

**Source**: https://www.seqrite.com/blog/operation-honey-trap-apt36-targets-defense-organizations-in-india/

## Content





	Operation ‘Honey Trap’: APT36 Targets Defence Organizations in India 










 

































































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
 












 Home  /  APT • Cybersecurity • Malware • Security  /  Operation ‘Honey Trap’: APT36 Targets Defence Organizations in India				






08
July
2020



					Operation ‘Honey Trap’: APT36 Targets Defence Organizations in India				
Written by Kalpesh Mantri


 


  APT, Cybersecurity, Malware, Security





 
Estimated reading time: 4 minutesSummary
In the last 3 months, we have noticed increased activity from APT36, a Pakistan-linked Cyber Threat actor. The target this time are personnel belonging to defence organizations & other Government organizations in India.
In the recent wave of attacks, APT36 is using honey trapping technique to lure their targets. The “honey trap” operations use fake profiles of attractive women to entice targets into opening their emails or chatting over messaging platforms, ultimately leading them into downloading malware.
Some of the attachment names that we found in the current themed attack:

When target opens such attachment, it drops MSIL based Crimson RAT which has been used by APT36 in many of their past attacks. This RAT is used for data-stealing activities and sending them to a CnC server.
Operation ‘Honey Trap’
Indian Army has described ‘honey trap’ cases as a weapon of hybrid warfare being waged by the enemy across the borders. The same theme is now being used by APT36 to lure its targets.
Image: News feeds showing the use of ‘honey trap’ cases
Campaign Overview
This campaign continues to use two separate infection chains. These two infection techniques of APT36 have remained the same in the past couple of years.
In the first chain, a spear-phishing email has a macro loaded document as an attachment. This document is responsible to execute a dropper module that starts the Crimson RAT tool to perform malicious activity.
Image: Infection Chain – Scenario 1
In the second chain, a spear-phishing email attachment directly contains a dropper module within a zip file. This dropper component opens a decoy document for the victim and runs Crimson RAT tool in the background to perform malicious activity.
Image: Infection Chain – Scenario 2
The second infection chain is not so successful in organizations as their firewalls usually block ‘EXE’ filetype within an email. This is the main reason, it is targeting personal accounts of individuals related to the  Indian Defence sector.
Crimson RAT
Crimson RAT remains a popular arsenal on APT36 group. We had published details of another APT36 attack last month; working of the malware remains the same.
https://www.seqrite.com/resources/transparent-tribe-targetting-critical-indian-organizations
Summarized behaviour of this RAT-

Process:

List processes
Kill process
Execute commands


File:

Drives, files and directory traversal
Delete files
Execute files
Search for file extensions
Metadata extraction


Capture Screen:

Single and Continuous screenshots
Get Thumbnails, Screen Size


Data Exfiltration:

Download from C2
Upload to C2



Shown here are some functionality implementations in crimson RAT code:
Image: Functionality to list all running process
Image: Functionality to check and add startup entry in the registry
Image: Functionality to search files of a given extension
Image: Functionality to capture screenshot.
 
Conclusion
It is a well-established fact, that APT36 targets defence and other critical sector organizations. Usually, their targets are individuals and organizations which are of strategic interest to India’s western neighbour. However, in this campaign, interestingly, some of the targeted entities belong to organizations based in the eastern states in India! In last one year, this is the second instance where we saw APT36 targeting organizations of interest to India’s eastern neighbour
 
IOCs associated to the honeytrap campaign:



03E499D6E15817F5C7EF0F4F2FFD6D27
0FD5FD92A6D8467A892C889B7DE49FC2
11C594AF9B478A1EC688E874BCF61FE9
2B22AC62E5843F22F4A51149ADE2D6D1
3709CE3826A3AEBA20341ED2EF38259F
3952EBEDF24716728B7355B8BE8E71B6
467B10934E97D66E738E56501C22D1C4
46B9FA19A52D0E83B63280547630BB33
485F08EE7F741219BC1F2438319A33E4
4B7D87FFA7D243A32D6D516583B04B8A
4C0E752600746B6D67CF1D49C103D64A
4DC350105A7879E14780B0A353816BC5
5111974611588AFFE86C99EB9897FE02
589729BC673FE05A2F3B4C85797E2CE6
60BC356B4C88431353756B9496CF8F55
6368B4E339D04B30DA20AF70C67EC743
6801133F37481D8D865E984766E49D34
6B2931A1E68E8C9B02B815DC8065B4F8
6C11F92F6646E696724DE47D41ADC9F0
6DAA8DB3ED3661F9BC708E9B3E5F5C3C
8B22B21F258207F6B2C71483EAFF8CA6
8D34A25D139F836FD36BBEB869A6BD3F
92A16E790F69E68C393B3BEEA15E14AA
94C00B72C37D5EB00E6B200AA71295C7
9C9A6005C14D4EDFF392EE174E3A6964
A15602E81A2E9860463F83ED66E7FFFD
A22DBB859B380E375DF17D0751E407F5
A7C8DD395CD707794A8BFFE9C06A6344
A93F9E7325567A01357C565F2875C02F
B6E5D3B7F74B99CB039B8226AAFE6E08
C0C2BCA1B2668D10D0B26E0F6DB34A64
C32E6BC20F46CF0EB6E3608F35651195
C9895D76ACE01B7A1DB407B18059B785
CBFAE579A25DF1E2FE0E02934EFD65DC
D504CAB93AB055267BDD7693BFCFED5B
D9CE6D2F89AFADD13D42CAC313C91582
E670F157F988FA13317CD878DEB55697
E89E1D0CDB0C0653744E5D12B6262F07
E8AA25A0D8A95E43712765FEFAC3C068
EA371D9282AB9C2A7274C5C8ACA9A64A
F0C1AEA58025973D254FF9FD08599E65
F70B3DA6C795B544FAC4F90AE4B45BA2
FE74761CE3EEDB20FF50FEFE9C2D49EF
FF2F32C78688AEC15C1283B1E625E72A





Subject matter experts:
Pavankumar Chaudhari
Kalpesh Mantri
 





 

  Previous PostAdvance Campaign Targeting Manufacturing and Export Sectors in In...Next Post  Snake Ransomware brings impending doom to enterprise networks 



 




About Kalpesh Mantri

 

 
                                                            Kalpesh Mantri is currently working as a Principal Security Researcher with Quick Heal Labs. He is currently working on hunting APTs and telemetry...                                                        
Articles by Kalpesh Mantri »



Related Posts 






Cyber Security in Automotive Supply Chain: Challenges and Solutions



February 8, 2024










All About XDR and Its Many Capabilities



January 18, 2024










Operation RusticWeb targets Indian Govt: From Rust-based malware to Web-service exfiltration



December 21, 2023





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

















