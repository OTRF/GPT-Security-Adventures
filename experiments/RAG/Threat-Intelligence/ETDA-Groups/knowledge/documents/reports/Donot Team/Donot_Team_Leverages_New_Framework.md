# Reference for threat actor for "Donot Team"

**Title**: Donot Team Leverages New Framework

**Source**: https://www.netscout.com/blog/asert/donot-team-leverages-new-modular-malware-framework-south-asia

## Content




































Donot Team Leverages New Framework






















      Skip to main content
    

























Under Attack? Call 1-734-794-5099


Contact Us


Careers


Investors 


Blog








Search






















Enterprise Solutions





Cloud Application Performance & Security
 






nGenius Enterprise Performance Management






Cloud Performance Monitoring






Digital Transformation






Software Defined Network






SaaS









Performance Management
 






Application Performance Management






UC&C and UCaaS






Network Performance Management






VPN/VDI






NETSCOUT Visibility as a Service









Cybersecurity & DDoS Protection
 






Network Detection and Response






NetOps and SecOps Collaboration






Adaptive DDoS Protection






Cybersecurity Stack Optimization






DNS Infrastructure Protection









5G Transformation
 






5G for Enterprise






Private 4G/5G









Technology Partners
 






Dell Technologies






VMware






AWS






ServiceNow






Splunk






Palo Alto Networks






Microsoft






Google Cloud






Oracle






F5






Cisco Systems






Red Hat






Citrix












Communication Service Provider Solutions





Cybersecurity & DDoS Protection
 






Arbor DDoS Protection






DNS Infrastructure Protection






Mobile Network Security









5G Ready Now
 







Cloud and Digital Transformation
 






Cloud Visibility






Network Function Virtualization/Cloud









LTE/VoLTE/VoWi-Fi
 







OTT Visibility
 







Analytics
 






Automated Analytics






Business Analytics









Radio Access Networking (RAN)
 






RAN Optimization & Automation






RAN Monitoring and Troubleshooting






GeoMarketing









Cable/MSO and Fixed Networks
 






Cable/MSO and Fixed Networks






Fiber (FTTx) and DAA Monitoring









Internet of Things (IoT)
 










Products





Enterprise
 






nGeniusONE for Enterprise






InfiniStreamNG






nGeniusPULSE






nGeniusEDGE Server






Edge Adaptor






nGenius Business Analytics






nPoint






vSTREAM






PFS Packet Broker









Network Security
 






Omnis Cyber Intelligence NDR






Omnis CyberStream






nGenius Decryption Appliance






PFS Packet Broker









Arbor DDoS Protection
 






Arbor Sightline






Arbor Sightline with Insight






Arbor Sightline with Sentinel






Arbor Sightline Mobile






MobileStream






Arbor Threat Mitigation System






Arbor Edge Defense & Arbor Enterprise Manager






Arbor Global DDoS Threat Intelligence






Arbor Cloud






Arbor Managed Services









Communication Service Provider
 






TrueCall






nGenius Session Analyzer






nGeniusONE for Carrier






nGenius Business Analytics






ISNG-RAN






InfiniStreamNG






vSTREAM






SpectraSecure DDoS Resilience Testing






Spectra2 Communications Testing












Industries





Education
 







Financial Services
 






Capital Markets






Retail Banking









Government
 






Department of Defense






Federal Civilian Agencies






State and Local Governments









Healthcare
 







Insurance
 







Manufacturing
 







Pharmaceutical
 







Retail
 







Telecommunications
 






Cable MSO’s/Fixed Line Operators






Cloud Communications Providers






Internet Service Providers






Mobile Network Operators






Service Provider IT









Transportation
 







Utilities
 










Resources & Education





Resource Library
 







Learning Center
 







NETSCOUT University
 







Blog
 







Events
 







Webinars
 







Problem Solvers Series
 







ASERT Threat Intelligence Team
 







DDoS Threat Intelligence Report
 







Omnis Threat Horizon
 










Support & Services





Overview
 







My.NETSCOUT
 







NO LATENCY
 










Company





Executive Team
 







Board of Directors
 







Careers
 







Newsroom
 







About Us
 







Partners
 







Environmental, Social, and Governance
 







Voice of the Customer
 













Under Attack?

























Home


ASERT Blog


Donot Team Leverages New Framework















Donot Team Leverages New Framework
Donot Team Leverages New Modular Malware Framework in South Asia













