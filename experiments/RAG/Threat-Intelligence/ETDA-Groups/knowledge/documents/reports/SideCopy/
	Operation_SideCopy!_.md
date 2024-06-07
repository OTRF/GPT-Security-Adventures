# Reference for threat actor for "SideCopy"

**Title**: 
	Operation SideCopy! 

**Source**: https://www.seqrite.com/blog/operation-sidecopy/

## Content





	Operation SideCopy! 










 
































































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
 












 Home  /  APT • Cybersecurity  /  Operation SideCopy!				






23
September
2020



					Operation SideCopy!				
Written by Kalpesh Mantri


 


  APT, Cybersecurity


  4


 
Estimated reading time: 3 minutesAn insight into Transparent Tribe’s sub-division which has been incorrectly attributed for years.
Introduction
Quick Heal’s threat intelligence team recently uncovered evidence of an advanced persistent threat (APT) against Indian defence forces. Our analysis shows that many old campaigns and attack in the past one year relate to ‘Operation SideCopy’ by common IOCs.
Key Findings

Operation SideCopy is active from early 2019, till date.
This cyber-operation has been only targeting Indian defence forces and armed forces personnel.
Malware modules seen are constantly under development and updated modules are released after a reconnaissance of victim data.
Actors are keeping track of malware detections and updating modules when detected by AV.
Almost all CnC belongs to Contabo GmbH and server names are similar to machine names found in the Transparent Tribe report.
This threat actor is misleading the security community by copying TTPs that point at Sidewinder APT group.
We suspect this threat actor has links with Transparent Tribe APT group.

Summary:
A few months ago, Quick Heal’s Next-Gen Behavioural Detection system alerted on a few processes executing HTA from some non-reputed websites.
We have made a list of URLs, connected from mshta.exe, across multiple customers:
hxxps://demo[.]smart-hospital[.]in/uploads/staff_documents/19/Armed-Forces-Spl-Allowance-Order/html/
hxxps://demo[.]smart-hospital[.]in/uploads/staff_documents/19/Defence-Production-Policy-2020/html/
hxxps://demo[.]smart-hospital[.]in/uploads/staff_documents/19/Images/8534
hxxps://demo[.]smart-hospital[.]in/uploads/staff_documents/19/IncidentReport/html/
hxxps://demo[.]smart-hospital[.]in/uploads/staff_documents/19/ParaMil-Forces-Spl-Allowance-Order/html/
hxxps://demo[.]smart-hospital[.]in/uploads/staff_documents/19/Req-Data/html
hxxps://demo[.]smart-hospital[.]in/uploads/staff_documents/19/Sheet_Roll/html
hxxps://demo[.]smart-school[.]in/uploads/staff_documents/9/Sheet_Roll/html
hxxps://demo[.]smart-school[.]in/uploads/student_documents/12/css/
hxxps://drivetoshare[.]com/mod[.]gov[.]in_dod_sites_default_files_Revisedrates/html
 
The highlighted ones were sent to targets across Indian defence units and armed forces individuals.
We started tracking this campaign as it was targeting critical Indian organizations.
Traces of this operation can be tracked from early 2019 till date. Till now, we have observed 3 infection chain process.
Initial infection vector in two of the chains was LNK file, that came from a malspam. But in one case, we saw attackers making use of template injection attack and equation editor vulnerability (CVE-2017-11882) as the initial infection vector. Though the initial infection vector is different in the third case, the final payload is similar to the first two chains.
Below images will provide an overview of malware infection in victim machines.
Infection Chain – Version 1:

Infection Chain – Version 2:

Infection Chain – Version 3:

 
We have provided an in-depth analysis of each of this module in our latest report which can be found here.
The background and analysis in this paper provide complete forensic and useful details of our current thinking on the use of malware in this operation. We have provided all factors that lead to our attribution.
Subject matter experts:
Kalpesh Mantri, Principal Security Researcher
Pawan Chaudhari, Threat Research Scientist
Goutam Tripathy, Senior Security Researcher


 

  Previous PostCould you be blindsided when your CEO emails you?Next Post  The return of the Emotet as the world unlocks! 



 




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





4 Comments

Leave a Reply.Your email address will not be published.  Cancel reply 
Name * 
Email * 


Leave this field empty











CAPTCHA Code
Comments * 

 




				Pingback: Researchers Uncover Cyber Espionage Operation Aimed At Indian Army - IT LinesIT Lines 



				Pingback: Researchers Uncover Cyber Espionage Operation Aimed At Indian Army – Cyber Briefs 



				Pingback: Researchers Uncover Cyber Espionage Operation Aimed At Indian Army - Cyber Security 



				Pingback: Researchers Uncover Cyber Espionage Operation Aimed At Indian Army – Auto Translate News 











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

















