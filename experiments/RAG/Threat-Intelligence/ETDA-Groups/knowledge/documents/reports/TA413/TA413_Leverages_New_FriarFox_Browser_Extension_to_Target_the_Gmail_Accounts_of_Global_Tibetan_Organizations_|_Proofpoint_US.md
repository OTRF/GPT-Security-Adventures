# Reference for threat actor for "TA413"

**Title**: TA413 Leverages New FriarFox Browser Extension to Target the Gmail Accounts of Global Tibetan Organizations | Proofpoint US

**Source**: https://www.proofpoint.com/us/blog/threat-insight/ta413-leverages-new-friarfox-browser-extension-target-gmail-accounts-global

## Content

































































TA413 Leverages New FriarFox Browser Extension to Target the Gmail Accounts of Global Tibetan Organizations | Proofpoint US









      Skip to main content
    







Products
Solutions
Partners
Resources
Company











English (Americas)
English (Europe, Middle East, Africa)
English (Asia-Pacific)
Español
Deutsch
Français
Italiano
Português
日本語
한국어



Login

Support Log-in
Digital Risk Portal
Email Fraud Defense
ET Intelligence
Proofpoint Essentials
Sendmail Support Log-in


Contact






Aegis Threat Protection PlatformDisarm BEC, phishing, ransomware, supply chain threats and more.
Sigma Information Protection PlatformDefend your data from careless, compromised and malicious users.
Identity Threat Defense PlatformPrevent identity risks, detect lateral movement and remediate identity threats in real time.
Intelligent Compliance PlatformReduce risk, control costs and improve data visibility to ensure compliance.
Premium ServicesLeverage proactive expertise, operational continuity and deeper insights from our skilled experts.





Email Security and Protection
Email Protection
Email Fraud Defense
Secure Email Relay
Threat Response Auto-Pull
Sendmail Open Source
Essentials for Small Business

Advanced Threat Protection
Targeted Attack Protection in Email
Threat Response
Emerging Threats Intelligence

Security Awareness Training
Assess
Change Behavior
Evaluate


Information Protection
Enterprise Data Loss Prevention (DLP)
Insider Threat Management
Intelligent Classification and Protection
Endpoint Data Loss Prevention (DLP)
Email Data Loss Prevention (DLP)
Email Encryption
Data Discover

Cloud Security
Isolation
Cloud App Security Broker
Web Security


Identity Threat Detection and Response
Spotlight
Shadow


Compliance and Archiving
Automate
Capture
Patrol
Track
Archive
Discover
Supervision


Premium Services
Managed Email Threat Protection
Managed Information Protection
Managed Security Awareness
Managed Abuse Mailbox
Recurring Consultative Services
Technical Account Managers
Threat Intelligence Services
People-Centric Security Program






  New threat protection solution bundles with flexible deployment options 
  AI-powered protection against BEC, ransomware, phishing, supplier risk and more with inline+API or MX-based deployment
Learn More






Solutions by Topic


Combat Email and Cloud ThreatsProtect your people from email and cloud threats with an intelligent and holistic approach.
Change User BehaviorHelp your employees identify, resist and report attacks before the damage is done.
Combat Data Loss and Insider RiskPrevent data loss via negligent, compromised and malicious insiders by correlating content, behavior and threats.
Modernize Compliance and ArchivingManage risk and data retention needs with a modern compliance and archiving solution.
Protect Cloud AppsKeep your people and their cloud apps secure by eliminating threats, avoiding data loss and mitigating compliance risk.


Prevent Loss from RansomwareLearn about this growing threat and stop attacks by securing today’s top ransomware vector: email.
Secure Microsoft 365Implement the very best security and compliance solution for your Microsoft 365 collaboration suite.
Defend Your Remote Workforce with Cloud EdgeSecure access to corporate resources and ensure business continuity for your remote workers.
Authenticate Your EmailProtect your email deliverability with DMARC.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.




