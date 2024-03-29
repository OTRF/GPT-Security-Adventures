# Reference for threat actor for "Mallard Spider"

**Title**: QBot uses Windows Defender Antivirus phishing bait to infect PCs

**Source**: https://www.bleepingcomputer.com/news/security/qbot-uses-windows-defender-antivirus-phishing-bait-to-infect-pcs/

## Content






















QBot uses Windows Defender Antivirus phishing bait to infect PCs
































































































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




























HomeNewsSecurityQBot uses Windows Defender Antivirus phishing bait to infect PCs







 















QBot uses Windows Defender Antivirus phishing bait to infect PCs


By Lawrence Abrams




October 12, 2020
03:50 PM
0





The Qbot botnet uses a new template for the distribution of their malware that uses a fake Windows Defender Antivirus theme to trick you into enabling Excel macros.
Qbot, otherwise known as QakBot or QuakBot, is Windows malware that steals bank credentials, Windows domain credentials, and provides remote access to threat actors who install ransomware.
Victims usually become infected with Qbot through another malware infection or via phishing campaigns using various lures, including fake invoices, payment and banking information, scanned documents, or invoices.

Example Qbot spam email
Source: Brad Duncan
Attached to these spam emails are malicious Excel (.xls) attachments. When opened, these attachments will prompt a user to 'Enable Content' so that malicious macros will run to install the Qbot malware on a victim's computer.
To trick a user into clicking the 'Enable Content button, and thus enabling macros, threat actors use stylized document templates that pretend to be from a trustworthy organization or from your operating system.
On August 25th, the Qbot switched to a new template that pretends to be an alert from Windows Defender Antivirus, claiming that the document is encrypted.
To decrypt the document, users need to click on 'Enable Editing' or 'Enable Content' to decrypt it using the 'Microsoft Office Decryption Core.'

New 'Windows Defender Antivirus' Qbot attachment
Once enable content is clicked, malicious macros will be executed that download and install the Emotet malware on a victim's computer.
To people who work in cybersecurity, are IT admins, or Windows enthusiasts, the above message appears silly and made up. To casual users, though, it is convincing enough that many would follow the instructions and become infected with Qbot.
Why it's essential to recognize Qbot attachments?
Over the past couple of months, Qbot has seen increased distribution, especially after being delivered in spam spewed forth by the Emotet botnet.
When infected, Qbot performs various malicious activities that allow threat actors to gain access to your bank accounts and your network.
Once they gain access to a network, they install ransomware such as ProLock throughout the system.
Due to this, it is vital to recognize the malicious document templates used by Qbot so that you do not accidentally become infected. 

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionMicrosoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flawsThe new Windows 11 features coming in 2024Microsoft January 2024 Patch Tuesday fixes 49 flaws, 12 RCE bugsQbot malware returns in campaign targeting hospitality industry











Maldoc
Microsoft
QakBot
Qbot
Spam
Windows
Windows Defender Antivirus
























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











