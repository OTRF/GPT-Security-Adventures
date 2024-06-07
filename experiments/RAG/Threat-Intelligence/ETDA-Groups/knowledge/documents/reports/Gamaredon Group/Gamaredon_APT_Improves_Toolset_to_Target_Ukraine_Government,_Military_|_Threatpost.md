# Reference for threat actor for "Gamaredon Group"

**Title**: Gamaredon APT Improves Toolset to Target Ukraine Government, Military | Threatpost

**Source**: https://threatpost.com/gamaredon-apt-toolset-ukraine/152568/

## Content


























Gamaredon APT Improves Toolset to Target Ukraine Government, Military | Threatpost

























































 












Threatpost


Podcasts
Malware
Vulnerabilities
InfoSec Insiders
Webinars



 





 Search














Community Housing Nonprofit Hit with $1.2M Loss in BEC ScamPrevious article 

Critical Cisco ‘CDPwn’ Flaws Break Network SegmentationNext article 










Gamaredon APT Improves Toolset to Target Ukraine Government, Military









Author: 
Tara Seals


February 5, 2020  6:00 am












 minute read
											


Share this article:





 













Research have been tracking an uptick in Gamaredon cyberattacks on Ukrainian military and security institutions that started in December.


The Gamaredon advanced persistent threat (APT) group has been supercharging its operations lately, improving its toolset and ramping up attacks on Ukrainian national security targets.
Vitali Kremez, head of SentinelLabs, said in research released on Wednesday that he has been tracking an uptick in Gamaredon cyberattacks on Ukrainian military and security institutions that started in December. He said that these include digital attacks on physical infrastructure and field hardware, including artillery – along with more expected cyber-espionage activity. One of the latter campaigns was a series of reconnaissance actions against the Hetman Petro Sahaidachnyi National Ground Forces Academy, in the Ukraine; and, spyware implants were spotted in a range of Ukrainian governmental targets.
“Based on SentinelLabs visibility into some of the affected victims, APT Gamaredon affected a large disposition of victim across Ukrainian separatist line with more than five thousand unique Ukrainian entities affected for the past months,” Kremez wrote.

In examining the campaign, SentinelLabs found that Gamaredon has improved its toolset. The latest malware implant appears to be a modified version of the group’s proprietary Pterodo malware, discovered on computers of state authorities of Ukraine performing system reconnaissance.
“This virus collects system data, regularly sends it to command-control servers and expects further commands,” Kremez wrote. “Packaged as self-extracting zip-archive (.SFX), the Gamaredon malware implant components contain a batch script, a binary processor .NET component and macro payloads.”
Notably, the implant boasts the addition of a .NET framework interop integrator known as Microsoft.Vbe.Interop.
“The newer tool [carries out] updated execution via an obfuscated .NET application of Excel and Word macros,” wrote Kremez. He added that the macro payload execution approach uses a specific processor that leverages scripting persistence. “The macro execution security registry [allows] macro execution and disabling Visual Basic for Applications (VBA) warnings,” he said. “[This] malware Interop component [also] uses fake Microsoft digital certificates belonging to Microsoft Time-Stamp Service.”
In addition, the group is also now using a system of Nginx forwarders to process traffic from compromised victim machines, oftentimes relying on dynamic DNS providers, according to the analysis.
Gamaredon, which Kremez said is linked to the Russian military, has ramped up its malware capabilities while exclusively targeting the Ukrainian national security institutions.
“Gamaredon has introduced new tools into its arsenal that significantly up its offensive capabilities,” he noted. “Their operations have impacted more than five thousand unique Ukrainian entities in the past few months.” He added, “This ability to efficiently integrate cyber-offense measures into the actual battlefield of a traditional or asymmetric warfare model has been for years tested in the long-term military conflict unfolding in Eastern Ukraine since 2014.”




Share this article:





 







Government
Malware










Suggested articles





 

New Hacker Forum Takes Pro-Ukraine Stance
A uniquely politically motivated site called DUMPS focuses solely on threat activity directed against Russia and Belarus


August 11, 2022








 

SolarWinds Hack Potentially Linked to Turla APT
Researchers have spotted notable code overlap between the Sunburst backdoor and a known Turla weapon.


January 11, 2021








 

Malicious Software Infrastructure Easier to Get and Deploy Than Ever
Researchers at Recorded Future report a rise in cracked Cobalt Strike and other open-source adversarial tools with easy-to-use interfaces.


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














