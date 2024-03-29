# Reference for threat actor for "FIN11"

**Title**: Clop now leaks data stolen in MOVEit attacks on clearweb sites

**Source**: https://www.bleepingcomputer.com/news/security/clop-now-leaks-data-stolen-in-moveit-attacks-on-clearweb-sites/

## Content






















Clop now leaks data stolen in MOVEit attacks on clearweb sites
































































































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




























HomeNewsSecurityClop now leaks data stolen in MOVEit attacks on clearweb sites







 















Clop now leaks data stolen in MOVEit attacks on clearweb sites


By Lawrence Abrams




July 23, 2023
03:10 PM
1





The Clop ransomware gang is copying an ALPHV ransomware gang extortion tactic by creating Internet-accessible websites dedicated to specific victims, making it easier to leak stolen data and further pressuring victims into paying a ransom.
When a ransomware gang attacks a corporate target, they first steal data from the network and then encrypt files. This stolen data is used as leverage in double-extortion attacks, warning victims that the data will be leaked if a ransom is not paid.
Ransomware data leak sites are usually located on the Tor network as it makes it harder for the website to be taken down or for law enforcement to seize their infrastructure.
However, this hosting method comes with its own issues for the ransomware operators, as a specialized Tor browser is required to access the sites, search engines do not index the leaked data, and the download speeds are typically very slow.
To overcome these obstacles, last year, the ALPHV ransomware operation, also known as BlackCat, introduced a new extortion tactic of creating clearweb websites to leak stolen data that were promoted as a way for employees to check if their data was leaked.
A clearweb website is hosted directly on the Internet rather than on anonymous networks like Tor, which require special software to access.
This new method makes it easier to access the data and will likely cause it to be indexed by search engines, further expanding the spread of the leaked information.
Clop ransomware gang adopts tactic
Last Tuesday, security researcher Dominic Alvieri told BleepingComputer that the Clop ransomware gang had started to create clearweb websites to leak data stolen during the recent and widespread MOVEit Transfer data theft attacks.
The first site created by the threat actors was for business consulting firm PWC, creating a website that leaked the company's stolen data in four spanned ZIP archives.
Soon after Alvieri told BleepingComputer, the threat actors also created websites for Aon, EY (Ernst & Young), Kirkland, and TD Ameritrade.
None of Clop's sites are as sophisticated as the ones created by ALPHV last year, as they simply list links to download the data rather than having a searchable database like BlackCat's sites.

Clearweb site created to leak PWC dataSource: BleepingComputer
A waste of time?
These sites aim to scare employees, executives, and business partners who may have been impacted by the stolen data, hoping it causes them to exert further pressure on a company to pay the ransom.
However, while there may be some benefits to leaking data in this way, they also come with their own problems, as putting them on the Internet, rather than Tor, makes them far more easily taken down.
At this time, all of the known Clop clearweb extortion sites have been taken offline.
It is unclear if these sites are down due to law enforcement seizures, DDoS attacks by cybersecurity firms, or hosting providers and registrars shutting down the sites.
Due to the ease with which they can be shut down, it is doubtful that this extortion tactic is worth the effort.

Related Articles:
Ransomware payments reached record $1.1 billion in 2023Ransomware payments drop to record low as victims refuse to payRansomware victims targeted by fake hack-back offersMGM casino's ESXi servers allegedly encrypted in ransomware attackIntegris Health patients get extortion emails after cyberattack











Clop
Data Leak Site
Extortion
MOVEit Transfer
Ransomware
Website
























Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.




 Previous Article 
Next Article 



Comments



  






leexgx  - 6 months ago 


 
 



Doesn't need to be up for long for it to be damaging/fast proof they have the data (doesn't affect tor/hidden so they can still be directed to it afterwards or both) 






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











