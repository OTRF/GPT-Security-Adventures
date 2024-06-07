# Reference for threat actor for "Patchwork, Dropping Elephant"

**Title**: Patchwork APT caught in its own web

**Source**: https://blog.malwarebytes.com/threat-intelligence/2022/01/patchwork-apt-caught-in-its-own-web/

## Content











Patchwork APT caught in its own web






































 




 








Skip to content





Search

Search Malwarebytes.com



Search for:








Contact Us

Personal Support
Business Support
Talk to Sales
Contact Press
Partner Programs
Submit Vulnerability


Company

About Malwarebytes
Careers
News & Press


Sign In

MyAccount sign in: manage your personal or Teams subscription >
Cloud Console sign in: manage your cloud business products >
Partner Portal sign in: management for Resellers and MSPs >


 














Personal


< Personal

ProductsMalwarebytes Premium >Malwarebytes Privacy VPN >Malwarebytes Identity Theft Protection >Malwarebytes Browser Guard >Malwarebytes for Teams/small offices >AdwCleaner for Windows >

Find the right productSee our plansInfected already?Clean your device now




SolutionsFree antivirus >Free virus scan & removal >Windows antivirus >Mac antivirus >Android antivirus >iOS security >Chromebook antivirus >
See personal pricingManage your subscriptionVisit our support page 





Business


< Business
BUNDLESCorePrevent and remediate threats and identify vulnerabilitiesAdvancedUtilize threat guidance and patch management plus everything in CoreEliteDeploy Managed Detection and Response plus everything in AdvancedUltimateProtect against categories of malicious websites plus everything in Elite


TECHNOLOGY HIGHLIGHTSManaged Detection & Response (MDR) Deploy fully-managed threat monitoring, investigation, and remediationEndpoint Detection & Response (EDR)Prevent more attacks with security that catches what others missSecurity AdvisorVisualize and optimize your security posture in just minutesFor EducationSecure your students and institution against cyberattacks







Learn more about Security Advisor (available in every bundle) and see the full list of our products and services.
Full technology list >




Pricing



< Pricing
Personal pricingProtect your personal devices and dataSmall office/home office pricingProtect your team’s devices and dataBusiness pricingExplore our award-winning endpoint security products, from EP to EDR to MDR




Partners



< Partners
Explore PartnershipsPartner SolutionsResellersManaged Service ProvidersComputer RepairTechnology PartnersAffiliate PartnersContact Us




Resources


< Resources
Learn About CybersecurityAntivirusMalwareRansomwareMalwarebytes Labs – BlogGlossaryThreat Center


Business ResourcesReviewsAnalyst ReportsCase StudiesPress & News


ReportsThe State of Malware 2023 ReportRead report



Support



< Support
Technical SupportPersonal SupportBusiness SupportPremium ServicesForumsVulnerability DisclosureReport a False Positive


Featured ContentActivate Malwarebytes Privacy on Windows device.See Content Product Videos



 

Free Download




Search
Search

Search Malwarebytes.com



Search for:









































SUBSCRIBE


rss

































 


News
						 | 						Threat Intelligence

Patchwork APT caught in its own web 
Posted: January 7, 2022
 by Threat Intelligence Team 


