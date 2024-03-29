# Reference for threat actor for "Wizard Spider, Gold Blackburn"

**Title**: UHS hospitals hit by reported country-wide Ryuk ransomware attack

**Source**: https://www.bleepingcomputer.com/news/security/uhs-hospitals-hit-by-reported-country-wide-ryuk-ransomware-attack/

## Content






















UHS hospitals hit by reported country-wide Ryuk ransomware attack

































































































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




























HomeNewsSecurityUHS hospitals hit by reported country-wide Ryuk ransomware attack







 














UHS hospitals hit by reported country-wide Ryuk ransomware attack


By Sergiu Gatlan


September 28, 2020
10:38 AM
4




Universal Health Services (UHS), a Fortune 500 hospital and healthcare services provider, has reportedly shut down systems at healthcare facilities around the US after a cyber-attack that hit its network during early Sunday morning.
UHS operates over 400 healthcare facilities in the US and the UK, has more than 90,000 employees and provides healthcare services to approximately 3.5 million patients each year.
The Fortune 500 corporation had annual revenues of $11.4 billion in 2019 and it is 330th on Forbes' ranking of US largest public companies.
Attacked during the night
According to reports coming from UHS' employees, UHS hospitals in the US including those from California, Florida, Texas, Arizona, and Washington D.C. are left without access to computer and phone systems.
At the moment the affected hospitals are redirecting ambulances and relocating patients in need of surgery to other nearby hospitals.
"When the attack happened multiple antivirus programs were disabled by the attack and hard drives just lit up with activity," one of the reports reads.
"After 1min or so of this the computers logged out and shutdown. When you try to power back on the computers they automatically just shutdown.
"We have no access to anything computer based including old labs, ekg's, or radiology studies. We have no access to our PACS radiology system."
Employees were also told to shut down all systems to block the attackers' from reaching all devices on the network.
If you have first-hand information about this or other unreported cyberattacks, you can confidentially contact us on Signal at +16469613731 or on Wire at @lawrenceabrams-bc.
Ryuk ransomware behind the attack
While UHS has made no official statement regarding the attack, reports coming from employees show all the signs of a ransomware attack, starting with its launch during the night to avoid detection before encrypting as many systems as possible and the immediate shut down of all systems after it was discovered to prevent more devices getting locked.
An employee told BleepingComputer that, during the cyberattack, files were being renamed to include the .ryk extension. This extension is used by the Ryuk ransomware.
Another UHS employee told us that one of the impacted computers' screens changed to display a ransom note reading "Shadow of the Universe," a similar phrase to that appearing at the bottom of Ryuk ransom notes.
Based on information shared with BleepingComputer by Advanced Intel's Vitali Kremez, the attack on UHS' system likely started via a phishing attack.

Our team has observed the following: Phishing -> #KEGTAP -> #BEACON -> #RYUK.
— Andrew Thompson (@anthomsec) September 28, 2020
According to Kremez, their Andariel intelligence platform detected both the Emotet and TrickBot Trojans affecting UHS Inc. throughout 2020, and more recently, in September 2020.
The Emotet trojan is spread via phishing emails containing malicious attachments that install the malware on a victim's computer.
After some time, Emotet will also install TrickBot, which ultimately opens a reverse shell to the Ryuk operators after harvesting sensitive information from compromised networks.
Once the Ryuk actors manually get access to the network they start with reconnaissance and, after gaining admin credentials, they deploy ransomware payloads on network devices using PSExec or PowerShell Empire.

Ryuk ransom note
Unfortunately, with ransomware attack, there is also a high chance of the attackers stealing patient and employee data which will further increase the damage.
Last week, BleepingComputer reported that a ransomware attack affecting a German hospital led to the death of a patient in a life-threatening condition after she was redirected to a more distant hospital.
Four deaths were also reported after the incident impacting UHS' facilities, caused by the doctors having to wait for lab results to arrive via courier. BleepingComputer has not been able to independently corroborate if the deaths were related to the attack.
If UHS decided to pay the Ryuk ransom, they need to be careful of using their decryptor as it is known to corrupt certain types of files.
Emsisoft is offering free ransomware recovery services to healthcare organizations during the pandemic, which include custom decryptors that are known to recover files 50% faster than the threat actor's decryptors.
"There are multiple factors and it depends a bit on the hardware, but there are three major factors: We heavily optimised I/O (so the reading and writing has been optimised a lot and been adjusted for modern mass storage), we use hardware accelerated cryptography, and we make creating a backup first unnecessary, because unlike the TA's tool, we operate on copies of data."
"The real benefit is in the fact that we focus on data safety first. So our decryptors generally are more stable, are safer to use, and produce correct results," Emsisoft CTO Fabian Wosar told BleepingComputer in a conversation.
BleepingComputer has contacted UHS for more information about the attack but has not heard back.
Update September 29, 18:45 EDT: Added information about Emsisoft decryptors.
Update September 28, 12:23 EDT: UHS confirmed that it was the victim of a security incident and says that no patient or employee data was impacted in the incident:

The IT Network across Universal Health Services (UHS) facilities is currently offline, due to an IT security issue.
We implement extensive IT security protocols and are working diligently with our IT security partners to restore IT operations as quickly as possible. In the meantime, our facilities are using their established back-up processes including offline documentation methods. Patient care continues to be delivered safely and effectively.
No patient or employee data appears to have been accessed, copied or otherwise compromised.


Related Articles:
Lurie Children's Hospital took systems offline after cyberattackJohnson Controls says ransomware attack cost $27 million, data stolenFidelity National Financial: Hackers stole data of 1.3 million peopleUS mortgage lender loanDepot confirms ransomware attackOnline museum collections down after cyberattack on service provider








Cyber Attack
Cyberattack
Health Care
Ransomware
Ryuk
UHS



















Sergiu Gatlan   
Sergiu is a news reporter who has covered the latest cybersecurity and technology developments for over a decade. Email or Twitter DMs for tips.



 Previous Article 
Next Article 


Comments


 




Shplad  - 3 years ago 

 
 


I think the writer meant "she" or "he", not "it". I'm pretty sure no person wants to be referred to as a thing. 
Last week, BleepingComputer reported that a ransomware attack affecting a German hospital led to the death of a patient in a life-threatening condition after it was redirected to a more distant hospital.





 




serghei  - 3 years ago 

 
 


Fixed, thank you!





 




warbenekar1  - 3 years ago 

 
 


To anyone's knowledge is there any connection between this ransomware and the Tyler Technologies incident that happened earlier?





 




KarmaComing  - 3 years ago 

 
 


The terrorists responsible need to be redentioned to gitmo for waterboarding, extract all info from them, then compost the left overs.





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











