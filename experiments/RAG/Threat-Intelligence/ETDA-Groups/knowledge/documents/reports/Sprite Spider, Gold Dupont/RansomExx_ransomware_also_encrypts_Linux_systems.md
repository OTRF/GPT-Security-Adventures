# Reference for threat actor for "Sprite Spider, Gold Dupont"

**Title**: RansomExx ransomware also encrypts Linux systems

**Source**: https://www.bleepingcomputer.com/news/security/ransomexx-ransomware-also-encrypts-linux-systems/

## Content






















RansomExx ransomware also encrypts Linux systems
































































































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




























HomeNewsSecurityRansomExx ransomware also encrypts Linux systems







 














RansomExx ransomware also encrypts Linux systems


By Lawrence Abrams


November 6, 2020
01:57 PM
3




With companies commonly using a mixed environment of Windows and Linux servers, ransomware operations have increasingly started to create Linux versions of their malware to ensure they encrypt all critical data.
A new report today by Kaspersky takes a look at the Linux version of the RansomExx ransomware, also known as Defray777.
RansomExx has been getting a lot of attention this week due to their ongoing attacks against Brazil's government networks and previous attacks against the Texas Department of Transportation (TxDOT), Konica Minolta, IPG Photonics, and Tyler Technologies.
Linux version of RansomExx
According to Kaspersky, when targeting Linux servers, the RansomExx operators will deploy an ELF executable named 'svc-new' used to encrypt a victim's server.
"After the initial analysis we noticed similarities in the code of the Trojan, the text of the ransom notes and the general approach to extortion, which suggested that we had in fact encountered a Linux build of the previously known ransomware family RansomEXX," Kaspersky researchers stated in their report.
Embedded in the Linux executable are a public RSA-4096 encryption key, the ransom note, and an extension named after the customer that will be appended to all encrypted files.

Code to encrypt files in Linux version
Unlike the Windows version, Kaspersky states that the Linux version is a no-frills ransomware. It does not contain any code to terminate processes, including security software, does not wipe free space like the Windows version does, and does not communicate with a command and control server.
If a victim pays the ransom, they will receive both a Linux and Windows decryptor with the corresponding RSA-4096 private key and encrypted file extension embedded in the executable.
The Linux version is named 'decryptor64' and is a command-line driven decryptor, as shown below.

Fabian Wosar, the CTO of cybersecurity firm Emsisoft, told BleepingComputer that he first saw RansomExx utilizing a Linux version in attacks in July 2020, but may have been used earlier. 
RansomExx is not the first ransomware to create Linux versions. In the past, Pysa (Menispoza), Snatch, and PureLocker have also distributed Linux variants.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaUbuntu 'command-not-found' tool can be abused to spread malwareTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBank of America warns customers of data breach after vendor hack








Defray777
Linux
RansomEXX
Ransomware



















Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.



 Previous Article 
Next Article 


Comments


 




TheDcoder  - 3 years ago 

 
 


Very interesting... I wonder how it manages to get into a linux machine in the first place, maybe exploiting old bugs in outdated software?





 




TsVk!  - 3 years ago 

 
 


Poorly configured or outdated servers facing the internet, or a lateral attack in a domain scenario from an exploited Microsoft machine.





 




NoneRain  - 3 years ago 

 
 


0day exploits are also a risk





Post a Comment Community Rules

You need to login in order to post a comment
Not a member yet? Register Now



You may also like:











Popular Stories






Hackers used new Windows Defender zero-day to drop DarkMe malware







Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flaws










Latest Downloads




Malwarebytes Anti-Malware
Version: 4.6.8.311
5M+ Downloads




Windows Repair (All In One)
Version: 4.14.1
2M+ Downloads




McAfee Consumer Products Removal tool
Version: NA
441,649 Downloads




AdwCleaner
Version: 8.4.0.0
56M+ Downloads




Everything Desktop Search
Version: 1.4.1.1017
24,866 Downloads



























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











