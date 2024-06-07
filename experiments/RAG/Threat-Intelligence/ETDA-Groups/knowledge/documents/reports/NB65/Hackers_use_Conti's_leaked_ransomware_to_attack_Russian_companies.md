# Reference for threat actor for "NB65"

**Title**: Hackers use Conti's leaked ransomware to attack Russian companies

**Source**: https://www.bleepingcomputer.com/news/security/hackers-use-contis-leaked-ransomware-to-attack-russian-companies/

## Content






















Hackers use Conti's leaked ransomware to attack Russian companies
































































































News



Featured
Latest







Microsoft: New critical Exchange bug exploited as zero-day





LockBit claims ransomware attack on Fulton County, Georgia





Trans-Northern Pipelines investigating ALPHV ransomware attack claims





Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flaws









Over 13,000 Ivanti gateways vulnerable to actively exploited bugs





Three critical application security flaws scanners can’t detect





Turla hackers backdoor NGOs with new TinyTurla-NG malware





New Qbot malware variant uses fake Adobe installer popup for evasion








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




























HomeNewsSecurityHackers use Conti's leaked ransomware to attack Russian companies







 














Hackers use Conti's leaked ransomware to attack Russian companies


By Lawrence Abrams


April 9, 2022
02:30 PM
0




A hacking group used the Conti's leaked ransomware source code to create their own ransomware to use in cyberattacks against Russian organizations.
While it is common to hear of ransomware attacks targeting companies and encrypting data, we rarely hear about Russian organizations getting attacked similarly.
This lack of attacks is due to the general belief by Russian hackers that if they do not attack Russian interests, then the country's law enforcement would turn a blind eye toward attacks on other countries.
However, the tables have now turned, with a hacking group known as NB65 now targeting Russian organizations with ransomware attacks.
Ransomware targets Russia
For the past month, a hacking group known as NB65 has been breaching Russian entities, stealing their data, and leaking it online, warning that the attacks are due to Russia's invasion of Ukraine.
The Russian entities claimed to have been attacked by the hacking group include document management operator Tensor, Russian space agency Roscosmos, and VGTRK, the state-owned  Russian Television and Radio broadcaster.

The attack on VGTRK was particularly significant as it led to the alleged theft of 786.2 GB of data, including 900,000 emails and 4,000 files, which were published on the DDoS Secrets website.
More recently, the NB65 hackers have turned to a new tactic — targeting Russian organizations with ransomware attacks since the end of March.
What makes this more interesting, is that the hacking group created their ransomware using the leaked source code for the Conti Ransomware operation, which are Russian threat actors who prohibit their members from attacking entities in Russia.

Conti's source code was leaked after they sided with Russia over the attack on Ukraine, and a security researcher leaked 170,000 internal chat messages and source code for their operation.
BleepingComputer first learned of NB65's attacks by threat analyst Tom Malka, but we could not find a ransomware sample, and the hacking group was not willing to share it.
However, this changed yesterday when a sample of the NB65's modified Conti ransomware executable was uploaded to VirusTotal, allowing us to get a glimpse of how it works.
Almost all antivirus vendors detect this sample on VirusTotal as Conti, and Intezer Analyze also determined it uses 66% of the same code as the usual Conti ransomware samples.
BleepingComputer gave NB65's ransomware a run, and when encrypting files, it will append the .NB65 extension to the encrypted file's names.

Files encrypted by NB65's ransomwareSource: BleepingComputer
The ransomware will also create ransom notes named R3ADM3.txt throughout the encrypted device, with the threat actors blaming the cyberattack on President Vladimir Putin for invading Ukraine.
"We're watching very closely.  Your President should not have commited war crimes. If you're searching for someone to blame for your current situation look no further than Vladimir Putin," reads the NB65 ransomware note displayed below.

Ransom note for NB65 ransomwareSource: BleepingComputer
A representative for the NB65 hacking group told BleepingComputer that they based their encryptor on the first Conti source code leak but modified it for each victim so that existing decryptors would not work.
"It's been modified in a way that all versions of Conti's decryptor won't work. Each deployment generates a randomized key based off of a couple variables that we change for each target," NB65 told BleepingComputer.
"There's really no way to decrypt without making contact with us."
At this time, NB65 has not received any communications from their victims and told us that they were not expecting any.
As for NB65's reasons for attacking Russian organizations, we will let them speak for themselves.

"After Bucha we elected to target certain companies, that may be civilian owned, but still would have an impact on Russias ability to operate normally.  The Russian popular support for Putin's war crimes is overwhelming.  From the very beginning we made it clear.  We're supporting Ukraine.  We will honor our word.  When Russia ceases all hostilities in Ukraine and ends this ridiculous war NB65 will stop attacking Russian internet facing assets and companies.
Until then, fuck em. 
We will not be hitting any targets outside of Russia.  Groups like Conti and Sandworm, along with other Russian APTs have been hitting the west for years with ransomware, supply chain hits (Solarwinds or defense contractors)... We figured it was time for them to deal with that themselves."

NB65 further stated on Monday that they will never target organizations outside of Russia, and any ransom payments will be donated to Ukraine.
Update 4/11/22: Added updated about how ransoms would be used

Related Articles:
AnyDesk says hackers breached its production servers, reset passwordsJohnson Controls says ransomware attack cost $27 million, data stolenUkraine: Hack wiped 2 petabytes of data from Russian research centerResearchers link 3AM ransomware to Conti, Royal cybercrime gangsFidelity National Financial: Hackers stole data of 1.3 million people








Conti
Cyberattack
NB65
Ransomware
Russia
Source Code
Ukraine



















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











