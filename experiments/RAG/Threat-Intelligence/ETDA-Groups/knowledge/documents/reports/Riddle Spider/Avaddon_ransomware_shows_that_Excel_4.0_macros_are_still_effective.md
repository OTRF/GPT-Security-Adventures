# Reference for threat actor for "Riddle Spider"

**Title**: Avaddon ransomware shows that Excel 4.0 macros are still effective

**Source**: https://www.bleepingcomputer.com/news/security/avaddon-ransomware-shows-that-excel-40-macros-are-still-effective/

## Content






















Avaddon ransomware shows that Excel 4.0 macros are still effective
































































































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




























HomeNewsSecurityAvaddon ransomware shows that Excel 4.0 macros are still effective







 














Avaddon ransomware shows that Excel 4.0 macros are still effective


By Ionut Ilascu


July 3, 2020
12:08 PM
0




Avaddon ransomware has been spreading this week via an old technique that's making a comeback, Microsoft cautions on Thursday.
The attacks appear to be more targeted and rely on malicious Excel 4.0 macros to download the malware directly on the system.
Campaign focused on Italy
This file-encrypting malware emerged at the beginning of June, delivered "with a wink and a smile" in a massive spam campaign that did not focus on a particular type of user. Its operators are currently recruiting affiliates for spreading the ransomware payload.
The encryption routine is solid and files cannot be unlocked for free. A sample analyzed by BleepingComputer asked for a ransom of $900.
Microsoft Security Intelligence notes that the latest effort from the attacker focused on specific targets mainly in Italy, sending out emails with documents laced with malicious Excel 4.0 macros.

Microsoft Security Intelligence
One such email found by malware hunter JamesWT_MHT pretends to be a notification from the Labor Inspectorate to a small business regarding work violations during "a period of crisis."
The subject of the message is alarming, informing the recipient of impending penalties and potential legal action. In the attachment, there is a ZIP archive named "Official notification."

source: JamesWT_MHT
The archived document contains an Excel 4.0 macro (XML), which is still compatible with modern software where VBA code is used instead.
When run, the macro downloads an Avaddon ransomware sample directly, without an intermediary downloader, Microsoft notes. This trend has been observed in other file-encrypting malware lately.
Using old macro bears fruit
Choosing Excel 4.0 macros to spread the malware may seem peculiar, especially since it is was introduced in Microsoft Office products 28 years ago. However, Avaddon and numerous other threat actors have started using it recently.
In the case of Avaddon, this seems to yield results as the ransomware identification website ID Ransomware received a large number of submissions from victims. As seen below, the rise started on June 18 and then again on June 28 and 30, which is consistent with Micosoft's observations.

ID Ransomware

"While an old technique, malicious Excel 4.0 macros started gaining popularity in malware campaigns in recent months. The technique has been adopted by numerous campaigns, including ones that used COVID-19 themed lures" - Microsoft Security Intelligence

Launched in 1992, Excel 4.0 uses XML-based macros that store functions in BIFF (Binary Interchange File Format) records. This makes them more difficult to analyze compared to VBA macros that have dedicated streams and that are being used since Excel 5.0.
Microsoft noticed an increase in malicious email campaigns with Excel 4.0 macro over the past few months. Since April, the attackers started using the Covid-19 theme.

Related Articles:
Bumblebee malware attacks are back after 4-month breakNew Qbot malware variant uses fake Adobe installer popup for evasionLockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offline








Avaddon
Excel
Macros
MalSpam
Phishing
Ransomware



















Ionut Ilascu   
Ionut Ilascu is a technology writer with a focus on all things cybersecurity. The topics he writes about include malware, vulnerabilities, exploits and security defenses, as well as research and innovation in information security. His work has been published by Bitdefender, Netgear, The Security Ledger and Softpedia.



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











