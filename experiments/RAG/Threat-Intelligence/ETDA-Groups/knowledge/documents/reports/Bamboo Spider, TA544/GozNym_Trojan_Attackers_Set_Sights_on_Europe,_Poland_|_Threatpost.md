# Reference for threat actor for "Bamboo Spider, TA544"

**Title**: GozNym Trojan Attackers Set Sights on Europe, Poland | Threatpost

**Source**: https://threatpost.com/attackers-behind-goznym-trojan-set-sights-on-europe/117647/

## Content


























GozNym Trojan Attackers Set Sights on Europe, Poland | Threatpost

























































 












Threatpost


Podcasts
Malware
Vulnerabilities
InfoSec Insiders
Webinars



 





 Search














Bangladesh Bank Hackers Accessed SWIFT System to Steal, Cover TracksPrevious article 

One Million Access Facebook Over TorNext article 










Attackers Behind GozNym Trojan Set Sights on Europe









Author: 
Chris Brook


April 25, 2016  2:35 pm












 minute read
											


Share this article:





 













The banking malware GozNym has spread into Europe and begun plaguing banking customers in Poland with redirection attacks, IBM said.


The banking malware GozNym has legs; only a few weeks after the hybrid Trojan was discovered, it has reportedly spread into Europe and begun plaguing banking customers in Poland with redirection attacks.
The malware has started targeting corporate, SMB, investment banking and consumer accounts at banks, including some in Portugal and the U.S., in addition to Poland, according to researchers at IBM’s X-Force team.
In the attacks, bank customers are redirected to a replica of their bank’s actual page and tricked into giving up sensitive information such as credentials and authentication codes. With GozNym, attackers dupe users by showing them the actual bank’s URL and SSL certificate. An overlay mask, facilitated by a Moscow-based server, covers the page, hiding any malicious content on the phishing page, something that makes it look normal to users and researchers alike.
Limor Kessem, a cybersecurity expert with IBM described the latest iteration of the malware Monday in a post on the company’s Security Intelligence blog.
After a user is redirected to the malicious page, the overlay is removed and users are encouraged to enter their bank username and password. From there, the information is fired off to another server.
“After that initial fake login, the malware displays a delay screen via webinjection asking the victim to wait,”Kessem wrote on Monday, “While the victim is on hold, the fraudster queries the C&C server for additional webinjections to trick users to divulge further information about their accounts,”
According to Kessem the malware has redirection instructions for 17 banks, and features an additional 230 URLs to assist attackers in targeting community banks and email service providers in Poland.
The technique is similar to one used by the Dridex Trojan earlier this year. Attackers took a page from Dyre and peddled Dridex by launching redirection attacks focused on U.K. users in January.
The method, which technically redirects users through local DNS poisoning, requires a fair bit of work; recreating and maintaining fake bank sites can be an arduous task, but Kessem claims the group behind GozNym – Nymaim – appear up to the task.
“Convincing redirection attacks are a resource-intensive endeavor that require their operators to invest heavily in creating website replicas of individual targeted banks. The Nymaim gang stands out as one of very few groups with this capability,” Kessem wrote.
The GozNym Trojan surfaced earlier this month after two other Trojans, Nymaim and Gozi, merged. Attackers went on to use the Trojan to steal $4 million from 24 banks, including 22 in the United States and two in Canada, in just two weeks. The malware is distributed primarily through laced spam emails that lure recipients into opening attachments.
Kessem warned the Trojan was a “very problematic threat” just 11 days ago when she spoke to Threatpost, calling the combination of the two Trojans a “double-headed beast,” adding that the number of attacks stemming from the malware the company observed were extremely high, especially given it had only existed for a few weeks at that point.




Share this article:





 







Malware










Suggested articles





 

Ghimob Android Banking Trojan Targets 153 Mobile Apps
A banking trojan is targeting mobile app users in Brazil – and researchers warn that its operator has big plans to expand abroad. 


November 10, 2020



 1









 

Wroba Mobile Banking Trojan Spreads to the U.S. via Texts
The Roaming Mantis group is targeting the States with a malware that can steal information, harvest financial data and send texts to self-propagate.


October 30, 2020








 

Alien Android Banking Trojan Sidesteps 2FA
A new ‘fork’ of the Cerberus banking trojan, called Alien, targets victims’ credentials from more than 200 mobile apps, including Bank of America and Microsoft Outlook.


September 24, 2020



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














