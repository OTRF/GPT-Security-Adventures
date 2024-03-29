# Reference for threat actor for "Sphinx"

**Title**: Sphinx (APT-C-15) Targeted cyber-attack in the Middle East. Table of Contents - PDF Free Download

**Source**: https://docplayer.net/83717233-Sphinx-apt-c-15-targeted-cyber-attack-in-the-middle-east-table-of-contents.html

## Content








Sphinx (APT-C-15) Targeted cyber-attack in the Middle East. Table of Contents - PDF Free Download




























 Log in
Registration







Search for


















Sphinx (APT-C-15) Targeted cyber-attack in the Middle East. Table of Contents























 















                                                        SHARE 




                                                        HTML 




                                                        DOWNLOAD 




































                                                            Size: px
                                                        

                                                            Start display at page:
                                                        










Download "Sphinx (APT-C-15) Targeted cyber-attack in the Middle East. Table of Contents"




                                                                Error: 




 Download Document









  Christian Lane
 5 years ago                                                                                            
 Views:  











Transcription







 1 2 Sphinx (APT-C-15) Targeted cyber-attack in the Middle East Table of Contents 1. Overview Payload Delivery ) Watering Holes on Social Websites ) Lure Documents ) Self-camouflage Malware Analysis - ROCK ) Functionality Brief ) Infrastructure ) C2 Communication ) Attack Techniques Correlation Analysis ) Attackers Facebook Accounts ) PDB Paths ) Lure Documents ) njrat ) Geo-location of C Appendix A: Sample Sources in Hebrew Appendix B: Updated Detection Results of the Samples... 183 Timeline of the report updates April 29, 2016, brief report and sample analysis report were drafted. May 12, 2016, comprehensive analysis report was completed. June 20, 2016, the public version of the report was updated.4 1. Overview Operation Sphinx is a cyber-espionage activity in the Middle East. The main victims are political and military organizations in Egypt, Israel and possibly other countries. Sensitive data theft is what the attackers plotted for during the period from June, 2014 to November, 2015 when the activity was in its prime. We encountered some timestamps of the samples to be as early as December, 2011 which suggests the attack might be started much earlier, though further sound proof is needed. The main approach of Sphinx is watering hole attack on social websites. Until now, we have obtained 314 pieces of sample malicious codes and 7 C2 domains. A common method attackers use to hide their trace is to cloak malicious exe files with Word or PDF icons so that users will not tell the difference without looking into the file attribution or property. The Sphinx attackers adopt it as well, but they also attempt to conceal the attacks by making the master program invisible. In our analysis, Sphinx master program was found to be disguised with Word icon in order to trap users to click. Upon clicking, the master program released several DLL files. The files can be categorized into 9 types of plugin modules by functionality. The core DLL fill could be self-started after registering as a plugin of the resource management panel. Then, based on different configurations, remote injection was triggered to inject other functional DLL to corresponding running process. This way, when the malware was running, the master program had already been split into several imperceptible pieces. That decreases the risk for the targets to realize the existence of the malware. Multiple encryption algorithms were adopted simultaneously to hamper the detection. Seeing from the PDB paths, we suspect that the attackers were using continuous integration tools, which indicts that the scale of operation may massive and the developers of the malware are professionals in relevant fields. Furthermore, we speculate that some third party organizations were involved in helping develop the malware to support the Middle East s attackers.5 2. Payload Delivery 1) Watering Holes on Social Websites One of the lure documents was found in the comments area on Israeli Army s Facebook. It shows the attackers took advantage of this social websites to deliver the payload because their targets often visit it. This is the watering hole that has been seen as compromise vector in many cyber-attacks. Traditionally, watering holes attacks can be categorized into two types by approach: a. Attackers will usually study and capture the website that their targets often visit. Then malware code (usually the scripts exploit some vulnerability) is directly embedded on the site. Now, the site is infected with Trojan and the trap is ready for victims. When the targets visit the site and click infected pages, the malware will be implanted in their computer if the network environment matches attackers preset conditions. b. Attackers will capture a website and replace certain application or link on it with malicious download link. Once target visits the site and download the file in the link, malware will be implanted in the victim s computer. Typical cases are the Havex Trojan 1 (also known as Dragonfly or Energetic Bear) unrevealed in 2014 and OceanLotus in late May, The commonness the two approaches share is attackers need to obtain the authorization to modify the website they aim to capture. However, in Sphinx attacks, it is much easier to get authorized to deploy the watering holes because they just need to simply register a Facebook account. That is all they need to be free to scatter malicious links in the comments area. It is a new approach in setting up watering holes in APT attacks. 1 Havex Hunts For ICS/SCADA Systems,   2 APT Group OceanLotus, 6 Picture 1 Location of the samples on Facebook The table below shows detailed download link and MD5 of the RAR file from the link: Malicious Download Link Status of the Domain MD5 of the Downloaded RAR File hxxp://israelleaks.is-a-chef.com/leaks/isleaks.rar Invalid, already been marked as sinkhole by security vendors 1e4ed1704e31917f8652aa0078a85459 Lure documents in the RAR file are about the amendment on individual income tax regulations. The original exe icon has been replaced with a PDF or Word icon to induce targets to click. Picture 2 Lure documents in RAR file folder With in-depth analysis, we found that 10 social website accounts in total were compromised in the attacks, including Israeli Army, Israeli Navy and other accounts related with Israeli military and government. Malicious comments are intense from late January to early February in The content containing a malicious link are mostly about the aforementioned adjustments of individual income tax. *Please review Appendix A for a whole list of the sites. 7 Picture 3 C2 domain took over by Kaspersky using sinkhole technique 2) Lure Documents There are two types lure documents and the contents can tell APT researchers what fields and geos the attackers were targeting. (A) Egypt - Arabic Picture 4 Lure documents 1 In the original lure document 3, the YouTube video links showing the arrests of students from Al-Azhar University that against the coup are included at the end of the file. 3 hxxps://docs.google.com/file/d/0byavzartlomhc3hfefhgn1jooe0/edit?pli=1 8 Picture 5 Lure Document 2 The name annonymous rabaa on the picture is an Egyptian hacker group that compromise government official sites to protest the slaughter in August, (B) Israel - Hebrew Picture 6 Lure document 3 This document quotes the adjustments of Israeli individual income tax.9 3) Self-camouflage The malware either cloak itself with documentation and image icon, or with application icon. The picture below shows a fake Adobe Flash installer file. Picture 7 Impersonation of a document Picture 8 Impersonation of an Adobe Flash application With the former approach, no document or image will pop-up upon clicking; while with the latter approach, the legitimate installer file will be released after the malware finishes its installation. The 9 plugin modules are disguised as Office components. In earlier version of the malware, the installation directory is %UserProfile%\AppData\Roaming\officeplugin. But later versions changed the path to be under C:\Program Files\{GUID}, for instance, C:\Program Files\{59f0641e-45ac-11e5-af9e-b8ca3af5855f} is a piece of malware that pretends to be a system component. Picture 9 File Property of the Malware 10 3. Malware Analysis - ROCK 1) Functionality Brief ROCK Trojan plays a main role in the Sphinx attacks. This malware family was developed by the attackers themselves or was customer-made by a third party group. We also found a variant of the njrat family in another sample which we will introduce in another chapter. The malware impersonated Word documents, images or installation programs in the attempt to disguise itself as PDF files, pictures or Flash installers to induce the users to click. The main purpose is to steal sensitive information from the victims, such as system information, account & password and search history saved in the browser. It also monitors victims through Skype chatting history, cameras, microphones and keyboard & mouse logging. The information collected will then be encrypted and passed back to specific C2 servers. 2) Infrastructure Picture 10 Infrastructure of the malware Configuration data of all the modules is saved in JSON configuration file. The file decides, to name a few, whether to run the module or not, what encryption key to use on the data files, what pixels and intervals of the screenshots and audio recordings are required, as well we what running process the master program should be injected in. It also provides the user ID (rkuid), due date, C2 address, etc.11 Picture 11 Modules and Functionalities The dropper releases 20 DLL files in total with ten 32-bit and ten 64-bit. Each module is composed of two versions to be compliant with 32-bit and 64-bit system. Module name Functionality zcore zulib plgcmd plgcomm plginput plgurl plgskype plgavbug plgusrstl plgfsflt Master program API function encapsulation Obtain system info, screenshots, startup/end progress Communication Mouse and keyboard logging Monitor the content in web browser s (IE, FireFox, Chrome) address bar Save and pass back Skype chatting history, screenshots and audio records Monitor through camera and microphone, send back the records Steal user information, including account name & password, search history, cookies, Pidgin (IM software) account Monitor and pass back data of specific file types like doc, docx, ppt, pptx, xls, xlsx, odf, txt, pdf, rtf, jpg, jpeg, gif, png When the master program Zcore is started, it decrypts the configuration file under installation directory and decides whether to inject into certain process according to the module status (true/false) in the configuration file. Function modules: Zcore.dll core module: mainly responsible for loading other function modules and injecting them to certain process; register, update and uninstall modules, distribute logs and messages Plgcmd.dll command module: obtain system information, delete file and directory, take screenshots, upload saved documents, start and end process. Plgcomm.dll communication module: transfer data generated and encrypted by other modules to specific C2 server. The module sends a request to the server per minute to 12 acquire remote commands. The cross-process communication between each module is completed via WM_COPYDATA messages. Every message begins with 0x34AB541 which is the unique identification. The body of the message is transferred in JSON codes. 3) C2 Communication The message is transferred in data package to server port 80 through HTTP POST. Sensitive strings in the package are replaced after querying the mapping table of JSON configuration file. Picture 1 C2 Communication13 Picture 13 Restored Strings of C2 Communication C2 communication modules is injected into the browser process and the port used to send data to C2 server is port 80, these two methods perfectly cloak the attack among the normal traffic.  14 4) Attack Techniques Random file names The module files are re-named randomly after being released by the Dropper and the names are stored in the JSON file (usually nouns in English, for instance, gendarme.dll, jerques.dll). Picture 14 File name of the modules String Encryption All the strings are encrypted by several encryption algorithms. Picture 15 String Encryption API function encapsulation A great amount of API functions (over 300) are encapsulated in zulib (a dynamic dll library) to hamper static analysis from security software. 15 Runtime without master program The core module is started up as an extension of explorer.exe. Other modules are injected into certain processes according to the configuration file. Therefore, there is no master program running during the malware runtime which makes the malicious activities hard to be noticed. Even though sometimes users may sense the abnormity, they would still relax their vigilance at last with checking attempt ending up in vain. Process injection The master module runs in a legitimate explorer which security software will not intercept. Communication module is usually injected into the browser process. But if there is no browser process, the malware will give up communicating with C2 server. The data theft module is injected into security software so as to make the malware s trace inconspicuous when it traverses files. PE and config file encryption PE files in the dropper are compressed by zlib and encrypted by AES algorithms, as well as the configuration files released by the dropper. No matter on dynamic or static combat, the attack tactics indicts that these malware developers must have spent time and efforts studying security software to compile customer-made malware so as to avoid detection and cover its trace. 4. Correlation Analysis 1) Attackers Facebook Accounts Attackers Facebook account %D7%93%D7%94/16 These Facebook accounts played important roles in the watering hole attacks. 2) PDB Paths PDB paths C:\Users\user\bamboo-agent-home\xml-data\build-dir\ROCK-RW2-BRW6R\x64\Release-RkLibDll Z:\rootkits\windows\zico\x64 Z:\build\rootkits\windows\zico\Release We have the below discoveries based on the PDB paths: The ID of the developer is zico The name of the program is ROCK-RW2-BRW6R The internal name used is rootkits 3) Lure Documents File Name English ر ب ج ام عة ال م ع ت ق الت م لف هللا ف ك االزه أ سرهن Detention of Al-Azhar University students the (1).pdf file may Allah free them(1).pdf ا س ترات يج ية ال حرا ك ثوري ال ل لم ق اوم ة Revolutionary movement of people s File1.pdf \ال ش ع ب ية resistance strategy/file1.pdf הכנסה מס pdf.עדכ ונ ים -הכנסה מס\מלכ ודת Adjustment on individual income tax.pdf ثوري ةال مجموع ات ت نظ ي م File1.pdf \ال Organizing revolutionary groups/file1.pdf ة والي مخطط-س ي ن اء ال س يطر ة ام ن\ال ك امن The state of the Sinai-scheme/underlying pdf.ال مط ار د security control Chaser.pdf ة والي مخطط-س ي ن اء ال س يطر ة ت وج يه\ال ك امن The state of the Sinai-scheme/underlying car pdf.ال م ب ان يض د ال م فخخة ال س ي ارا ت bombs directed against buildings control.pdf ة والي مخطط-س ي ن اء ال س يطر ة ه ن دسة\ال ك امن The state of the Sinai-scheme/underlying pdf.ف لسط ين من ال م ت فجرا ت explosives engineering control of Palestine.pdf The file names give us the hint that the attacks are related with Egypt and Israel. 4) njrat 52f461a133e95328ccd9ba7f70e2f3e6 is a remote control released by the samples and disguised in an Adobe.pdf icon. The remote control is a variant of njrat malware family which is prevalent in the Middle East.17 5) Geo-location of C2 Picture 16 Associations between samples and CC C2 IP is one of the samples that locate in Egypt. Incoherence, the C2 IP of njrat released by it is also in Egypt. MD5 Malware Family C&C IP Geo location 52f461a133e95328ccd9ba7f70e2f3e6 ROCK Egypt c80b3fb9293a932b4e814a32e7ca76d3 njrat Egypt18 Appendix A: Sample Sources in Hebrew Links to Social Websites Site Owners Dates hxxps:// / /?type=3&theater Shayetet 13 - Israeli special forces unit 9:01pm, Jan. 31, 2015 hxxps://  Israel Defense Forces (IDF) 8:33pm, Jan. 31, 2015 hxxp://statuscope.co.il/%d7%9e%d7%99-%d7%94%d7%99%d7%90-%d7%94 Israeli Navy 11:15:25, Feb. 4, 2015 %D7%99%D7%97%D7%99%D7%93%D7%94-%D7%94%D7%98%D7%9B%D7% A0%D7%95%D7%9C%D7%95%D7%92%D7%99%D7%AA-%D7%A9%D7%9C-%D 7%96%D7%A8%D7%95%D7%A2-%D7%94%D7%99%D7%9D-%D7%90%D7%A9 %D7%A8-%D7%96%D7%9B%D7%AA%D7%94-%D7%91%D7%AA%D7%97%D7 %A8%D7%95%D7%AA?id=c917c8e2 hxxps://  Israeli political 3:36pm, Feb. 2, / /?type=3&p=10 commentaries hxxps:// / /?type=1&theater Israeli Culture and Sports Minister - Miri Regev 6:09pm, Feb. 3, 2015 hxxps://  Israeli media -Maariv 6:22pm, Feb. 1, 2015 hxxps://webcache.googleusercontent.com/search?q=cache:nbi1mbsvr4mj:ht tps://  593-%25D7%25A7%25D7%25A8%25D7%25A7%25D7%259C /+&cd=6&hl=en&ct=clnk&gl=us Online Caracal Batallion - infantry combat battalion of the IDF 5:33, Jan. 31, 2015 hxxps://webcache.googleusercontent.com/search?q=cache:rtcajobx_3qj:htt Israeli Army 2:14, Feb. 1, 2015 ps://  hxxps://  Israeli Navy 9:00pm, Jan. 31, %9D / hxxps://  Israeli Air Force Feb. 3, / /?type=1&theater19 Appendix B: Updated Detection Results of the Samples 













