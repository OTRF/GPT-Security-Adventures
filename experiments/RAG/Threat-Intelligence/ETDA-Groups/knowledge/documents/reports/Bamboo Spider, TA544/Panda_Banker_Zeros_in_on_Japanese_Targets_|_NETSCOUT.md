# Reference for threat actor for "Bamboo Spider, TA544"

**Title**: Panda Banker Zeros in on Japanese Targets | NETSCOUT

**Source**: https://www.netscout.com/blog/asert/panda-banker-zeros-japanese-targets

## Content




































Panda Banker Zeros in on Japanese Targets | NETSCOUT






















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


Panda Banker Zeros in on Japanese Targets















Panda Banker Zeros in on Japanese Targets













by 
ASERT Team
on 
March 27th, 2018



Key FindingsA threat actor using the well-known banking malware Panda Banker (a.k.a Zeus Panda, PandaBot) has started targeting financial institutions in Japan.Based on our data and analysis this is the first time that we have seen Panda Banker injects targeting Japanese organizations.It is likely a new campaign or actor started using Panda Banker since in addition to the previously unseen Japanese targeting, Arbor has not seen any indicator of compromise (IOC) overlaps with previous Panda Banker campaigns.The sample used in this campaign was the first sample we observed in the wild to use the newest version of Panda Banker, version 2.6.6.OverviewPanda Banker is based on the Zeus malware family. One of its main functions is stealing user credentials, account numbers, and ultimately money from financial institutions. It does this by using a technique known as “man in the browser” along with “webinjects” that specify what websites to target and how. This banking malware was first seen in the wild in the beginning of 2016 (version 2.1.x) and has had consistent, incremental development since then. While some details have changed, our “Who Let the Pandas Out? Zeus, Zeus, Zeus, Zeus” blog post is still a good introduction to the technical details of the malware. Panda Banker is sold as a kit on underground forums so there are multiple users of the malware. Cybercrime threat actors tend to focus their campaigns on particular countries—usually dependent on their ability to convert stolen credentials and account details from those locations into real money. Over the years we’ve seen Panda Banker campaigns focus on financial institutions in: Italy, Canada, Australia, Germany, United States, United Kingdom, and now Japan.Campaign AnalysisA new version of Panda Banker, version 2.6.6, was observed being distributed in the wild on March 26th:SHA256: 8db8f6266f6ad9546b2b5386a835baa0cbf5ea5f699f2eb6285ddf401b76ccb7Compilation date: 2018-03-26 09:54:57 While we didn’t see any significant changes to the malware itself (possibly just a “bug fix” release), the campaign using this sample stood out for two reasons:No IOC overlap with any previous Panda Banker campaigns that we’ve seen.Webinjects targeting Japan, a country we haven’t seen targeted by Panda Banker before.Command & Control (C2) The C2 servers configured for this sample are listed below:https://hillaryzell[.]xyz/1wekenauhivwauvaxquor.dathttps://buscamapa1[.]top/2yrfuupcovylaawubitvy.dathttps://buscamapa2[.]top/3toaxkatoindyepidikuv.dathttps://buscamapa3[.]top/4heequktuepahvoyfofit.dathttps://buscamapa4[.]top/5ufyfegtuobekpykobeul.dathttps://buscamapa5[.]top/6lubanuoxapywinlaokow.datAt the time of research, only hillaryzell[.]xyz was operational and it was registered to a “Petrov Vadim” using an email address of “yalapinziw@mail.ru”. Campaign Name The threat actor named this campaign “ank”. Webinjects At the time of research, the C2 server returned 27 webinjects that can be broken down into the following categories:17 Japanese banking web sites mostly focusing on credit cards1 US based web email site1 US based video search engine4 US based search engines1 US based online shopping site2 US based social media sites1 US based adult content hubAn example, redacted webinject for this campaign looks like the following: [caption id="attachment_9530" align="aligncenter" width="700"] Example webinject targeting Japan.[/caption] The webinjects in this campaign make use of a “grabber” / automated transfer system (ATS) system known as “Full Info Grabber” to capture credentials and account information. As can be seen in figures above, the threat actor is using a path of “jpccgrab” possibly meaning “Japanese credit card grabber”. Given the targeting, this name makes some sense. Distribution (update March 28, 2018) Security researcher kafeine has released more details on how this threat is being distributed in the wild: a malicious advertisement (malvertising) is redirecting victims to a RIG exploit kit which is distributing the Panda Banker malware.ConclusionJapan is no stranger to banking malware. Based on recent reports, the country has been plagued by attacks using the Ursnif and Urlzone banking malware. This post was our first analysis of the first Panda Banker campaign that we’ve seen to target financial institutions in Japan. 





Posted In

Analysis
Botnets
Indicators of Compromise
Interesting Research
Malware
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






























