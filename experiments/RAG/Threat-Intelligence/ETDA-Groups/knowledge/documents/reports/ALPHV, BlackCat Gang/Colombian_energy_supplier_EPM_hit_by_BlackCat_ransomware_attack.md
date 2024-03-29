# Reference for threat actor for "ALPHV, BlackCat Gang"

**Title**: Colombian energy supplier EPM hit by BlackCat ransomware attack

**Source**: https://www.bleepingcomputer.com/news/security/colombian-energy-supplier-epm-hit-by-blackcat-ransomware-attack/

## Content






















Colombian energy supplier EPM hit by BlackCat ransomware attack
































































































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




























HomeNewsSecurityColombian energy supplier EPM hit by BlackCat ransomware attack







 















Colombian energy supplier EPM hit by BlackCat ransomware attack


By Lawrence Abrams




December 16, 2022
01:47 PM
0





Colombian energy company Empresas Públicas de Medellín (EPM) suffered a BlackCat/ALPHV ransomware attack on Monday, disrupting the company's operations and taking down online services.
EPM is one of Colombia’s largest public energy, water, and gas providers, providing services to 123 municipalities. The company generated over $25 billion in revenue in 2022 and is owned by the Colombian Municipality of Medellin.
On Tuesday, the company told approximately 4,000 employees to work from home, with IT infrastructure down and the company's websites no longer available.
EPM disclosed to local media that they were responding to a cybersecurity incident and provided alternative methods for customers to pay for services.
The Prosecutor's Office later confirmed to EL COLOMBIANO that ransomware was behind the attack on EPM that caused devices to be encrypted and data to be stolen.
However, the ransomware operation behind the attack was not disclosed.
BlackCat ransomware behind the attack
BleepingComputer has since learned that the BlackCat ransomware operation, aka ALPHV, was behind the attacks, claiming to have stolen corporate data during the attacks.
BleepingComputer has also seen the encryptor sample and ransom notes from the EPM attack and has confirmed that they are from the BlackCat ransomware operation.

EPM ransom note from BlackCat ransomwareSource: BleepingComputer
While the ransom note created in the attack states that the threat actors stole a wide variety of data, it should be noted that this is the exact text used in all BlackCat ransom notes and is not specific to EPM.
However, further discoveries indicate that hackers likely stole quite a bit of data from EPM during the attack.
Chilean security researcher Germán Fernández discovered a recent sample of BlackCat's 'ExMatter' data-theft tool, uploaded from Colombia to a malware analysis site.
ExMatter is a tool used in BlackCat ransomware attacks to steal data from corporate networks before devices are encrypted. This data is then used as part of the ransomware gang's double-extortion attempts.
When the tool is run, it will steal data from devices on the network and store it on attacker-controlled servers within folders named after the Windows computer name that it was stolen from.
When analyzing the ExMatter tool, Fernández found that it uploaded the data to a remote server that was not adequately secured, allowing any visitor to see the data stored on it.
In the ExMatter variant from Colombia, the data was uploaded into various folders starting with 'EPM-,' as shown below. Fernández told BleepingComputer that these computer names match known computer naming formats used by Empresas Públicas de Medellín.

BlackCat data exfiltration serverSource: Germán Fernández
While it is unclear how much total data was stolen, Fernández told BleepingComputer that there were a little over 40 devices listed on the site.
BleepingComputer has reached out to EPM to learn more about the attack and how much data was stolen, but a response was not immediately available.
This is not the first time a ransomware attack has targeted a Colombian energy company.
In 2020, the Enel Group suffered a ransomware attack twice in the same year.
Colombia has also seen an increase in attacks over the last months, with the country's healthcare system disrupted last month by a RansomHouse attack on Keralty, a multinational healthcare organization.

Related Articles:
Trans-Northern Pipelines investigating ALPHV ransomware attack claimsNew RustDoor macOS malware impersonates Visual Studio updateMGM Resorts ransomware attack led to $100 million loss, data theftFidelity National Financial: Hackers stole data of 1.3 million peopleMGM casino's ESXi servers allegedly encrypted in ransomware attack











ALPHV
BlackCat
Colombia
Empresas Públicas de Medellín
EPM
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











