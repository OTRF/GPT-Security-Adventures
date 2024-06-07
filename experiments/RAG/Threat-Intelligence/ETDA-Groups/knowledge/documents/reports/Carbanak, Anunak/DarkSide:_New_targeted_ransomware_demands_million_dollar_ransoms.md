# Reference for threat actor for "Carbanak, Anunak"

**Title**: DarkSide: New targeted ransomware demands million dollar ransoms

**Source**: https://www.bleepingcomputer.com/news/security/darkside-new-targeted-ransomware-demands-million-dollar-ransoms/

## Content






















DarkSide: New targeted ransomware demands million dollar ransoms
































































































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




























HomeNewsSecurityDarkSide: New targeted ransomware demands million dollar ransoms







 














DarkSide: New targeted ransomware demands million dollar ransoms


By Lawrence Abrams


August 21, 2020
02:12 PM
2




A new ransomware operation named DarkSide began attacking organizations earlier this month with customized attacks that have already earned them million-dollar payouts.
Starting around August 10th, 2020, the new ransomware operation began performing targeted attacks against numerous companies.
In a "press release" issued by the threat actors, they claim to be former affiliates who had made millions of dollars working with other ransomware operations.
After not finding a "product" that suited their needs, they decided to launch their own operation.
"We are a new product on the market, but that does not mean that we have no experience and we came from nowhere.
We received millions of dollars profit by partnering with other well-known cryptolockers.
We created DarkSide because we didn't find the perfect product for us. Now we have it."
DarkSide states that they only target companies that can pay the specified ransom as they do not "want to kill your business."

The threat actors have also stated that they do not target the following types of organizations.
Medicine (hospitals, hospices).
Education (schools, universities).
Non-profit organizations.
Government sector.
It is too soon to tell if they will honor this statement.
From victims seen by BleepingComputer, DarkSide's ransom demands range from $200,000 to $2,000,000. These numbers can likely be more or less depending on the victim.

Random demand ranges
At least one of the victims seen by BleepingComputer appears to have paid a million+ dollar ransom.
DarkSide steals data before encrypting victims
Like other human-operated ransomware attacks, when the DarkSide operators breach a network, they will spread laterally throughout a network until they gain access to an administrator account and the Windows domain controller.
While they spread laterally, the attackers will harvest unencrypted data from the victim's servers and upload it to their own devices.
This stolen data is then posted to a data leak site under their control and used as part of the extortion attempt.
When data is posted to the leak site, the threat actors will list the company name, the date they were breached, how much data was stolen, screenshots of the data, and the types of stolen data.

DarkSide data leak site
DarkSide states that if a victim does not pay, they will publish all of the data on their website for at least six months.
This extortion strategy is designed to scare a victim into paying the ransom even if they can recover from backups.
If a victim pays the ransom, DarkSide states that they will remove the stolen data from their leak site.
For the victim that had paid the ransom, their data has already been removed from the site.
Customized ransomware attacks
When performing attacks, DarkSide will create a customized ransomware executable for the specific company they are attacking.
When executed, the ransomware will execute a PowerShell command that deletes Shadow Volume Copies on the system so that they cannot be used to restore files.
According to Advanced Intel's Vitali Kremez, it then proceeds to terminate various database, office applications, and mail clients to prepare the machine for encryption.
When encrypting a computer, DarkSide will avoid terminating certain processes.

vmcompute.exe
vmms.exe
vmwp.exe
svchost.exe
TeamViewer.exe
explorer.exe

Specifically avoiding TeamViewer is not common, if ever seen with ransomware, and could indicate that the threat actors are using it for remote access to computers.
Michael Gillespie, who analyzed the encryption process, told BleepingComputer that the ransomware utilizes a SALSA20 key to encrypt files. This key is then encrypted with a public RSA-1024 key included in the executable.
Each victim will also have a custom extension created using a custom checksum of the victim's MAC address.
 

DarkSide encrypted files
Each executable is customized to include personalized "Welcome to Dark" ransom note, which will include the amount of data that was stolen, the type of data, and a link to their data on the data leak site.

DarkSide Ransom Note
At this time, the ransomware looks secure, and there is no way to recover files for free. 
Possible connection to REvil
When analyzing DarkSide, it was discovered that it has some similarities with the REvil ransomware.
The most obvious similarity is the ransom note, which uses almost the same template, as shown in the REvil ransom note below.

REvil Ransom Note
In BleepingComputer's behavioral analysis of DarkSide, we noticed that it would execute an encoded PowerShell script when first executed.

Executed PowerShell command
When deobfuscated, we can see that this PowerShell command is used to delete Shadow Volume Copies on the machine before encrypting it.

Get-WmiObject Win32_Shadowcopy | ForEach-Object {$_.Delete();}
Using PowerShell to execute the above command is the same method used by REvil.
Finally, MalwareHunterTeam found that DarkSide purposely avoids infecting victims in CIS countries.  The code to do this is similar to what is used in REvil and also GandCrab.

While these connections are tenuous, it is something that should be monitored.
Update 8/21/20: Added further technical information from Vitali Kremez and Michael Gillespie.

Related Articles:
New RustDoor macOS malware impersonates Visual Studio updateRansomware payments reached record $1.1 billion in 2023Ransomware payments drop to record low as victims refuse to payRansomware victims targeted by fake hack-back offersMGM casino's ESXi servers allegedly encrypted in ransomware attack








DarkSide
Data Exfiltration
Enterprise
Extortion
Ransomware



















Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.



 Previous Article 
Next Article 


Comments


 




NeutronJack  - 3 years ago 

 
 


I find it ironic that these a**holes write "We take our reputation very seriously..." while engaging in blatant extortion. Seems to me that cryptocurrency in the real enabler here.





 




abcdef345678  - 2 years ago 

 
 


The company I work for was attacked on 2/22/2021 with Darkside ransomware. We are still unsure if any data left our network which would constitute a reportable data breach. As of two days ago (2/25/2021), Darkside hasn't posted any leaked data to their TOR site. Assuming we cannot trust anything they tell us (since they *are* criminals), how do we know if they actually have any leaked data to post or not? At what point and how can be confident no data was actually exfiltrated?





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











