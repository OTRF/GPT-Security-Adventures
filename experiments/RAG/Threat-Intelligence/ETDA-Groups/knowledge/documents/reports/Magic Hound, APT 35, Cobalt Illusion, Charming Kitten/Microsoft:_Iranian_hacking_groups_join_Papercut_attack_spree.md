# Reference for threat actor for "Magic Hound, APT 35, Cobalt Illusion, Charming Kitten"

**Title**: Microsoft: Iranian hacking groups join Papercut attack spree

**Source**: https://www.bleepingcomputer.com/news/security/microsoft-iranian-hacking-groups-join-papercut-attack-spree/

## Content






















Microsoft: Iranian hacking groups join Papercut attack spree

































































































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




























HomeNewsSecurityMicrosoft: Iranian hacking groups join Papercut attack spree







 















Microsoft: Iranian hacking groups join Papercut attack spree


By Sergiu Gatlan




May 8, 2023
10:47 AM
2





Microsoft says Iranian state-backed hackers have joined the ongoing assault targeting vulnerable PaperCut MF/NG print management servers.
These groups are tracked as Mango Sandstorm (aka Mercury or Muddywater and linked to Iran's Ministry of Intelligence and Security) and Mint Sandstorm (also known as Phosphorus or APT35 and tied to Iran's Islamic Revolutionary Guard Corps).
"The PaperCut exploitation activity by Mint Sandstorm appears opportunistic, affecting organizations across sectors and geographies," the Microsoft Threat Intelligence team said.
"Observed CVE-2023-27350 exploitation activity by Mango Sandstorm remains low, with operators using tools from prior intrusions to connect to their C2 infrastructure."
They follow attacks linked to Lace Tempest by Microsoft, a hacking group whose malicious activity overlaps with the FIN11 and TA505 cybercrime gangs connected to the Clop ransomware operation.
Redmond also found that some intrusions led to LockBit ransomware attacks but couldn't provide more information when asked to share additional details.
CISA added this bug to its catalog of actively exploited vulnerabilities on April 21, ordering federal agencies to secure their PaperCut servers within three weeks by May 12, 2023.

More actors are exploiting unpatched CVE-2023-27350 in print management software Papercut since we last reported on Lace Tempest. Microsoft has now observed Iranian state-sponsored threat actors Mint Sandstorm (PHOSPHORUS) & Mango Sandstorm (MERCURY) exploiting CVE-2023-27350.
— Microsoft Threat Intelligence (@MsftSecIntel) May 5, 2023
The PaperCut vulnerability exploited in these attacks and tracked as CVE-2023-27350 is a pre-authentication critical remote code execution bug in PaperCut MF or NG versions 8.0 or later.
Large companies, state organizations, and education institutes worldwide are using this enterprise printing management software, with PaperCut's developer claiming more than 100 million users from over 70,000 companies. 
Security researchers released PoC exploits for the RCE bug soon after the initial disclosure in March 2023, with Microsoft warning several days later that the vulnerability was being used for initial access to corporate networks by the Clop and LockBit ransomware gangs.
While multiple cybersecurity companies have released indicators of compromise and detection rules for PaperCut exploits, VulnCheck shared details on a new attack method last week that can bypass existing detections, allowing attackers to keep exploiting CVE-2023-27350 unobstructed.
"Detections that focus on one particular code execution method, or that focus on a small subset of techniques used by one threat actor are doomed to be useless in the next round of attacks," VulnCheck vulnerability researcher Jacob Baines said.
"Attackers learn from defenders' public detections, so it's the defenders' responsibility to produce robust detections that aren't easily bypassed."
Defenders are encouraged to immediately upgrade theirPaperCut MF and PaperCut NG software to versions 20.1.7, 21.2.11, and 22.0.9 and later, which address this RCE bug and remove the attack vector.

Related Articles:
Microsoft February 2024 Patch Tuesday fixes 2 zero-days, 73 flawsWindows 10 KB5034763 update released with new fixes, changesWindows 11 KB5034765 update released with Start Menu fixesVisualize data with $220 off Microsoft Visio 2021 ProfessionalCriminal IP ASM: A new cybersecurity listing on Microsoft Azure











Iran
Microsoft
PaperCut
























Sergiu Gatlan   
Sergiu is a news reporter who has covered the latest cybersecurity and technology developments for over a decade. Email or Twitter DMs for tips.




 Previous Article 
Next Article 



Comments



  






NoneRain  - 9 months ago 


 
 



Zero reasons to have not updated it.





  






LIstrong  - 9 months ago 


 
 



They are an Australian co. Perhaps they are a plug-in used in other products? They integrate with lots of apps, most not known to me except ConnectWise (breached 2022), Quickbooks (breached 2023) and Zero. LOTS OF LEGAL software integration. The only payment processor I recognized is PP. The software doesn’t make sense in enterprise except if it was installed by MSP or contractors to circumvent their inability to print. Most corporates block vendors and contractors from printing. Corporates should NOT assume this isn’t in their environment. Like SolarWinds this could be everywhere but no one knows it is. Does it scrape and retain user data? They are resold through channel partners. Also this person is using it for other purposes https://github.com/capgemini-stavanger/gi-en-jul

Zoom info reports them as having 31 employees in the US and only $3M rev. LI reports them as having between 11-50 employees in the US. https://www.linkedin.com/company/paperclip-inc-

How many attacks in AUS? I guess universities don’t perform vendor risk assessments. How could a company this small design or support US cybersecurity regulations? University data is regulated in the U.S. and EU. So this is bizarre that’s it’s used by some very top schools/research institutions that even claim to be cybersecurity experts. You get what you pay for.






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











