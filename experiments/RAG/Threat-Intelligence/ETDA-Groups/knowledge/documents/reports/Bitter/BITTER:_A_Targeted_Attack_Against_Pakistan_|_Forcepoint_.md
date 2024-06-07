# Reference for threat actor for "Bitter"

**Title**: BITTER: A Targeted Attack Against Pakistan | Forcepoint 

**Source**: https://www.forcepoint.com/blog/x-labs/bitter-targeted-attack-against-pakistan

## Content



  





























































BITTER: A Targeted Attack Against Pakistan | Forcepoint 



















Skip to main content














  Forcepoint


 



PartnersPartnersPartner Login
Find a Partner
Become a Partner
Global Partner Program
Technology Partners
Find a Distributor

Services & SupportServices & SupportSupport Login
Professional Services
Training

CompanyCompanyCustomers
Newsroom
Work With Us
Events
Contact Us
Forcepoint Trust Hub

 




EN - EnglishES - Español (América Latina)FR - FrançaisDE - DeutschIT - ItalianoPT-BR - PortuguêsZH-HANS - 简体中文ZH-HANT - 繁體中文JA - 日本語KO - 한국어TR - TürkçeAR - العربية

















 







            Enter your keywords          








            Is Type          







 


 







 



Jump to



 Why Forcepoint
Why Forcepoint group
 
About Us
Our vision and mission
  
Our Approach
Our data-first approach to cybersecurity
  
Our Customers
We help people work freely, securely and with confidence
    Data-first SASE
Data-first SASE group (row1)
 group (FP ONE)
 
Forcepoint ONE SSE
Data-first SASE starts with Forcepoint ONE. Protect data everywhere, secure access anywhere, and simplify security on one platform.
Learn More
   group (products)
 group (products 1st row)
 Simplify Security with SSE
  
CASB
Secure data on any public cloud application.
  
ZTNA
Remotely access every private web app on any device.
  
SWG
Safely browse the web and download files.
  
DLP SaaS
Prevent data exfiltration from the cloud with DLP SaaS.
   group (products 2nd row)
 Work Safely Anywhere With SASE
  
FlexEdge Secure SD-WAN
Connect and protect branches, offices and more.
     group (row2)
 Schedule a Live Demo
  On-Demand Demo
    More Products and Solutions
More Products and Solutions group (popular products 1st row)
 Products
  group (Data Security)
 Data Security Solutions
  
Enterprise DLP
Industry-leading data security for web, cloud, email, network and endpoint.
   group (Products)
 
Data Visibility
Get a panoramic view of data at rest with AI and LLMs.
  
Insider Threat
Monitor, analyze and gain insight on user behavior.
  
Data Classification
Increase the accuracy and efficiency of classification.
  
Risk Adaptive
Respond to risk in real-time with policy automation.
    group (solutions 1st row)
 Solutions
  Securing Data Everywhere
  Embrace ChatGPT and Protect Your Data
  Adopt Continuous Zero Trust Security
  Safely Use MS 365
   group (popular products 2nd row)
 group (Network and Threat Protection)
 Network and Threat Protection
  
FlexEdge Secure SD-WAN
Secure the network. Connect and protect offices, branches and remote sites.
   products (2nd row)
 
Cross Domain Solutions
Improve security and access for segmented networks.
  
NGFW
Modernize connectivity with next-generation security.
  
Zero Trust CDR
Prevent files from launching known or zero-day attacks.
  
RBI
Render risky websites in a container to browse safely.
    group (solutions 2nd row)
 Solutions
  Protect Remote Offices
  Securely Enable Remote Workers
   group (products cta column 1)
 View All Products
   group (products cta column 2)
 View All Solutions
    Resources
Resources group (links column)
 group (resource links)
 Blog
  Webcasts
  Podcasts
  Analyst Reports
  Customer Stories
  Resource Library
  Events
  Training
     group (cyber edut)
 
