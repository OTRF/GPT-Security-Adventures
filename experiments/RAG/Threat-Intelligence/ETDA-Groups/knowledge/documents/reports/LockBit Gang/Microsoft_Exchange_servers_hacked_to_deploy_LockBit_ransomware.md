# Reference for threat actor for "LockBit Gang"

**Title**: Microsoft Exchange servers hacked to deploy LockBit ransomware

**Source**: https://www.bleepingcomputer.com/news/security/microsoft-exchange-servers-hacked-to-deploy-lockbit-ransomware/

## Content






















Microsoft Exchange servers hacked to deploy LockBit ransomware
































































































News



Featured
Latest







Microsoft: New critical Exchange bug exploited as zero-day





LockBit claims ransomware attack on Fulton County, Georgia





Trans-Northern Pipelines investigating ALPHV ransomware attack claims





Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flaws









Three critical application security flaws scanners can’t detect





Turla hackers backdoor NGOs with new TinyTurla-NG malware





New Qbot malware variant uses fake Adobe installer popup for evasion





Take an extra $5 off this ad-blocking DNS for Presidents' Day








Tutorials



Latest
Popular







How to enable Kernel-mode Hardware-enforced Stack Protection in Windows 11





How to use the Windows Registry Editor





How to backup and restore the Windows Registry





How to open a Windows 11 Command Prompt as Administrator









How to start Windows in Safe Mode





How to remove a Trojan, Virus, Worm, or other Malware





How to show hidden files in Windows 7





How to see hidden files in Windows








Virus Removal Guides



Latest
Most Viewed
Ransomware







Remove the Theonlinesearch.com Search Redirect





Remove the Smartwebfinder.com Search Redirect





How to remove the PBlock+ adware browser extension





Remove the Toksearches.xyz Search Redirect









Remove Security Tool and SecurityTool (Uninstall Guide)





How to Remove WinFixer / Virtumonde / Msevents / Trojan.vundo





How to remove Antivirus 2009 (Uninstall Instructions)





How to remove Google Redirects or the TDSS, TDL3, or Alureon rootkit using TDSSKiller









Locky Ransomware Information, Help Guide, and FAQ





CryptoLocker Ransomware Information Guide and FAQ





CryptorBit and HowDecrypt Information Guide and FAQ





CryptoDefense and How_Decrypt Ransomware Information Guide and FAQ








Downloads



Latest
Most Downloaded







Qualys BrowserCheck





STOPDecrypter





AuroraDecrypter





FilesLockerDecrypter









AdwCleaner





ComboFix





RKill





Junkware Removal Tool








Deals



Categories







eLearning





IT Certification Courses





Gear + Gadgets





Security








VPNs



Popular







Best VPNs





How to change IP address





Access the dark web safely





Best VPN for YouTube








Forums
More

Startup Database
Uninstall Database
Glossary
Chat on Discord
Send us a Tip!
Welcome Guide




























HomeNewsSecurityMicrosoft Exchange servers hacked to deploy LockBit ransomware







 















Microsoft Exchange servers hacked to deploy LockBit ransomware


By Sergiu Gatlan




October 11, 2022
12:59 PM
0





Microsoft is investigating reports of a new zero-day bug abused to hack Exchange servers which were later used to launch Lockbit ransomware attacks.
In at least one such incident from July 2022, the attackers used a previously deployed web shell on a compromised Exchange server to escalate privileges to Active Directory admin, steal roughly 1.3 TB of data, and encrypt network systems.
As described by South Korean cybersecurity firm AhnLab, whose forensic analysis experts were hired to help with the investigation, it took the threat actors only a week to hijack the AD admin account from when the web shell was uploaded.
AhnLab says the Exchange servers were likely hacked using an "undisclosed zero-day vulnerability," given that the victim received technical support from Microsoft to deploy quarterly security patches after a previous compromise from December 2021.
"Among the vulnerabilities disclosed after May, there were no reports of vulnerabilities related to remote commands or file creation," AhnLab explained.
"Therefore, considering that WebShell was created on July 21, it is expected that the attacker used an undisclosed zero-day vulnerability."
As a Microsoft spokesperson told BleepingComputer earlier today, the company is "investigating the claims in this report and will take any action needed to help protect customers."
New Microsoft Exchange zero-days?
While Microsoft is currently working on security patches to address two actively exploited Microsoft Exchange zero-days tracked as CVE-2022-41040 and CVE-2022-41082, AhnLab added that the one used to gain access to the Exchange server in July might be different since attack tactics don't overlap.
"There is a possibility that the vulnerabilities of Microsoft Exchange Server (CVE-2022-41040, CVE-2022-41082) disclosed by GTSC, a Vietnamese security company, on September 28 were used, but the attack method, the generated WebShell file name, and subsequent attacks after WebShell creation," AhnLab says.
"It is presumed that a different attacker used a different zero-day vulnerability."
Although differences in the delivery method can't be considered enough evidence the attackers used a new zero-day and security experts are also not convinced this is the case, at least one more security vendor knows of three other undisclosed Exchange flaws and provides "vaccines" to block exploitation attempts.
Discovered by Zero Day Initiative vulnerability researcher Piotr Bazydlo and reported to Microsoft three weeks ago, they are tracked by cybersecurity software firm Trend Micro tracks as ZDI-CAN-18881, ZDI-CAN-18882, and ZDI-CAN-18932 after its analysts validated the issues.

Undisclosed Exchange flaws (Trend Micro)
The company has also added detection signatures for these Exchange zero-days (tagged as critical severity by Trend Micro) to its IPS N-Platform, NX-Platform, or TPS products since October 4, 2022.
"This filter protects against exploitation of a zero-day vulnerability affecting Microsoft Exchange," Trend Micro says in a Digital Vaccine support document.
Microsoft hasn't disclosed any information regarding these three security flaws since they were reported and is yet to assign a CVE ID to track them.

Related Articles:
Microsoft: New critical Exchange bug exploited as zero-dayLockBit claims ransomware attack on Fulton County, GeorgiaBank of America warns customers of data breach after vendor hackThe Week in Ransomware - February 2nd 2024 - No honor among thievesThe Week in Ransomware - January 26th 2024 - Govts strike back











LockBit
Microsoft Exchange
Ransomware
Zero-Day
























Sergiu Gatlan   
Sergiu is a news reporter who has covered the latest cybersecurity and technology developments for over a decade. Email or Twitter DMs for tips.




 Previous Article 
Next Article 



Post a Comment Community Rules

You need to login in order to post a comment

Not a member yet? Register Now



You may also like:













Popular Stories






Hackers used new Windows Defender zero-day to drop DarkMe malware







Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flaws

































Follow us:









Main Sections

News
VPN Buyer Guides
Downloads
Virus Removal Guides
Tutorials
Startup Database
Uninstall Database
Glossary



Community

Forums
Forum Rules
Chat



Useful Resources

Welcome Guide
Sitemap



Company

About BleepingComputer
Contact Us
Send us a Tip!
Advertising
Write for BleepingComputer
Social & Feeds
Changelog








Terms of Use -  Privacy Policy - Ethics Statement - Affiliate Disclosure


Copyright @ 2003 - 2024  Bleeping Computer® LLC  - All Rights Reserved












Login


Username



Password





Remember Me



Sign in anonymously





 Sign in with Twitter

Not a member yet? Register Now
















  
Reporter

Help us understand the problem. What is going on with this comment?




Spam


Abusive or Harmful


Inappropriate content


Strong language


Other





Read our posting guidelinese to learn what content is prohibited.



Submitting...
SUBMIT