Patchwork is an Indian threat actor that has been active since December 2015 and usually targets Pakistan via spear phishing attacks. In its most recent campaign from late November to early December 2021, Patchwork has used malicious RTF files to drop a variant of the BADNEWS (Ragnatela) Remote Administration Trojan (RAT).  What is interesting among victims of this latest campaign, is that the actor has for the first time targeted several faculty members whose research focus is on molecular medicine and biological science.  Instead of focusing entirely on victimology, we decided to shade some light on this APT. Ironically, all the information we gathered was possible thanks to the threat actor infecting themselves with their own RAT, resulting in captured keystrokes and screenshots of their own computer and virtual machines.  Ragnatela   We identified what we believe is a new variant of the BADNEWS RAT called Ragnatela being distributed via spear phishing emails to targets of interest in Pakistan. Ragnatela, which means spider web in Italian, is also the project name and panel used by Patchwork APT.     Ragnatela RAT was built sometime in late November as seen in its Program Database (PDB) path “E:new_opsjlitest __change_ops -29no – CopyReleasejlitest.pdb”. It features the following capabilities:   Executing commands via cmd Capturing screenshots Logging Keystrokes  Collecting list of all the files in victim’s machine Collecting list of the running applications in the victim’s machine at a specific time periods Downing addition payloads Uploading files     In order to distribute the RAT onto victims, Patchwork lures them with documents impersonating Pakistani authorities. For example, a document called EOIForm.rtf was uploaded by the threat actor onto their own server at karachidha[.]org/docs/.     That file contains an exploit (Microsoft Equation Editor) which is meant to compromise the victim’s computer and execute the final payload (RAT).     That payload is stored within the RTF document as an OLE object. We can deduce the file was created on December 9 2021 based on the source path information.     Ragnatela RAT communicates with the attacker’s infrastructure via a server located at bgre.kozow[.]com. Prior to launching this campaign (in late November), the threat actor tested that their server was up and running properly.     The RAT (jli.dll) was also tested in late November before its final compilation on 2021-12-09, along with MicroScMgmt.exe used to side-load it.     Also in late November, we can see the threat actor testing the side-loading in a typical victim machine.     Victims and victim   We were able to gain visibility on the victims that were successfully compromised:   Ministry of Defense- Government of Pakistan National Defense University of Islam Abad Faculty of Bio-Science, UVAS University, Lahore, Pakistan International center for chemical and biological sciences HEJ Research institute of chemistry, International center for chemical and biological sciences, univeristy of Karachi SHU University, Molecular medicine  Another – unintentional – victim is the threat actor himself which appears to have infected is own development machine with the RAT. We can see them running both VirtualBox and VMware to do web development and testing. Their main host has dual keyboard layouts (English and Indian).     Other information that can be obtained is that the weather at the time was cloudy with 19 degrees and that they haven’t updated their Java yet. On a more serious note, the threat actor uses VPN Secure and CyberGhost to mask their IP address.     Under the VPN they log into their victim’s email and other accounts stolen by the RAT.     Conclusion   This blog gave an overview of the latest campaign from the Patchwork APT. While they continue to use the same lures and RAT, the group has shown interest in a new kind of target. Indeed this is the first time we have observed Patchwork targeting molecular medicine and biological science researchers.  Thanks to data captured by the threat actor’s own malware, we were able to get a better understanding about who sits behind the keyboard. The group makes use of virtual machines and VPNs to both develop, push updates and check on their victims. Patchwork, like some other East Asian APTs is not as sophisticated as their Russian and North Korean counterparts.  Indicators of Compromise   Lure  karachidha[.]org/docs/EOIForm.rtf5b5b1608e6736c7759b1ecf61e756794cf9ef3bb4752c315527bcc675480b6c6  RAT  jli.dll3d3598d32a75fd80c9ba965f000639024e4ea1363188f44c5d3d6d6718aaa1a3  C2  bgre[.]kozow[.]com  




SHARE THIS ARTICLE
































RELATED ARTICLES





 



News
																	 | 																	Privacy

Facebook Marketplace users’ stolen data offered for sale


February 15, 2024 - Personal data belonging to 200,000 Facebook Marketplace users has been published online, including email addresses and phone numbers.

CONTINUE READING
 0 Comments






 



Cybercrime
																	 | 																	Ransomware
																	 | 																	Threats

How ransomware changed in 2023


February 14, 2024 - In 2023, the CL0P ransomware gang broke the scalability barrier and shook the security world with a series of short, automated campaigns.

CONTINUE READING
 0 Comments






 



News
																	 | 																	Personal

Malwarebytes crushes malware all the time


February 14, 2024 - The PC Security Channel tested Malwarebytes against 2015 files.  Here's how we did.

CONTINUE READING
 0 Comments






 



Exploits and vulnerabilities
																	 | 																	News

Update now! Microsoft fixes two zero-days on February Patch Tuesday


February 14, 2024 - Microsoft has issued patches for 73 security vulnerabilities in its February 2024 Patch Tuesday.

CONTINUE READING
 0 Comments






 



Android
																	 | 																	News
																	 | 																	Personal

TheTruthSpy stalkerware, still insecure, still leaking data


February 13, 2024 - Stalkerware app TheTruthSpy has been hacked for the fourth time, once again leaking the sensitive data it captures.

CONTINUE READING
 0 Comments










ABOUT THE AUTHOR









Threat Intelligence Team













Contributors



Threat Center



Podcast



Glossary



Scams










 

					Cyberprotection for every one.					



FOR PERSONAL
Windows Antivirus
Mac Antivirus
Android Antivirus
Free Antivirus
VPN App (All Devices)
Malwarebytes for iOS
SEE ALL

COMPANY
About Us
Contact Us
Careers
News and Press
Blog
Scholarship
Forums
 

FOR BUSINESS
Small Businesses
Mid-size business
Larger Enterprise
Endpoint Protection
Endpoint Detection & Response
Managed Detection and Response (MDR)

FOR PARTNERS
Managed Service Provider (MSP) Program
Resellers

MY ACCOUNT
Sign In


SOLUTIONS
Rootkit Scanner
Trojan Scanner
Virus Scanner
Spyware Scanner
Password Generator
Anti Ransomware Protection

ADDRESS
One Albert Quay2nd FloorCork T12 X8N6Ireland
3979 Freedom Circle12th FloorSanta Clara, CA 95054


LEARN
Malware
Hacking
Phishing
Ransomware
Computer Virus
Antivirus
What is VPN?
 




 Twitter




 Facebook




 LinkedIn




 Youtube




 Instagram




Cybersecurity info you can’t live without
Want to stay informed on the latest news in cybersecurity? Sign up for our newsletter and learn how to protect your computer from threats.


Email Address



















English


Legal
Privacy
Accessibility
Vulnerability Disclosure
Terms of Service
 
						© 2024 All Rights Reserved						










Select your language








