Solutions by Industry

Federal Government
State and Local Government
Higher Education
Financial Services
Healthcare
Mobile Operators
Internet Service Providers
Small and Medium Businesses






Partner Programs


Channel PartnersBecome a channel partner. Deliver Proofpoint solutions to your customers and grow your business.
Archive Extraction PartnersLearn about Proofpoint Extraction Partners.
Global System Integrator (GSI) and Managed Service Provider (MSP) PartnersLearn about our global consulting and services partners that deliver fully managed and integrated solutions.


Technology and Alliance PartnersLearn about our relationships with industry-leading firms to help protect your people, data and brand.
Social Media Protection PartnersLearn about the technology and alliance partners in our Social Media Protection Partner program.
Proofpoint Essentials Partner ProgramsSmall Business Solutions for channel partners and MSPs.




Partner Tools

Become a Channel Partner
Channel Partner Portal








Resource LibraryFind the information you're looking for in our library of videos, data sheets, white papers and more.
BlogKeep up with the latest news and happenings in the ever‑evolving cybersecurity landscape.
PodcastsLearn about the human side of cybersecurity. Episodes feature insights from experts and executives.
New Perimeters MagazineGet the latest cybersecurity insights in your hands – featuring valuable knowledge from our own industry experts.


Threat GlossaryLearn about the latest security threats and how to protect your people, data, and brand.
EventsConnect with us at events to learn how to protect your people and data from ever‑evolving threats.
Customer StoriesRead how Proofpoint customers around the globe solve their most pressing cybersecurity challenges.
WebinarsBrowse our webinar library to learn about the latest threats, trends and issues in cybersecurity.




Security Hubs

Get free research and resources to help you protect against threats, build a security culture, and stop ransomware in its tracks.

Threat Hub
CISO Hub
Cybersecurity Awareness Hub
Ransomware Hub
Insider Threat Management Hub









About ProofpointProofpoint is a leading cybersecurity company that protects organizations' greatest assets and biggest risks: their people.
Why ProofpointToday’s cyber attacks target people. Learn about our unique people-centric approach to protection.
CareersStand out and make a difference at one of the world's leading cybersecurity companies.


News CenterRead the latest press releases, news stories and media highlights about Proofpoint.
Privacy and TrustLearn about how we handle data and make commitments to privacy and other regulations.
Environmental, Social, and GovernanceLearn about our people-centric principles and how we implement them to positively impact our global community.




Support

Access the full range of Proofpoint support services.
Learn More











 




BlogThreat Insight
                                    TA413 Leverages New FriarFox Browser Extension to Target the Gmail Accounts of Global Tibetan Organizations 
                              

 












TA413 Leverages New FriarFox Browser Extension to Target the Gmail Accounts of Global Tibetan Organizations 





Share with your network!








 February 25, 2021


                Michael Raggi and the Proofpoint Threat Research Team 
  
        

 Since March 2020, Proofpoint Threat Research has tracked low volume phishing campaigns targeting Tibetan organizations globally. In January and February 2021, we observed a continuation of these campaigns where threat actors aligned with the Chinese Communist Party’s state interests delivered a customized malicious Mozilla Firefox browser extension that facilitated access and control of users’ Gmail accounts. Proofpoint has named this malicious browser extension “FriarFox”. We attribute this activity to TA413, who in addition to the FriarFox browser extension, was also observed delivering both Scanbox and Sepulcher malware to Tibetan organizations in early 2021. Proofpoint has previously reported on Sepulcher malware and its links to the Lucky Cat and Exile Rat malware campaigns that targeted Tibetan organizations. This actor is believed to be an APT group aligned with the Chinese state with strategic objectives associated with espionage and civil dissident surveillance that includes the Tibetan Diaspora. This blog provides a detailed analysis of the JavaScript-based FriarFox browser extension, identifies TA413’s use of the Scanbox framework dating back to June 2020, and establishes links to watering hole attacks that targeted Tibetan organizations in 2019. 

