# Threat actor: Cobalt Group

**UUID**: d8339e9a-c946-4304-aac4-722d8652d273

**First seen**: 2016

**Source last modified**: 2021-12-09

## Threat actor aliases

Cobalt Group (Group-IB), Cobalt Gang (Palo Alto), Cobalt Spider (CrowdStrike), Gold Kingswood (SecureWorks), ATK 67 (Thales), TAG-CR3 (Recorded Future)

## Description

Cobalt Group is a financially motivated threat group that has primarily targeted financial institutions. The group has conducted intrusions to steal money via targeting ATM systems, card processing, payment systems and SWIFT systems. Cobalt Group has mainly targeted banks in Eastern Europe, Central Asia, and Southeast Asia. The group has been known to target organizations in order to use their access to then compromise additional victims. Reporting indicates there may be links between Cobalt Group and both the malware Carbanak and the group {{Carbanak, Anunak}}.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Financial crime


## Country of origin

Russia

## Observed attacked sectors where victims operate in

Financial, High-Tech, Media, Retail

## Observed attacked countries where victims operate in

Argentina, Armenia, Austria, Azerbaijan, Belarus, Bulgaria, Canada, China, Czech, Estonia, Georgia, Italy, Jordan, Kazakhstan, Kuwait, Kyrgyzstan, Malaysia, Moldova, Netherlands, Poland, Romania, Russia, Spain, Taiwan, Tajikistan, Thailand, Turkey, UK, Ukraine, USA, Vietnam

## Observed usage of tools

ATMSpitter, ATMRipper, AtNow, Cobalt Strike, CobInt, Cyst Downloader, FlawedAmmyy, Formbook, Little Pig, Mimikatz, Metasploit Stager, More_eggs, NSIS, Pony, SDelete, SoftPerfect Network Scanner, Taurus Loader, ThreatKit, VenomKit

## Reported hacking operations

2016-06: In June 2016, the first attack conducted by the Cobalt group was tracked at a large Russian bank, where hackers attempted to steal money from ATMs. The attackers infiltrated the bank’s network, gained control over it, compromised the domain administrator’s account, and reached the ATM control server.
https://www.group-ib.com/blog/cobalt

2016-07: ATM heist at the First Commercial Bank in Taiwan
https://www.reuters.com/article/us-taiwan-cyber-atms/taiwan-atm-heist-linked-to-european-hacking-spree-security-firm-idUSKBN14P0CX

2016-08: ATM heist at the Government Saving Bank in Thailand
ThaiCERT's whitepaper:
https://www.dropbox.com/s/1xvhee0s7o12i61/Whitepaper ATM Heist GSB August 2016.pdf?dl=0

2017-05: In May, Proofpoint observed multiple campaigns using a new version of Microsoft Word Intruder (MWI). MWI is a tool sold on underground markets for creating exploit-laden documents, generally used in targeted attacks. We previously reported about MWI when it added support for CVE-2016-4117. After the latest update, MWI is now using CVE-2017-0199 to launch an HTML Application (HTA) used for both information collection and payload execution.
This activity targets organizations in the financial vertical including banks, banking software vendors, and ATM software and hardware vendors. The emails are sent to technology and security personnel working in departments including Fraud and Information Security.
https://www.proofpoint.com/us/threat-insight/post/microsoft-word-intruder-integrates-cve-2017-0199-utilized-cobalt-group-target

2017-08: The first spam run on August 31 used a Rich Text Format (RTF) document laden with malicious macros. The second, which ran from September 20 to 21, used an exploit for CVE-2017-8759 (patched last September), a code injection/remote code execution vulnerability in Microsoft’s .NET Framework. The vulnerability was used to retrieve and execute Cobalt Strike from a remote server they controlled.
https://blog.trendmicro.com/trendlabs-security-intelligence/cobalt-spam-runs-use-macros-cve-2017-8759-exploit/

2017-11: On Tuesday, November 21, a massive spear-phishing campaign began targeting individual employees at various financial institutions, mostly in Russia and Turkey. Purporting to provide info on changes to ‘SWIFT’ terms, the email contained a single attachment with no text in the body. It was an attempt by the Cobalt Group to gain a foothold in the networks of the targeted individuals’ organizations
https://www.riskiq.com/blog/labs/cobalt-strike/

2018-01: Spear-phishing attacks to Russian banks
The emails were sent in the name of a large European bank in an attempt to social engineer the receiver into trusting the email. The emails were quite plain with only a single question in the body and an attachment with the name once.rtf. In other cases, we saw a file with the name Заявление.rtf attached to an email that was also written in Russian.
https://www.riskiq.com/blog/labs/cobalt-group-spear-phishing-russian-banks/

2018-05: On May 23, 1:21 p.m (Moscow time) Group-IB tracked a new large-scale Cobalt cyberattack on the leading banks of Russia and the CIS. It was like a challenge: phishing emails were sent acting as a major anti-virus vendor. Bank employees received a “complaint”, in English, that their computers allegedly violated legislation.
https://www.group-ib.com/blog/renaissance

2018-09: In 2018, CTU researchers observed several GOLD KINGSWOOD campaigns involving SpicyOmelette, a tool used by the group during initial exploitation of an organization. This sophisticated JavaScript remote access tool is generally delivered via phishing, and it uses multiple defense evasion techniques to hinder prevention and detection activities.
https://www.secureworks.com/blog/cybercriminals-increasingly-trying-to-ensnare-the-big-financial-fish

2018-10: One of the latest examples related to the campaign under analysis was used in attacks just a few days ago. It shows the simplicity of the attack delivery employed by this group.
The attack reinforces the fact that email is still one of the primary attack vectors we continuously observe. This attack begins by targeting employees at several banking entities across the globe using an email with subject “Confirmations on October 16, 2018”.
https://unit42.paloaltonetworks.com/unit42-new-techniques-uncover-attribute-cobalt-gang-commodity-builders-infrastructure-revealed/

2019-10: Magecart Group 4: A link with Cobalt Group?
https://blog.malwarebytes.com/threat-analysis/2019/10/magecart-group-4-a-link-with-cobalt-group/

## Reported counter operations against threat actor

2018-03: Mastermind behind EUR 1 billion cyber bank robbery arrested in Spain
https://www.europol.europa.eu/newsroom/news/mastermind-behind-eur-1-billion-cyber-bank-robbery-arrested-in-spain

2018-08: Three Carbanak cyber heist gang members arrested
https://www.computerweekly.com/news/252446153/Three-Carbanak-cyber-heist-gang-members-arrested



