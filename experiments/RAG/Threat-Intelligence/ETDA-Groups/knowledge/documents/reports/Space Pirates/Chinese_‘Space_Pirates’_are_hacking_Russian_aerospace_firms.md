# Reference for threat actor for "Space Pirates"

**Title**: Chinese ‘Space Pirates’ are hacking Russian aerospace firms

**Source**: https://www.bleepingcomputer.com/news/security/chinese-space-pirates-are-hacking-russian-aerospace-firms/

## Content






















Chinese ‘Space Pirates’ are hacking Russian aerospace firms
































































































News



Featured
Latest







Microsoft: New critical Exchange bug exploited as zero-day





LockBit claims ransomware attack on Fulton County, Georgia





Trans-Northern Pipelines investigating ALPHV ransomware attack claims





Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flaws









Over 13,000 Ivanti gateways vulnerable to actively exploited bugs





Three critical application security flaws scanners can’t detect





Turla hackers backdoor NGOs with new TinyTurla-NG malware





New Qbot malware variant uses fake Adobe installer popup for evasion








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




























HomeNewsSecurityChinese ‘Space Pirates’ are hacking Russian aerospace firms







 















Chinese ‘Space Pirates’ are hacking Russian aerospace firms


By Bill Toulas




May 18, 2022
12:51 PM
0





A previously unknown Chinese hacking group known as 'Space Pirates' targets enterprises in the Russian aerospace industry with phishing emails to install novel malware on their systems.
The threat group is believed to have started operating in 2017, and while it has links to known groups like APT41 (Winnti), Mustang Panda, and APT27, it is thought to be a new cluster of malicious activity.
Russian threat analysts at Positive Technologies named the group "Space Pirates" due to their espionage operations focusing on stealing confidential information from companies in the aerospace field.
In the wild detections
The Space Pirates APT group has been seen targeting government agencies and enterprises involved in IT services, aerospace, and electric power industries located in Russia, Georgia, and Mongolia.
The threat analysts first discovered signs of Space Pirates' activity last summer during incident response and quickly confirmed that the threat actors used the same malware and infrastructure against at least four more domestic entities since 2019.
Two of these cases concern Russian companies with state participation, which the hackers successfully compromised.
In the first case, the threat actors maintained their access to 20 servers for ten months, stealing over 1,500 documents, employee details, and other sensitive data.
In the second case, the Chinese hackers stayed in the network of the compromised company for over a year, siphoning confidential information and installing their malware to 12 corporate network nodes in three distinct regions.
Novel malware
The arsenal of Space Pirates consists of custom loaders hiding behind decoy documents, slightly modified backdoors that have been around for years, the Chinese trademark malware PlugX, and tailored spins of the PcShare backdoor.
Moreover, Space Pirates' attacks have also employed ShadowPad, Zupdax, PoisonIvy, and ReVBShell in attacks.
In addition to the above, the newly discovered APT uses three previously undocumented modular malware tools, namely Deed RAT, BH_A006, and MyKLoadClient.
MyKLoadClient is a loader using SFX archives combined with DLL side-loading through an auxiliary launcher library signed by McAfee Inc. The launcher supports commands that give the threat actors close control over the infection.
BH_A006 is a heavily modified version of the Gh0st backdoor, featuring many layers of obfuscation to bypass security protections and thwart analysis.
Its features include network service creation, UAC bypassing, and shellcode unpacking and launching in the memory.

BH_A006 shellcode loading (PT)
Another interesting custom tool is Deed RAT, which features an unusual, intelligent method of transferring control to the shellcode.
Deed RAT's functions depend on which plugins are fetched and loaded. For example, PT has seen eight plugins for startup, C2 config, installation, code injection into processes, network interactions, connection management, registry editing, registry monitoring, and proxy sniffing.
The supported protocols for C2 communication include TCP, TLS, HTTP, HTTPS, UDP, and DNS, so there's generally a high level of versatility.
The commands supported by Deed RAT are the following:
Collect system information
Create a separate communication channel for a plugin
Self-remove
Ping
Deactivate connection
Update the shellcode for an injection stored in the registry
Update the main shellcode on disk and delete all plugins
Chinese convolution
The threat analysts believe that the overlaps between various Chinese APTs are due to tool exchanges, a common phenomenon for hackers in the region.
Using shared tools further obscures the traces of distinct threat groups and makes the work of analysts a lot harder, so Chinese APTs have multiple reasons to follow this practice.

Various links between Chinese APTs (PT)
Space Pirates has also been seen deploying their custom malware on some Chinese firms for financial gains, so the threat group might have a dual function.
Chinese hackers have been very aggressive against Russian targets lately, as confirmed by recent findings of analysts at Secureworks and Google.
Espionage is a standard operation for Chinese APTs, and Russia is a valid target that excels in aerospace, weapons, electrical engineering, shipbuilding, and nuclear technology.

Related Articles:
Turla hackers backdoor NGOs with new TinyTurla-NG malwareChinese hackers hid in US infrastructure network for 5 yearsChinese hackers fail to rebuild botnet after FBI takedownFBI disrupts Chinese botnet by wiping malware from infected routersChinese hackers infect Dutch military network with malware











Aerospace
APT
China
Russia
Space Pirates
























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











