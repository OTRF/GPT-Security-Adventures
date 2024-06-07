# Reference for threat actor for "Carbanak, Anunak"

**Title**: CompuCom MSP hit by DarkSide ransomware cyberattack

**Source**: https://www.bleepingcomputer.com/news/security/compucom-msp-hit-by-darkside-ransomware-cyberattack/

## Content






















CompuCom MSP hit by DarkSide ransomware cyberattack
































































































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




























HomeNewsSecurityCompuCom MSP hit by DarkSide ransomware cyberattack







 















CompuCom MSP hit by DarkSide ransomware cyberattack


By Lawrence Abrams




March 4, 2021
03:58 PM
0





Update 3/4/21: This article was originally published on 3/3/21 and has been updated with new info.
US managed service provider CompuCom has suffered a DarkSide ransomware attack leading to service outages and customers disconnecting from the MSP's network to prevent the spread of malware.
CompuCom is an IT managed services provider (MSP) that provides remote support, hardware and software repair, and other technology services to companies. CompuCom is a wholly-owned subsidiary of The ODP Corporation (Office Depot/Office Max) and employs approximately 8,000 people.
Some of the past and existing customers of CompuCom include well-known names, such as Home Depot, Target, Citibank, Wells Fargo, Truist Bank, and Lowe's.
If you have first-hand information about this or other unreported cyberattacks, you can confidentially contact us on Signal at +16469613731 or on Wire at @lawrenceabrams-bc.
The attack occurred over the weekend
Over the weekend, CompuCom suffered an outage that prevented customers from accessing the company's customer portal to open troubleshooting tickets.
When visiting the portal, the website greeted customers with a general error message stating, "An error occurred while processing your request."

Error message on CompuCom client portal
BleepingComputer was told that CompuCom began contacting customers to alert them that they had been compromised by malware soon after the attack. However, customers were not told what type of attack occurred and whether it was ransomware.
In later conversations with affected customers, BleepingComputer learned that CompuCom had disconnected their access to some customers to prevent the malware's spread. Another customer told us that they had detached from CompuCom's VDIs (Virtual Desktop Infrastructure) to ensure their data was not affected by the attack.
Multiple people also told BleepingComputer that this was a ransomware attack, but we could not confirm independently if this is true.
After reaching out to CompuCom about the attack, the company issued a statement to BleepingComputer stating that they suffered a 'malware incident' and that there is no evidence of it spreading to customers' systems.
You can read the full CompuCom statement below:

"Certain CompuCom information technology systems have been affected by a malware incident which is affecting some of the services that we provide to certain customers. Our investigation is in its early stages and remains ongoing. We have no indication at this time that our customers' systems were directly impacted by the incident. 
As soon as we became aware of the situation, we immediately took steps to contain it, and engaged leading cybersecurity experts to begin an investigation. We are also communicating with customers to provide updates about the situation and the actions we are taking. 
We are in the process of restoring customer services and internal operations as quickly and safely as possible. We regret the inconvenience caused by the interruption and appreciate the ongoing support of our customers." - CompuCom

CompuCom confirms ransomware attack in FAQ
Today, a CompuCom customer shared a 'Customer FAQ Regarding Malware Incident' that provides more details about the attack than the company shared in their press release.
According to the FAQ, CompuCom was breached by threat actors who installed Cobalt Strike beacons on several systems in their environment. 
These beacons allow remote threat actors access to the network to steal data, spread to other machines, and ultimately deploy the ransomware, which the threat actors deployed on February 28th.
"Based on our expert's analysis to date, we understand that the attacker deployed a persistent Cobalt Strike backdoor to several systems in the environment and acquired administrative credentials. These administrative credentials were then used to deploy the Darkside Ransomware," the CompuCom FAQ reads.
Cobalt Strike is increasingly being deployed through a variety of Trojans installed via phishing campaigns. These Trojans include BazarLoader, TrickBot, ZLoader, and QBot.
Now that DarkSide Ransomware has been confirmed to be behind the attack, it is likely that the threat actors harvested unencrypted files before encrypting the devices.
If data was stolen and a ransom is not paid, we will likely see this data published on their ransomware data leak site in the next few weeks.
In the past, other companies hit by DarkSide include Discount Car and Truck Rentals, Brookfield Residential, and the Brazilian Eletrobras and Copel energy companies.

Related Articles:
Lurie Children's Hospital took systems offline after cyberattackOnline museum collections down after cyberattack on service providerGerman battery maker Varta halts production after cyberattackPrudential Financial breached in data theft cyberattackAnyDesk says hackers breached its production servers, reset passwords











CompuCom
Cyberattack
DarkSide
MSP
Outage
























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