Similar documents





Operation Liberpy : Keyloggers and information theft in Latin America



        Operation Liberpy : Keyloggers and information theft in Latin America Diego Pérez Magallanes Malware Analyst Pablo Ramos HEAD of LATAM Research Lab 7/7/2015 version 1.1 Contents Introduction... 3 Operation    

        More information 




Overview. Map of the Arabic Languagge. Some tips. Need to over-learn to reach a stage of unconscious competence. Recap Parts of Speech



        Map of the Arabic Languagge Recap Parts of Speech Overview in Understanding the Qur an Start-up Initial growth Rapid growth Continuous growth Some tips Don t take furious notes Videos will be downloadable    

        More information 




What do a banking Trojan, Chrome and a government mail server have in common? Analysis of a piece of Brazilian malware



        What do a banking Trojan, Chrome and a government mail server have in common? Analysis of a piece of Brazilian malware Contents Introduction.................................2 Installation: Social engineering    

        More information 




DRIVE-BY DOWNLOAD WHAT IS DRIVE-BY DOWNLOAD? A Typical Attack Scenario



        DRIVE-BY DOWNLOAD WHAT IS DRIVE-BY DOWNLOAD? Drive-by Downloads are a common technique used by attackers to silently install malware on a victim s computer. Once a target website has been weaponized with    

        More information 




