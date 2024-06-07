# Reference for threat actor for "Shadow Brokers"

**Title**: ShadowBrokers Dump More Equation Group Hacks, Auction File Password | Threatpost

**Source**: https://threatpost.com/shadowbrokers-dump-more-equation-group-hacks-auction-file-password/124882/

## Content


























ShadowBrokers Dump More Equation Group Hacks, Auction File Password | Threatpost

























































 












Threatpost


Podcasts
Malware
Vulnerabilities
InfoSec Insiders
Webinars



 





 Search














Travel Routers, NAS Devices Among Easily Hacked IoT DevicesPrevious article 

Breaking Signal: A Six-Month JourneyNext article 










ShadowBrokers Dump More Equation Group Hacks, Auction File Password









Author: 
Michael Mimoso


April 10, 2017  3:26 pm












 minute read
											


Share this article:





 













The ShadowBrokers’ latest dump of Equation Group hacks focuses on UNIX systems and GSM networks, and was accompanied by an open letter to President Trump. 


The mysterious ShadowBrokers, long thought to have given up their cause, released on Saturday additional hacking tools allegedly belonging to the Equation Group, along with the password guarding the original set of exploits the group planned to auction off.
The password was at the tail end of a rambling open letter to President Donald Trump in which the ShadowBrokers expressed their discontent with the administration’s actions in Syria, its defeat on Obamacare, the removal of Steve Bannon from the National Security Council and more.
“Respectfully, what the f%&k are you doing? TheShadowBrokers voted for you. TheShadowBrokers supports you. TheShadowBrokers is losing faith in you,” the letter begins.
As for the tools, as in past leaks it appears these are older exploits. They run the gamut from remote code execution attacks against enterprise operating systems such as Solaris, Netscape Server, FTP servers, various webmail clients and more.
There are also a number of antiforensics tools that the Equation Group, linked in many circles to the National Security Agency, uses to clean up its tracks after an intrusion.
Saturday’s dump also includes a number of backdoors and post-exploitation remote access shells for UNIX and SPARC systems, as well as keyloggers, network monitoring tools and kernel-level implants for UNIX systems.
“What is stunning is the way it specifically targets Solaris/HP-UX systems that are most likely used in big corporations or telecoms companies,” said a researcher who goes by the handle x0rz. “Which means they are in for the big fish.”
The extent of the Equation Group’s reach into its targets is illustrated in a long list of compromised hosts and tools used against them, including UNIX backdoors PITCHIMPAR and INTONATION.
X0rz was among a handful of researchers who examined the dump over the weekend and posted the files and an index for other researchers to examine. X0rz said the Equation Group was particularly invested in exploiting and attacking GSM core networks. GSM stands for Global System for Mobile Communication, used primarily in Europe, and is the telephony system for data compression and transmission; there are estimated five billion GSM phone users worldwide.
In one instance, it appears the Equation Group had access to the Pakistan Mobilink GSM network.

#EquationGroup used CURSEHAPPY to harvest CDRs from these GSM networks (targeting MSC) https://t.co/QCqbJPpLKK #ShadowBrokers
— x0rz (@x0rz) April 9, 2017

“From what I understand they have tools to collect CDRs (Call detail record) that are generated on GSM core networks for billing purpose (who is calling who, etc.),” x0rz said. “They are deep into these systems.”
There are more than 1,000 files included in the dump and it’s unknown whether any of the vulnerabilities being exploited remain unpatched.
Edward Snowden, the NSA whistleblower, said in a series of tweets on Saturday that the latest dump does not represent the totality of the NSA’s hacking tools.

…much here that NSA should be able to instantly identify where this set came from and how they lost it. If they can't, it's a scandal.
— Edward Snowden (@Snowden) April 8, 2017

In January, the ShadowBrokers said they were done and were deleting all of their accounts. The group did first put a set of Windows exploits for sale for 750 Bitcoin which included a zero-day exploit for a Windows SMB protocol flaw. Researcher Jacob Williams looked at the screenshots and surmised the zero day by the price the ShadowBrokers are asking.
“Note that most of the tools have apparently been through multiple revisions, adding apparent legitimacy to the claim that these exploits are real,” Williams said. “Though another screenshot hints at a possible zero day SMB exploit, there’s no indication of which exploit names involve SMB (or any other target service).”
The identity of the ShadowBrokers remains open for debate, and the candidates could be anyone from an intelligence outfit, to a NSA insider. Saturday’s letter gives no concrete clues as to who they may be, or their motivations.




Share this article:





 







Government
Malware










Suggested articles





 

Biden to Appoint Cybersecurity Advisor to NSC – Report
Anne Neuberger will join the National Security Council, according to sources.


January 7, 2021








 

NSA Urges SysAdmins to Replace Obsolete TLS Protocols
The NSA released new guidance providing system administrators with the tools to update outdated TLS protocols.


January 6, 2021



 2









 

Feds Pinpoint Russia as ‘Likely’ Culprit Behind SolarWinds Attack
The widespread compromise affecting key government agencies is ongoing, according to the U.S. government.


January 6, 2021










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














