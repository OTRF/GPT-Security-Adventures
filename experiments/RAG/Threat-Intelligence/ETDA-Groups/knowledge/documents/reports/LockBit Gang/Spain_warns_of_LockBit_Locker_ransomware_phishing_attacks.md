# Reference for threat actor for "LockBit Gang"

**Title**: Spain warns of LockBit Locker ransomware phishing attacks

**Source**: https://www.bleepingcomputer.com/news/security/spain-warns-of-lockbit-locker-ransomware-phishing-attacks/

## Content






















Spain warns of LockBit Locker ransomware phishing attacks
































































































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




























HomeNewsSecuritySpain warns of LockBit Locker ransomware phishing attacks







 














Spain warns of LockBit Locker ransomware phishing attacks


By Bill Toulas


August 28, 2023
02:25 PM
0




The National Police of Spain is warning of an ongoing 'LockBit Locker' ransomware campaign targeting architecture companies in the country through phishing emails.
"A wave of sending emails to architecture companies has been detected, although it is not ruled out that they extend their action to other sectors," reads the machine-translated police announcement.
"The detected campaign has a very high level of sophistication since the victims do not suspect anything until they suffer the encryption of the terminals."
Spain's cyber police have detected that many emails are sent from the non-existent domain "fotoprix.eu" and impersonate a photographic firm.
The threat actors pretend to be a newly launched photography store requesting a facility renovation/development plan and a cost estimate for the work from the architecture firm.
After exchanging several emails to build trust, the LockBit operators propose to specify a meeting date to discuss the budget and details of the building project and send an archive with documents on the exact specifications of the renovation.
While the Spanish polish does not provide much technical detail, in a sample seen by BleepingComputer, this archive is a disk image (.img) file that, when opened in newer versions of Windows, will automatically mount the file as a drive letter and display its contents.
These archives contain a folder named 'fotoprix' that includes numerous Python files, batch files, and executables. The archive also contains a Windows shortcut named 'Caracteristicas,' that, when launched, will execute a malicious Python script.

IMG file contentsSource: BleepingComputer
BleepingComputer's analysis shows that the executed Python script will check if the user is an admin of the device, and if so, make modifications to the system for persistence and then executes the 'LockBit Locker' ransomware to encrypt files.

Malicious Python scriptSource: BleepingComputer
If the Windows user is not an admin on the device, it will use the Fodhelper UAC bypass to launch the ransomware encryptor with admin privileges.
The Spanish police underline the "very high level of sophistication" of these attacks, particularly noting the consistency of the communications that convince victims they interact with individuals genuinely interested in discussing architectural project details.
While the ransomware gang claims to be affiliated with the notorious LockBit ransomware operation, BleepingComputer believes this campaign is conducted by different threat actors using the leaked LockBit 3.0 ransomware builder.
The regular LockBit operation negotiates through a Tor negotiation site, while this 'LockBit Locker' negotiates via email at 'lockspain@onionmail.org' or via the Tox messaging platform.

LockBit Locker ransom noteSource: BleepingComputer
Furthermore, automated analysis by Intezer's scanning engine identifies the ransomware executable as being BlackMatter, a ransomware operation that shut down in 2021 and later rebranded as ALPHV/BlackCat.
However, this is expected, as the leaked LockBit 3.0 builder, also known as LockBit Black, is also identified by Intezer as BlackMatter for its use of BlackMatter source code.
Given the reported sophistication of the phishing emails and social engineering seen by BleepingComputer, it is likely that the threat actors behind this campaign are using different lures for companies in other sectors.
Phishing actors have extensively used the "call to bid" bait in campaigns impersonating private firms or government agencies and using well-crafted documents to convince of the legitimacy of their messages.
Notorious ransomware gangs adopting similar practices for initial compromise is a worrying development, as posing as legitimate customers could help them overcome obstacles like their targets' anti-phishing training.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaBank of America warns customers of data breach after vendor hackThe Week in Ransomware - February 2nd 2024 - No honor among thievesInterpol operation Synergia takes down 1,300 servers used for cybercrimeThe Week in Ransomware - January 26th 2024 - Govts strike back








Architecture
LockBit
Phishing
Police
Ransomware
Spain



















Bill Toulas   
Bill Toulas is a tech writer and infosec news reporter with over a decade of experience working on various online publications, covering open-source, Linux, malware, data breach incidents, and hacks.



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











