# Reference for threat actor for "LockBit Gang"

**Title**: LockBit ransomware moves quietly on the network, strikes fast

**Source**: https://www.bleepingcomputer.com/news/security/lockbit-ransomware-moves-quietly-on-the-network-strikes-fast/

## Content






















LockBit ransomware moves quietly on the network, strikes fast
































































































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




























HomeNewsSecurityLockBit ransomware moves quietly on the network, strikes fast







 














LockBit ransomware moves quietly on the network, strikes fast


By Ionut Ilascu


October 21, 2020
10:28 AM
0




LockBit ransomware takes as little as five minutes to deploy the encryption routine on target systems once it lands on the victim network.
Joining the ransomware-as-a-service (RaaS) business in September 2019, LockBit is atypical in that it’s driven by automated processes for quick spreading across the victim network, identifying valuable systems and locking them up.
LockBit attacks leave few traces for forensic analysis as the malware loads into the system memory, with logs and supporting files removed upon execution.
Scripts and backdoors
After investigating a series of eight incidents at smaller organizations, security researchers at Sophos were able to add more pieces to the puzzle that is LockBit.
In one case, they found that the attack began from a compromised Internet Information Server that launched a remote PowerShell script calling another script embedded in a remote Google Sheets document.

This script connects to a command and control server to retrieve and install a PowerShell module for adding a backdoor and establish persistence.
To evade monitoring and go unnoticed in the logs, the attacker renamed copies of PowerShell and the binary for running Microsoft HTML Applications (mshta.exe); this prompted Sophos to call this a “PS Rename“ attack.
The backdoor is responsible for installing attack modules and executes a VBScript that downloads and executes a second backdoor on systems restart. An overview of the attack is available below:

“The attack scripts also attempt to bypass Windows 10’s built-in anti-malware interface [AMSI], directly applying patches to it in memory,” says Sean Gallagher, Senior Threat Researcher at Sophos
Artifacts found on attacked systems suggest the use of scripts based on the PowerShell Empire post-exploitation framework. Their purpose was to collect details about the victim network, identify valuable systems, and check for available defense solutions.
Gallagher says that these scripts also used regular expressions to search Windows Registry for “very specific types of business software” used for point-of-sale systems or accounting.
Below is a list of with keywords of interest included in the search:

The malicious code would deploy LockBit ransomware only if the targets matched a fingerprint indicating an attractive target, the researcher notes in a report today.
Quick strike
After picking the valuable targets, LockBit ransomware would execute in memory within five minutes using a Windows Management Instrumentation (WMI) command.

“All of the targets were hit within five minutes over WMI. The server-side file used to distribute the ransomware, along with most of the event logs on the targeted systems and the server itself, were wiped in the course of the ransomware deployment” - Sean Gallagher

The researcher says that WMI commands could pass from a server to a system because the attack modules modified firewall rules to allow it.
In these attacks, the initial compromise method remains unknown. In a report from May, McAfee Labs and cybersecurity firm Northwave detail how LockBit ransomware gained access to the victim network by brute-forcing an admin’s logins for an outdated VPN service.
In three hours, the malware encrypted about 25 servers and 225 computer systems.

Related Articles:
LockBit claims ransomware attack on Fulton County, GeorgiaBank of America warns customers of data breach after vendor hackThe Week in Ransomware - February 2nd 2024 - No honor among thievesThe Week in Ransomware - January 26th 2024 - Govts strike backThe Week in Ransomware - January 12th 2024 - Targeting homeowners' data








LockBit
Ransomware



















Ionut Ilascu   
Ionut Ilascu is a technology writer with a focus on all things cybersecurity. The topics he writes about include malware, vulnerabilities, exploits and security defenses, as well as research and innovation in information security. His work has been published by Bitdefender, Netgear, The Security Ledger and Softpedia.



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