ﺮﺋﺎ ﻤﱠﻀﻟا The Arabic Pronouns



        ر الض م اي ر The Arabic Pronouns (The Arabic Pronouns) Designed and compiled by the one in need of Allah s pardon Aboo Imraan Abdus-Saboor bin Tomas Maldonado al-mekseekee -may Allah forgive him, his family,    

        More information 




System Requirements and Technical Prerequisites for SAP SuccessFactors HCM Suite



        System Requirements and Technical Prerequisites for SAP SuccessFactors HCM Suite SAP SuccessFactors HCM Suite is a fully web-based offering. You will need an Internet connection and a system that meets    

        More information 




WildFire Overview. WildFire Administrator s Guide 1. Copyright 2007-2015 Palo Alto Networks



        WildFire Overview WildFire provides detection and prevention of zero-day malware using a combination of malware sandboxing and signature-based detection and blocking of malware. WildFire extends the capabilities    

        More information 




From Georgia, with Love Win32/Georbot. Is someone trying to spy on Georgians?



        From Georgia, with Love Win32/Georbot Is someone trying to spy on Georgians? At the beginning of the year, a curious piece of malware came to our attention. An analyst in our virus laboratory noticed that    

        More information 




Hide and seek - how targeted attacks hide behind clean applications Szappanos Gábor



        Hide and seek - how targeted attacks hide behind clean applications Szappanos Gábor Principal Malware Researcher 1 Honourable mentions: 2010. Stuxnet digitally signed drivers: stolen certificate June 2012.    

        More information 




