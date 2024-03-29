# Reference for threat actor for "Mummy Spider, TA542"

**Title**: Emotet now drops Cobalt Strike, fast forwards ransomware attacks

**Source**: https://www.bleepingcomputer.com/news/security/emotet-now-drops-cobalt-strike-fast-forwards-ransomware-attacks/

## Content






















Emotet now drops Cobalt Strike, fast forwards ransomware attacks

































































































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




























HomeNewsSecurityEmotet now drops Cobalt Strike, fast forwards ransomware attacks







 















Emotet now drops Cobalt Strike, fast forwards ransomware attacks


By Lawrence Abrams




December 7, 2021
06:21 PM
0





In a concerning development, the notorious Emotet malware now installs Cobalt Strike beacons directly, giving immediate network access to threat actors and making ransomware attacks imminent.
Emotet is a malware infection that spreads through spam emails containing malicious Word or Excel documents. These documents utilize macros to download and install the Emotet Trojan on a victim's computer, which is then used to steal email and deploy further malware on the device.
Historically, Emotet would install the TrickBot or Qbot trojans on infected devices. These Trojans would eventually deploy Cobalt Strike on an infected device or perform other malicious behavior.
Cobalt Strike is a legitimate penetration testing toolkit that allows attackers to deploy "beacons" on compromised devices to perform remote network surveillance or execute further commands.
However, Cobalt Strike is very popular among threat actors who use cracked versions as part of their network breaches and is commonly used in ransomware attacks.
Emotet changes its tactics
Today, Emotet research group Cryptolaemus warned that Emotet is now skipping their primary malware payload of TrickBot or Qbot and directly installing Cobalt Strike beacons on infected devices.

WARNING  We have confirmed that #Emotet is dropping CS Beacons on E5 Bots and we have observed the following as of 10:00EST/15:00UTC. The following beacon was dropped: https://t.co/imJDQTGqxV Note the traffic to lartmana[.]com. This is an active CS Teams Server. 1/x
— Cryptolaemus (@Cryptolaemus1) December 7, 2021
A Flash Alert shared with BleepingComputer by email security firm Cofense explained that a limited number of Emotet infections installed Cobalt Strike, attempted to contact a remote domain, and then was uninstalled.
"Today, some infected computers received a command to install Cobalt Strike, a popular post-exploitation tool," warns the Cofense Flash Alert.
"Emotet itself gathers a limited amount of information about an infected machine, but Cobalt Strike can be used to evaluate a broader network or domain, potentially looking for suitable victims for further infection such as ransomware."
"While the Cobalt Strike sample was running, it attempted to contact the domain lartmana[.]com. Shortly afterward, Emotet uninstalled the Cobalt Strike executable."
This is a significant change in tactics as after Emotet installed its primary payload of TrickBot or Qbot, victims typically had some time to detect the infection before Cobalt Strike was deployed.
Now that these initial malware payloads are skipped, threat actors will have immediate access to a network to spread laterally, steal data, and quickly deploy ransomware.
"This is a big deal. Typically Emotet dropped TrickBot or QakBot, which in turn dropped CobaltStrike. You'd usually have about a month between first infection and ransomware. With Emotet dropping CS directly, there's likely to be a much much shorter delay," security researcher Marcus Hutchins tweeted about the development.
This rapid deployment of Cobalt Strike will likely speed up ransomware deployment on compromised networks. This is especially true for the Conti ransomware gang who convinced the Emotet operators to relaunch after they were shut down by law enforcement in January.
Cofense says that it is unclear if this is a test, being used by Emotet for their own network surveillance, or is part of an attack chain for other malware families that partner with the botnet.

"We don’t know yet whether the Emotet operators intend to gather data for their own use, or if this is part of an attack chain belonging to one of the other malware families. Considering the quick removal, it might have been a test, or even unintentional." - Cofense.

Researchers will closely monitor this new development, and as further information becomes available, we will update this article.

Related Articles:
New RustDoor macOS malware impersonates Visual Studio updateNew Mimic ransomware abuses ‘Everything’ Windows search toolMicrosoft disables MSIX protocol handler abused in malware attacksNew Qbot malware variant uses fake Adobe installer popup for evasionNew ‘Gold Pickaxe’ Android, iOS malware steals your face for fraud











Cobalt Strike
Emotet
Malware
Ransomware
Windows
























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











