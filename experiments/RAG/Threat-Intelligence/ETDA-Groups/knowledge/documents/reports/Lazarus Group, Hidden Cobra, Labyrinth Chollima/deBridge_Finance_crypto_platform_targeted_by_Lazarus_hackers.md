# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: deBridge Finance crypto platform targeted by Lazarus hackers

**Source**: https://www.bleepingcomputer.com/news/security/debridge-finance-crypto-platform-targeted-by-lazarus-hackers/

## Content






















deBridge Finance crypto platform targeted by Lazarus hackers
































































































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




























HomeNewsSecuritydeBridge Finance crypto platform targeted by Lazarus hackers







 














deBridge Finance crypto platform targeted by Lazarus hackers


By Ionut Ilascu


August 8, 2022
07:04 PM
0




Hackers suspected to be from the North Korean Lazarus group tried their luck at stealing cryptocurrency from deBridge Finance, a cross-chain protocol that enables the decentralized transfer of assets between various blockchains.
The threat actor used a phishing email to trick company employees into launching malware that collected various information from Windows systems and allowed the delivery of additional malicious code for subsequent stages of the attack.
Fake PDF and text files
The hackers targeted deBridge Finance employees on Thursday with an email purporting to be from the company co-founder, Alex Smirnov, allegedly sharing new information about salary changes.

Email targeting targeting deBridge employeessource: Alex Smirnov
The email reached multiple employees and included an HTML file named ‘New Salary Adjustments’ that pretended to be a PDF file along with a Windows shortcut file (.LNK) that poses as a plain text file containing a password.

Fake PDF and text files used for targeting deBridge employeessource: Alex Smirnov
Clicking the fake PDF opened a cloud storage location claiming to provide a password-protected archive containing the PDF, thus bringing the target to launching the fake text file to obtain the password.
In a thread on Twitter, Smirnov explains that the LNK file executes the Command Prompt with the following command that retrieves a payload from a remote location:

Command for fetching malicious scriptsource: Alex Smirnov
The script was created to show a Notepad with the “pdf password: salary2022” and to check if the compromised system is protected by a security solution from ESET, Tencent, or Bitdefender.

Script checks for AV processessource: Alex Smirnov
Smirnov says that if the processes for the abovementioned security products are not present, the generated malicious file was saved in the startup folder, to ensure persistence.
This allowed the malware to achieve persistence and send out requests to the attacker’s command and control server for further instructions.
At this stage, the threat actor collected details about the infected system like username, operating system, CPU, network adapters, and running processes.
Smirnov says that the malware used in the attack was flagged by a small number of antivirus solutions.
The email was sent to multiple deBridge employees but most of them reported it as suspicious. However, one of them took the bait and downloaded and opened the document, which allowed Smirnov to analyze the attack.
Tied to North Korean Lazarus hackers
The connection to the North Korean hackers in the Lazarus group was possible due the overlap in file names and infrastructure used in a previous attack attributed to the threat actor.
Back in July, security researchers from PwC U.K. and Malwarebytes reported another campaign from the Lazarus hacker group - also referred to as CryptoCore and CryptoMimic - that used either the same same filenames or similar ones.


Malwarebytes and PwC researchers report similar Lazarus campaigns
BleepingComputer has learned that the same campaign has targeting cryptocurrency firms even earlier, in March, when the hackers targeted the crypto trading platform Woo Network with a document pretending to be a job offer from Coinbase cryptocurrency exchange platform.
While the file names are different, the attacker used the same fake PDF trick mask the malicious file and to get the victim to execute it.
In both attacks on deBridge and Woo Network, the hackers used malware for Windows systems. If a macOS system was detected, the victim would get a ZIP archive with a real PDF file.

Real PDF delivered to non-Windows machinessource: BleepingComputer
North Korea's Lazarus group has been focusing on hitting companies that rely in their business on blockchain technology and dececentralization concepts.
The threat actor uses social engineering tricks to establish a foothold on the victim computer and then tries to find a way to syphon cryptocurrency funds and assets.
One of the largest cryptocurrency heists attributed to this group is the theft of $620 million in Ethereum from Axie Infinity's Ronin network bridge.

Related Articles:
Orbit Chain loses $86 million in the last fintech hack of 2023Russian pleads guilty to running crypto exchange used by ransomware gangsEx-Amazon engineer pleads guilty to hacking crypto exchangesHackers mint 1.79 billion crypto tokens from PlayDapp gaming platformPalestine crypto donation scams emerge amid Israel-Hamas war








Crypto Exchange
CryptoCurrency
deBridge
Lazarus Group
North Korea
PDF



















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











