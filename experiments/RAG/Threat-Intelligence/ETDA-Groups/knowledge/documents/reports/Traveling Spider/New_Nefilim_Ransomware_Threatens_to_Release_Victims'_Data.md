# Reference for threat actor for "Traveling Spider"

**Title**: New Nefilim Ransomware Threatens to Release Victims' Data

**Source**: https://www.bleepingcomputer.com/news/security/new-nefilim-ransomware-threatens-to-release-victims-data/

## Content






















New Nefilim Ransomware Threatens to Release Victims' Data































































































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




























HomeNewsSecurityNew Nefilim Ransomware Threatens to Release Victims' Data







 














New Nefilim Ransomware Threatens to Release Victims' Data


By Lawrence Abrams


March 17, 2020
12:28 PM
0




A new ransomware called Nefilim that shares much of the same code as Nemty has started to become active in the wild and threatens to release stolen data.
Nefilim became active at the end of February 2020 and while it not known for sure how the ransomware is being distributed, it is most likely through exposed Remote Desktop Services.
Head of SentinelLabs Vitali Kremez and ID Ransomware's Michael Gillespie both told BleepingComputer that Nefilim and Nemty 2.5 share much of the same code.
The main difference is that Nefilim has removed the Ransomware-as-a-Service (RaaS) component and now relies on email communications for payments rather than a Tor payment site.
It is not known if this is a fork of their ransomware from the original operators or if new threat actors obtained the source code to release a new version.
Nefilim threatens to release data
In the Nefilim ransom note, the attackers state that if a user does not pay the ransom in seven days they will release data that was stolen from the network.
A large amount of your private files have been extracted and is kept in a secure location.
If you do not contact us in seven working days of the breach we will start leaking the data.
After you contact us we will provide you proof that your files have been extracted.
In the past, this would have been seen as an empty threat, but with ransomware infections such as Maze, Sodinokibi, DoppelPaymer, and Nemty all following through with their threats, it should no longer be ignored.
The Nefilim encryption process
When encrypting files, Nefilim will encrypt a file using AES-128 encryption. This AES encryption key will then be encrypted by an RSA-2048 public key that is embedded in the ransomware executable.
This encrypted AES key will then be added to the contents of each encrypted file and can only be decrypted by the RSA private key known to the ransomware developers.
For each encrypted file, Nefilim will append the .NEFILIM extension to the file name. For example, a file called 1.doc would be encrypted and named 1.doc.NEFILIM.

Files encrypted by the Nefilim Ransomware
In addition to the encrypted AES key, the ransomware will also add the "NEFILIM" string as a file marker to all encrypted files as shown below.

NEFILIM file marker
When done, a ransom note named NEFILIM-DECRYPT.txt will be created throughout the system that contains instructions on how to contact the ransomware developers.
This ransom note contains different contact emails and the threat that they will leak data if a ransom is not paid within seven days of the "breach".

Caption
Unfortunately, a brief analysis by Gillespie indicates that this ransomware appears to be secure, which means that there is no current way to recover files for free.
The ransomware, though, is still being researched and if new weaknesses we will publish updated information.

Related Articles:
Ransomware payments drop to record low as victims refuse to payNew RustDoor macOS malware impersonates Visual Studio updateRansomware payments reached record $1.1 billion in 2023Kasseika ransomware uses antivirus driver to kill other antivirusesMajorca city Calvià extorted for $11M in ransomware attack

IOCs
Hashes:

5ab834f599c6ad35fcd0a168d93c52c399c6de7d1c20f33e25cb1fdb25aec9c6
Associated files:

NEFILIM-DECRYPT.txt
Associated emails:

jamesgonzaleswork1972@protonmail.com
pretty_hardjob2881@mail.com
dprworkjessiaeye1955@tutanota.com
Ransom note text:

All of your files have been encrypted with military grade algorithms.
We ensure that the only way to retrieve your data is with our software.
We will make sure you retrieve your data swiftly and securely when our demands are met.
Restoration of your data requires a private key which only we possess.
A large amount of your private files have been extracted and is kept in a secure location.
If you do not contact us in seven working days of the breach we will start leaking the data.
After you contact us we will provide you proof that your files have been extracted.
To confirm that our decryption software works email to us 2 files from random computers. 
You will receive further instructions after you send us the test files.
jamesgonzaleswork1972@protonmail.com
pretty_hardjob2881@mail.com
dprworkjessiaeye1955@tutanota.com







Data Exfiltration
Extortion
Nefilim
Nemty Ransomware
Ransom
Ransomware



















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











