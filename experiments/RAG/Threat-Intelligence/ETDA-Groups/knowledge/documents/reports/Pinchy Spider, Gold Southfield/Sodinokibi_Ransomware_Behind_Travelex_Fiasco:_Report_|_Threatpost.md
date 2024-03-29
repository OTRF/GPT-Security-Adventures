# Reference for threat actor for "Pinchy Spider, Gold Southfield"

**Title**: Sodinokibi Ransomware Behind Travelex Fiasco: Report | Threatpost

**Source**: https://threatpost.com/sodinokibi-ransomware-travelex-fiasco/151600/

## Content


























Sodinokibi Ransomware Behind Travelex Fiasco: Report | Threatpost

























































 












Threatpost


Podcasts
Malware
Vulnerabilities
InfoSec Insiders
Webinars



 





 Search














FBI Taps Apple to Unlock Pensacola Shooter’s iPhonePrevious article 

Google Fixes Critical Android RCE FlawNext article 










Sodinokibi Ransomware Behind Travelex Fiasco: Report












Author: 
Tara Seals


January 7, 2020  12:04 pm












 minute read
											


Skip to:

Unpatched Pulse Secure Servers
Comments



Share this article:





 










Researchers suspect the cybercriminals attacked using an unpatched critical vulnerability in the company’s seven Pulse Secure VPN servers.


The Sodinokibi ransomware strain is apparently behind the New Year’s Eve attack on foreign currency-exchange giant Travelex, which has left its customers and banking partners stranded without its services.
The criminals behind the attack are demanding a six-figure sum in return for the decryption key, according to reports, and are directing the company to a payment website hosted in Colorado.
“It is just business. We absolutely do not care about you or your details, except getting benefits. If we do not do our work and liabilities – nobody will not co-operate with us. It is not in our interests,” the readme file for the ransomware, obtained by Computer Weekly, said. “If you do not cooperate with our service – for us it does not matter. But you will lose your time and your data, cause just we have the private key. In practice time is much more valuable than money.”

Sodinokibi, also known as REvil, appeared in April 2019. It has been responsible for a string of high-profile hits, including attacks on 22 Texas municipalities and various dentist offices around the country. Researchers from Secureworks Counter Threat Unit (CTU) believe that the group behind the infamous GandCrab ransomware, which earlier this year claimed to have retired, is actually responsible for Sodinokibi, given that the string decoding functions and other code aspects employed by Sodinokibi and GandCrab are nearly identical.
Travelex, a ubiquitous fixture at airports, provides foreign-exchange services in 70 countries across more than 1,200 retail branches. The attack resulted in Travelex websites in at least 20 countries going offline, left its retail locations to carry out tasks manually, and many customers remain stranded without travel money. Its global banking partners, including Barclays, First Direct, HSBC, Sainsbury’s Bank, Tesco and Virgin Money, have also been left adrift with no way to buy or sell foreign currency.
It’s unclear whether the company plans to pay the ransom, and it has offered no timeline on cleanup. While the company has admitted the attack, many of its websites merely are showing a warning screen saying that they’re down for “planned maintenance.”
It has not returned Threatpost’s requests for comment.
Unpatched Pulse Secure Servers
The attack could have been successful in part because Travelex took several months to patch critical vulnerabilities in its Pulse Secure VPN servers, according to Bad Packets.
Pulse Secure offers a popular enterprise remote access family of products. The company issued an urgent patch for two critical vulnerabilities in its Zero Trust VPN product in April. CVE-2019-11510 is an arbitrary file reading vulnerability allows sensitive information disclosure enabling unauthenticated attackers to access private keys and user passwords, according to the advisory; further exploitation using the leaked credentials can lead to remote command injection (CVE-2019-11539) and allow attackers to gain access inside private VPN networks.
“That vulnerability is incredibly bad — it allows people without valid usernames and passwords to remotely connect to the corporate network the device is supposed to protect, turn off multi-factor authentication controls, remotely view logs and cached passwords in plain text (including Active Directory account passwords),” explained researcher Kevin Beaumont (a.k.a. Gossi the Dog), in a posting this week.
He said that in August, he became aware that public exploits had been made available and that cybercriminals including APTs were actively scanning the internet for the issue (using public tools like the Shodan search engine). A corresponding report from Bad Packets that month indicated that major cyberattacks could be imminent.
“On August 25th 2019, Bad Packets scanned the internet and found almost 15,000 endpoints across the world had the issue directly exploitable,” Beaumont noted. “Those results included networks at governments across the world — many incredibly sensitive organizations included — and basically a list of the world’s largest companies. It was clear organizations were simply not patching.”
One of these organizations was Travelex, which had seven unsecured Pulse Secure servers, according to Bad Packets; it also said that the company waited until November – eight months after the vulnerability disclosure – to patch the issues.

We notified Travelex about their vulnerable Pulse Secure VPN servers on September 13, 2019.
No response. pic.twitter.com/lCjk7IY3OM
— Bad Packets Report (@bad_packets) January 4, 2020

Bad Packets indicated that this lag time could have provided the window in which the cybergang infiltrated the Travelex network – a speculation that is somewhat supported by Pulse Secure itself, which issued a statement this week that it has indeed seen the Sodinokibi ransomware being delivered via exploits for the vulnerabilities.
“The ransomware situation at Travelex shines a harsh spotlight on the potential devastation of a cybersecurity incident,” Jonathan Knudsen, senior security strategist at Synopsys, said in an emailed statement. “The lost business and negative publicity from a scenario such as this can be crushing. Ransomware continues to be a popular tool for cybercriminals…If you fall victim to a ransomware attack, you must have a plan ready to execute. The plan should include removing infected systems from your network, wiping them and reinstalling the operating system and applications, then restoring data from your backups.”
Concerned about mobile security? Check out our free Threatpost webinar, Top 8 Best Practices for Mobile App Security, on Jan. 22 at 2 p.m. ET. Poorly secured apps can lead to malware, data breaches and legal/regulatory trouble. Join our experts to discuss the secrets of building a secure mobile strategy, one app at a time. Click here to register.




Share this article:





 







Malware
Vulnerabilities










Suggested articles





 

SolarWinds Hack Potentially Linked to Turla APT
Researchers have spotted notable code overlap between the Sunburst backdoor and a known Turla weapon.


January 11, 2021











 

A Look Ahead at 2021: SolarWinds Fallout and Shifting CISO Budgets
Threatpost editors discuss the SolarWinds hack, healthcare ransomware attacks and other threats that will plague enterprises in 2021.


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














