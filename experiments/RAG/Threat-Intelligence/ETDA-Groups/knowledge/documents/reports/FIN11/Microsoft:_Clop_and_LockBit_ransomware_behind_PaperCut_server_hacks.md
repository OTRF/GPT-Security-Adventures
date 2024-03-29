# Reference for threat actor for "FIN11"

**Title**: Microsoft: Clop and LockBit ransomware behind PaperCut server hacks

**Source**: https://www.bleepingcomputer.com/news/security/microsoft-clop-and-lockbit-ransomware-behind-papercut-server-hacks/

## Content






















Microsoft: Clop and LockBit ransomware behind PaperCut server hacks
































































































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




























HomeNewsSecurityMicrosoft: Clop and LockBit ransomware behind PaperCut server hacks







 















Microsoft: Clop and LockBit ransomware behind PaperCut server hacks


By Lawrence Abrams




April 26, 2023
07:28 PM
0





​Microsoft has attributed recent attacks on PaperCut servers to the Clop and LockBit ransomware operations, which used the vulnerabilities to steal corporate data.
Last month, two vulnerabilities were fixed in the PaperCut Application Server that allows remote attackers to perform unauthenticated remote code execution and information disclosure:
CVE-2023–27350 / ZDI-CAN-18987 / PO-1216: Unauthenticated remote code execution flaw impacting all PaperCut MF or NG versions 8.0 or later on all OS platforms, for both application and site servers. (CVSS v3.1 score: 9.8 – critical)
CVE-2023–27351 / ZDI-CAN-19226 / PO-1219: Unauthenticated information disclosure flaw impacting all PaperCut MF or NG versions 15.0 or later on all OS platforms for application servers. (CVSS v3.1 score: 8.2 – high)
On April 19th, PaperCut disclosed that these flaws were actively exploited in the wild, urging admins to upgrade their servers to the latest version.
A PoC exploit for the RCE flaw was released a few days later, allowing further threat actors to breach the servers using these exploits.
Ransomware gangs behind attacks
Today, Microsoft disclosed that the Clop and LockBit ransomware gangs are behind these PaperCut attacks and using them to steal corporate data from vulnerable servers.
PaperCut is a printing management software compatible with all major printer brands and platforms. It is used by large companies, state organizations, and education institutes, with the company's website claiming it is used by hundreds of millions of people from over 100 countries.
In a series of tweets posted Wednesday afternoon, Microsoft states that it has attributed the recent PaperCut attacks to the Clop ransomware gang.
"Microsoft is attributing the recently reported attacks exploiting the CVE-2023-27350 and CVE-2023-27351 vulnerabilities in print management software PaperCut to deliver Clop ransomware to the threat actor tracked as Lace Tempest (overlaps with FIN11 and TA505)," tweeted Microsoft's Threat Intelligence researchers.
Microsoft tracks this particular threat actor as 'Lace Tempest,' whose activity overlaps with FIN11 and TA505, both linked to the Clop ransomware operation.
Microsoft says that the threat actor has been exploiting the PaperCut vulnerabilities since April 13th for initial access to the corporate network.
Once they gained access to the server, they deployed the TrueBot malware, which has also been previously linked to the Clop ransomware operation.
Ultimately, Microsoft says a Cobalt Strike beacon was deployed and used to spread laterally through the network while stealing data using the MegaSync file-sharing application. 
In addition to Clop, Microsoft says some intrusions have led to LockBit ransomware attacks. However, it's unclear if these attacks began after the exploits were publicly released.
Microsoft recommends admins apply the available patches as soon as possible as other threat actors will likely begin exploiting the vulnerabilities.
A prime target for Clop
The exploitation of PaperCut servers fits a general pattern we have seen with the Clop ransomware gang over the past three years.
While the Clop operation still encrypts files in attacks, they have told BleepingComputer that they prefer to steal data to extort companies into paying a ransom.
This shift in tactics was first seen in 2020 when Clop exploited an Accellion FTA zero-day vulnerability to steal data from approximately 100 companies.
The Clop gang recently utilized zero-day vulnerabilities in the GoAnywhere MFT secure file-sharing platform to steal data from 130 companies.
PaperCut includes a 'Print Archiving' feature that saves all print jobs and documents sent through the server, making it a good candidate for data exfiltration attacks from the operation.
All organizations utilizing PaperCut MF or NG are strongly advised to upgrade to versions 20.1.7, 21.2.11, and 22.0.9 immediately and later to fix these vulnerabilities.
Update 4/27/28: The Clop ransomware operation confirmed to BleepingComputer that they were behind the attacks on PaperCut servers, which they started exploiting on April 13th.
However, they said that they used the vulnerabilities for initial access to networks, rather than to steal documents from the server itself.
In reply to our questions about the LockBit attacks, Microsoft said they had nothing further to share.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaBank of America warns customers of data breach after vendor hackNew RustDoor macOS malware impersonates Visual Studio updateThe Week in Ransomware - February 2nd 2024 - No honor among thievesThe Week in Ransomware - January 26th 2024 - Govts strike back











CL0P
Clop
Data Exfiltration
LockBit
PaperCut
Ransomware
Vulnerability
























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











