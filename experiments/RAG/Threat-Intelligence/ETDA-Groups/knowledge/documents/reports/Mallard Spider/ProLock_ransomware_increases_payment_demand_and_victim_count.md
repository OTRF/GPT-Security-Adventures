# Reference for threat actor for "Mallard Spider"

**Title**: ProLock ransomware increases payment demand and victim count

**Source**: https://www.bleepingcomputer.com/news/security/prolock-ransomware-increases-payment-demand-and-victim-count/

## Content






















ProLock ransomware increases payment demand and victim count
































































































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




























HomeNewsSecurityProLock ransomware increases payment demand and victim count







 















ProLock ransomware increases payment demand and victim count


By Ionut Ilascu




September 10, 2020
04:44 AM
0





Using standard tactics, the operators of ProLock ransomware were able to deploy a large number of attacks over the past six months, averaging close to one target every day.
Following a failed start in late 2019, under the name PwndLocker, due to a crypto bug that allowed unlocking the files for free, the operators rebooted the operation with fixing the flaw and renaming the malware to ProLock.
From the beginning, the threat actor aimed high, targeting enterprise networks and demanding ransoms between $175,000 to more than $660,000.
A fresh start in March under the ProLock label also meant increased activity and larger ransoms. Since then, the average figure swelled to $1.8 million, indicates incident response data from cybersecurity company Group-IB.
Simple, efficient tactics
The threat actor has no preference for its targets or the sector of their activity as long as they are companies with big networks, able to pay a higher ransom. So far, the focus seems to be on businesses in Europe and North America.
For the past half-year, Group-IB detected more than 150 ProLock operations, the most recent victim being asked 225 Bitcoins (more than $2,3 million at current value).

The group’s tactics, techniques, and procedures are simple and effective, the partnership with QakBot (QBot) banking trojan allowing them to map the network, move laterally, ultimately deploy the ransomware.
Between the initial compromise and running the file-encryption routine, the actor spends about a month on the network, gathering information for better targeting and exfiltrating data (via Rclone).
Running ProLock on the target network is the last step of the attack, which typically starts with a spear-phishing email containing weaponized VBScripts and Office documents that deliver QakBot, oftentimes via replies in hijacked email threads.
Group-IB found that many times the VBScripts for downloading QakBot are very large, weighing even 40MB, to bypass security solutions that skip scanning large files.
Once on the target host, QakBot establishes persistence and makes sure that active defenses don’t spot it by modifying Windows Registry to add its binaries on the list of Windows Defender exclusions.

“QakBot also collects a lot of information about the infected host, including the IP address, hostname, domain, and list of installed programs. Thanks to this information, the threat actor acquires a basic understanding of the network and can plan post-exploitation activities” - Group-IB

With tools like Bloodhound and ADFind, the threat actor profiles the environment to distribute the banking trojan to other hosts on the network. In some cases, this was done manually using PsExec, suggesting a strong connection between ProLock and QakBot operators.
Moving laterally also involved the use of remote desktop (RDP), and when this was not available on a machine, the actor ran the following batch script via PsExec to enable the remote connection:

ProLock’s toolkit includes Mimikatz post-exploitation tool for penetration testers, which is deployed through Cobalt strike software for red team engagements.
Group-IB found that the ransomware actor sometimes relies on a vulnerability in Windows (CVE-2019-0859) that enables them to escalate privileges on compromised systems.
According to the report today, the file-encrypting malware lands on the host either via QakBot, downloaded with the Background Intelligent Transfer Service (BITS) from the attacker's server or by executing a script using Windows Management Instrumentation (WMIC) on a remote host.
Despite using standard tools, ProLock attacks remain largely undetected on the network, giving them time to prepare the file encryption stage and steal data.
Attacks from this threat actor have intensified lately, causing the FBI to release two FLASH Alerts about this actor this year [1, 2]. In the first one, the agency warns that the ProLock decryption tool may cause data loss because it does not work properly all the time.
Group-IB said that they could not verify this statement because they're none of their customers had to pay the ransom.

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionKasseika ransomware uses antivirus driver to kill other antivirusesNew Black Basta decryptor exploits ransomware flaw to recover filesVans and North Face owner VF Corp hit by ransomware attackQbot malware returns in campaign targeting hospitality industry











Encryption
ProLock
QakBot
Qbot
Ransomware
Trojan
























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











