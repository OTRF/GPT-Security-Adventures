# Reference for threat actor for "LockBit Gang"

**Title**: LockBit ransomware goes 'Green,' uses new Conti-based encryptor

**Source**: https://www.bleepingcomputer.com/news/security/lockbit-ransomware-goes-green-uses-new-conti-based-encryptor/

## Content






















LockBit ransomware goes 'Green,' uses new Conti-based encryptor
































































































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




























HomeNewsSecurityLockBit ransomware goes 'Green,' uses new Conti-based encryptor







 















LockBit ransomware goes 'Green,' uses new Conti-based encryptor


By Lawrence Abrams




February 1, 2023
05:48 PM
0





The LockBit ransomware gang has again started using encryptors based on other operations, this time switching to one based on the leaked source code for the Conti ransomware.
Since its launch, the LockBit operation has gone through numerous iterations of its encryptor, starting with a custom one and moving to LockBit 3.0 (aka LockBit Black), which is derived from the BlackMatter gang's source code.
This week, cybersecurity collective VX-Underground first reported that the ransomware gang is now using a new encryptor named 'LockBit Green,' based on the leaked source code of the now-disbanded Conti gang.
The Conti ransomware gang shut down after a series of embarrassing data breaches caused by the leaking of 170,000 internal messages and the source code for their encryptor.
Soon after the source code was leaked, other hacking groups began utilizing it to create their own encryptors, with some ironically used against Russian companies.
A look at LockBit Green
Since the news of LockBit Green became public, researchers have found samples of the new encryptor circulating on VirusTotal and other malware-sharing sites.
A malware analyst known as CyberGeeksTech reverse-engineered a sample of LockBit Green and told BleepingComputer that it was definitely based on the Conti encryptor they previously analyzed.
"I've analyzed the sample and it's 100% based on the Conti source code," the researcher told BleepingComputer.
"The decryption algorithm is just an example of a similarity. It's weird that they've chosen to build a payload based on Conti, they have their own encryptor for some time."
Cybersecurity firm PRODAFT also shared four MD5 hashes of LockBit Green samples that they found, including a Yara rule that can detect the new variant.
PRODAFT told BleepingComputer that they know of at least five victims that have been attacked using the new LockBit Green variant.
BleepingComputer tested one of the samples shared by PRODAFT, which utilizes the same command-line arguments as the previous Conti encryptors.
The ransom notes have been modified to use the LockBit 3.0 ransom note rather than Conti's format, as shown below.

LockBit Green ransom noteSource: BleepingComputer
However, one change we noticed is that LockBit Green uses what appears to be a random extension rather than the standard .lockbit extension.

Different encrypted file extension used in LockBit GreenSource: BleepingComputer
While it's unclear why the LockBit operation is utilizing a new Conti-based encryptor when their previous one works fine, PRODAFT may have the answer.
"We especially observed that ex-Conti members preferred LockBit Green after the announcement. They probably feel comfortable using conti-based ransomware," PRODAFT told BleepingComputer.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaBank of America warns customers of data breach after vendor hackThe Week in Ransomware - February 2nd 2024 - No honor among thievesThe Week in Ransomware - January 26th 2024 - Govts strike backResearchers link 3AM ransomware to Conti, Royal cybercrime gangs











Conti
Encryptor
Leak
LockBit
Ransomware
Source Code
























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











