# Reference for threat actor for "SunCrypt Gang"

**Title**: SunCrypt Ransomware shuts down North Carolina school district

**Source**: https://www.bleepingcomputer.com/news/security/suncrypt-ransomware-shuts-down-north-carolina-school-district/

## Content






















SunCrypt Ransomware shuts down North Carolina school district
































































































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




























HomeNewsSecuritySunCrypt Ransomware shuts down North Carolina school district







 














SunCrypt Ransomware shuts down North Carolina school district


By Lawrence Abrams


September 4, 2020
03:03 PM
0




A school district in North Carolina has suffered a data breach after having unencrypted files stolen during an attack by the SunCrypt Ransomware operators, BleepingComputer has discovered.
The Haywood County School district in North Carolina announced that they had suffered a ransomware attack on August 24th, 2020, but had not stated what ransomware was used.
This attack caused the district to shut down its network and halt remote learning, which had started on August 17th.
"Our delay in restarting remote instruction is the uncertainty about the use of staff computers. We will know more when the forensic work is complete."
"We apologize for being unable to communicate as effectively as normal. Servers, Internet, and telephone services are still down in the school system. We will send another update at the end of the day," the Haywood County School District explained in their report to parents.
The school district has since resumed remote learning on August 31st, but with some school technology services still impacted.
Ransomware attack led to a data breach
After performing an investigation, the Haywood Country School District states that unencrypted data was stolen during the ransomware attack.
"In announcing the ransomware attack on Monday, we wanted everyone to understand a data breach was possible. We have now confirmed a data breach occurred. We are taking every possible step to eliminate any potential harm to staff, students, and affiliates. At this point, the forensic work has not determined the extent of specific data that was stolen. We ask staff, students, and parents to monitor for any suspicious activity," the school district announced in a new update this week.
BleepingComputer has learned that the SunCrypt Ransomware operators are behind the attack on the school district.
As part of their tactics, the SunCrypt operators will steal unencrypted data before encrypting an organization's devices and threaten to release the data if a ransom is not paid.
After not paying, the ransomware operators have published a 5GB archive containing data stolen from the school district.

SunCrypt data leak site
This leaked data contains numerous sensitive documents and personal information related to the school district, students, and teachers.
A closer look at the Haywood County School District attack
When the SunCrypt ransomware operators perform an attack, they create a PowerShell script named after the victim and store it on the network's Windows domain controller.
BleepingComputer obtained the PowerShell script used in the Haywood County School District attack, as shown below. When executed on a device, it will launch the ransomware and encrypt the files on the computer.

Haywood.ps1 PowerShell file
To launch the PowerShell script on every computer, the attackers will push a batch file to each Windows device on the network. When executed, this batch file will run the haywood.ps1 script stored on the domain controller and encrypt the computer.
By performing the attack in this way, attackers can compromise a network, quietly harvest files to steal, and then push out the ransomware to all of the devices simultaneously. This method allows the attackers to quickly encrypt all devices on the network without being detected.
Once done, the victims will be left with folders containing files that have been renamed and encrypted.

SunCrypt Encrypted Files
In each folder is a ransom note named YOUR_FILES_ARE_ENCRYPTED.HTML, which contains instructions on how to access the Tor payment site where a victim can negotiate with the ransomware operators.

SunCrypt ransom note
Unfortunately, SunCrypt appears to be secure, which means there is no way to currently recover files for free.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaMGM Resorts ransomware attack led to $100 million loss, data theftTrans-Northern Pipelines investigating ALPHV ransomware attack claims200,000 Facebook Marketplace user records leaked on hacking forumRansomware attack forces 100 Romanian hospitals to go offline








Data Leak
Ransomware
School District
SunCrypt



















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











