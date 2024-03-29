# Reference for threat actor for "Riddle Spider"

**Title**: New Avaddon Ransomware launches in massive smiley spam campaign

**Source**: https://www.bleepingcomputer.com/news/security/new-avaddon-ransomware-launches-in-massive-smiley-spam-campaign/

## Content






















New Avaddon Ransomware launches in massive smiley spam campaign































































































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




























HomeNewsSecurityNew Avaddon Ransomware launches in massive smiley spam campaign







 














New Avaddon Ransomware launches in massive smiley spam campaign


By Lawrence Abrams


June 8, 2020
02:14 PM
0




With a wink and a smile, the new Avaddon Ransomware has come alive in a massive spam campaign targeting users worldwide.
Avaddon was launched at the beginning of this month and is actively recruiting hackers and malware distributors to spread the ransomware by any means possible.
As its first known attack, the Avaddon Ransomware is being distributed in a spam campaign reminiscent of February's Nemty Ransomware Love Letter campaign.
You like my photo?
In a wave of emails using subjects like "Your new photo?" or "Do you like my photo?" containing nothing but a winking smiley face, a JavaScript downloader for the Avaddon ransomware is being distributed.

Example Avaddon spam email
In a related report shared with BleepingComputer, the cybersecurity firm Appriver stated that the Phorphiex/Trik Botnet is distributing the malicious emails.
This campaign is not small, as AppRiver security researcher David Picket told us that they had blocked over 300,000 emails in just a short period.
Attached to these emails is a JavaScript file masquerading as a JPG photo with names like IMG123101.jpg.
Before you ask why someone would open a JavaScript file that was emailed to them, it is important to remember that Windows hides file extension by default, even though it is a known security risk.
That means to the recipient, it would just appear as a .jpg file, as shown  below.

JavaScript file displayed as a JPG
When executed, the JS attachment will launch both a PowerShell and Bitsadmin command to download the Avaddon ransomware executable to the %Temp% folder and run it.

Avaddon JScript downloader
In the sample tested by BleepingComputer, once executed, the ransomware will search for data to encrypt and append the .avdn extension to encrypted files.

Files encrypted by Avaddon
In each folder, a ransom note named [id]-readme.html will also be created. This ransom note contains a link to the TOR payment site and a unique victim ID used to login to the site.

Avaddon Ransom Note (Click to enlarge)
This TOR payment site includes the ransom amount, which in our cause was $900, and instructions on how to pay for a decryptor.

Avaddon TOR payment site
Other sections of the TOR site include a support chat, free test decryption, and a help page illustrated by Harry Potter characters.

Avaddon TOR help page
Unfortunately, ID-Ransomware creator Michael Gillespie has analyzed the ransomware and stated that it is secure and cannot be decrypted for free.
More to come
In advertisements posted to Russian-speaking hacker forums at the beginning of the month, Avaddon has stated that they are a new Ransomware-as-an-Affiliate (RaaS) program.

Avaddon advertisement on dark web
A RaaS program is when the ransomware creator is responsible for the development of the malware and the operation of the TOR payment site.
Affiliates who join the program are responsible for distributing the ransomware via spam, compromising networks, and exploit kits.
As part of this arrangement, Avaddon is paying affiliates 65% of any ransom payments they bring in, and the Avaddon operators will receive 35%. Larger affiliates are commonly able to negotiate a higher revenue share depending on the size of their attacks.
As is typical with RaaS programs, Avaddon has a series of rules that affiliates must follow when distributing the ransomware. The most common rule is that they cannot target victims in the Commonwealth of Independent States (CIS).
It is forbidden to work in the CIS countries (AZ, AM, BY, KZ, KG, MD, RU, TJ, UZ, UA, GE , TM)
It is forbidden to indicate or pass on to third parties the address of the admin panel on the .onion network.
It is forbidden to upload .exe to unverified scanners that merge AV labs.
 
Now that the Avaddon creators have started accepting applications, we should expect to see distribution increase and more advanced attacks to occur.

Related Articles:
Ransomware payments reached record $1.1 billion in 2023Zeppelin ransomware source code sold for $500 on hacking forumLockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claims200,000 Facebook Marketplace user records leaked on hacking forum

IOCs
Hashes:

Attachment: 94faa76502bb4342ed7cc3207b3158027807a01575436e2b683d4816842ed65d
Avaddon: 05af0cf40590aef24b28fa04c6b4998b7ab3b7f26e60c507adb84f3d837778f2
Associated files:

IMG123101.jpg.js.zip
IMG123101.jpg.js
%temp%\97459754.exe
%temp%\646246465.exe
[id]-readme.html
Ransom note text:

Your network has been infected by Avaddon
All your documents, photos, databases and other important files have been encrypted and you are not able to decrypt it by yourself. But don't worry, we can help you to restore all your files!

The only way to restore your files is to buy our special software - Avaddon General Decryptor. Only we can give you this software and only we can restore your files!

You can get more information on our page, which is located in a Tor hidden network.

How to get to our page
Download Tor browser - https://www.torproject.org/
Install Tor browser
Open link in Tor browser - avaddonbotrxmuyl.onion

Follow the instructions on this page

Your ID:
XXX

DO NOT TRY TO RECOVER FILES YOURSELF!

DO NOT MODIFY ENCRYPTED FILES!

OTHERWISE, YOU MAY LOSE ALL YOUR FILES FOREVER!







Avaddon
Hacker Forum
RaaS
Ransomware
Smiley
Wink



















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











