# Reference for threat actor for "Mallard Spider"

**Title**: QBot phishing lures victims using US election interference emails

**Source**: https://www.bleepingcomputer.com/news/security/qbot-phishing-lures-victims-using-us-election-interference-emails/

## Content






















QBot phishing lures victims using US election interference emails
































































































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




























HomeNewsSecurityQBot phishing lures victims using US election interference emails







 















QBot phishing lures victims using US election interference emails


By Sergiu Gatlan




November 4, 2020
06:18 PM
0





The Qbot botnet is now spewing U.S. election-themed phishing emails used to infect victims with malicious payloads designed to harvest user data and emails for use in future campaigns.
Qbot (aka Qakbot, Pinkslipbot, and Quakbot) is a banking trojan with worm features [1, 2, 3] actively used since at least 2009 to steal financial data and banking credentials, as well as to log user keystrokes, to deploy backdoors, and to drop additional malware.
Election interference baits
The malspam emails recently spotted by Malwarebytes Labs' Threat Intelligence Team are camouflaged as replies in previously stolen email threads, a tactic used to add legitimacy in the targets' eyes.
Each of the phishing messages come with malicious Excel spreadsheet attachments disguised as secure DocuSign file allegedly containing information related to election interference.
This new template has been adopted to abuse the public's concerns regarding the 2020 US elections' outcome, and to make it easier for the threat actors to lure potential victims into opening bait documents and enabling macros used to drop malware payloads.
After the Qbot malware is executed and infects the victims' computers, it will reach out to its command and control center to ask for further instructions.
"In addition to stealing and exfiltrating data from its victims, QBot will also start grabbing emails that will later be used as part of the next malspam campaigns," Malwarebytes' Jérôme Segura and Hossein Jazi explain.

Aggressive malware used in targeted campaigns
Besides phishing campaigns, attackers are also often using exploit kits to drop Qbot payloads, with the bot subsequently infecting other devices on the victims' network using network share exploits and highly aggressive brute-force attacks that target Active Directory admin accounts.
Even though active for over a decade, the Qbot banking trojan was mostly used in targeted attacks against corporate entities that provide a higher return on investment.
As proof of this, Qbot campaigns have been quite uncommon over time, with researchers detecting one in October 2014, one in April 2016, and another one in May 2017.

Qbot process flow (Malwarebytes)
Qbot has also seen a resurgence last year, being dropped as a first stage or as a second stage malware payload by the Emotet gang, as well as part of a context-aware phishing campaign in March 2019 using hijacked email threads.
During 2020, Qbot was used to harvest credentials from customers of dozens of U.S. financial institutions and to deliver ProLock ransomware following Qbot spear-phishing campaigns.
A full list of indicators of compromised (IOCs) including a matrix of MITRE ATT&CK techniques and malware sample hashes used in this Qbot campaign can be found at the end of the Malwarebytes report.

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionQbot malware returns in campaign targeting hospitality industryNew ‘Gold Pickaxe’ Android, iOS malware steals your face for fraudFBI disrupts Chinese botnet by wiping malware from infected routersMicrosoft Teams phishing pushes DarkGate malware via group chats











Banking Trojan
Election 2020
MalSpam
Malware
Phishing
QakBot
Qbot
Trojan
USA
























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