Delivery and Exploitation  
In late January 2021 a phishing email was detected which targeted several Tibetan organizations. The email impersonated the “Tibetan Women's Association” in the From field and utilized the email subject “Inside Tibet and from the Tibetan exile community”. Further the email was delivered from a known TA413 Gmail account that has been in use for several years, which impersonates the Bureau of His Holiness the Dalai Lama in India. The email contained the following malicious URL that impersonated YouTube:  

hxxps://you-tube[.]tv/  

This URL once clicked led to a fake “Adobe Flash Player Update” themed landing page which executes several JavaScript (“JS”) files which profile the user’s system. These scripts determine whether to deliver the malicious FireFox Browser extension (“.XPI” file) that Proofpoint has named “FriarFox”. XPI files are compressed installation archives used by various Mozilla applications and contain the contents of a FireFox browser extension. The use of landing pages for JS redirection is a technique commonly used in watering hole attacks. In this case, the domain is controlled by the threat actors, and the redirection is obtained via a malicious URL contained within a phishing email.  
 The installation and delivery of the FriarFox browser extension depends on several conditions of the user’s browsing state. Threat actors appear to be targeting users that are utilizing a Firefox Browser and are utilizing Gmail in that browser. The user must access the URL from a FireFox browser to receive the browser extension. Additionally, it appeared that the user must be actively logged in to a Gmail account with that browser to successfully install the malicious XPI file. Not all detected FriarFox campaigns required an active Gmail session for the successful installation of the browser extension. Additionally, Proofpoint analysts could not isolate the functionality that requires an active Gmail login session. Therefore, analysts could not definitively determine if a Gmail login was an intended pre-condition of TA413 browser extension installation or if the resulting corrupt file installation error was attributable to another cause. The following three user states were tested during Proofpoint’s research of the FriarFox extension. They account for use of varying browsers and Gmail login states tested when accessing the domain, you-tube[.]tv.  

User accesses the you-tube[.]tv URL with a non-FireFox browser and no Gmail Session  

The user is temporarily displayed the Adobe Flash Player landing page at you-tube[.]tv before being redirected to a legitimate youtube[.]com login page that attempts to access an active domain cookie in use on the site. Actors may be attempting to leverage this domain cookie to access the user’s Gmail account in the instance that a GSuite federated login session is used to log in to the user’s YouTube account. This user is not served the FriarFox browser extension.   
 Figure 01: YouTube redirect attempting to access domain cookie 

User Accesses the you-tube[.]tv URL with a FireFox browser, but is not logged in to Gmail  

The user is displayed the Adobe Flash Player landing page and prompted to allow the installation of software from the site. If the user clicks “Allow”, the browser indicates that the “add-on downloaded from you-tube[.]tv could not be installed because it appears to be corrupt.” The browser extension is served to the user but is not successfully installed. No redirect occurs. 

URL Request for FriarFox Browser Extension  

hxxps://you-tube[.]tv/download.php  
 Figure 02: You-tube[.]tv landing page unsuccessful installation of FriarFox browser extension.  

User Accesses the you-tube[.]tv URL with a FireFox browser and is logged in to Gmail  

The user is served the FriarFox extension from hxxps://you-tube[.]tv/download.php. They are then prompted to allow the download of software from the site, and they are prompted to “Add” the browser extension named “Flash update components” by approving the extension’s permissions. If the user clicks “Add” the browser redirects to the benign webpage hxxps://Tibet[.]net and the message “Flash update components has been added to Firefox.” Will appear in the upper right corner of the browser.   
 Figure 03: Mozilla Firefox prompt to add malicious FriarFox browser extension. 
 Figure 04: Browser redirect to Tibet[.]net and installation confirmation for FriarFox browser extension.  
