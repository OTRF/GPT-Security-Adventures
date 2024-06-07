# Reference for threat actor for "TA505, Graceful Spider, Gold Evergreen"

**Title**: TA505 Crime Gang Debuts Brand-New ServHelper Backdoor | Threatpost

**Source**: https://threatpost.com/ta505-servhelper-malware/140792/

## Content


























TA505 Crime Gang Debuts Brand-New ServHelper Backdoor | Threatpost

























































 












Threatpost


Podcasts
Malware
Vulnerabilities
InfoSec Insiders
Webinars



 





 Search














U.S. Government Shutdown Leaves Dozens of .Gov Websites VulnerablePrevious article 

Pre-Installed Android App Impacts Millions with Slew of Malicious ActivityNext article 










TA505 Crime Gang Debuts Brand-New ServHelper Backdoor












Author: 
Tara Seals


January 11, 2019  12:49 pm












 minute read
											


Share this article:





 










The latest malware from TA505 has been seen targeting banks, retailers and restaurants with two different versions.


A new backdoor named ServHelper has been spotted in the wild, acting as both a remote desktop agent as well as a downloader for a RAT called FlawedGrace.
According to Proofpoint, the prolific cybercriminal gang known as TA505 developed ServHelper, which has two variants: one focused on remote desktop functions and a second that primarily functions as a downloader. It’s named after the file names that are associated with the infection; and, a sample from one campaign used command and control (C2) URIs containing “/rest/serv.php.”
The primary motive is, as usual, financial: “TA505 appears to be actively targeting banks, retail businesses, and restaurants as they distribute these malware families,” said Proofpoint researchers, in a posting this week.
Researchers said that the remote desktop version, a.k.a. the “tunnel” variant, was seen in November spreading via a few thousand spam messages that contained Microsoft Word or Publisher attachments with macros that, when enabled, download and execute the malware. This version focuses on setting up reverse SSH tunnels to allow the threat actor to access the infected host via Remote Desktop Protocol (RDP).
“Once ServHelper establishes remote desktop access, the malware contains functionality for the threat actor to hijack legitimate user accounts or their web browser profiles and use them as they see fit,” according to Proofpoint.
Click to expand.
A similar campaign consisting of tens of thousands of email messages surfaced later in November, according to Proofpoint. In addition to financial institutions, this campaign also targeted the retail industry. The messages also contained Microsoft Word or Publisher attachments with macros, along with Microsoft Wizard attachments. This campaign used the downloader variant of ServHelper, the researchers said. The version is stripped of the tunneling and hijacking functionality and is used as a basic downloader.
In December, TA505 mixed it up with another downloader-variant campaign. It targeted retail and financial services customers again, but this time used a mixture of Microsoft Word attachments with embedded malicious macros; PDF attachments with URLs linking to a fake “Adobe PDF Plugin” webpage (which linked to the malware); and direct URLs in the email body linking to a ServHelper executable. It also added a new malware payload.
“In this campaign, we observed ServHelper download and execute an additional malware that we call FlawedGrace,” according to Proofpoint. “FlawedGrace is a robust remote access trojan (RAT) that we initially encountered in November 2017, but have rarely observed since.”
Per the malware’s debug strings, the last significant development of FlawedGrace took place during the end of 2017. The ServHelper campaigns were distributing version 2.0.10 of the malware, which is related to the more widely known FlawedAmmy RAT.
In general, it appears that TA505 is enjoying its new toy: ServHelper is being actively developed.
“New commands and functionality are being added to the malware in almost every new campaign,” Proofpoint researchers noted.
TA505, a well-resourced organized cybercrime ring, is known for ongoing malware authoring and development, with everything from fully-fledged backdoors to what seems like beta-stage code making appearances in its campaigns. In this case, ServHelper is unlikely to be a flash in the pan.
“Threat actor TA505 is both consistent and prolific,” Proofpoint researchers said. “When the group distributes new malware, it may be a blip (like Bart ransomware, which was only distributed for one day in 2016) or like Locky ransomware it may become the dominant strain of malware in the wild. We will continue to observe the distribution of these three malware variants but, at this time, they do not appear to be one-offs, but rather long-term investments by TA505.”
They added, that also extends the trend that emerged in 2018, in which threat actors increasingly focused on distribution of downloaders, information stealers, RATS and “other malware that can remain resident on victim devices for far longer than destructive, smash-and-grab malware like ransomware.”
To the latter point, it’s worth noting that TA505 was responsible for hundreds of Dridex campaigns beginning in 2014, in addition to the massive Locky campaigns that came later. In all cases, hundreds of millions of malicious messages were distributed worldwide.




Share this article:





 







Malware










Suggested articles





 

It’s Not the Trump Sex Tape, It’s a RAT
Criminals are using the end of the Trump presidency to deliver a new remote-access trojan (RAT) variant disguised as a sex video of the outgoing POTUS, researchers report.


January 6, 2021








 

ElectroRAT Drains Cryptocurrency Wallet Funds of Thousands
At least 6,500 cryptocurrency users have been infected by new, ‘extremely intrusive’ malware that’s spread via trojanized macOS, Windows and Linux apps.


January 5, 2021








 

Agent Tesla Keylogger Gets Data Theft and Targeting Update
The infamous keylogger has shifted its targeting tactics and now collects stored credentials for less-popular web browsers and email clients.


December 15, 2020



 2











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














