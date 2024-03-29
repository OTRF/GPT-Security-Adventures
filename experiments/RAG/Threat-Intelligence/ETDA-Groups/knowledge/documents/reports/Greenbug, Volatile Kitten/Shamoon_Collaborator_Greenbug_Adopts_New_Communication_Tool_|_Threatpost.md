# Reference for threat actor for "Greenbug, Volatile Kitten"

**Title**: Shamoon Collaborator Greenbug Adopts New Communication Tool | Threatpost

**Source**: https://threatpost.com/shamoon-collaborator-greenbug-adopts-new-communication-tool/125383/

## Content


























Shamoon Collaborator Greenbug Adopts New Communication Tool | Threatpost

























































 












Threatpost


Podcasts
Malware
Vulnerabilities
InfoSec Insiders
Webinars



 





 Search














IBM: Destroy USBs Infected with Malware DropperPrevious article 

Proposed NIST Password Guidelines Soften Length, Complexity FocusNext article 










Shamoon Collaborator Greenbug Adopts New Communication Tool












Author: 
Tom Spring


May 2, 2017  5:52 pm












 minute read
											


Share this article:





 










New clues surface on Shamoon’s ability steal credentials ahead of attacks. 


Researchers have identified a possible new collaborator in the continued Shamoon attacks against Saudi organizations. Called Greenbug, this group is believed to be instrumental in helping Shamoon steal user credentials of targets ahead of Shamoon’s destructive attacks.
However, researchers know about as much about Greenbug as they do Shamoon; which isn’t much. But, that’s slowly changing.
On Tuesday, Arbor Networks said that it has new leads on a credential stealing remote access Trojan (RAT) called Ismdoor, possibly used by Greenbug to steal credentials on Shamoon’s behalf.
“With our latest research we now see how Greenbug has shifted away from HTTP-based C2 communication with Ismdoor. It’s now relying on a new DNS-based attack technique to better cloak command and control communications between Greenbug and the malware,” said Dennis Schwarz, research analyst on Arbor’s ASERT Team, in an interview with Threatpost.
He said Greenbug is using DNS TXT record queries and responses to create a bidirectional command and control channel.
“One major change in recent versions (of Ismdoor) has been the replacement of the old HTTP based command and control functionality with a custom covert channel using AAAA DNS queries for IPv6 addresses,” Schwarz wrote in a technical analysis of the malware posted Monday.
Using the DNS attack technique, adversaries can use DNS communications to submit commands to be run on systems infected with the Ismdoor RAT. Schwarz said using this technique, data is also be exfiltrated from the machines as well. “This is an extremely rare and covert way to administer a RAT,” he said.
DNS tunneling takes advantage of the TXT transport layer within the DNS protocol used by top- and second-level domain name system servers. A maximum of 255 bytes of data can be transported via DNS requests between endpoint and a DNS server using the TXT layer. For attackers that have already gained a foothold on targeted systems, the DNS tunneling of commands and DNS tunneling used to remove data is extremely slow, but well suited for long term APT campaigns.
“All data sent between the bot and the C2 is done using AAAA DNS UDP queries. Data to the C2 is via specially crafted query names and data from the C2 is returned via IPv6 addresses. The bot side of the connection drives all communications,” according  to Schwarz’s analysis.
Use of DNS-based message attacks has been used in similar attacks documented by Cisco Talos where adversaries use DNS queries to carry out malicious PowerShell commands on compromised computers. Last year, Palo Alto Networks reported a shift in malware tactics used by the APT group Wekby that utilized the DNS TXT transport layer. Cisco calls these types of attacks DNSMessenger attacks. Palo Alto Networks calls them DNS tunneling attacks.
In the context of the Ismdoor RAT, the DNS attack technique is used primarily by Greenbug for stealing credentials. To do this, it employs a number of specific commands via DNSMessenger. One is “CreateMimi1Bat”; which likely executes Mimikatz (executes PowerShell scripts: ccd61.ps1 and Invoke-bypassuac), according to Arbor. Another command is “ExecuteKL”; which likely executes a keylogger (executes Winit.exe and sends “Start Keylog Done” message back to the C2), according to Arbor.
“The threat group that could be behind the original Shamoon attacks is still alive and well. They are definitely advancing the malware. While this DNS form of communication is not new, it’s far from a copy-and-paste type attack. This type of attack takes a dedicated programmer to think it through and put it together,” Schwarz said.




Share this article:





 







Government
Hacks
Malware
Web Security










Suggested articles





 

It’s Not the Trump Sex Tape, It’s a RAT
Criminals are using the end of the Trump presidency to deliver a new remote-access trojan (RAT) variant disguised as a sex video of the outgoing POTUS, researchers report.


January 6, 2021








 

ElectroRAT Drains Cryptocurrency Wallet Funds of Thousands
At least 6,500 cryptocurrency users have been infected by new, ‘extremely intrusive’ malware that’s spread via trojanized macOS, Windows and Linux apps.


January 5, 2021








 

Sunburst’s C2 Secrets Reveal Second-Stage SolarWinds Victims
Examining the backdoor’s DNS communications led researchers to find a government agency and a big U.S. telco that were flagged for further exploitation in the spy campaign.


December 18, 2020



 1











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