After the installation of the FriarFox browser extension, threat actors gain the following access to the user’s Gmail account and FireFox browser data included below. Additionally, FriarFox contacts a threat actor command and control server to retrieve the PHP and JS-based payload Scanbox. Here are the Gmail account functionality and FireFox browser attributes FriarFox attempts to collect:  
Gmail Access  
Search emails  
Archive emails  
Receive Gmail notifications  
Read emails  
Alter FireFox browser audio and visual alert features for the FriarFox extension  
Label emails  
Marks emails as spam  
Delete messages  
Refresh inbox  
Forward emails  
Perform function searches  
Delete messages from Gmail trash  
Send mail from compromised account  
FireFox Browser Access – (Based on Granted browser permissions)  
Access user data for all websites.  
Display notifications  
Read and modify privacy settings  
Access browser tabs.
   
Figure 05: FriarFox browser extension required permissions. 
Analysis of the FriarFox Browser Extension 
The FriarFox browser extension appears to be largely based on an open source tool named “Gmail Notifier (restartless)”. This is a free tool available on Github, the Mozilla Firefox Browser ADD-ONS store, and the QQ App store among other locations. It allows users to receive notifications and perform certain Gmail actions on up to five Gmail accounts that are actively logged in simultaneously. There are also versions of this tool that exist for Google Chrome and Opera, but currently FriarFox has been the only browser instance identified targeting FireFox browsers as an XPI file. In recent campaigns identified in February 2021, browser extension delivery domains have prompted users to “Switch to the Firefox Browser” when accessing malicious domains using the Google Chrome Browser. Further details on the tool’s capabilities can be found below: 
 
Figure 06: Open Source Gmail Notifier (restartless) tool in Firefox Browser ADD-ONS 
https://addons.mozilla.org/en-US/firefox/addon/gmail-notifier-restartless/ 
(Gmail Notifier Demo Video) https://www.youtube.com/watch?v=5Z2huN_GNkA 
TA413 threat actors altered several sections of the open source browser extension Gmail Notifier to enhance its malicious functionality, conceal browser alerts to victims, and disguise the extension as an Adobe Flash related tool. The threat actors conceal FriarFox’s existence and their usage of the tool by altering the following:  
The PNG file icon appears as an Adobe Flash icon in the browser extension menu, replacing the Gmail icon from the standard Gmail Notifier tool.    
The extension metadata description supports its appearance as a Flash update providing the description displayed in the browser extension menu.    
All audio and visual browser alerts are set not to alert active users after the time of installation. This conceals FriarFox’s existence and threat actors’ usage from the affected victims.   
The legitimate Gmail Notifier browser extension consists of approximately 17 independent JS files and additional configuration files that enable functionality for viewing emails, archiving, marking emails as spam, labelling, deleting, and visiting a user’s inbox for up to five accounts at a time. The FriarFox Browser Extension keeps the core functionality of this tool continuing to leverage many of these scripts in their original form, but also expands the functionality by adding three malicious JavaScripts and expanding the maximum number of accounts that can be monitored.  
 
Figure 07: FriarFox (modified Gmail Notifier) browser extension XPI directory with actor modifications 
TA413 actors added the malicious JS file “tabletView.js” to the existing Gmail Notifier tool. The goal of TA413 in adding this file is likely to leverage an active domain cookie value to gain access to an affiliated Gmail account while also causing infected users to contact an active Scanbox command-and-control server. This malicious file is responsible for redirecting users to the YouTube account login page. This redirect may be an attempt by the threat actors to retrieve the domain cookie from an active YouTube login session that was achieved via a federated G-Suite login. The following URLs were generated by the script in tabletView.js:   

hxxp://accounts.youtube[.]comhttps://accounts.youtube[.]com/_/AccountsDomainCookiesCheckConnectionHttp/jserror?script=hxxps%3A%2F%2Findiatrustdalailama[.]com%2Ffile%2Fi%2F%3F5&error=Permission%20denied%20to%20get%20property%20%22href%22%20on%20cross-origin%20object&line=61  

