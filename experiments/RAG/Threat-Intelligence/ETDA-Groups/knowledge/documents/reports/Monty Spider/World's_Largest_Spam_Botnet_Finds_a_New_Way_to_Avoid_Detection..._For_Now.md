# Reference for threat actor for "Monty Spider"

**Title**: World's Largest Spam Botnet Finds a New Way to Avoid Detection... For Now

**Source**: https://www.bleepingcomputer.com/news/security/worlds-largest-spam-botnet-finds-a-new-way-to-avoid-detection-for-now/

## Content






















World's Largest Spam Botnet Finds a New Way to Avoid Detection... For Now































































































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




























HomeNewsSecurityWorld's Largest Spam Botnet Finds a New Way to Avoid Detection... For Now







 















World's Largest Spam Botnet Finds a New Way to Avoid Detection... For Now


By Catalin Cimpanu




April 27, 2018
01:00 AM
0





Necurs, the world's largest spam botnet, with millions of infected computers under its control, has updated its arsenal and is currently utilizing a new technique to infect victims.
This new technique consists of sending an email to a potential victim containing an archive file, which unzips to a file with the extension of .URL. This is a typical Windows shortcut file that opens a web page directly into a browser, instead of a location on disk.
The final destination of this link is a remote script file that downloads and automatically executes a final payload.
Necurs dropping Quant Loader via .URL shortcut files
For this particular spam run, Necurs had been infecting victims with Quant Loader, a run-of-the-mill and nothing-special malware family that is intended only to gain boot persistence and download another strain of more potent malware down the road.
While this technique is most likely not new entirely, as crooks have abused .URL files in the past, it is new for Necurs. What makes this technique stand out is the simplified infection chain, which now relies only on delivering a zipped .URL shortcut file.
For the past six years, since Necurs has been around, the botnet's operators have rarely used such a simple spam technique and have always relied on complicated infection chains.
We've seen stuff like one-time or double-zipped archives delivering WSF files, JS files, Visual Basic scripts, and all sorts of Office file formats, either boobytrapped with macros or leveraging exploits to infect victims.
New technique evades email malware scanners
The purpose of this much simpler routine is to avoid malware scanners that analyze emails, looking for malicious links or boobytrapped attachments. Such solutions work on preset rules, many of which have been set up by security researchers based on previously observed malicious patterns.
The deployment of a simple .URL file is not a game-breaker, as security researchers only need to update existing detection rules with a new one, but this will give the Necurs botnet time to breathe and infect victims easier in the following weeks, as email malware scanners will receive updated detection rules.
At that point, just like we've seen Necurs in the past years, botnet operators will just make a small tweak to the infection chain —like putting the .URL file inside a double-zipped file instead of a one-time zipped file— and this whole cat and mouse game will start anew.
How users can protect themselves
What users need to know —or remember, if they're old enough to have seen this trick before— is that .URL files work like typical Windows shortcut file, such as .LNK, and hence, can use custom icons.
Trend Micro, the cyber-security firm who spotted this recent Necurs .URL-based malspam campaign, warns that crooks are using the standard folder icon to hide .URL files.
This makes it somewhat easy to trick users into thinking the email file attachment they just unzipped has created a folder that they need to enter and view the actual file. Unfortunately, this is what crooks want because trying to access this faux folder will launch the infection chain.
But there is a giveaway that may protect users. Just like every other typical Windows shortcut file, .URL files also show the classic arrow icon on the bottom-left corner of the folder icon, like in the image below.

If you ever spot such markers on files you received via email attachments, these files are malicious 100 percent, and users should avoid opening them.

Related Articles:
 Google Groups is ending support for Usenet to combat spam‘Wall of Flippers’ detects Flipper Zero Bluetooth spam attacks











MalSpam
Necurs
Spam
























Catalin Cimpanu  
Catalin Cimpanu is the Security News Editor for Bleeping Computer, where he covers topics such as malware, breaches, vulnerabilities, exploits, hacking news, the Dark Web, and a few more. Catalin previously covered Web & Security news for Softpedia between May 2015 and October 2016. The easiest way to reach Catalin is via his XMPP/Jabber address at campuscodi@xmpp.is. For other contact methods, please visit Catalin's author page.




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











