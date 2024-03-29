# Reference for threat actor for "LockBit Gang"

**Title**: LockBit ransomware self-spreads to quickly encrypt 225 systems

**Source**: https://www.bleepingcomputer.com/news/security/lockbit-ransomware-self-spreads-to-quickly-encrypt-225-systems/

## Content






















LockBit ransomware self-spreads to quickly encrypt 225 systems































































































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




























HomeNewsSecurityLockBit ransomware self-spreads to quickly encrypt 225 systems







 














LockBit ransomware self-spreads to quickly encrypt 225 systems


By Lawrence Abrams


May 4, 2020
05:09 PM
0




A feature of the LockBit ransomware allows threat actors to breach a corporate network and deploy their ransomware to encrypt hundreds of devices in just a few hours.
Started in September 2019, LockBit is a relatively new Ransomware-as-a-Service (RaaS) where the developers are in charge of the payment site and development and 'affiliates' sign up to distribute the ransomware.

LockBit Ransom Note
As part of this setup, the LockBit developers earn a percentage of the ransom payments, typically around 25-40%, while the affiliates receive a more significant share at about 60-75%.
Encrypted corporate network in three hours
In a new joint report by the researchers at McAfee Labs and cybersecurity firm Northwave, who handled the incident response, we get insight into how a LockBit ransomware affiliate hacked into a corporate network and encrypted approximately 25 servers and 225 workstations.
All of this was done in just three hours.
According to Patrick Van Looy, a cybersecurity specialist for Northwave, the hackers gained access to the network by brute-forcing an administrator account through an outdated VPN service.
While most cyberattacks require the hackers to gain access to administrative credentials after breaching a network, as they already had an admin account, they were one step ahead and could quickly deploy the ransomware on the network.
"In this specific case it was a classic hit and run. After gaining access through brute-forcing the VPN, the attacker almost immediately launched the ransomware (which he could with the administrator account that he had access to). It was around 1:00 AM that the initial access took place, after which the ransomware was launched and at around 4:00 AM the attacker logged off. This was the only interaction that we have observed," Looy told BleepingComputer via email.
Not all devices on the network were encrypted, which Looy attributes to a bug in the ransomware that caused it to crash.
For those systems that were encrypted, though, it was done quickly through an interesting feature built into LockBit.
LockBit spreads itself
Analysis by McAfee shows that the LockBit ransomware includes a feature that allows it to spread itself to the rest of the computers on a network.
When executed, in addition to encrypting the device's files, LockBit will also perform ARP requests to find other active hosts on the network and then attempts to connect to them over SMB.

Connecting to other computers via SMB
If the ransomware was able to connect to a computer via SMB, it issues a remote PowerShell command to download the ransomware and execute it.

Command to download and execute the LockBit ransomware
As more computers on the network become infected, these same infected computers help to speed up the deployment of the ransomware to other computers on the network.
This feature allowed the attackers to breach the network and encrypt 225 computers in an automated manner in just three hours.
The faster your attack, the less chance of being detected
When attackers breach a network, the longer they move you around within it, the greater the chances they will be detected.
This causes unskilled hackers to be detected more frequently as they attempt to spread laterally in a network compared to more advanced and skilled attackers.
With the ransomware automatically spreading by itself, it makes it easier for unskilled attackers to perform a successful attack.
"The unusual aspect, compared to other cases that we had, was that the attacker was only in the network for such a short period. Normally we see that attackers are in the network for days or even weeks before deploying the ransomware."
"In this specific case an attacker did not need to be that skilled. The ransomware is self-spreading, so after gaining (administrator) access, it is simply launching the ransomware and job is done," Looy told BleepingComputer.com.
With speed and ease of deployment, we should expect to see LockBit continue to grow and expand with affiliates who want to quickly get in and out of a network, while still encrypting most of its devices.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaBank of America warns customers of data breach after vendor hackThe Week in Ransomware - February 2nd 2024 - No honor among thievesJohnson Controls says ransomware attack cost $27 million, data stolenHow SMBs can lower their risk of cyberattacks and data breaches








Cyberattack
Enterprise
LockBit
Ransomware
SMB



















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