Cyber Edu
Learn More
    group (cta column)
 group (cards)
 Guide
Ultimate Guide to Data Security
Dive into the Guide
  Video
ChatGPT for IT: Increase Productivity with Generative AI using Forcepoint Data Security
Watch the Video
  Analyst Report
2023 Gartner® Magic Quadrant™ for Single-Vendor SASE
Read the Report
  Podcast
The Radical Transparency Opportunity in Cybersecurity
Listen to the Podcast
   View All Resources
    Talk to an Expert
  



Main Menu






You are hereHome:Blogs:BITTER: a targeted attack against Pakistan 










			X-Labs		




    October 21, 2016  




BITTER: a targeted attack against Pakistan







APT Backdoor Cyber Attack Malware 















	Introduction

	Forcepoint Security Labs™ recently encountered a strain of attacks that appear to target Pakistani nationals. We named the attack "BITTER" based on the network communication header used by the latest variant of remote access tool (RAT) used:



	Our investigation indicates that the campaign has existed since at least November 2013 but has remained active until today. This post intends to share the results of our research.

	Infection Vector

	Spear-phishing emails are used to target prospective BITTER victims. The campaign predominantly used the older, relatively popular Microsoft Office exploit, CVE-2012-0158, in order to download and execute a RAT binary from a website. Below is an example of a spear-phishing email they used earlier this month. The recipient is an individual from a government branch in Pakistan, while the sender purports to be coming from another government branch of Pakistan:



	Other attachment filenames they used that also contained the CVE-2012-0158 exploit are as follows:


Requirement List.doc



Cyber Espionage Prevention.doc



New email guidelines.doc



Gazala-ke-haseen-nagme.doc