by 
ASERT Team
on 
March 8th, 2018



Authors: Dennis Schwarz and Jill SopkoSpecial thanks to Richard Hummel and Hardik Modi for their contributions on this post. Figure 1: Pakistan themed decoy documentKey FindingsASERT discovered a new modular malware framework, we call yty, that focuses on file collection, screenshots, and keylogging.We believe the threat actors, Donot Team, who created EHDevel, also created the yty framework.With medium confidence, ASERT believes this new malware framework will pick up where EHDevel left off and continue to focus on targets in South Asia.OverviewIn late January 2018, ASERT discovered a new modular malware framework we call "yty". The framework shares a striking resemblance to the EHDevel framework. We believe with medium confidence that a team we call internally as "Donot Team" is responsible for the new malware and will resume targeting of South Asia.In a likely effort to disguise the malware and its operations, the authors coded several references into the malware for football—it is unclear whether they mean American football or soccer. The theme may allow the network traffic to fly under the radar.While we believe this framework and its components are new, it shares many Tactics, Techniques, and Procedures (TTPs) and Indicators of Compromise (IOCs) with the EHDevel malware framework. In September 2017, Bitdefender released a white paper describing EHDevel and some of the campaigns that used it. Some of the highlights of it included the following:Labeled as an APT (advanced persistent threat) and active since at least 2016.Modular architecture with malware functionality spread over multiple components.Components used a variety of programming languages (C++, .NET, Python, VBS, and AutoIt).Functionality included: file collection, screenshots, key logging, and gathering system information.Command and control (C2) hosts stored in a document hosted on Google Docs.Decoy documents, timestamp analysis, and C2 server log analysis showed a focus on Pakistan. We assess with medium confidence that the yty framework is a replacement for the EHDevel framework and that the Donot Team may start using it in campaigns in a similar manner as EHDevel. The evolution from EHDevel to yty shows the threat actors are continually improving and modifying their malware framework, adding to their sophistication.Campaign AnalysisDonot Team campaigns use multiple methods to mimic legitimate applications, organizations, and services like Adobe, Gmail or news outlets. They also including seemingly benign domains that likely raise minimal suspicion to a human observer. The following domains are a few examples:abodeupdater[.]com
	Adobe update servicesqmails[.]org
	Gmail webmail serviceserviceupports[.]com
	Generic services domainssundayobserver[.]net
	Mimics weekly English-language newspaper in Sri Lankathebangladeshtoday[.]net
	English version of the national daily newspaper in BangladeshThe actors use false personas to register their domains instead of opting for privacy protection services.  Depending on the registrar service chosen, this could be seen as another cost control measure.  The actors often used typo-squatting to slightly alter a legitimate domain name. In contrast, the registration information used accurate spelling, possibly indicating the domain naming was intentional, typos included. Each unique registrant usually registered only a few domains, but mistakenly reused phone numbers or the registration data portrayed a similar pattern across domains. Looking at shared IP infrastructure, it was easy to see the registration patterns and expand the network used by the attackers. The Donot Team relies heavily on subdomains.  Nearly every domain discovered through the course of this investigation had multiple, unique subdomains and every malware sample analyzed communicated to subdomains.  In at least two instances, the domain never resolved to an IP address. Instead, the malware used subdomains, which lead to active infrastructure. Many of the sub-domains only navigated to the third level, but other samples used overly complex subdomain structures down to the sixth or seventh level.update.<domain>[.]comservice.<domain>[.]orgmail-live.outlook-com.332dhgka93t-veri9fjg3j-2s33gl.system.thebangladeshtoday[.]netLooking at registration patterns and passive DNS, many of these domains resolve for as little as three days before going offline. It is possible the attackers use these small windows to test their malware operations. Although we did not observe the original distribution of the core binary, we believe the group specifically targeted Pakistani individuals based on the decoy documents observed.  They appeared to be official Government of Pakistan memos, see Figure 1, above.AttributionDonot Team’s TTPs, infrastructure, and the malware code are strikingly similar to the EHDevel malware reported by BitDefender and is likely the same group of operators.  Bitdefender noted that the EHDevel malware appeared similar to malware analyzed by Blue Coat Labs in their report “Snake in the Grass”.  The “Snake in the Grass” report also showed malware similarities and infrastructure overlap with Operation Hangover (also known as the Patchwork Group).  While Arbor agrees that there are suspicious similarities between the Donot Team and Patchwork, we did not uncover definitive evidence to link the two groups. Additionally, a malicious document associated with yty was tagged by Hybrid Analysis as “Viceroy Tiger”, but there hasn’t been much recent public information on this group that we could find to corroborate.yty Malware Framework AnalysisOne of the TTPs associated with the Donot Team is the use of modular/plugin-based malware frameworks. We call the new malware framework “yty” (based on debugging strings in its components). The components of the framework are shown in Figure 2: Figure 2: yty malware components.Circular.xls AnalysisThe first piece of the framework is a malicious Excel document named “Cirular.xls” (9ce56e1403469fc74c8ff61dde4e83ad72597c66ce07bbae12fa70183687b32d). The content of the spreadsheet is an executable that is extracted and executed by macros, Figure 3. Figure 3: Circular.xls macro scriptThe delivery mechanism for the XLS file is unknown, but evidence suggests it could be a test document as seen in Figure 4:Figure 4: XLS document properties .exe (Downloader 1)  AnalysisSHA256:8d7eb0b7251bc4a40ebc9142a59ed8af16fb11cf8168e76dca48a78d6d7e4595Compilation Date: 2018-02-05 09:06:13PDB Path: C:\Users\donot\Documents\Visual Studio 2010\Projects\downloader\Debug\downloader.pdbDue to a bug in the macro code, the extracted executable is saved as “.exe”. This is a stripped down C++ program that, as its PDB path string indicates, downloads and executes another executable, then removes itself. The downloader attempts to retrieve and execute the following file (not active at the time of research):http://conf.serviceupdateres[.]com/Setup.exeThis host is a direct overlap with the EHDevel malware framework as it was also seen distributing payloads in Bitdefender’s analysis.Setup.exe (Downloader 2) AnalysisSHA256: 6bbd10ac20782542f40f78471c30c52f0619b91639840e60831dd665f9396365Compilation Date: 2018-01-04 09:43:28PDB Path: C:\Users\803\Desktop\ytyboth\yty 2.0\Release\Setup.pdbSetup.exe is another downloader written in C++ but contains more functionality than the “.exe” downloader. First, it checks/creates a mutex named “toptwo” so that only one copy of itself is running on the victim.Evasion TechniquesTo confuse malware analysts, it mixes in junk code as seen in Figure 5. Figure 5: Junk code contained in binary.It also has some basic anti-sandbox detection that tries to detect Virtual PC, Sandboxie, and VMware (example in Figure 6): Figure 6: VMWare check.Debugging CodeSimilar to some components in the EHDevel framework, it creates logs for debugging purposes, though the messages are not as verbose as in EHDevel’s samples, Figure 7. Figure 7: Debugging logCommand & Control Much like EHDevel, in order to get its C2 host, it downloads a file from Google Docs. The document in this case was located at:https://drive.google[.]com/uc?authuser=0&id=1BUuYXU6bLdH_k_NWQIo7n5Uo_7…At the time of research, the name of the document was “ip2.txt” and it contained the following IP address:5.135.199[.]0Per its metadata, the owner of the document is:Alfred Vilfimasterplan00007@gmail.comAn example C2 beacon is show in Figure 8: Figure 8: C2 beaconBased on the “/football/goal”, “score”, “ball”, and “loose” strings they are using a football theme to help disguise its traffic. The POST data contains:CPU informationWindows versionIs a virtual machine?Computer nameUser nameSerial number of main disk volumeAt the time of analysis, we only elicited a “loose” response from the C2 server. Continued execution is reliant on eliciting a “win” response. If a “win” response does not occur, the malware continues beaconing until it receives the appropriate response. Once the correct response is seen, the malware downloads the next component from the same C2 using the following URL path:/football/download/2/boothelpPersistence MechanismA secondary macro in circular.xls establishes persistence for the setup.exe download as seen in Figure 9. Figure 9: Persistence mechanismUnique StringsSetup.exe introduces three common names seen in the rest of the malware framework:“yty”, the name we use for the framework, from the PDB path string.“bigdata” from the schtasks /tn (taskname) parameter used in the persistence mechanism.A “bot id” consisting of computer name, user name, and volume serial number separated by dashes.boothelp.exe – Plugin DownloaderSHA256:a2e9d9a00e7e75ab1d5e96dd327a89b55608a0319461f2866aadada5bd50e728Compilation Date: 2018-01-03 09:42:00PDB Path: C:\Users\803\Desktop\ytyboth\yty 2.0\Release\boothelp.pdbAnother TTP used by the Donot Team is the transition from one programming language to another.  We see this with boothelp.exe, which is written in .NET--instead of C++ like the other components. boothelp.exe is a downloader responsible for retrieving modules/plugins that contain added functionality.The plugin downloader uses the same C2 channels as setup.exe by downloading a Google Doc file which contains the C2 IP address. It then continues the football theme by beaconing to the “/football/flag” folder on the C2 server, Figure 10. Figure 10: C2 communications to retrieve modulesUsing an HTML <div> element labeled “pcinfo”—possibly displayed verbatim in the C2 panel—the malware beacon message contains various pieces of system information outlined below:User nameComputer nameWindows versionNumber of processorsSystem directoryDomain name.NET versionInformation on drivesCPU informationThe response from the C2 is an odd string containing multiple pieces, delimited by various characters, but boils down to what plugins to download/run and their file sizes. The plugins for this framework were downloaded from the same URI path (“/football/download/2/”) where boothelp.exe was located. As of February 2018, we observed the following plugins:vstservice.exe – document listing pluginabode.exe – file exfiltration pluginmdriver.exe – key logger plugindspcheck.exe – screenshot pluginmboard.exe – system information pluginThese modules share functionality with components of the EHDevel framework, creating further overlap between the two malware frameworks. boothelp.exe has an interesting but unused function that takes a list of benign URLs and opens connections to them. As noted previously, we believe the actors are still testing the malware framework and it’s possible these URLs will become an anti-analysis feature to hide C2 communication among benign traffic. Some of the interesting benign URLs listed below:https://www.google[.]co.in/http://www.imdb[.]com/title/tt3501632/https://www.rottentomatoes[.]com/m/thor_ragnarok_2017vstservice.exe – File Listing PluginSHA256: e3fb0ab2f3d11f12c11b3ee1e1781eaec5581def820afe7e01902f31ba9e1936Compilation Date: 2018-01-03 08:14:32PDB Path: C:\Users\803\Desktop\ytyboth\yty 2.0\Release\vstservice.pdb The vstservice.exe plugin is .NET file responsible for sending a list of the file system to the C2. The malware retrieves the C2 from a Google Docs file like the previous binaries. The file was located at the following location:https://docs.google[.]com/uc?id=0B42CqDoBbigYM1lEamRDRjhFbGc&export=dow…At the time of research, the Google Doc was named “domain.txt” and contained the following C2 host:upload.cloudsekurity[.]onlinePer its metadata, it is owned by the same owner as the document above. The plugin sends two file listings. The first one focuses on files with the following extensions:pptpdfdocxlsdocxxlsxpptxdocmrtfinpxlsmcsvodtppsvcfThe second one contains all other files. An example is shown in Figure 11. Figure 11: C2 file list name exfiltrationThe URL path for this C2 references the “bigdata” string observed in the macro persistence mechanism. Some of the POST parameters are unclear, but contain the following items:status – hardcoded to “Found”path – hardcoded to “Unknown”pc – bot IDtype – unclearfname – file namecnumber – a number representative of large files broken into chunksorname – unclearofid – order ID for files broken into chunksSimilar to the plugin downloader, this plugin includes an unused function that connects to benign URLs. Some of the URLs are listed below:https://www.livechart[.]me/fall-2017/tvhttps://500px[.]com/editorshttps://paytm[.]com/metro-card-rechargeabode.exe – File Exfiltration PluginSHA256: 4d0114b1292714a13d43a4c0de3ea4498fa752354ad4f5b73a8ba441af6064aeCompilation Date: 2018-01-03 08:14:46PDB Path: C:\Users\803\Desktop\ytyboth\yty 2.0\Release\abode.pdb abode.exe is a .NET file  capable of file exfiltration. It uses the same Google Doc document and C2 as the vstservice.exe plugin. Two sets of files can be exfiltrated. The first set is a periodic sending of files generated by other plugins that do not include a C2 mechanism themselves. The second set of files is specified by the C2 as seen in Figure 12. Figure 12: C2 response specifying file for exfiltrationThe “id” parameter is hardcoded and the “pc” parameter is the bot ID. The file is then sent to the C2 as seen in Figure 13. Figure 13: File exfiltrationThis plugin also includes unused, benign URLs as seen below:https://www.gamespot[.]com/https://www.rottentomatoes[.]com/tv/mr_robot/s03mdriver.exe – Keylogger PluginSHA256: 600e7cfeea0ef8bd23cf95602a6b873898aa51848909aad1a7e8d4c5403797afCompilation Date: 2018-01-03 08:14:19PDB Path: C:\Users\803\Desktop\ytyboth\yty 2.0\Release\mdriver.pdb This plugin is written in C++ and is a key logger. It checks/creates a mutex named “twotwo“, uses the Windows SetWindowsHookEx and SetWinEventHook APIs to perform its key logging, and then relies on abobe.exe to exfiltrate the captured key strokes. Figure 14 shows an example of exfiltrated key log data. Figure 14: Key log exfiltrationdspcheck.exe – Screenshot PluginSHA256: 7d893d4f077e8e76a44a7830c5c3806dc956a6ef1a06c9f2dc33477c70f8cc9bCompilation Date: 2018-01-09 08:33:36PDB Path: D:\Soft\DevelopedCode\yty 2.0\Release\dspcheck.pdbdspcheck.exe is a screenshot plugin written in .NET. This plugin also shows evidence that the actors are continuing their testing efforts as seen in Figure 15. 
