# Reference for threat actor for "Lapsus$"

**Title**: Globant confirms hack after Lapsus$ leaks 70GB of stolen data

**Source**: https://www.bleepingcomputer.com/news/security/globant-confirms-hack-after-lapsus-leaks-70gb-of-stolen-data/

## Content






















Globant confirms hack after Lapsus$ leaks 70GB of stolen data
































































































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




























HomeNewsSecurityGlobant confirms hack after Lapsus$ leaks 70GB of stolen data







 














Globant confirms hack after Lapsus$ leaks 70GB of stolen data


By Ionut Ilascu


March 30, 2022
02:47 PM
2




IT and software consultancy firm Globant has confirmed that they were breached by the Lapsus$ data extortion group, where data consisting of administrator credentials and source code was leaked by the threat actors.
As part of the leak, the hacking group released a 70GB archive of data stolen from Globant, describing it as “some customers source code.”
Source code and private keys
Globant is an IT and software development firm with over 16,000 employees worldwide and $1.2 billion in revenue for 2021.
Founded in Buenos Aires, Argentina, Globant is currently headquartered in Luxembourg and boasts a well-known list of customers, including Metropolitan Police, SmileDirectClub, Autodesk, Electronic Arts, Santander, Interbank, Royal Carribbean, and many more.
Following the leak from Lapsus$, Globant issued a press release confirming that some of the company source code has been exposed to an unauthorized party.

“We have recently detected that a limited section of our company's code repository has been subject to unauthorized access” - Globant

Among the data published by Lapsus$, there is a screenshot the group claims to be of an archived directory from Globant, containing folder names that appear to be company customers.
Some of the source code folders listed in the screenshot include, Abbott, apple-health-app, C-span, Fortune, Facebook, DHL, and Arcserve.

The metadata for the entries shows that the folders have been modified on March 29, which could indicate when the data was stolen.
In a follow-up post, Lapsus$ published a set of credentials for what they say give administrator access to various platforms used by Globant for developing, reviewing, and collaborating on customer code (Jira, Confluence, GitHub, Crucible).

A third post from the gang today shared a torrent file for about 70GB of data stolen from Globant. The company says that the intruder on its systems accessed “certain source code and project-related documentation for a very limited number of clients.”

The damage appears to be significant.
According to threat intelligence company SOS Intelligence, the leaked data contains customer information as well as a  code repositories with a large number of private keys (full chain, web server SSL certificates, Globant server, API keys).
One of the repositories is for the Bluecap app for consultancy in the financial sector, that Globant acquired in late 2020.

 
The cache that Lapsus$ leaked also includes a little over 150 SQL database files for various customer applications, SOS Intelligence says.

"In terms of legitimacy, going just by volume alone it's hard to fabricate that amount of data - however samples of the data have been cross referenced with live systems and other methods that show the leak is legitimate and very significant as far as Globant and Globant's impacted customers are concerned" - SOS Intelligence

Globant said today that its investigation into the incident did not reveal any evidence that the hackers compromised other parts of its infrastructure system.
Lapsus$ on LE radar
The Lapsus$ data extortion group has been constantly making the news due to their attacks on big technological companies, like Microsoft, Nvidia, Samsung, Okta, Ubisoft, many of them resulting in big data leaks.
Despite the big names on their victim list, Lapsus$ is believed to be formed mainly by teenagers exercising their hacking skills driven mainly by making a name on the hacking scene, not by financial motivation.
The group has been on the radar of law enforcement for a while and some individuals, all teens believed to be connected to Lapsus$, have been arrested in the U.K.
The FBI is also investigating the activities of the group and has asked the public for any information leading to identifying Lapsus$ members involved in the compromise of computer networks from U.S.-based companies.

However, it is unclear how many active members are in the group and what roles they play.
It is believed that Lapsus$ has affiliates all over the world, as their Telegram chats seem to suggest that some of them speak English, Russian, Turkish, German, and Portuguese.

Related Articles:
A mishandled GitHub token exposed Mercedes-Benz source codeDHS employees jailed for stealing data of 200K U.S. govt workers23andMe data breach: Hackers stole raw genotype data, health reportsJason’s Deli says customer data exposed in credential stuffing attackMGM Resorts ransomware attack led to $100 million loss, data theft








Data Breach
Data Leak
Lapsus$
Source Code



















Ionut Ilascu   
Ionut Ilascu is a technology writer with a focus on all things cybersecurity. The topics he writes about include malware, vulnerabilities, exploits and security defenses, as well as research and innovation in information security. His work has been published by Bitdefender, Netgear, The Security Ledger and Softpedia.



 Previous Article 
Next Article 


Comments


 




Elko_NV  - 1 year ago 

 
 


Not sure which techniques were used, but Pentesters often first run a program called Responder to make LLMNR requests- In many environments, this is the first step method for gaining initial credentials on a domain. Exposes password hashes which can later be cracked.
(HKLM\Software\Policies\Microsoft\Windows NT\DNSClient\EnableMulticast to 0) &
(Linux, modify /etc/systemd/resolved.conf and set LLMNR=no)
See Also, Wmic, NBNS, WPAD, SMB Signing, etc. Some good advice on mitigations here old.reddit.com/r/SecurityCadence/





 




Elko_NV  - 1 year ago 

 
 


*Got it...... "Lapsus$ and SolarWinds hackers both use the same old trick to bypass MFA. The Lapsus$ member claimed that the MFA prompt-bombing technique was effective against Microsoft, which earlier this week said the hacking group was able to access the laptop of one of its employees.
“Even Microsoft!” the person wrote. “Able to login to an employee’s Microsoft VPN from Germany and USA at the same time and they didn’t even seem to notice. Also was able to re-enroll MFA twice.”
Mandiant identified multiple attempts by the threat actor to dump the Active Directory database (ntds.dit) using the built-in ntdsutil.exe command. There was also evidence that the threat actor used Sysinternals ProcDump to dump the process memory of the LSASS process. In addition to this, Mandiant discovered that the threat actor had stolen the AD FS token signing certificate and the DKM key material. This would allow the threat actor to perform Golden SAML attacks and authenticate as any user into federated environments that used AD FS for authentication, such as Microsoft 365."





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











