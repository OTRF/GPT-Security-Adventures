# Reference for threat actor for "Bluenoroff, APT 38, Stardust Chollima"

**Title**: Lazarus APT Spinoff Linked to Banking Hacks | Threatpost

**Source**: https://threatpost.com/lazarus-apt-spinoff-linked-to-banking-hacks/124746/

## Content


























Lazarus APT Spinoff Linked to Banking Hacks | Threatpost

























































 












Threatpost


Podcasts
Malware
Vulnerabilities
InfoSec Insiders
Webinars



 





 Search














Fileless Banking Malware Attackers Break In, Cash Out, DisappearPrevious article 

Security Analyst Summit 2017 Day One RecapNext article 










Lazarus APT Spinoff Linked to Banking Hacks












Author: 
Michael Mimoso


April 3, 2017  4:38 pm












 minute read
											


Share this article:





 










The Lazarus Group has splintered off a group whose mission is to attack banks and steal money in order to fund its operations. 


SINT MAARTEN—The Lazarus Group, a nation-state level of attacker tied to the 2014 attacks on Sony Pictures Entertainment, has splintered off a portion of its operation to concentrate on stealing money to fund itself.
The group, widely believed to be North Korean, has been linked to a February 2016 attack against the Bangladesh Central bank that resulted in more than $850 million in fraudulent SWIFT network transactions, $80 million of which still has not been recovered.
At the Security Analyst Summit, researchers from Kaspersky Lab and BAE Systems explained how the splinter group, known as Bluenoroff, has almost exclusively hit financial institutions, casinos, financial trade software development companies and cryptocurrency businesses. The group has also been connected to an attack earlier this year against banks in Poland, based on code strings and wiper malware discovered and known to be part of Lazarus’ arsenal.

Vitaly Kamluk of Kaspersky Lab and Adrian Nish and Sergey Shevchenko of BAE Systems today published an update on Lazarus and Bluenoroff, pinning to them their unique interest in SWIFT software. SWIFT is a global network supporting financial transactions and messaging between institutions. The attackers, researchers said, aren’t looking for smash-and-grab bank robberies. They learn the inner workings of SWIFT software and develop and implement patches that allow the attackers to steal significant amounts of money without leaving a trace behind on the hacked systems.
Dries Watteyne, SWIFT head of customer security intelligence, also appeared at SAS and said the attackers had intimate knowledge of how the SWIFT network processes transactions and messages between financial institutions.
“They had sophisticated knowledge on a business level,” Watteyne said. “They were able to make sure all messages sent from the bank and statements from the U.S. bank were hidden.”
Watteyne explained that with an international transaction of U.S. dollars, emitters send payment instructions to a U.S. bank, which remits an acknowledgement before sending funds to an offshore bank.
The attackers used stolen credentials to inject custom malware at the bank that was able to delete all payment instructions from the targeted database, modify SWIFT messages, including start- and end-of-day statements, and also bypass integrity verification checks built into the system.
The Lazarus Group is alleged to have leaked mountains of sensitive data from Sony Pictures Entertainment in 2014, including emails, movie scripts and other confidential information. Following the Sony hack in January 2015, the U.S. levied sanctions against North Korean defense agencies, two other government agencies and 10 individuals. The Executive Order explaining the sanctions came two weeks after North Korea suffered a DDoS attack that disconnected much of the country from the Internet.
Lazarus Group’s interest in profit is relatively new, the researchers said. They’ve adopted a number of tactics preferred by cybercriminals, including watering hole attacks to compromise financial targets. In these attacks, a website of common interest to the target is attacked and spiked with malicious code designed to exploit a vulnerable browser or piece of third-party software.
BAE’s Nish said they used iframes to redirect browsers to sites hosting scripts that check for vulnerabilities, deliver exploits and payloads. Most of the Bluenoroff attacks were initially focused on Southeast Asia and developing countries. Starting with the Poland attacks, their bravado grew and was much more global.
The link between Bluenoroff, North Korea and Lazarus gained steam, Kamluk said, from an analysis of a command and control server in Europe used in attacks. The researchers determined how the attackers connected to the server and tested their backdoors using multiple IPs from around the world. One short connection, however, was made from an IP range in North Korea.

Kamluk said the attackers’ installation of cryptocurrency mining software crashed the server and likely kept the attackers from properly wiping their traces. While none of the researchers would commit fully to attributing North Korea to these attacks, the evidence does indicate some involvement.
“If it is North Korea,” Kamluk said, “we know very little about its current motivation and use of offensive capabilities.”





Share this article:





 







Hacks
Security Analyst Summit










Suggested articles





 

Lazarus Group Hits COVID-19 Vaccine-Maker in Espionage Attack
The nation-state actor is looking to speed up vaccine development efforts in North Korea.


December 23, 2020








 

Hacked Security Software Used in Novel South Korean Supply-Chain Attack
Lazarus Group is believed to be behind a spate of attacks that leverage stolen digital certificates tied to browser software that secures communication with government and financial websites in South Korea. 


November 16, 2020



 1









 

Nation-State Attackers Actively Target COVID-19 Vaccine-Makers
Three major APTs are involved in ongoing compromises at pharma and clinical organizations involved in COVID-19 research, Microsoft says.


November 13, 2020










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














