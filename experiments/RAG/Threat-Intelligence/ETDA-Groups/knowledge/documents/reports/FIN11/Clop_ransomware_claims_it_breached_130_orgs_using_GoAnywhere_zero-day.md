# Reference for threat actor for "FIN11"

**Title**: Clop ransomware claims it breached 130 orgs using GoAnywhere zero-day

**Source**: https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-it-breached-130-orgs-using-goanywhere-zero-day/

## Content






















Clop ransomware claims it breached 130 orgs using GoAnywhere zero-day
































































































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




























HomeNewsSecurityClop ransomware claims it breached 130 orgs using GoAnywhere zero-day







 















Clop ransomware claims it breached 130 orgs using GoAnywhere zero-day


By Sergiu Gatlan




February 10, 2023
03:15 PM
0





The Clop ransomware gang claims to be behind recent attacks that exploited a zero-day vulnerability in the GoAnywhere MFT secure file transfer tool, saying they stole data from over 130 organizations.
The security flaw, now tracked as CVE-2023-0669, enables attackers to gain remote code execution on unpatched GoAnywhere MFT instances with their administrative console exposed to Internet access.
Clop reached out to BleepingComputer and told us that they had allegedly stolen the data over the course of ten days after breaching servers vulnerable to exploits targeting this bug.
They also claimed that they could move laterally through their victims’ networks and deploy ransomware payloads to encrypt their systems but decided against it and only stole the documents stored on the compromised GoAnywhere MFT servers.
The gang refused to provide proof or share additional details regarding their claims when BleepingComputer asked them when the attacks began, if they'd already started extorting their victims, and what ransoms they were asking for.
BleepingComputer could not independently confirm Clop's claims, and Fortra has not replied to emails asking for more info regarding CVE-2023-0669 exploitation and the ransomware group's allegations.
However, Huntress Threat Intelligence Manager Joe Slowik linked the GoAnywhere MFT attacks to TA505, a threat group known for deploying Clop ransomware in the past, while investigating an attack where the TrueBot malware downloader was deployed.
"While links are not authoritative, analysis of Truebot activity and deployment mechanisms indicate links to a group referred to as TA505. Distributors of a ransomware family referred to as Clop, reporting from various entities links Silence/Truebot activity to TA505 operations," Slowik said.
"Based on observed actions and previous reporting, we can conclude with moderate confidence that the activity Huntress observed was intended to deploy ransomware, with potentially additional opportunistic exploitation of GoAnywhere MFT taking place for the same purpose."
Actively exploited flaw in secure file transfer tool
GoAnywhere MFT's developer Fortra (formerly known as HelpSystems) disclosed to its customers last week that the vulnerability was being exploited as a zero-day in the wild.
On Monday, a proof-of-concept exploit was also released online, allowing unauthenticated remote code execution on vulnerable servers.
The company issued emergency security updates the next day to allow customers to secure their servers from incoming attack attempts.
Since then, Fortra has published another update on its support website (accessible only after logging in with a user account) on Thursday, saying that some of its MFTaaS instances were also breached in the attacks.
"We have determined that an unauthorized party accessed the systems via a previously unknown exploit and created unauthorized user accounts," Fortra said.
"As part of our actions to address this and out of an abundance of caution, we have implemented a temporary service outage. Service continues to be restored on a customer-by-customer basis as mitigation is applied and verified within each environment.
"We are working directly with customers to assess their individual potential impact, apply mitigations, and restore systems."
CISA also added the CVE-2023-0669 GoAnywhere MFT vulnerability to its  Known Exploited Vulnerabilities Catalog on Friday, ordering federal agencies to patch their systems within the next three weeks, until March 3rd.
While Shodan shows that over 1,000 GoAnywhere instances are exposed online, only 135 are on ports 8000 and 8001 (the ones used by the vulnerable admin console).

Internet-exposed GoAnywhere MFT appliances (Shodan)
Clop's Accellion extortion attacks
Clop's alleged use of the GoAnywhere MFT zero-day to steal data is a very similar tactic to the one they used in December 2020, when they discovered and exploited an Accellion FTA zero-day vulnerability to steal the data of approximately 100 companies.
At the time, companies were receiving emails demanding $10 million ransom payments to avoid having their data publicly leaked.
In the 2020 Accellion attacks, Clop's operators stole large amounts of data from high-profile companies using Accellion's legacy File Transfer Appliance (FTA).
Organizations that had their servers hacked by Clop include, among others, energy giant Shell, supermarket giant Kroger, cybersecurity firm Qualys, and multiple universities worldwide (e.g., Stanford Medicine, University of Colorado, University of Miami, University of Maryland Baltimore (UMB), and the University of California).
In June 2021, some of Clop's infrastructure was shut down following an international law enforcement operation codenamed Operation Cyclone when six money launderers who provided services to the Clop ransomware gang were arrested in Ukraine.
The gang has also been linked to ransomware attacks worldwide since at least 2019. Some victims that had their servers encrypted by Clop include Maastricht University, Software AG IT, ExecuPharm, and Indiabulls.
Update February 10, 15:25 EST: Added a section showing that Huntress made a between GoAnywhere MFT attacks and threat actors known for deploying Clop ransomware.

Related Articles:
Ransomware payments reached record $1.1 billion in 2023Ransomware payments drop to record low as victims refuse to payFortra warns of new critical GoAnywhere MFT auth bypass, patch nowRansomware victims targeted by fake hack-back offersMGM casino's ESXi servers allegedly encrypted in ransomware attack











Clop
Extortion
GoAnywhere MFT
Ransomware
Vulnerability
























Sergiu Gatlan   
Sergiu is a news reporter who has covered the latest cybersecurity and technology developments for over a decade. Email or Twitter DMs for tips.




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