As part of this redirect script, an additional URL is visible. It contains the command-and-control domain information for the actor-controlled server indiatrustdalailama[.]com which delivers an encoded JavaScript payload Scanbox. Further analysis of the tabletView.js script indicates that this file is an altered version of a browser extension file created with the copyright belonging to “Jason Savard”. Open source research indicates that this individual has created several browser extensions and plug-ins including a tool called Checker Plus for Gmail. This tool contains similar functionality to the Gmail Notifier tool discussed above. The presence of this unrelated copyright in the FriarFox browser extension files may indicate that actors have historically experimented with similar tools before modifying the Gmail Notifier tool set.  
In addition to the redirection JavaScript that attempts to access cookies and communicate with Scanbox servers, threat actors altered an existing Gmail Notifier browser extension script to display the decoy domain hxxps://tibet[.]net in the browser upon initial FriarFox installation. This redirection was described earlier in the delivery section of this blog. The use of the legitimate Tibet[.]net as a decoy domain further reinforces that the targets of this campaign were narrow and likely selected based on their involvement with Tibetan organizations and the Tibetan exile community.   
 Lastly, actors also included an additional script entitled default.js that appears to add supplemental malicious capabilities to the FriarFox extension that were not included in the initial open source Gmail Notifier tool. While the initial tool includes the ability to check settings, access inbox, archive, mark as spam, delete messages, refresh inbox and mark as read, it does not include features related to sending or responding to mail. The default.js script adds features like forwarding mail, performing function searches, deleting mail, deleting Gmail trash, and sending mail from the compromised account. 
 Figure 08: Default.js script detail “SendMail” Function 
 
Figure 09: Default.js script detail “FWmailandDelete” Function 
 
Figure 10: Default.js script detail “DeleteMail” Function 
Analysis of ScanBox Malware 
After the FriarFox browser extension is installed, the JS file TabletView tabletView.js contacts an actor-controlled server to retrieve the Scanbox framework. Scanbox is a PHP and JavaScript-based reconnaissance framework that dates to 2014. Its usage of PHP and JS enables a file-less malware approach when targeting victims’ hosts. Scanbox is primarily used by Chinese APT’s and shared across multiple groups. To a lesser degree, Scanbox has been reportedly used by OceanLotus, an APT actor who supports the national interests of Vietnam but has no relevance to this analysis. Scanbox has been used in numerous campaigns since 2014 to target the Tibetan Diaspora along with other ethnic minorities often targeted by groups aligned with the Chinese state interests. The tool is capable of tracking visitors to specific websites, performing keylogging, and collecting user data that can be leveraged in future intrusion attempts. 
In this campaign TabletView.js initiates a request to the actor-controlled domain indiatrustdalailama[.]com via port 443: 

hxxps://indiatrustdalailama[.]com:443/file/i?5 

The request specified in the URI path a project id (“/file/i?5”) which corresponds to the specific Scanbox project code. As a result of this request encoded Scanbox JavaScript containing the Scanbox payload is returned in an HTTP response. Following the execution of the Scanbox JavaScript, the below “basicposturl” response can be observed which represents victim information being posted to threat actor’s command and control server. This URL was first reported publicly in June of 2020 on VirusTotal by a user in India which suggests that this actor likely has been leveraging Scanbox against Tibetan related entities in the region since at least mid-2020: 

hxxps://indiatrustdalailama[.]com/file/i/recv.php 

In addition to the “basicposturl”, traffic was observed which was identified as the Scanbox “basicliveurl” or the framework’s heartbeat indicating a live infection and connection with the actor command-and-control server. The Scanbox heartbeat URI “/file/i/s.php?” is followed by numerical Base64 encoded seed and “alivetime” values that are included in the URI. A simulated example of this has been included below:  

 hxxps://indiatrustdalailama[.]com/file/i/s.php?seed=NlAxMFZ3NET3NjIxMCc2OEA=&alivetime=MTYxNUd2NjF1MQ==&r=0.6520957992508899 

