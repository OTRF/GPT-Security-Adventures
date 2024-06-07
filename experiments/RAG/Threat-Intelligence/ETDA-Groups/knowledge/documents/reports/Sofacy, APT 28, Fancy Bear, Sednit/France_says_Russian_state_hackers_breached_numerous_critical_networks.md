# Reference for threat actor for "Sofacy, APT 28, Fancy Bear, Sednit"

**Title**: France says Russian state hackers breached numerous critical networks

**Source**: https://www.bleepingcomputer.com/news/security/france-says-russian-state-hackers-breached-numerous-critical-networks/

## Content






















France says Russian state hackers breached numerous critical networks
































































































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




























HomeNewsSecurityFrance says Russian state hackers breached numerous critical networks







 















France says Russian state hackers breached numerous critical networks


By Bill Toulas




October 26, 2023
12:40 PM
0





The Russian APT28 hacking group (aka 'Strontium' or 'Fancy Bear') has been targeting government entities, businesses, universities, research institutes, and think tanks in France since the second half of 2021.
The threat group, which is considered part of Russia's military intelligence service GRU, was recently linked to the exploitation of CVE-2023-38831, a remote code execution vulnerability in WinRAR, and CVE-2023-23397, a zero-day privilege elevation flaw in Microsoft Outlook.
The Russian hackers have been compromising peripheral devices on critical networks of French organizations and moving away from utilizing backdoors to evade detection.
This is according to a newly published report from ANSSI (Agence Nationale de la sécurité des systèmes d'information), the French National Agency for the Security of Information Systems, that conducted investigations on the activities of the cyber-espionage group.
Network reconnaissance and initial access
ANSSI has mapped the TTPs (techniques, tactics, and procedures) of APT28, reporting that the threat group uses brute-forcing and leaked databases containing credentials to breach accounts and Ubiquiti routers on targeted networks.
In one case from April 2023, the attackers ran a phishing campaign that tricked the recipients into running PowerShell that exposed their system configuration, running processes, and other OS details.
Between March 2022 and June 2023, APT28 sent emails to Outlook users that exploited the then zero-day vulnerability now tracked as CVE-2023-23397, placing the initial exploitation a month earlier than what was recently reported.
During this period, the attackers also exploited CVE-2022-30190 (aka "Follina") in the Microsoft Windows Support Diagnostic Tool and CVE-2020-12641, CVE-2020-35730, CVE-2021-44026 in the Roundcube application.
The tools used in the first stages of the attacks include the Mimikatz password extractor and the reGeorg traffic relaying tool, as well as the Mockbin and Mocky open-source services.
ANSSI also reports that APT28 uses a range of VPN clients, including SurfShark, ExpressVPN, ProtonVPN, PureVPN, NordVPN, CactusVPN, WorldVPN, and VPNSecure.

Addresses that disseminated emails exploiting CVE-2023-23397 (ANSSI)
Data access and exfiltration
As a cyber-espionage group, data access and exfiltration are at the core of Strontium's operational goals.
ANSSI has observed the threat actors retrieving authentication information using native utilities and stealing emails containing sensitive information and correspondence.
Specifically, the attackers exploit CVE-2023-23397 to trigger an SMB connection from the targeted accounts to a service under their control, allowing the retrieval of the NetNTLMv2 authentication hash, which can be used on other services, too.
APT28's command and control server (C2) infrastructure relies on legitimate cloud services, such as Microsoft OneDrive and Google Drive, to make the exchange less likely to raise any alarms by traffic monitoring tools.
Finally, ANSSI has seen evidence that the attackers collect data using the CredoMap implant, which targets information stored in the victim's web browser, such as authentication cookies.
Mockbin and the Pipedream service are also involved in the data exfiltration process.

APT28 attack chain (ANSSI)
Defense recommendations
ANSSI emphasizes a comprehensive approach to security, which entails assessing risks. In the case of the APT28 threat, focusing on email security is crucial.
The agency's key recommendations around email security include:
Ensure the security and confidentiality of email exchanges.
Use secure exchange platforms to prevent email diversions or hijacks.
Minimize the attack surface of webmail interfaces and reduce risks from servers like Microsoft Exchange.
Implement capabilities to detect malicious emails.
For more details on ANSSI's findings and defense tips, check out the full report here.

Related Articles:
Stealthy KV-botnet hijacks SOHO routers and VPN devicesBlackwood hackers hijack WPS Office update to install malwareMicrosoft disrupts Russian hackers' operation on NATO targetsIvanti Connect Secure zero-days exploited to deploy custom malwareTurkish hackers Sea Turtle expand attacks to Dutch ISPs, telcos











APT28
Cyber-espionage
Data Exfiltration
Email
Espionage
France
























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