Botnets: The Advanced Malware Threat in Kenya's Cyberspace



        Botnets: The Advanced Malware Threat in Kenya's Cyberspace AfricaHackon 28 th February 2014 Who we Are! Paula Musuva-Kigen Research Associate Director, Centre for Informatics Research and Innovation (CIRI)    

        More information 








        Malicious Websites uncover vulnerabilities (browser, plugins, webapp, server), initiate attack steal sensitive information, install malware, compromise victim s machine Malicious Websites uncover vulnerabilities    

        More information 




Where every interaction matters.



        Where every interaction matters. Peer 1 Vigilant Web Application Firewall Powered by Alert Logic The Open Web Application Security Project (OWASP) Top Ten Web Security Risks and Countermeasures White Paper    

        More information 




The Nitro Attacks. Security Response. Stealing Secrets from the Chemical Industry. Introduction. Targets. Eric Chien and Gavin O Gorman



        The Nitro Attacks Stealing Secrets from the Chemical Industry Eric Chien and Gavin O Gorman Contents Introduction... 1 Targets... 1 Attack methodology... 2 Geographic Spread... 3 Attribution... 4 Technical    

        More information 




The full setup includes the server itself, the server control panel, Firebird Database Server, and three sample applications with source code.



        Content Introduction... 2 Data Access Server Control Panel... 2 Running the Sample Client Applications... 4 Sample Applications Code... 7 Server Side Objects... 8 Sample Usage of Server Side Objects...    

        More information 




Why Won t you Think?



        Why Won t you Think? www.detailedquran.com إ ن ش ر الد و اب ع ند الل ه الص م ال ب ك م ال ذ ين ل ي ع ق ل ون Truly, the worst of all creatures in the sight of Allah are the deaf, the dumb, those who do not    

        More information 




Agenda. Taxonomy of Botnet Threats. Background. Summary. Background. Taxonomy. Trend Micro Inc. Presented by Tushar Ranka



        Taxonomy of Botnet Threats Trend Micro Inc. Presented by Tushar Ranka Agenda Summary Background Taxonomy Attacking Behavior Command & Control Rallying Mechanisms Communication Protocols Evasion Techniques    

        More information 




This report is a detailed analysis of the dropper and the payload of the HIMAN malware.



        PAGE 5 Check Point Malware Research Group HIMAN Malware Analysis December 12, 2013 Researcher: Overview This report is a detailed analysis of the dropper and the payload of the HIMAN malware. This malware    

        More information 




Covert Operations: Kill Chain Actions using Security Analytics



        Covert Operations: Kill Chain Actions using Security Analytics Written by Aman Diwakar Twitter: https://twitter.com/ddos LinkedIn: http://www.linkedin.com/pub/aman-diwakar-ccie-cissp/5/217/4b7 In Special    

        More information 




Inception: APT Campaign Spanning PCs, Mobile, the Cloud, and Home Routers



        SESSION ID: BR-T10 Inception: APT Campaign Spanning PCs, Mobile, the Cloud, and Home Routers Snorre Fagerland Sr. Principal Security Researcher Blue Coat Systems @SnorreFagerland Waylon Grange Sr. Threat    

        More information 




VISA SECURITY ALERT December 2015 KUHOOK POINT OF SALE MALWARE. Summary. Distribution and Installation



        VISA SECURITY ALERT December 2015 KUHOOK POINT OF SALE MALWARE Distribution: Merchants, Acquirers Who should read this: Information security, incident response, cyber intelligence staff Summary Kuhook    

        More information 




April 11, 2011. (Revision 2)



        Passive Vulnerability Scanning Overview April 11, 2011 (Revision 2) Copyright 2011. Tenable Network Security, Inc. All rights reserved. Tenable Network Security and Nessus are registered trademarks of    

        More information 




Web Conferencing Version 8.3 Troubleshooting Guide



        System Requirements General Requirements Web Conferencing Version 8.3 Troubleshooting Guide Listed below are the minimum requirements for participants accessing the web conferencing service. Systems which    

        More information 




The HeartBeat APT Campaign



        Trend Micro Incorporated Research Paper 2012 The HeartBeat APT Campaign Roland Dela Paz Contents About This Paper... 1 Introduction... 1 Campaign Targets... 2 Context... 2 Attack Vector... 3 Infection    

        More information 