Rules.xls


	In one instance, they used a RAR SFX dropper that drops both their RAT and a picture of a Pakistani woman as a decoy. A quick Google image search on the dropped picture indicates that the picture was grabbed from Pakistani dating sites.

	RAT Component

	BITTER used RATs that are compiled using Microsoft Visual C++ 8.0. They use a few iterations of their RAT with the main difference being the RAT's command and control (C2) communication method. Earlier variants communicated to its C2 via an unencrypted HTTP POST. Below is an example of an older variant's phone home request:



	Newer ones, on the other hand, use encrypted TCP connection such as the one shown in the introduction above. Both older and newer variants are used simultaneously today in the campaign.

	The RAT version (SHA1 d7a770233848f42c5e1d5f4b88472f7cb12d5f3d) that they used in their latest campaign is capable of executing the following backdoor capabilities, essentially allowing the attackers to gain full remote control over a victim's PC:


		Get system information - computer name, current user name, and operating system



		Enumerate logical drives



		Enumerate and log files and their corresponding timestamps



		Open a remote command shell



		List processes with active UDP connections



		Manipulate running processes



		Manipulate files



		Download a file


	In addition, the vast majority of their RAT binaries contained the following digital signature with a non-trusted CA Root certificate:



	The following table shows the timeline of appearance of BITTER RATs, based on their compilation timestamps, along with their embedded PDB paths:



	It is important to note that some of these RATs are distributed at a later time than their compilation date.

	Command and Control

	BITTER used free dynamic DNS (DDNS) and dedicated server hosting services in order to set up their C2s. The download site where the exploit documents download the RAT binaries are, in most cases, different from the actual RAT C2. However, both of them are typically registered using a Gmail email address and a spoofed identity purporting to be either from United Kingdom or Great Britain. Below is an example of a spoofed registrant information for the C2, spiralbook71[.]com:



	A list of all related malicious domains we managed to collect are as follows:



	The email address witribehelp@gmail.com​ points to an empty Google Plus profile with the name "WhatsApp Support". Interestingly, however, the account is connected to another Google Plus account with the handle "Love Pakistan":  



	Intent

	While cyber-espionage is a common motivation for targeted attacks, this is often hard to conclude unless a forensic investigation is conducted on the actual victims' machines. In some cases, specific capabilities in RATs provides us with clues on what the attackers' true intents are.

	One of the backdoor capabilities mentioned above is the logging of files and files' time stamps from the victim's machine. Furthermore, an older variant of their RAT from 2014 that has the SHA1 3ab4ce4b3a44c96d6c454efcece774b33335dda2 are found to look for more specific file types. After identifying the logical drives from a victim PC, this RAT variant proceeds to enumerate files and check if they match any of the hard coded document and archive file extensions below:



	While it is hard to conclude based only on these artifacts, the nature of these targeted file types suggests that the attackers may be after sensitive documents.

	Other Tools Used

	In December 2015 one of the campaign's download sites hosted a binary at scholars90[.]website/putty. The downloaded file is a free SSH and Telnet client application called "PuTTY", which has been used in the past in other targeted attacks.

	In addition, the same RAT variant previously mentioned (SHA1 3ab4ce4b3a44c96d6c454efcece774b33335dda2) connects to the C2 info2t[.]com/m2s.php​. This has also served as a C2 for at least two AndroRAT variants in the past. The following diagram shows these relationships:



	AndroRAT is an open source remote administration tool for Android. Its GitHub repository lists the following capabilities:


		Get contacts (and all theirs informations)



		Get call logs



		Get all messages



		Location by GPS/Network



		Monitoring received messages in live



		Monitoring phone state in live (call received, call sent, call missed..)



		Take a picture from the camera



		Stream sound from microphone (or other sources..)



		Streaming video (for activity based client only)



		Do a toast



		Send a text message



		Give call



		Open an URL in the default browser



		Do vibrate the phone


	The AndroRAT variant with SHA1 7d47ae3114f08ecf7fb473b7f5571d70cf2556da disguises itself as the Islam Adhan Alarm - an Android app that alerts to prayer times of Islam, which is the state religion of Pakistan. The variant with SHA1 645a6e53116f1fd7ece91549172480c0c78df0f, on the other hand, disguises itself as Kashmir News app. Kashmir is the northernmost geographical region of South Asia and is a disputed territory between India and Pakistan.

	Protection Statement


		Stage 2 (Lure) - Spear-phishing e-mails associated with this attack are identified and blocked.



		Stage 5 (Dropper File) - Related RATs are prevented from being downloaded.



		Stage 6 (Call Home) - Communication between the RAT and command and control are blocked.


	Conclusion

	Many targeted attacks continue to be discovered today. It is interesting to see that while these attacks are not always sophisticated in nature, the same characteristic allows them to stay under the radar by blending in with common attacks in the wild. BITTER is able to achieve this by using available online services such as free DDNS, dedicated server hosting and Gmail to setup their C2s. Such setup is exhibited by today's common malware.

	It is worth noting that in all the artifacts collected in this research, none of the English words that were used had spelling errors, suggesting that the actors behind BITTER are proficient in the English language. Furthermore, as discussed above, all the artifacts we have seen are consistent with Pakistan being the target of this group. There may be other targets that have not been discovered yet or BITTER may be a branch of a larger campaign with broader targets, but only time will tell whether any of these are correct.

	Indicators of Compromise

	RAT (SHA1)