Figure 15: Screenshot code shows testing evidenceIt has the beginnings of C2 functionality, but this sample still relies on abobe.exe to send screenshots back to the C2, see Figure 16. Figure 16: Screenshot exfiltrationmboard.exe – System Information PluginPacked SHA256: 50281cdd1b22f2b85de5809bf69ebd10e399410f519e357c1cb941c5dc7c95e1The last plugin seen in this framework was mboard.exe. It is written in Golang and is packed with UPX. The purpose of this plugin is to gather various system information such as the following:Drive informationOutput of systeminfo commandInstalled softwareOutput of ipconfig /all commandOutput of net view commandOutput of tasklist commandThe collected is saved into multiple files with a “qr” extension appended. They are then sent to the C2 via abobe.exe. An example showing the running process list being sent to the C2 is shown in Figure 17. Figure 17: Running process list exfiltrationAppendix A (IOCs):SHA256 Hashes 9ce56e1403469fc74c8ff61dde4e83ad72597c66ce07bbae12fa70183687b32d 8d7eb0b7251bc4a40ebc9142a59ed8af16fb11cf8168e76dca48a78d6d7e4595 6bbd10ac20782542f40f78471c30c52f0619b91639840e60831dd665f9396365 a2e9d9a00e7e75ab1d5e96dd327a89b55608a0319461f2866aadada5bd50e728 e3fb0ab2f3d11f12c11b3ee1e1781eaec5581def820afe7e01902f31ba9e1936 4d0114b1292714a13d43a4c0de3ea4498fa752354ad4f5b73a8ba441af6064ae 600e7cfeea0ef8bd23cf95602a6b873898aa51848909aad1a7e8d4c5403797af 7d893d4f077e8e76a44a7830c5c3806dc956a6ef1a06c9f2dc33477c70f8cc9b 50281cdd1b22f2b85de5809bf69ebd10e399410f519e357c1cb941c5dc7c95e1 C2 Domains conf[.]serviceupdateres[.]com upload[.]cloudsekurity[.]online abodeupdater[.]com qmails[.]org serviceupports[.]com thebangladeshtoday[.]net sundayobserver[.]net C2 IP Addresses 5[.]135[.]199[.]0 89[.]33[.]246[.]99 





Posted In

Advanced Persistent Threats
Analysis
Botnets
Indicators of Compromise
Interesting Research
Malware
Reverse Engineering
threat analysis





















Guardians of the Connected World®








Discover





Enterprise Solutions






Communication Service Provider Solutions






Products






Industries






Support & Services









Learn





Resource Library






Learning Center






MyNETSCOUT






Events






Webinars






Blog









About





Careers






Environmental, Social, and Governance






For Investors






News & Media






Partners









Connect





1-888-357-7667






Contact Us



































© 2024 NETSCOUT


Terms & Conditions


Website Terms of Use


Data Privacy and Trust Center


Transparency in Supply Chains


Privacy Policy


Vendor Portal


Do Not Sell or Share My Personal Information


California Privacy Notice


UK Disclosure






