mypro Installation and Handling Manual Version: 7



        mypro Installation and Handling Manual Version: 7 Date: JAN 2016 Thank you for using mypro on your PC. myscada is a full featured HMI/SCADA system with advanced options such as vector graphics views, advanced    

        More information 




Sophos for Microsoft SharePoint Help



        Sophos for Microsoft SharePoint Help Product version: 2.0 Document date: March 2011 Contents 1 About Sophos for Microsoft SharePoint...3 2 Dashboard...4 3 Configuration...5 4 Reports...27 5 Search...28    

        More information 




Sophos Mobile Encryption Help. Product version: 1.0 Document date: April 2012



        Sophos Mobile Encryption Help Product version: 1.0 Document date: April 2012 Contents 1 About Sophos Mobile Encryption...3 2 Home view...5 3 itunes...6 4 Dropbox...7 5 Favorites...9 6 Document view...11    

        More information 




Prayer Book for. Children &



        Prayer Book for Muslim Children & New Muslims s (Prayer Book for Muslim Children & New Muslims) Designed and compiled by the one in need of Allah s pardon Aboo Imraan Abdus-Saboor bin Tomas Maldonado al-mekseekee    

        More information 




Malware B-Z: Inside the Threat From Blackhole to ZeroAccess



        Malware B-Z: Inside the Threat From Blackhole to ZeroAccess By Richard Wang, Manager, SophosLabs U.S. Over the last few years the volume of malware has grown dramatically, thanks mostly to automation and    

        More information 




Trend Micro Incorporated Research Paper 2012. Adding Android and Mac OS X Malware to the APT Toolbox



        Trend Micro Incorporated Research Paper 2012 Adding Android and Mac OS X Malware to the APT Toolbox Contents Abstract... 1 Introduction... 1 Technical Analysis... 2 Remote Access Trojan Functionality...    

        More information 




Advanced Endpoint Protection Overview



        Advanced Endpoint Protection Overview Advanced Endpoint Protection is a solution that prevents Advanced Persistent Threats (APTs) and Zero-Day attacks and enables protection of your endpoints by blocking    

        More information 




Workday Mobile Security FAQ



        Workday Mobile Security FAQ Workday Mobile Security FAQ Contents The Workday Approach 2 Authentication 3 Session 3 Mobile Device Management (MDM) 3 Workday Applications 4 Web 4 Transport Security 5 Privacy    

        More information 




G DATA SECURITYLABS CASE STUDY OPERATION TOOHASH HOW TARGETED ATTACKS WORK



        G DATA SECURITYLABS CASE STUDY OPERATION TOOHASH HOW TARGETED ATTACKS WORK CONTENTS Executive Summary... 2 The Malware used 2 Information Stealing 2 Campaign Analysis... 3 Targets 3 Spear Phishing Campaign    

        More information 




BlackBerry Enterprise Service 10. Secure Work Space for ios and Android Version: 10.1.1. Security Note



        BlackBerry Enterprise Service 10 Secure Work Space for ios and Android Version: 10.1.1 Security Note Published: 2013-06-21 SWD-20130621110651069 Contents 1 About this guide...4 2 What is BlackBerry Enterprise    

        More information 




U S E R M A N U A L. Alcatel-Lucent. Click to call plugin for OmniPCX Enterprise. User manual. Alcatel-Lucent Enterprise Services Page 1/12



        U S E R M A N U A L Alcatel-Lucent Click to call plugin for OmniPCX Enterprise User manual Alcatel-Lucent Enterprise Services Page 1/12 Index table 1 D o c u m e n t h i s t o r y 3 2 S c o p e 3 2.1 Overview...    

        More information 




Citrix Access Gateway Plug-in for Windows User Guide



        Citrix Access Gateway Plug-in for Windows User Guide Access Gateway 9.2, Enterprise Edition Copyright and Trademark Notice Use of the product documented in this guide is subject to your prior acceptance    

        More information 




Gateway Apps - Security Summary SECURITY SUMMARY



        Gateway Apps - Security Summary SECURITY SUMMARY 27/02/2015 Document Status Title Harmony Security summary Author(s) Yabing Li Version V1.0 Status draft Change Record Date Author Version Change reference    

        More information 




Sophos for Microsoft SharePoint Help. Product version: 2.0



        Sophos for Microsoft SharePoint Help Product version: 2.0 Document date: September 2015 Contents 1 About Sophos for Microsoft SharePoint...3 2 Dashboard...4 3 Configuration...5 3.1 On-access scan...5 3.2    

        More information 




A Server and Browser-Transparent CSRF Defense for Web 2.0 Applications. Slides by Connor Schnaith



        A Server and Browser-Transparent CSRF Defense for Web 2.0 Applications Slides by Connor Schnaith Cross-Site Request Forgery One-click attack, session riding Recorded since 2001 Fourth out of top 25 most    

        More information 




WEB SECURITY. Oriana Kondakciu 0054118 Software Engineering 4C03 Project



        WEB SECURITY Oriana Kondakciu 0054118 Software Engineering 4C03 Project The Internet is a collection of networks, in which the web servers construct autonomous systems. The data routing infrastructure    

        More information 




Dragonfly: Energy Companies Under Sabotage Threat Symantec Security Response



        Dragonfly: Energy Companies Under Sabotage Threat Symantec Security Response Dragonfly: Western Energy Companies Under Sabotage Threat 1 What is Dragonfly? Ongoing cyberespionage campaign Targeting the    

        More information 




5 Steps to Advanced Threat Protection



        5 Steps to Advanced Threat Protection Agenda Endpoint Protection Gap Profile of Advanced Threats Consensus Audit Guidelines 5 Steps to Advanced Threat Protection Resources 20 Years of Chasing Malicious    

        More information 