A partially decoded portion of the delivered Scanbox JavaScript has been included below. The standard Scanbox configuration values first observed in a 2014 watering hole attack are available in open source and have been included on the right of Figure 11 for comparison. Note that the “basicpluginurl” and “basicposturlkeylogs” keys visible in the configuration were not observed during Proofpoint analysis. 
 Figure 11: Decoded Scanbox configuration comparison to standard Scanbox instance 
The Scanbox code which is JavaScript delivered as part of an HTTP response is heavily encoded in its initial state. De-obfuscation of the JavaScript has proven to be a time intensive endeavor requiring an iterative process. The actors rely on three primary layers of obfuscation for the JavaScript:   
 Firstly, the threat actors have converted the integer values of the Scanbox code to Base36 which designates these values as strings using symbols “0-9” and “A-Z”. By reverting the integer values from their Base36 form we were able to de-obfuscate the decoding function present in the Scanbox JavaScript which details the second layer of obfuscation it uses. The decoding function indicates that actors took an array of integers and generated ASCII character codes from each of them by subtracting charset value 398 and then concatenating the resulting characters together. By performing the equivalent of the decoding function on the integer array values analysts were able to de-obfuscate them. So finally, because of this de-obfuscation we were able to replace references to the array integer values with the corresponding decoded strings. Many of which were function values. This revealed a mostly decoded Scanbox code base.  
 In addition to these methods Proofpoint analysts were able to draw parallels between the encoded JavaScript and open source examples of Scanbox code. This combination of separate efforts allowed for partial decoding of the Scanbox JavaScript. 
Figure 12: Encoded Scanbox JavaScript with sections mapped to open source Scanbox code 
 Figure 13: Scanbox decoding function with strings reverted from Base36 
 
Figure 14: Decoded Scanbox Integer Array 
The encoding used in this Scanbox code appears to be consistent with a historic instance of Scanbox used to target Pakistani and Tibetan government websites in March 2019. This campaign reported by Recorded Future detailed watering hole attacks that delivered Scanbox after redirecting users from the domain tibct[.]net. That domain replicated the legitimate content present on Tibet[.]net to entice victims who would be redirected to a Scanbox delivery domain. The FriarFox campaign also leveraged Tibet[.]net as a decoy redirection prior to delivering Scanbox via the malicious browser extension. While the victimology, use of the Scanbox tool, and encoding are shared between these campaigns it is important to note again that Scanbox is a shared tool in use since 2014. Proofpoint cannot definitively attribute the 2019 campaign reported by Recorded Future to TA413 at this time, but analysts note similar tactics have been used against the Tibetan Diaspora in the recent past. 
Links to Previous TA413 Campaigns 
In addition to the observation of a known sender email address that has been used by TA413 in the Exile Rat campaign dating back several years, an examination of the FriarFox manifest.json file contained within the XPI archive indicated further ties to known TA413 activity. The manifest.json file included an update URL for the FriarFox browser extension. The URL address hxxps://nagnsihistory[.]vip/update.json was included. The domain nangsihistory[.]vip had previously been observed by Proofpoint in TA413 phishing campaigns targeting Tibetan organizations on January 12, 2021 and January 15, 2021. The emails used the domain in the following URLs which delivered malicious RTF files that ultimately installed Sepulcher malware.  
hxxp://www.nangsihistory[.]vip/doc/Protect%20yourself%20and%20others%20from%20COVID-19(Masks).doc 
hxxp://www.nangsihistory[.]vip/doc/Self%20Immolations%20inside%20Tibet.doc 
  
