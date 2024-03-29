# Reference for threat actor for "Achilles"

**Title**: Another Hacker Selling Access to Charity, Antivirus Firm Networks

**Source**: https://www.bleepingcomputer.com/news/security/another-hacker-selling-access-to-charity-antivirus-firm-networks/

## Content






















Another Hacker Selling Access to Charity, Antivirus Firm Networks































































































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




























HomeNewsSecurityAnother Hacker Selling Access to Charity, Antivirus Firm Networks







 














Another Hacker Selling Access to Charity, Antivirus Firm Networks


By Ionut Ilascu


June 6, 2019
10:14 AM
0




A threat actor observed on underground hacker forums peddling internal network access to various entities claims to have breached the infrastructure of notable organizations such as UNICEF and cybersecurity companies Symantec and Comodo.
The hacker uses the online name Achilles and offers to sell details for a way in for modest prices, between $2,000 and $5,000, depending on the value of the target. Their activity jumped over the past seven months particularly in Fall 2019 and Spring 2019.
This appears to be a different threat actor than Fxmsp, who advertised access to antivirus companies with offices in the U.S., namely Symantec, McAfee, and Trend Micro. While Fxmsp is believed to be a group of Russian-speaking hackers, the new seller speaks English and may be Iranian.
Hacker built a good reputation
A report from fraud prevention company Advanced Intelligence (AdvIntel) notes that Achilles enjoys a good reputation and positive reviews on the forums they advertise on and has a record of sales. To increase credibility, the hacker insists that payment for some deals be completed through the forum's escrow service.
In conversations with potential buyers, Achilles said they could get into internal networks belonging to Symantec, cybersecurity company Comodo,  3-D software maker Hash Inc, and children's rights protection advocate UNICEF.
The hacker states in private messages that Symantec's internal infrastructure is possible through a remote desktop connection. The same type of illegal entry was advertised for Hash Inc.

Answering our request for comments, a Symantec spokesperson provided the following statement to BleepingComputer.
“At this time, Symantec has no evidence of a network intrusion, nor do we believe there is a reason for our customers to be concerned.”
Unsupported claims
The claims of having access to Comodo's network is shown in in private messages between Achilles and potential buyers. There is no evidence that such access exists and Comodo and has not responded to BleepingComputer's queries regarding the alleged access.

According to AdvIntel, the hacker also tried to sell entry into the corporate network of Transat, a Canadian holiday travel company. They claim to have breached their network on May 12 or May 13.
Although the affirmations are bold, all this could be just talk, despite the good reputation the actor has on underground forums. The report from AdvIntel report comments that the hacker provided no evidence to support their claims about breaching the networks of Symantec, Comodo, and Transat.
Terabytes of UNICEF data
For UNICEF, though, the hacker stated that they had direct network access and offered to sell it for $4,000.
For this money, the buyer would also be able to snoop through and download a large volume of data - about 3.6 terabytes.

The statement is backed by screenshots from the hacker and obtained by AdvIntel, which show that Achilles could access documents allegedly belonging to UNICEF.
Folders included information relating to the activity of various UNICEF committees, meetings, policies, and country-specific policy guidance.
In one of the pictures, it appears that the hacker could get to two network locations, one of them being a 4TB drive that had only 388GB of free space.

BleepingComputer has also seen images showing more detailed information on the type of data the attacker allegedly has access to and that belongs to Unicef. Due to the nature of these images, we have decided not to publish them.
BleepingComputer has contacted Comodo, UNICEF, Hash Inc, and Transat for statements and did not receive a reply from any of the three organizations at publishing time.
Achilles' work
By offering compromised network access on multiple hacking forums, Achilles was able to build the reputation of a trustworthy seller. On l33t, they advertised DNS server access for several domains managed by the UK government.
The hacker suggested that this could be used for phishing and that they could change the DNS records for any of the listed domains. A buyer could get the entire package for $300.

In April, the actor posted on the same forum that they had 600GB of data from various companies in the UK along with RDP access to them.
Furthermore, AdvIntel says that Achilles also pushed details and credentials of employees from GoDaddy, DHL, Citrix, BBC, and Facebook.
Most of the victims are from the private sector but the hacker's list of targets is diverse, including entities from the defense, energy, tourism, finance, real estate, and information technology verticals.
For a typical intrusion, "they either compromise a Remote Desktop Protocol (RDP) or leverage stolen credentials to establish stable and secure external Virtual Private Network (VPN) access into the victim's network," says Yelisey Boguslavskiy, director of security research at AdvIntel.
Information obtained by the researcher indicates that Achilles tries to avoid malware and adopts a living-off-the-land strategy that counts on utilities and services already available on the target systems. This usually makes detection more difficult because the traffic comes from legitimate sources.
Boguslavskiy says that a common tactic of this threat actor is to use a brute-force attack to get passwords to a company's external portal and remote services.
Once in, Achilles tries to elevate privileges and sets sight on Active Directory (AD) servers, which are responsible for authenticating and authorizing computers in a Windows domain type network.


Who is Achilles?
Some of the clues uncovered by AdvIntel indicate that Achilles has ties with at least some Iranian hackers that made headlines. One of them is Mr. Xhat, who is blamed for compromising the control panel for Tajikistan's domain registrar website (domain.tj) and changing the DNS records.
The incident happened in 2014 and resulted in redirecting visitors of localized versions of Yahoo!, Twitter, Google, and Amazon sites to a defaced webpage under the control of the attacker.
Another theory, fueled only by conjecture, is that the attacker is linked to the Iranian hacker group Iridium. One that could point to this conclusion are the use of password spraying tactics used by both Achilles and Iridium. Another is Achilles talking about Citrix VPN systems at a time when Iridium had allegedly breached Citrix; the hacker's activity on forums and messengers also increased.
The Iranian connection is also supported by an incident affecting a shipbuilder in Australia. According to press in Australia, an Iranian-based hacker was responsible. Achilles offered access data for a defense shipbuilder on l33t and KickAss forums, and "additional evidence provided by Achilles suggests that the information was stolen from an Australian shipbuilder Austal," the researcher adds in the report.
Even if these incidents are not related to Achilles, Boguslavskiy noticed that the hacker's activity follows the timezone in Iran. Also, when asked if they'd rather talk in Farsi, Achilles reply was that more trust was required to switch the language.

Related Articles:
Citibank sued over failure to defend customers against hacks, fraudUkraine: Hack wiped 2 petabytes of data from Russian research center Cybercriminals train AI chatbots for phishing, malware attacksUS court docs expose fake antivirus renewal phishing tacticsMandiant's X account hacked by crypto Drainer-as-a-Service gang








Antivirus
Comodo
Hack
Hackers
RDP
Remote Desktop
Remote Desktop Protocol
Symantec



















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