CamGuard Security System CamGuard Security System Manual



        CamGuard Security System Manual JMC Electron Co.,LTD Brief Introduction... 3 Features... 3 System Requirements... 3 Configuration... 4 Add Camera... 4 Device Options... 4 About Alarm... 5 Alarm Actions...    

        More information 




DiskPulse DISK CHANGE MONITOR



        DiskPulse DISK CHANGE MONITOR User Manual Version 7.9 Oct 2015 www.diskpulse.com info@flexense.com 1 1 DiskPulse Overview...3 2 DiskPulse Product Versions...5 3 Using Desktop Product Version...6 3.1 Product    

        More information 




Enterprise Remote Control 5.6 Manual



        Enterprise Remote Control 5.6 Manual Solutions for Network Administrators Copyright 2015, IntelliAdmin, LLC Revision 3/26/2015 http://www.intelliadmin.com Page 1 Table of Contents What is Enterprise Remote    

        More information 




RDM+ Desktop for Windows Getting Started Guide



        RDM+ Remote Desktop for Mobiles RDM+ Desktop for Windows Getting Started Guide Introduction... 3 1. Installing RDM+ Desktop on a computer... 3 2. Preparing for remote connection... 4 3. RDM+ Desktop window...    

        More information 




ivms-4500 (Android Tablet) Mobile Client Software User Manual (V3.0)



        ivms-4500 (Android Tablet) Mobile Client Software User Manual (V3.0) Thank you for purchasing our product. This manual applies to ivms-4500 (Android Tablet) mobile client software; please read it carefully    

        More information 




Cyber Security in Taiwan's Government Institutions: From APT To. Investigation Policies



        Cyber Security in Taiwan's Government Institutions: From APT To Investigation Policies Ching-Yu, Hung Investigation Bureau, Ministry of Justice, Taiwan, R.O.C. Abstract In this article, we introduce some    

        More information 




IBM Aspera Add-in for Microsoft Outlook 1.3.2



        IBM Aspera Add-in for Microsoft Outlook 1.3.2 Windows: 7, 8 Revision: 1.3.2.100253 Generated: 02/12/2015 10:58 Contents 2 Contents Introduction... 3 System Requirements... 5 Setting Up... 6 Account Credentials...6    

        More information 




Kaspersky Fraud Prevention: a Comprehensive Protection Solution for Online and Mobile Banking



        Kaspersky Fraud Prevention: a Comprehensive Protection Solution for Online and Mobile Banking Today s bank customers can perform most of their financial activities online. According to a global survey    

        More information 




Cybercrime myths, challenges and how to protect our business. Vladimir Kantchev Managing Partner Service Centrix



        Cybercrime myths, challenges and how to protect our business Vladimir Kantchev Managing Partner Service Centrix Agenda Cybercrime today Sources and destinations of the attacks Breach techniques How to    

        More information 




Phone.com. Communicate Better



        1 Communicate Better - 1 / 16 - 2 Faxes Setting a Number to Receive Faxes Fax Notification Email Notification Text Message (SMS) notification Managing Faxes Viewing a Fax Downloading a Fax Viewing a Fax    

        More information 




When you listen to the news, you hear about many different forms of computer infection(s). The most common are:



        Access to information and entertainment, credit and financial services, products from every corner of the world even to your work is greater than ever. Thanks to the Internet, you can conduct your banking,    

        More information 




HoneyBOT User Guide A Windows based honeypot solution



        HoneyBOT User Guide A Windows based honeypot solution Visit our website at http://www.atomicsoftwaresolutions.com/ Table of Contents What is a Honeypot?...2 How HoneyBOT Works...2 Secure the HoneyBOT Computer...3    

        More information 




My Account User Guide. Popfax.com login page. Easy, inexpensive Effective!



        Popfax.com login page You can access your Popfax account by going to https://www.popfax.com/index.php?pop=compte. You might want to bookmark this link. You will be asked to enter your Login (the email    

        More information 




ArcGIS Server Security Threats & Best Practices 2014. David Cordes Michael Young



        ArcGIS Server Security Threats & Best Practices 2014 David Cordes Michael Young Agenda Introduction Threats Best practice - ArcGIS Server settings - Infrastructure settings - Processes Summary Introduction    

        More information 




Tespok Kenya icsirt: Enterprise Cyber Threat Attack Targets Report



        Tespok Kenya icsirt: Enterprise Cyber Threat Attack Targets Report About this Report This report was compiled and published by the Tespok icsirt in partnership with the Serianu Cyber Threat Intelligence    

        More information 




Sophistication of attacks will keep improving, especially APT and zero-day exploits



        FAQ Isla Q&A General What is Isla? Isla is an innovative, enterprise-class web malware isolation system that prevents all browser-borne malware from penetrating corporate networks and infecting endpoint    

        More information 




How to create an Email



        How to create an Email Don't share mail You can set the mailbox not to be shared individually. The first thing to do after launching the Send mail screen is to select whether to share or not to share the    

        More information 




Getting Ahead of Malware



        IT@Intel White Paper Intel Information Technology Security December 2009 Getting Ahead of Malware Executive Overview Since implementing our security event monitor and detection processes two years ago,    

        More information 




Practice Fusion API Client Installation Guide for Windows



        Practice Fusion API Client Installation Guide for Windows Quickly and easily connect your Results Information System with Practice Fusion s Electronic Health Record (EHR) System Table of Contents Introduction    

        More information 




Alert (TA14-212A) Backoff Point-of-Sale Malware



        Alert (TA14-212A) Backoff Point-of-Sale Malware Original release date: July 31, 2014 Systems Affected Point-of-Sale Systems Overview This advisory was prepared in collaboration with the National Cybersecurity    

        More information 




Endpoint Business Products Testing Report. Performed by AV-Test GmbH



        Business Products Testing Report Performed by AV-Test GmbH January 2011 1 Business Products Testing Report - Performed by AV-Test GmbH Executive Summary Overview During November 2010, AV-Test performed    

        More information 