Figure 15: FriarFox Manifest.json update URL 
The malicious RTF files utilized COVID-19 and self-immolation themed social engineering lures while also containing malicious embedded objects that installed subsequent stage malware. The files appeared to be built by the well-known shared Chinese APT tool referred to as “Royal Road” in open source publications. Specifically, the embedded objects within the Royal Road RTF’s in this campaign once extracted were found to be the Microsoft Word Add-In file “winor.wll”. This file name has previously been observed as the embedded object file within Royal Road RTF attachments that are then executed by being saved to the Microsoft Word startup directory. Notably in March 2020 TA413 was observed using Royal Road RTF attachments to deliver Sepulcher malware.  
 Figure 16: COVID-19 Themed TA413 Malicious RTF File 
 Figure 17: Self Immolation Themed TA413 Malicious RTF File 
Conclusion 
The introduction of the FriarFox browser extension in TA413’s arsenal further diversifies a varied, albeit technically limited repertoire of tooling. The use of browser extensions to target the private Gmail accounts of users combined with the delivery of Scanbox malware demonstrates the malleability of TA413 when targeting dissident communities. These communities have a traditionally low barrier for compromise by threat actor groups and TA413 appears to be modulating their tools and techniques while continuing to rely on proven social engineering techniques. Their degrees of success may vary among more sophisticated targets, however, the limited resources afforded to dissident organizations globally may allow for success with the patchwork of tooling and techniques TA413 displays. While not conventionally sophisticated when compared to other active APT groups, TA413 combines modified open source tools, dated shared reconnaissance frameworks, a variety of delivery vectors, and very targeted social engineering tactics. The result is that this group finds mileage from previously disclosed tools like Scanbox and Royal Road by varying the method of their introduction to the victim environment. Apart from the custom toolsets observed in Exile Rat, Sepulcher, and other now dated implants, TA413 appears to be pivoting to modified open source tooling to compromise the global dissident organizations they have been tasked with surveilling. Unlike many APT groups, the public disclosure of campaigns, tools, and infrastructure has not led to significant TA413 operational changes. Accordingly, we anticipate continued use of a similar modus operandi targeting members of the Tibetan Diaspora in the future.   
 
Indicators of Compromise 

IOC 


IOC Type 


Description 


hxxps://you-tube[.]tv 


URL 


Fake Flash Update Landing Page  


hxxps://you-tube[.]tv/download.php 


URL 


Browser Extension Delivery URL  
(Serves Malicious FriarFox Browser Extension) 


hxxps://vaccine-icmr[.]org/ 


URL 


Impersonation of Indian Council of Medical Research COVID-19 Vaccine Portal.  
(Serves Malicious FriarFox Browser Extension) 


hxxps://vaccine-icmr[.]net/ 


URL 


Impersonation of Indian Council of Medical Research COVID-19 Vaccine Portal. 


hxxp://accounts.youtube[.]comhxxps://accounts.youtube[.]com/_/AccountsDomainCookiesCheckConnectionHttp/jserror?script=hxxps%3A%2F%2Findiatrustdalailama[.]com%2Ffile%2Fi%2F%3F5&error=Permission%20denied%20to%20get%20property%20%22href%22%20on%20cross-origin%20object&line=61 


URL 


Redirect to Youtube[.]com and Scanbox C2 Check-In (Performed by TabletView.js) 
 


hxxps://indiatrustdalailama[.]com:443/file/i?5 


URL 


Scanbox Beacon 


hxxps://indiatrustdalailama[.]com/file/i/recv.php 


URL 


Scanbox “basicposturl” 


hxxps://indiatrustdalailama[.]com/file/i/s.php?seed=<value>=&alivetime=<vaue>==&r=<value> 


URL 


Scanbox “basicaliveurl” 


hxxp://www.nangsihistory[.]vip/doc/Protect%20yourself%20and%20others%20from%20COVID-19(Masks).doc 


URL 


URL delivers RTF that installs Sepulcher malware 


hxxp://www.nangsihistory[.]vip/doc/Self%20Immolations%20inside%20Tibet.doc 


URL 


URL delivers RTF that installs Sepulcher malware 


