# Reference for threat actor for "Bluenoroff, APT 38, Stardust Chollima"

**Title**: Banco de Chile Wiper Attack Just a Cover for $10M SWIFT Heist | Threatpost

**Source**: https://threatpost.com/banco-de-chile-wiper-attack-just-a-cover-for-10m-swift-heist/132796/

## Content


























Banco de Chile Wiper Attack Just a Cover for $10M SWIFT Heist | Threatpost


























































 












Threatpost


Podcasts
Malware
Vulnerabilities
InfoSec Insiders
Webinars



 





 Search














Dixons Carphone Cyberattack Targets 5.9M Bank CardsPrevious article 

Two Bugs in WordPress Tooltipy Plugin PatchedNext article 










Banco de Chile Wiper Attack Just a Cover for $10M SWIFT Heist









Author: 
Tara Seals


June 13, 2018  12:19 pm












 minute read
											


Share this article:





 













The wiper malware affecting 9,000 workstations and 500 servers inside Chile’s largest financial institution turns out to have been a distraction.


A cyberattack against Chile’s largest financial institution last month, which reportedly destroyed 9,000 workstations and 500 servers, was actually cover for a larger plot to compromise endpoints handling transactions on the SWIFT network. When the dust settled on the attacks, investigators said $10 million was stolen from Banco de Chile and funneled off to an account in Hong Kong.
On Sunday, the bank’s general manager Eduardo Ebensperger told Chilean media outlet Pulso that the late-May attack allowed adversaries to complete four separate fraudulent transactions on the SWIFT system before the heist was discovered.
“We found some strange transactions in the SWIFT system (where banks internationally remit their transactions to different countries),” Ebensperger told the outlet. “There we realized that the virus was not necessarily the underlying issue, but apparently [the attackers] wanted to defraud the bank.”
The initial attack was carried out using a wiper malware that Ebensperger described as a “zero-day virus” that had never been seen in the wild. However, in report published Tuesday by  Flashpoint, analysts discovered that the code is actually a modified version of the Buhtrap malware component known as kill_os. The module renders the local operating system and the Master Boot Record (MBR) unreadable by erasing them.
After reverse-engineering the codebase, Flashpoint analysts found that the Chile-attack malware, dubbed “MBR Killer,” was identical with only minor modifications to Buhtrap’s kill_os. For instance, the Buhtrap code, which was leaked onto the Dark Web in February, contains an almost identical Nullsoft Scriptable Install System (NSIS) script as the unpacked Banco de Chile malware (NSIS is an open-source system used to build Windows installers).
This revelation could potentially help with attribution: The Buhtrap malware and its components, including MBR Killer, were previously used by a Russian-speaking hacker collective in attacks against multiple financial institutions in Russia and the Ukraine, Flashpoint noted.
However, the attribution behind the Banco de Chile attack remains uncertain.
“It is notable, however, that Chilean financial institutions were targeted entities by the Lazarus Group, which was linked to North Korea, during the compromise of the Polish Financial Supervision Authority website in 2017,” Vitali Kremez, director of research, told Threatpost in an interview. “More specifically, the breached website was filtered to serve payloads to only targeted IP ranges associated with financial institutions of interest to the group.”
He added, “the above-referenced indicators point to two possible groups behind – purported North-Korean affiliated group Lazarus and the known Russian-speaking sophisticated criminal group Buhtrap.”
It’s also possible, researchers said, that it’s an entirely different copycat group making use of Buhtrap’s leaked source code.
Meanwhile, Ebensperger said that a forensic analysis conducted by Microsoft attributed the attack to either Eastern European or Asian groups. Further, Ofer Israeli, CEO of Illusive Networks, said via email that he too believes the North Korea-linked Lazarus Group, which is thought to have carried out the SWIFT attacks in Bangladesh in 2016, is behind it all.
“Targeting financial organizations is part of their long-term strategy and compromising global financial networks via small to medium-sized banks in Central and South America whose cyber-defenses may be less sophisticated poses a higher probability of success,” he explained.
In any event, Banco de Chile is the latest victim in a string of cyber-attacks targeting payment transfer systems. For instance, in May, Somewhere between $18 million to $20 million went missing during unauthorized interbank money transfers in Mexico’s central banking system.
“Third-party providers of payment and transfer systems have become one of the most effective attack vectors for hackers trying to siphon money from banks,” said Fred Kneip, CEO at CyberGRX, via email. “We’ve seen the SWIFT Network under attack for years now, and just last month hackers targeted the Mexican central bank SPEI interbank transfer system.”
He added, “A large international bank has tens of thousands of third parties in their digital ecosystem, but hackers have figured out that it only takes one weak link to make millions of dollars. Understanding the level of risk exposure introduced by all third parties is important, but that becomes even more critical for a Tier 1 partner like a transfer system provider.”
 
 




Share this article:





 







Hacks
Malware










Suggested articles





 

SolarWinds Hack Potentially Linked to Turla APT
Researchers have spotted notable code overlap between the Sunburst backdoor and a known Turla weapon.


January 11, 2021








 

Malicious Software Infrastructure Easier to Get and Deploy Than Ever
Researchers at Recorded Future report a rise in cracked Cobalt Strike and other open-source adversarial tools with easy-to-use interfaces.


January 8, 2021








 

Ryuk Rakes in $150M in Ransom Payments
An examination of the malware gang’s payments reveals insights into its economic operations.


January 8, 2021










InfoSec Insider






Securing Your Move to the Hybrid Cloud


August 1, 2022









Why Physical Security Maintenance Should Never Be an Afterthought


July 25, 2022









Conti’s Reign of Chaos: Costa Rica in the Crosshairs


July 20, 2022









How War Impacts Cyber Insurance


July 12, 2022









Rethinking Vulnerability Management in a Heightened Threat Landscape


July 11, 2022







 





 






Threatpost

The First Stop For Security News



Home
About Us
Contact Us
RSS Feeds
 



Copyright © 2024 ThreatpostPrivacy Policy
Terms and Conditions
 

 


Topics
Black Hat
Breaking News
Cloud Security
Critical Infrastructure
Cryptography
Facebook
Government
Hacks
IoT
Malware
Mobile Security
Podcasts
Privacy
RSAC
Security Analyst Summit
Videos
Vulnerabilities
Web Security















Threatpost



 









Topics
Cloud SecurityMalwareVulnerabilitiesPrivacy
Show all

Black HatCritical InfrastructureCryptographyFacebookFeaturedGovernmentHacksIoTMobile SecurityPodcastsRSACSecurity Analyst SummitSlideshowVideosWeb Security

Authors
Elizabeth MontalbanoNate Nelson

Threatpost
HomeAbout UsContact UsRSS Feeds 





 Search










 












InfoSec Insider

Infosec Insider Post
Infosec Insider content is written by a trusted community of Threatpost cybersecurity subject matter experts. Each contribution has a goal of bringing a unique voice to important cybersecurity topics. Content strives to be of the highest quality, objective and non-commercial.












Sponsored

Sponsored Content
Sponsored Content is paid for by an advertiser. Sponsored content is written and edited by members of our sponsor community. This content creates an opportunity for a sponsor to provide insight and commentary from their point-of-view directly to the Threatpost audience. The Threatpost editorial team does not participate in the writing or editing of Sponsored Content.














