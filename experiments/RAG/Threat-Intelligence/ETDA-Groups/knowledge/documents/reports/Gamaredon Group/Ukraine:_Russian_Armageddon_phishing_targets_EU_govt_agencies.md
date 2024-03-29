# Reference for threat actor for "Gamaredon Group"

**Title**: Ukraine: Russian Armageddon phishing targets EU govt agencies

**Source**: https://www.bleepingcomputer.com/news/security/ukraine-spots-russian-linked-armageddon-phishing-attacks/

## Content






















Ukraine: Russian Armageddon phishing targets EU govt agencies
































































































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




























HomeNewsSecurityUkraine: Russian Armageddon phishing targets EU govt agencies







 














Ukraine: Russian Armageddon phishing targets EU govt agencies


By Bill Toulas


April 5, 2022
09:10 AM
3




The Computer Emergency Response Team of Ukraine (CERT-UA) has spotted new phishing attempts attributed to the Russian threat group tracked as Armageddon (Gamaredon).
The malicious emails attempt to trick the recipients with lures themed after the war in Ukraine and infect the target systems with espionage-focused malware.
CERT-UA has identified two separate cases, one targeting Ukrainian organizations and the other focusing on government agencies in the European Union.
Who is Armageddon
Armageddon is a Russian state-sponsored threat actor who has been targeting Ukraine since at least 2014 and is considered part of the FSB (Russian Federal Security Service).
According to a detailed technical report published by the Ukrainian secret service in November 2021, Armageddon has launched at least 5,000 cyber-attacks against 1,500 critical entities in the country.
The Ukrainian forces have previously identified members of the Armageddon cyber-force, exposed their toolset, and traced custom malware development efforts to Russian hacking forums.
As such, even in chaotic wartime situations where cyber-response teams have limited resources and time, some attributions can be made with greater confidence due to the extensive identification efforts that took place in the past.
Ukraine-focused campaign
Armageddon’s Ukraine-targeting campaign distributes emails on “Information on war criminals of the Russian Federation,” to various government agencies in the country.
The emails, sent from “vadim_melnik88@i[.]ua”, contain an HTML attachment that CERT-UA says has low detections by security software at this time.
If opened, a RAR file is automatically created and dropped on the computer, supposedly containing the identification details of those responsible for war crimes in Ukraine in a shortcut file (.lnk).
However, clicking on this LNK file will download another HTA file laced with VBScript code that runs a PowerShell script to fetch the final payload.

Details of the Ukraine-targeting campaign (CERT-UA)
EU campaign
In the campaign targeting various EU government officials, Armageddon uses RAR archive attachments named “Assistance” and “Necessary_military_assistance”.
Those archives contain shortcut files (.lnk) that supposedly include lists of things needed for military and humanitarian assistance to Ukraine. Opening that file triggers the same malware infection chain described in the previous section.
The sender’s address is “info@military-ukraine[.]site”, which may pass as legitimate, while the signee is supposedly the Deputy Commander for Armaments and Major General in Ukraine.

Details of the EU phishing campaign (CERT-UA)
The CERT-UA has confirmed at least one case of these emails reaching the inbox of the Latvian government. As such, the same campaign is likely targeting more European governments.
This report is in line with other recent findings of Russia-originating attacks targeting EU entities, like last week's Google TAG phishing campaign report, the deployment of wiper-malware against the KA-SAT satellite service, GPS system interference in the Baltic region, and phishing attacks against those aiding with the refugee crisis.

Related Articles:
Russian military hackers target Ukraine with new MASEPIE malwareUkraine: Hack wiped 2 petabytes of data from Russian research centerGoogle: Russian FSB hackers deploy new Spica backdoor malwareMicrosoft disrupts Russian hackers' operation on NATO targetsUK and allies expose Russian FSB hacking group, sanction members








Armageddon
Gamaredon
Phishing
Russia
Ukraine



















Bill Toulas   
Bill Toulas is a tech writer and infosec news reporter with over a decade of experience working on various online publications, covering open-source, Linux, malware, data breach incidents, and hacks.



 Previous Article 
Next Article 


Comments


 




Amigo-A  - 1 year ago 

 
 


Another monthly effusion CERT-UA. How can you trust these bazaar 'traderess'? They do not see a lot of ransomware/extortionists under their noses, in Ukraine, including Crysis / Dharma, STOP / Djvu and a bunch of others that apparently contain them. Such types can only shit in their house and blame others for their vyser.





 




LittleDickPutin  - 1 year ago 

 
 


"Another monthly effusion CERT-UA. How can you trust these bazaar 'traderess'? They do not see a lot of ransomware/extortionists under their noses, in Ukraine, including Crysis / Dharma, STOP / Djvu and a bunch of others that apparently contain them. Such types can only shit in their house and blame others for their vyser."
Just checking in comrade saying hi. Finally have time for that Yandex comparison.. 





 




Amigo-A  - 1 year ago 

 
 


Hi. They still do not know what this Yandex is doing with the Internet and with computers, otherwise they would write about it as a terrible Russian virus, although it is just an offshoot of a company from the Netherlands. 





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