42cdfe465ed996c546c215a8e994a82fea7dc24c
3ab4ce4b3a44c96d6c454efcece774b33335dda2
1990fa48702c52688ce6da05b714a1b3e634db76
93e98e9c4cf7964ea4e7a559cdd2720afb26f7f7
c3a39dc22991fcf2455b8b6b479eda3009d6d0fd
37e59c1b32684cedb341584387ab75990749bde7
52485ae219d64daad6380abdc5f48678d2fbdb54
137a7dc1c33dc04e4f00714c074f35c520f7bb97
e57c88b302d39f4b1da33c6b781557fed5b8cece
0172526faf5d0c72122febd2fb96e2a01ef0eff8
e7e0ba30878de73597a51637f52e20dc94ae671d
fa8c800224786bab5a436b46acd2c223edda230e
c75b46b50b78e25e09485556acd2e9862dce3890
72fa5250069639b6ac4f3477b85f59a24c603723
f898794563fa2ae31218e0bb8670e08b246979c9
2b873878b4cfbe0aeab32aff8890b2e6ceed1804
d7a770233848f42c5e1d5f4b88472f7cb12d5f3d
ddf5bb366c810e4d524833dcd219599380c86e7a
23b28275887c7757fa1d024df3bd7484753bba37
6caae6853d88fc35cc150e1793fef5420ff311c6
1a2ec73fa90d800056516a8bdb0cc4da76f82ade
ff73d3c649703f11d095bb92c956fe52c1bf5589

	RAT Dropper (SHA1)

c0fcf4fcfd024467aed379b07166f2f7c86c3200
0116b053d8ed6d864f83351f306876c47ad1e227
4be6e7e7fb651c51181949cc1a2d20f61708371a
998d401edba7a9509546511981f8cd4bff5bc098
21ef1f7df01a568014a92c1f8b41c33d7b62cb40
c77b8de689caee312a29d30094be72b18eca778d

	AndroRAT (SHA1)

7d47ae3114f08ecf7fb473b7f5571d70cf2556da
645a6e53116f1fd7ece91549172480c0c78df0f

	RAT download sites

kart90.website/sysdll 
range7.com/svcf.exe
scholars90.website/ifxc
scholars90.website/ifxc
scholars90.website/cnhost.exe
kart90.website/cnhost
frontier89.website/wmiserve
reloadguide71.com/winter/iofs
creed90.com/ismr
wester.website/uwe
chinatel90.com/min
wester.website/nqw
scholars90.website/splsrv

	RAT C2s

ranadey.net78.net/Muzic/exist.php
info2t.com
range7.com/m2s_reply_u2.php
www.queryz4u.com
www.sportszone71.com/games/hill.php
micronet.no-ip.co.uk
www.inspire71.com/warzone/hill.php
spiralbook71.com/warzone/hill.php
govsite.ddns.net
randomvalue90.com/warzone/hill.php
marvel89.com/ahead.php
cloudupdates.servehttp.com
pickup.ddns.net
marvel89.com/msuds.php
updateservice.redirectme.net
pickup.ddns.net
destiny91.com/truen/adfsdsqw.php
medzone71.com/medal/adfsdsqw.php
nexster91.com/winter/war.php
















      About Forcepoint  



    Forcepoint is the leading user and data protection cybersecurity company, entrusted to safeguard organizations while driving digital transformation and growth. Our solutions adapt in real-time to how people interact with data, providing secure access while enabling employees to create value.  

Learn more about Forcepoint 














    Email Security,Awareness








Share
LinkedIn
Twitter
Facebook

 









Forcepoint | X-Labs







 

Sign up for the latest from our research and development team









To the Point Cybersecurity
A podcast covering latest trends and topics in the world of cybersecurity
Listen now







More articles in X-LabsPrevious



			X-Labs		




              Carbanak Group uses Google for malware command-and-control            
 




          Jan 17 2017        



Next



			X-Labs		




              Compromised Microsoft OneDrive for Business accounts used to spread malware            
 




          Nov 22 2016        



 

















Insights



 





    Network DLP vs. Endpoint DLP (and Why Both Are Critical)  


  
 





 

X-Labs
Get insight, analysis & news straight to your inbox











CompanyNewsroom
Work With Us
Executive Team
Blog
Events
Free E-Learning Courses

FeedbackAll Products
All Solutions
Government
Customer Stories
Report a Vulnerability
Contact Us

 



Terms & ConditionsLegal and PrivacyManage Cookies
© 2024 Forcepoint 



LinkedIn
Twitter
Facebook
YouTube
RSS
 



















