HACKER INTELLIGENCE INITIATIVE. The Secret Behind CryptoWall s Success



        HACKER INTELLIGENCE INITIATIVE The Secret Behind 1 1. Introduction The Imperva Application Defense Center (ADC) is a premier research organization for security analysis, vulnerability discovery, and compliance    

        More information 




Islamic Studies. Student Workbook. Level 1. Name. 2 Dudley Street Cheetham Hill Manchester, M89DA. manchestersalafischool.



        Islamic Studies Level 1 Student Workbook Name 2 Dudley Street Cheetham Hill Manchester, M89DA manchestersalafischool.com 0161 317 1481 Islamic Studies Level 1 Student Workbook Overview Coming to the Masjid    

        More information 




Multi-Site 4200. Remote Viewing Software. User Guide



        Multi-Site 4200 Remote Viewing Software User Guide Document 800-12064V1 Rev A 09/2012  User Guide Revisions Issue Date Revisions A 07/2012 New document. V1 Rev A 09/2012 Updated the description of the    

        More information 




ADTVision (ios) Mobile Client Software User Manual (V1.6)



        ADTVision (ios) Mobile Client Software User Manual (V1.6) Thank you for purchasing our product. This manual applies to ADTVision (ios) mobile client software, please read it carefully for the better use    

        More information 




Advancements in Botnet Attacks and Malware Distribution



        Advancements in Botnet Attacks and Malware Distribution HOPE Conference, New York, July 2012 Aditya K Sood Rohit Bansal Richard J Enbody SecNiche Security Department of Computer Science and Engineering    

        More information 




Redline Users Guide. Version 1.12



        Redline Users Guide Version 1.12 Contents Contents 1 About Redline 5 Timeline 5 Malware Risk Index (MRI) Score 5 Indicators of Compromise (IOCs) 5 Whitelists 5 Installation 6 System Requirements 6 Install    

        More information 




TLP: GREEN FBI. FBI Liaison Alert System # A-000049-MW



        Liaison Alert System # A-000049-MW The following information was obtained through investigation and is provided in conjunction with the s statutory requirement to conduct victim notification as outlined    

        More information 




Enterprise Cybersecurity Best Practices Part Number MAN-00363 Revision 006



        Enterprise Cybersecurity Best Practices Part Number MAN-00363 Revision 006 April 2013 Hologic and the Hologic Logo are trademarks or registered trademarks of Hologic, Inc. Microsoft, Active Directory,    

        More information 




SPEAR-PHISHING ATTACKS



        SPEAR-PHISHING ATTACKS WHY THEY ARE SUCCESSFUL AND HOW TO STOP THEM WHITE PAPER RECENTLY, THERE HAS BEEN A RAPID AND DRAMATIC SHIFT FROM BROAD SPAM ATTACKS TO TARGETED EMAIL-BASED-PHISHING CAMPAIGNS THAT    

        More information 




Aspera Connect 2.4.7. Linux 32/64-bit. Document Version: 1



        Aspera Connect 2.4.7 Linux 32/64-bit Document Version: 1 2 Contents Contents Introduction... 3 Setting Up... 4 Upgrading from a Previous Version...4 Installation... 4 Set Up Network Environment... 5 Basic    

        More information 




McAfee.com Personal Firewall



        McAfee.com Personal Firewall 1 Table of Contents Table of Contents...2 Installing Personal Firewall...3 Configuring Personal Firewall and Completing the Installation...3 Configuring Personal Firewall...    

        More information 




Security+ Guide to Network Security Fundamentals, Third Edition. Chapter 2 Systems Threats and Risks



        Security+ Guide to Network Security Fundamentals, Third Edition Chapter 2 Systems Threats and Risks Objectives Describe the different types of software-based attacks List types of hardware attacks Define    

        More information 




WEB ATTACKS AND COUNTERMEASURES



        WEB ATTACKS AND COUNTERMEASURES February 2008 The Government of the Hong Kong Special Administrative Region The contents of this document remain the property of, and may not be reproduced in whole or in    

        More information 




Tech Report. Targeted attack on. France s TV5Monde



        Tech Report Targeted attack on France s TV5Monde May 05, 2015 Tabel of Content Introduction... 3 Attack Outline... 3 Findings #1: Njrat and Njworm, based in the Middle East... 6 Findings #2: Source code    

        More information 




Trends in Advanced Threat Protection



        Trends in Advanced Threat Protection John Martin Senior Security Architect IBM Security Systems Division 1 2012 IBM Corporation John Martin Senior Security Architect IBM Security Systems Division Security    

        More information 




Advanced Persistent Threats



        White Paper INTRODUCTION Although most business leaders and IT managers believe their security technologies adequately defend against low-level threats, instances of (APTs) have increased. APTs, which    

        More information 




Uroburos Highly complex espionage software with Russian roots



        G Data Red Paper 2014 Uroburos Highly complex espionage software with Russian roots G Data discovers alleged intelligence agency software G Data SecurityLabs Contact: intelligence@gdata.de Red Paper_February-2014    

        More information 




User Guide - Table of Contents



        User Guide - Table of Contents Receiving Faxes Fax-to-Email Web Access to Faxes File Format Options Receiving Faxes on Wireless Devices Receiving Faxes Securely Integration and API Methods Archive Service    

        More information 




This section will focus on basic operation of the interface including pan/tilt, video, audio, etc.



        Catalogue Basic Operation... 2 For Internet Explorer... 2 For Other Non-IE Web Browsers... 5 Camera Settings... 6 System... 6 About... 6 PT Setting... 7 Backup and Restore Setup... 8 NTP Setting... 8 System    

        More information 