hxxps://167.179.99[.]136/Fw9f 


URL 


Sepulcher Malware C2 Communication 


you-tube[.]tv 


Domain 


Delivers FriarFox Browser Extension 


vaccine-icmr[.]org 


Domain 


Delivers Malicious Browser Extension 


vaccine-icmr[.]net 


Domain 


Malicious Domain Related by Hosting IP 


indiatrustdalailama[.]com 


Domain 


Scanbox C2 Domain 


www.nangsihistory[.]vip 


Domain 


Delivers Sepulcher Malware RTF’s 


115.126.6[.]47 


IP 


Domain Hosting IP 


118.99.9[.]47 


IP 


Domain Hosting IP 


167.179.99[.]136 


IP 


Sepulcher Command and Control IP 


d4bca797b5d40618dcf72ff471b325860bd1830cbd74012e9d643512f93c5778 


SHA256 


1.0.3.xpi 
FriarFox Browser Extension XPI File 


b918318506cffe468bbe8bf57aacbe035fe1242dafc14696682c42656ffb2582 


SHA256 


Protect yourself and others from COVID-19(Masks).rtf - Malicious Royal Road RTF 


5adce130e28cfac30253f0532ffff0f80280af2f236234825a5954267e2fdc06 


SHA256 


Self Immolations inside Tibet[1].rtf 
Malicious Royal Road RTF 


555ec25f872108af2daab488d8ec62c4e6a8c43c43a92cb572b0d2a7dc891bd1  


SHA256 


Protect_yourself_and_others_from_COVID-19(Masks)[1].doc - Decoy Doc 


e1501a0297a3d7fc326d3923fdc8f9156ed954602ba34e6b435158d39956dce4 


SHA256 


~$lf_Immolations_inside_Tibet[1].doc 
Decoy Doc 


91d19b7b44d4e286a40bd28e269e4d172b642ea792c018551bcc5ca8efceb54c 


SHA256 


Encoded Shellcode Loader of Sepulcher Malware 


0469df3f6a8d3e05927f0739e8af9c84e995e3813ad78e18c78a333cf086ef08  


SHA256 


winor.wll - Decoded Shellcode Loader of Sepulcher Malware 


00099b0c4b664ed872ad4db5d28f2a0a1875a86c756f497562be825a7074757d 


SHA256 


credential.dll – Sepulcher Malware 

 
ET Signatures  
2019094 ET EXPLOIT_KIT ScanBox Framework used in WateringHole Attacks Initial (POST) 
2019096 ET CURRENT_EVENTS ScanBox Framework used in WateringHole Attacks KeepAlive
SID: 2021542 ET EXPLOIT_KIT ScanBox Jun 06 2015 M1 T1
SID: 2021543 ET EXPLOIT_KIT ScanBox Jun 06 2015 M2 T1
SID: 2021544 ET EXPLOIT_KIT ScanBox Jun 06 2015 M3 T1
 
 
 






Previous Blog Post


Next Blog Post







Subscribe to the Proofpoint Blog

























About


Overview
Why Proofpoint
Careers
Leadership Team
News Center
Nexus Platform
Privacy and Trust




Threat Center


Threat Hub
Cybersecurity Awareness Hub
Ransomware Hub
Threat Glossary
Threat Blog








Products


Email Security & Protection
Advanced Threat Protection
Security Awareness Training
Cloud Security
Archive & Compliance
Information Protection
Product Bundles




Resources


White Papers
Webinars
Data Sheets
Events
Customer Stories
Blog
Free Trial








Connect


+1-408-517-4710
Contact Us
Office Locations
Request a Demo




Support


Support Login
Support Services
IP Address Blocked?
















Facebook
Twitter
linkedin
Youtube





English (US)
English (UK)
English (AU)
Español
Deutsch
Français
Italiano
Português
日本語
한국어





© 2024. All rights reserved.
            Terms and conditions
Privacy Policy
Sitemap

 







 

















