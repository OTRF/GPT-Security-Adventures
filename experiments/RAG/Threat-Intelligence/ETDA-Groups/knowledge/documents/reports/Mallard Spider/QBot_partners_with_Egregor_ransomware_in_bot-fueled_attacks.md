# Reference for threat actor for "Mallard Spider"

**Title**: QBot partners with Egregor ransomware in bot-fueled attacks

**Source**: https://www.bleepingcomputer.com/news/security/qbot-partners-with-egregor-ransomware-in-bot-fueled-attacks/

## Content






















QBot partners with Egregor ransomware in bot-fueled attacks
































































































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




























HomeNewsSecurityQBot partners with Egregor ransomware in bot-fueled attacks







 















QBot partners with Egregor ransomware in bot-fueled attacks


By Lawrence Abrams




November 20, 2020
05:00 AM
0





The Qbot banking trojan has dropped the ProLock ransomware in favor of the Egregor ransomware who burst into activity in September.
Qbot, otherwise known as QakBot or QuakBot, is Windows malware that steals bank credentials, Windows domain credentials, and provides remote access to threat actors who install ransomware.
Victims usually become infected with Qbot through phishing emails utilizing Excel documents that pretend to be DocSign documents, as shown below.

Qbot Docusign phishing email
Similar to how Ryuk works with TrickBot and DoppelPaymer/BitPaymer work with Dridex for access to networks, the ProLock ransomware has historically worked with Qbot to gain access to compromised networks.
When the ransomware gang is given access to a network, they use the Cobalt Strike pentesting tool to remotely spread laterally through the network while stealing unencrypted files and gathering admin credentials.
Once the attackers gain access to a domain admin account, they use it to deploy the ransomware throughout the Windows domain.
Qbot dumps ProLock for Egregor ransomware
In a new report by Oleg Skulkin, Senior Digital Forensics Analyst at Group-IB. a Singapore-based cybersecurity company, has found that Qbot is has stopped distributing ProLock and is now working with Egregor.
Since their launch in September 2020, Egregor has been one of the most active big game hunting ransomware operations currently active.
After the notorious Maze ransomware gang began shutting down their operation in September, many of their affiliates moved to the new Egregor operation.
Fueled by experienced ex-Maze affiliates and hackers, Egregor quickly started amassing a huge amount of victims worldwide.
"In less than 3 months Egregor operators have managed to successfully hit 69 companies around the world with 32 targets in the US, 7 victims in France and Italy each, 6 in Germany, and 4 in the UK. Other victims happened to be from the APAC, Middle East, and Latin America. Egregor’s favorite sectors are Manufacturing (28.9% of victims) and Retail (14.5%)," Skulkin explained.

Egregor activity since September 2020
Source: Group-IB
While the ransomware has changed, Skulkin states that the tactics, techniques, and procedures (TTPs) currently used by Egregor are similar to the previous attacks with ProLock.
'Tactics, techniques and procedures observed are very similar to those seen in the past Qakbot’s Big Game Hunting operations,” Skulkin stated  in a report shared with BleepingComputer.
As more Maze affiliates become involved in the Egregor operation, Skulkin expects the TTPs to eventually align to those seen historically in Maze attacks.
As the ransomware landscape continually evolves, threat actors switch to different operations, and partnerships are made, it is important for security professionals to keep track of the TTPs used by each operation to defend against them.
"The use of CobaltStike and QakBot are to watch when hunting for Egregor. More threat hunting and detection tips from Group-IB DFIR team as well as a detailed technical analysis of Egregor operations are available in Group-IB’s blog," Skulkin offers as advice when defending against Egregor.
Since its launch, Egregor has been responsible for other high profile attacks on Crytek, Ubisoft, Cencosud, and Barnes and Noble.

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionQbot malware returns in campaign targeting hospitality industryNew RustDoor macOS malware impersonates Visual Studio updateNew ‘Gold Pickaxe’ Android, iOS malware steals your face for fraudLockBit claims ransomware attack on Fulton County, Georgia











Egregor
Malware
QakBot
Qbot
Ransomware
Trojan
























Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.




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