McAfee Labs Threat Advisory W32/Autorun.worm.aaeb-h



        Summary McAfee Labs Threat Advisory W32/Autorun.worm.aaeb-h August 9, 2013 W32/Autorun.worm.aaeb-h has the ability to infect removable media devices, as well as mounted network shares. Infection starts    

        More information 




ivms-4200 Client Software Quick Start Guide



        ivms-4200 Client Software Quick Start Guide UD.6L0202B1538A01 Thank you for purchasing our product. If there is any question or request, please do not hesitate to contact the dealer. This manual applies    

        More information 




1. Digital Asset Management User Guide... 2 1.1 Digital Asset Management Concepts... 2 1.2 Working with digital assets... 4 1.2.1 Importing assets in



        1. Digital Asset Management User Guide....................................................... 2 1.1 Digital Asset Management Concepts.................................................... 2 1.2 Working with    

        More information 




Streamlining Web and Email Security



        How to Protect Your Business from Malware, Phishing, and Cybercrime The SMB Security Series Streamlining Web and Email Security sponsored by Introduction to Realtime Publishers by Don Jones, Series Editor    

        More information 




Innovations in Network Security



        Innovations in Network Security Michael Singer April 18, 2012 AT&T, the AT&T logo and all other AT&T marks contained herein are trademarks of AT&T Intellectual Property and/or AT&T affiliated companies.    

        More information 




Client applications are available for PC and Mac computers and ios and Android mobile devices. Internet



        Introduction to OpenVPN 1 - Introduction to OpenVPN The AN-300-RT-4L2W router features a built-in OpenVPN server for secure, easily configured access to the network from the Internet using devices with    

        More information 




Executable Integrity Verification



        Executable Integrity Verification Abstract Background Determining if a given executable has been trojaned is a tedious task. It is beyond the capabilities of the average end user and even many network    

        More information 




Quick Start. Installing the software. for Webroot Internet Security Complete, Version 7.0



        Quick Start for Webroot Internet Security Complete, Version 7.0 This Quick Start describes how to install and begin using the Webroot Internet Security Complete 2011 software. This integrated suite delivers    

        More information 




Cyber Security Workshop Ethical Web Hacking



        Cyber Security Workshop Ethical Web Hacking May 2015 Setting up WebGoat and Burp Suite Hacking Challenges in WebGoat Concepts in Web Technologies and Ethical Hacking 1 P a g e Downloading WebGoat and Burp    

        More information 




Adobe Systems Incorporated



        Adobe Connect 9.2 Page 1 of 8 Adobe Systems Incorporated Adobe Connect 9.2 Hosted Solution June 20 th 2014 Adobe Connect 9.2 Page 2 of 8 Table of Contents Engagement Overview... 3 About Connect 9.2...    

        More information 




The Epic Turla Operation: Information on Command and Control Server infrastructure



        The Epic Turla Operation: Information on Command and Control Server infrastructure v1.00 (August 7, 2014) Short Report by Laboratory of Cryptography and System Security (CrySyS Lab) http://www.crysys.hu/    

        More information 




7.7 DDoS : Unknown Secrets and Botnet Counter-Attack. www.issuemakerslab.com sionics & kaientt



        7.7 DDoS : Unknown Secrets and Botnet Counter-Attack sionics & kaientt Contents Overview Botnet Structure 7.7 DDoS Bot Malware Analysis Botnet Counter-Attack Demo Overview 7.7 DDoS Attack Cyber attack    

        More information 




User Guide FOR TOSHIBA STORAGE PLACE



        User Guide FOR TOSHIBA STORAGE PLACE (This page left blank for 2-sided "book" printing.) Table of Contents Overview... 5 System Requirements... 5 Storage Place Interfaces... 5 Getting Started... 6 Using    

        More information 




Unknown threats in Sweden. Study publication August 27, 2014



        Unknown threats in Sweden Study publication August 27, 2014 Executive summary To many international organisations today, cyber attacks are no longer a matter of if but when. Recent cyber breaches at large    

        More information 




WHITEPAPER. How a DNS Firewall Helps in the Battle against Advanced Persistent Threat and Similar Malware



        WHITEPAPER How a DNS Firewall Helps in the Battle against Advanced Persistent Threat and Similar Malware How a DNS Firewall Helps in the Battle against Advanced As more and more information becomes available    

        More information 




2014 Entry Form (Complete one for each entry.) Fill out the entry name exactly as you want it listed in the program.



        2014 Entry Form (Complete one for each entry.) Fill out the entry name exactly as you want it listed in the program. Entry Name HFA Submission Contact Phone Email Qualified Entries must be received by    

        More information 




Making the difference between read to output, and read to copy GOING BEYOND BASIC FILE AUDITING FOR DATA PROTECTION



        Making the difference between read to output, and read to copy GOING BEYOND BASIC FILE AUDITING FOR DATA PROTECTION MOST OF THE IMPORTANT DATA LOSS VECTORS DEPEND ON COPYING files in order to compromise    

        More information 




ZeroAccess. James Wyke. SophosLabs UK



        ZeroAccess James Wyke SophosLabs UK Abstract ZeroAccess is a sophisticated kernel-mode rootkit that is rapidly becoming one of the most widespread threats in the current malware ecosystem. ZeroAccess ability    

        More information 




Sophos Endpoint Security and Control Help



        Sophos Endpoint Security and Control Help Product version: 10.3 Document date: June 2014 Contents 1 About Sophos Endpoint Security and Control...3 2 About the Home page...4 3 Sophos groups...5 4 Sophos    

        More information 


















                2024 © DocPlayer.net Privacy Policy | Terms of Service | Feedback
                                    | Do Not Sell My Personal Information


















    To make this website work, we log user data and share it with processors. To use this website, you must agree to our Privacy Policy, including cookie policy.
        I agree.    




