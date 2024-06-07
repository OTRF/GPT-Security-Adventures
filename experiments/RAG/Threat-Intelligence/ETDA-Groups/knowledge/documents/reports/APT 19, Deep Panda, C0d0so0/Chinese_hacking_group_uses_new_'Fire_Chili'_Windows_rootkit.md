# Reference for threat actor for "APT 19, Deep Panda, C0d0so0"

**Title**: Chinese hacking group uses new 'Fire Chili' Windows rootkit

**Source**: https://www.bleepingcomputer.com/news/security/chinese-hacking-group-uses-new-fire-chili-windows-rootkit/

## Content






















Chinese hacking group uses new 'Fire Chili' Windows rootkit
































































































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




























HomeNewsSecurityChinese hacking group uses new 'Fire Chili' Windows rootkit







 














Chinese hacking group uses new 'Fire Chili' Windows rootkit


By Bill Toulas


March 31, 2022
01:11 PM
2




The Chinese hacking group Deep Panda is targeting VMware Horizon servers with the Log4Shell exploit to deploy a novel rootkit named 'Fire Chili.'
The rootkit is digitally signed using a certificate from Frostburn Studios (game developer) or one from Comodo (security software) to evade detection by AV tools.
Analysts at Fortinet who tracked Deep Panda's recent activity believe the certificates have been stolen from the mentioned software developers.
Deep Panda is a notorious Chinese APT focusing on cyber-espionage operations that has been active for many years now. The FBI had arrested one of its members back in 2017 after linking him with the exploitation of three zero-day vulnerabilities.
Fire Chili rootkit
In a recent Deep Panda campaign discovered by Fortinet, the hacking group is deploying the new 'Fire Chili' rootkit to evade detection on compromised systems.
A rootkit is malware typically installed as a driver that hooks various Windows APIs to hide the presence of other files and configuration settings in the operating system. For example, by hooking Windows programming functions, a rootkit can filter data to not display malicious file names, processes, and Registry keys APIs to Windows programs requesting the data.
In the attacks, the rootkit is signed by valid digital certificates allowing it to bypass detection by security software and load into Windows without any warnings.

Certificates stolen from legitimate companies (Fortinet)
Upon launch, Fire Chili performs basic system tests to ensure it's not running on a simulated environment and checks that the kernel structures and objects to be abused during operation are present.
Fortinet reports that the most recent supported operating system version for Fire Chili is Windows 10 Creators Update, released in April 2017.
The goal of the rootkit is to keep file operations, processes, registry key additions, and malicious network connections hidden from the user and any security software that could be running on the compromised machine.
For this hiding function, the malware uses IOCTLs (input/output control system calls) that are pre-populated with the malicious artifacts and can be dynamically configured.
For example, to hide malicious TCP connections from netstat, the rootkit intercepts routine IOCTL calls to the device stack, retrieves the complete list of network connections, filters out its own, and finally returns a sanitized structure.

IOCTLs to hide malicious artifacts (Fortinet)
Winnti overlaps
While looking into the latest Deep Panda campaign, Fortinet found several overlaps with Winnti, another notorious Chinese hacking group known for using digitally signed certificates.
Also, Winnti is known for persistently targeting gaming companies, so they could have stolen those certificates during one of their successful campaigns.

"The reason these tools are linked to two different groups is unclear at this time. It's possible that the groups' developers shared resources, such as stolen certificates and C2 infrastructure, with each other. This may explain why the samples were only signed several hours after being compiled." - Fortinet

Sophisticated hacking collectives that focus on cyberespionage, and not so much for financial profit, are more likely to be backed or even coordinated by government handlers, so this overlap is hardly surprising.

Related Articles:
Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flawsMicrosoft unveils new 'Sudo for Windows' feature in Windows 11Chinese hackers hid in US infrastructure network for 5 yearsChinese hackers fail to rebuild botnet after FBI takedownFBI disrupts Chinese botnet by wiping malware from infected routers








China
Deep Panda
Rootkit
Windows
Winnti



















Bill Toulas   
Bill Toulas is a tech writer and infosec news reporter with over a decade of experience working on various online publications, covering open-source, Linux, malware, data breach incidents, and hacks.



 Previous Article 
Next Article 


Comments


 




MisterVVV  - 1 year ago 

 
 


If the certificate shown in the image from Fortinet is the one used by Deep Panda, how can it be that Windows allows the use of a non-valid Certificate, it expired 4/24/2018
.......or
Microsoft !!!!





 




NoneRain  - 1 year ago 

 
 


Certificates are used to ensure that the software is legit, and that it was not modified after publication. Expiring doesn't make it invalid. You can't use it in new stuff, but you still can access the software signed by it (legit signed software).
This is not Windows fault. To run unpatched Apache servers and 5 years old Win10 versions, are.





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











