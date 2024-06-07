# Reference for threat actor for "Traveling Spider"

**Title**: Fake PayPal Site Spreads Nemty Ransomware

**Source**: https://www.bleepingcomputer.com/news/security/fake-paypal-site-spreads-nemty-ransomware/

## Content






















Fake PayPal Site Spreads Nemty Ransomware
































































































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




























HomeNewsSecurityFake PayPal Site Spreads Nemty Ransomware







 















Fake PayPal Site Spreads Nemty Ransomware


By Ionut Ilascu




September 8, 2019
11:01 AM
0





A web page pretending to offer an official application from PayPal is currently spreading a new variant of Nemty ransomware to unsuspecting users.
It appears that the operators of this file-encrypting malware are trying various distribution channels as it was recently observed as a payload from the RIG exploit kit (EK).
Luring with cashback rewards
The latest occurrence of Nemty was observed on a fake PayPal page that promises to return 3-5% from purchases made through the payment system.

Several clues point to the fraudulent nature of the page, which is also flagged as dangerous by major browsers, but users may still fall for the trick and proceed with downloading and running the malware, which is conveniently named 'cashback.exe'.
Security researcher nao_sec found the new Nemty distribution channel and used AnyRun test environment to deploy the malware and follow its activity on an infected system.

Paypal Fake Site -> #NEMTY Ransomware
(CC: @malware_traffic, @jeromesegura, @VK_Intel, @BleepinComputer)https://t.co/YC7pVMSFwm pic.twitter.com/yzakaFEzi0
— nao_sec (@nao_sec) September 7, 2019
The automated analysis showed that it took about seven minutes for the ransomware to encrypt the files on the victim host. However, this may differ from one system to another.
Fortunately, the malicious executable is detected by most popular antivirus products on the market. A scan on VirusTotal shows that it is detected by 36 out of 68 antivirus engine.
Homoglyph attack
At a first look, the web page seems genuine as cybercriminals used visuals and the structure present on the original page.
To add to the deception, the cybercriminals also use what is known as homograph domain name spoofing for links to various sections of the site (Help & Contact, Fees, Security, Apps, and Shop).
The crooks achieved this by using in the domain name Unicode characters from different alphabets. To distinguish between them, browsers automatically translate them into Punycode. In this case, what in Unicode looks like paypal.com translates to 'xn--ayal-f6dc.com' in Punycode.
Security researcher Vitali Kremez analyzing this variant of Nemty ransomware noted that it is now at version 1.4, which comes with minor bug fixes.
One thing the researcher observed is that the "isRU" check, which verifies if the infected computer is in Russia, Belarus, Kazakhstan, Tajikistan, or Ukraine, has been modified. In the latest version, if the result of the check is positive, the malware does not move with the file-encrypting function, the researcher told BleepingComputer.

credit: Vitali Kremez
Computers outside these countries, though, are a target and will have their files encrypted and their shadow copies deleted.
Nemty ransomware has been present on cybercriminal forums for some time but it emerged on the radar of the infosec community towards the end of August, when security researcher Vitali Kremez published details of his analysis. The expert noticed in the code messages and references that made the malware stand out.
BleepingComputer tests showed that the ransom demand was 0.09981 BTC, which is about $1,000, and that the payment portal is hosted in the Tor network for anonymity.
At the end of August, another security researcher, Mol69, saw Nemty being distributed via RIG EK, which is probably an odd choice considering that exploit kits are on the brink of extinction as they target products that are on their death bed: Internet Explorer, Flash Player.
According to Yelisey Boguslavskiy of Advanced Intelligence, Nemty was received with "with extreme skepticism and aggression" on a cybercriminal forum, which is normal in that community. This may also influence its success, which is nothing compared to what Sodinokibi ransomware currently enjoys.
Update [09/08/2019, 18:00 EST]: Article updated with new information from security researcher Vitali Kremez.

Related Articles:
New Qbot malware variant uses fake Adobe installer popup for evasionLockBit claims ransomware attack on Fulton County, GeorgiaTrans-Northern Pipelines investigating ALPHV ransomware attack claimsRansomware attack forces 100 Romanian hospitals to go offlineBumblebee malware attacks are back after 4-month break











Nemty Ransomware
PayPal
Phishing
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











