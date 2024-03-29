# Reference for threat actor for "Sandworm Team, Iron Viking, Voodoo Bear"

**Title**: Russian hackers use WinRAR to wipe Ukraine state agency’s data

**Source**: https://www.bleepingcomputer.com/news/security/russian-hackers-use-winrar-to-wipe-ukraine-state-agencys-data/

## Content






















Russian hackers use WinRAR to wipe Ukraine state agency’s data
































































































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




























HomeNewsSecurityRussian hackers use WinRAR to wipe Ukraine state agency’s data







 














Russian hackers use WinRAR to wipe Ukraine state agency’s data


By Bill Toulas


May 3, 2023
04:41 PM
1




The Russian 'Sandworm' hacking group has been linked to an attack on Ukrainian state networks where WinRar was used to destroy data on government devices.
In a new advisory, the Ukrainian Government Computer Emergency Response Team (CERT-UA) says the Russian hackers used compromised VPN accounts that weren't protected with multi-factor authentication to access critical systems in Ukrainian state networks.
Once they gained access to the network, they employed scripts that wiped files on Windows and Linux machines using the WinRar archiving program.
On Windows, the BAT script used by Sandworm is 'RoarBat,' which searches disks and specific directories for filetypes such as doc, docx, rtf, txt, xls, xlsx, ppt, pptx, vsd, vsdx, pdf, png, jpeg, jpg, zip, rar, 7z, mp4, sql, php, vbk, vib, vrb, p7s, sys, dll, exe, bin, and dat, and archives them using the WinRAR program.

RoarBat searching for specified filetypes on all drives (CERT-UA)
However, when WinRar is executed, the threat actors use the "-df" command-line option, which automatically deletes files as they are archived. The archives themselves were then deleted, effectively deleting the data on the device.
CERT-UA says RoarBAT is run through a scheduled task created and centrally distributed to devices on the Windows domain using group policies.

Scheduled task set to run the BAT script (CERT-UA)
On Linux systems, the threat actors used a Bash script instead, which employed the "dd" utility to overwrite target file types with zero bytes, erasing their contents. Due to this data replacement, recovery for files "emptied" using the dd tool is unlikely, if not entirely impossible.
As both the 'dd' command and WinRar are legitimate programs, the threat actors likely used them to bypass detection by security software.
CERT-UA says the incident is similar to another destructive attack that hit the Ukrainian state news agency "Ukrinform" in January 2023, also attributed to Sandworm.
"The method of implementation of the malicious plan, the IP addresses of the access subjects, as well as the fact of using a modified version of RoarBat testify to the similarity with the cyberattack on Ukrinform, information about which was published in the Telegram channel "CyberArmyofRussia_Reborn" on January 17, 2023." reads the CERT-UA advisory.
CERT-UA recommends that all critical organizations in the country reduce their attack surface, patch flaws, disable unneeded services, limit access to management interfaces, and monitor their network traffic and logs.
As always, VPN accounts that allow access to corporate networks should be protected with multi-factor authentication.

Related Articles:
Ukraine: Hack wiped 2 petabytes of data from Russian research centerRussian hackers wiped thousands of systems in KyivStar attackPro-Ukraine hackers breach Russian ISP in revenge for KyivStar attackRussian military hackers target Ukraine with new MASEPIE malwareTurla hackers backdoor NGOs with new TinyTurla-NG malware








Data Wiper
Hackers
Russia
Sandworm
Ukraine
WinRAR
Wiper



















Bill Toulas   
Bill Toulas is a tech writer and infosec news reporter with over a decade of experience working on various online publications, covering open-source, Linux, malware, data breach incidents, and hacks.



 Previous Article 
Next Article 


Comments


 




cyberwolfe  - 9 months ago 

 
 


The article doesn't mention if the group paid for WinRaR. 





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











