# Reference for threat actor for "Karakurt"

**Title**: Karakurt extortion group: Threat profile

**Source**: https://blog.malwarebytes.com/cybercrime/2022/06/karakurt-extortion-group-threat-profile/

## Content











Karakurt extortion group: Threat profile












































 




 








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

































 


Cybercrime
						 | 						News

Karakurt extortion group: Threat profile 
Posted: June 14, 2022
 by Jovi Umawing 


The FBI (Federal Bureau of Investigation), together with CISA (Cybersecurity and Infrastructure Security Agency) and other federal agencies, recently released a joint cybersecurity advisory (CSA) about the Karakurt data extortion group (also known as Karakurt Team and Karakurt Lair).
Like RansomHouse, Karakurt doesn’t bother encrypting data. Instead, it just steals the data and demands a ransom. If the victim organization refuses to pay up, the stolen data is auctioned off or leaked to the public for anyone to scrape and misuse for personal gain.

🚨With our partners @FBI, @USTreasury and FinCEN, @CISAgov issued a joint cybersecurity advisory on #Karakurt data extortion group. Known ransom demands ranged from $25K to $13M in Bitcoin. Mitigate your risk: https://t.co/gNiDbLsNJQ pic.twitter.com/0ft8mPediO— Jen Easterly🛡️ (@CISAJen) June 1, 2022

One may wonder why federal agencies decided to focus on Karakurt when it is a relatively obscure group. It has no prolific attacks attributed to it and doesn’t appear to have a high number of attacks under its belt.
According to Bleeping Computer, Karakurt is said to be the “data extortion arm” of the Conti ransomware syndicate. Further evidence from two blockchain traffic firms, Chainalysis and Tetra Defense, can back this up. In a report last month, they assessed“with a high degree of confidence” that Karakurt is “operationally linked to both Conti and Diavol ransomware groups”.
Karakurt extortion group

The Karakurt group got its name from a type of black widow spider. Researchers have pointed outthat the group liken its extortion tactics to a karakurt spider’s bite.

Karakurts poison is very toxic and dangerous. Don't waste your time.What would you do? Of course you will have to take an antidote.In your situation it means that you still have a chance to survive. But it will cost as double.All you need is to accept our terms and conditions without any sort of bargain.
The NCC Group’s Cyber Incident Response Team (CIRT) spotlighted Karakurt activities in February 2022. However, Karakurt, known initially as the Karakurt Hacking Team (KHT), has been around since June 2021. This also marked the creation of domains and accounts associated with the group, namely its dump sites and, later on, its Twitter account in August 2021.
Per a report from Accenture Security, Karakurt wasn’t actively extorting until September 2021. After two months, the extortion group had already bagged 40 organizations across multiple industries. However, experts from Digital Shadows seem to dispute this number, claiming that the victim number is more than 80.
Regarding victimization, it’s clear that Karakurt isn’t picky with what to target. Regarding target locations, the extortion group prefers small organizations based in the US, the UK, Canada, and Germany.
The extortion group targets organizations using single-factor Fortigate VPN (Virtual Private Network) servers using legitimate Active Directory credentials. It is unknown how the group obtains these credentials; however, it’s no surprise that they get administrative access and privileges on compromised servers.
From there, Karakurt can use the various tools it has at its disposal. Depending on the goals, the group can do a “living off the land” approach in its tactics, toolset, and intrusion techniques. It can also use common post-exploit tools like Cobalt Strike, AnyDesk, and Mimikatz.
Once Karakurt has the data it wants to exfiltrate, it uses 7zip and WinZip to compress the files before sending them to Mega.iovia FileZilla or Rclone.

Karakurt demands a ransom ranging from $25,000 to $13M in Bitcoin. The payment deadline is typically seven days after the victim contacts the extortion group.
Splintering into cells
Ransomware groups have been undergoing a new phasefor a few months now. If they’re not splitting into smaller groups (“cells”) to join other criminal groups, they are rotating their use of malware to avoid the growing US sanctions and pressure from law enforcement.
Since the US officially sanctioned Evil Corp, the Russian group behind the Dridexbanking Trojan, things started changing, both on the side of ransomware victims and affiliates that use ransomware. Victims began refusing to pay to comply with sanctions, and these groups started rotating the use of ransomware variants in their campaigns to avoid getting associated with a sanctioned group.
With Conti “gone,”a splintering also happened within the syndicate. Researchers from Advanced Intel have data showing members of the former ransomware syndicate dispersing from the core group to join smaller ransomware groups.
Conti is not affiliated with Evil Corp, but both groups are in a similar bind that affects their profit margins but not enough to make them completely give up a criminal life. Unfortunately, members and affiliates gain from splintering and distancing themselves from these groups.
In an interviewwith the Wall Street Journal, Kimberly Goody, Mandiant’s director of cybercrime analysis, said that these changes obscured Evil Corp hackers’ identities “at the point of attack, throwing off investigators and sanction-compliant victim companies”. The same can be said about former actors associated with the Conti syndicate.
Keep Karakurt away from your network anddata
We advise organizations to prioritize mitigating steps to keep extortion groups like Karakurt from successfully infiltrating your network. Here are some ways to do that.

Implement multi-factor authentication (MFA)in every business access point, including single-factor VPN access
Ensure that all domain control servers are kept updated with the latest patches
Disable unused ports
Install an efficient and effective endpoint security solutionthat focuses on a layered approach to protecting systems and business assets
Create and implement a recovery plan (if your business doesn’t have one already), including how to maintain and retain backups
Segment your network to keep bad guys from reaching destinations that house your organization’s most sensitive and proprietary data
Audit high-privileged accounts regularly

The federal agencies have more mitigation points in the advisory, which you can find here.
Stay safe!




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









Jovi Umawing

Knows a bit about everything and a lot about several somethings. Writes about those somethings, usually in long-form.












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








































