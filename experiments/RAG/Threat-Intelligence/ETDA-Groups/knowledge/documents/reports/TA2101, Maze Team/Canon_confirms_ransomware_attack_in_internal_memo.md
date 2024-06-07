# Reference for threat actor for "TA2101, Maze Team"

**Title**: Canon confirms ransomware attack in internal memo

**Source**: https://www.bleepingcomputer.com/news/security/canon-hit-by-maze-ransomware-attack-10tb-data-allegedly-stolen/

## Content






















Canon confirms ransomware attack in internal memo
































































































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




























HomeNewsSecurityCanon confirms ransomware attack in internal memo







 














Canon confirms ransomware attack in internal memo


By Lawrence Abrams


August 6, 2020
03:12 PM
1




08/06 update added below. This post was originally published on August, 5th, 2020.
​Canon has suffered a ransomware attack that impacts numerous services, including Canon's email, Microsoft Teams, USA website, and other internal applications. In an internal alert sent to employees, Canon has disclosed the ransomware attack and working to address the issue.
BleepingComputer has been tracking a suspicious outage on Canon's image.canon cloud photo and video storage service resulting in the loss of data for users of their free 10GB storage feature.
The image.canon site suffered an outage on July 30th, 2020, and over six days, the site would show status updates until it went back in service yesterday, August 4th.
However, the final status update was strange as it mentions that while data was lost, "there was no leak of image data."  This led BleepingComputer to believe there was more to the story and that they suffered a cyberattack.

Image.canon outage notice
Source: BleepingComputer
When we contacted Canon about this outage, they referred us to the notice on the image.canon site.
If you work at Canon or know someone working there with first-hand information on this incident, you can confidentially contact us on Signal at +16469613731.
Canon suffers ransomware attack
Today, a source contacted BleepingComputer and shared an image of a company-wide notification titled "Message from IT Service Center" that was sent at approximately 6 AM this morning from Canon's IT department.
This notification states that Canon is experiencing "wide spread system issues affecting multiple applications, Teams, Email, and other systems may not be available at this time."

Notice from Canon's IT department
Source: BleepingComputer
As part of this outage, Canon USA's website is now displaying errors or page not found errors when visited.

Canon USA website is down
Source: BleepingComputer
The list of Canon domains that appear to be affected by this outage, include:

www.canonusa.com
www.canonbroadcast.com
b2cweb.usa.canon.com
canondv.com
canobeam.com
canoneos.com
bjc8200.com
canonhdec.com
bjc8500.com
usa.canon.com
imagerunner.com
multispot.com
canoncamerashop.com
canoncctv.com
canonhelp.com
bjc-8500.com
canonbroadcast.com
imageland.net
consumer.usa.canon.com
bjc-8200.com
bjc3000.com
downloadlibrary.usa.canon.com
www.cusa.canon.com
www.canondv.com
Since then, BleepingComputer has obtained a partial screenshot of the alleged Canon ransom note, which we have been able to identify as from the Maze ransomware.

Partial Maze ransomware note
Source: BleepingComputer
Maze claims to have stolen 10TB of data from Canon
After contacting the ransomware operators, BleepingComputer was told by Maze that their attack was conducted this morning when they stole "10 terabytes of data, private databases etc" as part of the attack on Canon.
Maze declined to share any further info about the attack including the ransom amount, proof of stolen data, and the amount of devices encrypted. 
While we first thought that the image.canon outage was related to the ransomware attack, Maze has told us that it was not caused by them.
Maze is an enterprise-targeting human-operated ransomware that compromises and stealthily spreads laterally through a network until it gains access to an administrator account and the system's Windows domain controller.
During this process, Maze will steal unencrypted files from servers and backups and upload them to the threat actor's servers.
Once they have harvested the network of anything of value and gain access to a Windows domain controller, Maze will deploy the ransomware throughout the network to encrypt all of the devices.
If a victim does not pay the ransom, Maze will publicly distribute the victim's stolen files on a data leak site that they have created.
Maze has claimed responsibility for other high-profile victims in the past, including LG, Xerox, Conduent, MaxLinear, Cognizant, Chubb, VT San Antonio Aerospace, the City of Pensacola, Florida, and more.
In a statement to BleepingComputer, Canon says they are "currently investigating the situation."
Canon discloses ransomware attack to employees
Update 08/06/20: BleepingComputer has obtained a screenshot of an internal message sent by Canon to employees that discloses the ransomware attack.
This message further states that they have hired an outside cybersecurity company to aid in their recovery.
"Canon U.S.A, Inc. and its subsidiaries understand the importance of maintaining the operational integrity and security of our systems. Access to some Canon systems is currently unavailable as a result of a ransomware incident we recently discovered. This is unrelated to the recent issue which affected image.canon."

Internal notice sent to employees
In response to our query, Canon continues to state "We are currently investigating the situation. Thank you."
This is a developing story and will be updated as more information is available.
Update 8/5/20: Article updated to reflect that the image.canon outage was not related to the Maze ransomware attack.Update 8/6/20: Canon has internally notified their employees of the ransomware attack.

Related Articles:
New RustDoor macOS malware impersonates Visual Studio updateKansas City public transportation authority hit by ransomwareMajorca city Calvià extorted for $11M in ransomware attackOnline museum collections down after cyberattack on service providerThe Week in Ransomware - December 22nd 2023 - BlackCat hacked








Canon
Data Exfiltration
Maze
Outage
Ransomware



















Lawrence Abrams   
Lawrence Abrams is the owner and Editor in Chief of BleepingComputer.com. Lawrence's area of expertise includes Windows, malware removal, and computer forensics. Lawrence Abrams is a co-author of the Winternals Defragmentation, Recovery, and Administration Field Guide and the technical editor for Rootkits for Dummies.



 Previous Article 
Next Article 


Comments


 




longdog10  - 3 years ago 

 
 


We called Canon trying to get support for one of our devices this morning, and the reason their customer service rep gave us as to why they could not put in a service ticket for dispatch was "a tornado ripped through a Canon datacenter causing a power outage". Maybe they named the ransomware event "Tornado"...





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











