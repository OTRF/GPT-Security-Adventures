# Reference for threat actor for "Scarab"

**Title**: Scarab attackers took aim at select Russian targets since 2012 | Symantec Connect

**Source**: https://web.archive.org/web/20150124025612/http:/www.symantec.com:80/connect/blogs/scarab-attackers-took-aim-select-russian-targets-2012

## Content














Scarab attackers took aim at select Russian targets since 2012 | Symantec Connect
 





















































 



































Dec
JAN
Mar




24




2014
2015
2016







success
fail






















 About this capture






COLLECTED BY



		Organization: Alexa Crawls


	  Starting in 1996, Alexa Internet has been donating their crawl data to the Internet Archive.  Flowing in every day, these data are added to the Wayback Machine after an embargo period.
	



Collection: Alexa Crawls


	  Starting in 1996, Alexa Internet has been donating their crawl data to the Internet Archive.  Flowing in every day, these data are added to the Wayback Machine after an embargo period.
	




TIMESTAMPS





The Wayback Machine - https://web.archive.org/web/20150124025612/http://www.symantec.com:80/connect/blogs/scarab-attackers-took-aim-select-russian-targets-2012







Symantec Connect 

Blogs > Security Response
Entire Site



Search Tips 











Home

Community:Security  

Blogs Overview
Forums
Articles
Blogs
Downloads
Events
Groups
Ideas
Videos


Security Response
RSS








Login or Register to participate    


English 

English


 

简体中文


 

Français


 

Deutsch


 

日本語


 

Español


 

Help 

Store  

Backup Exec


 

Endpoint Protection (AntiVirus)


 

SSL Certificates


 






Video Screencast Help
















Security Response 
Scarab attackers took aim at select Russian targets since 2012
The Scarab attack group has been distributing back door threats, Trojan.Scieron and Trojan.Scieron.B, to Russian-speaking individuals both inside and outside of Russia.

     Created: 22 Jan 2015 13:57:40 GMT • Updated: 23 Jan 2015 01:33:47 GMT     




Gavin O Gorman Symantec Employee






+3
3 Votes  




Login to vote












  Tweet


Contributor: Yi Li
A group of attackers, which we call Scarab, has been performing highly targeted attacks against particular Russian-speaking individuals both inside and outside of Russia since at least January 2012. In each campaign, the attackers typically target a small amount of individuals—rather than enterprises or governments—using economic, military, topical, or generic lures. On average, less than ten unique computers are infected per month and there is no indication that the attackers are trying to spread through the victim’s local network, suggesting that Scarab’s campaigns are extremely targeted in nature.
Many of Scarab’s campaigns focus on distributing the group’s custom malware (Trojan.Scieron and Trojan.Scieron.B) through emails with malicious attachments. These files contain exploits that take advantage of older vulnerabilities that are already patched by vendors. If the attackers successfully compromise the victims’ computers, then they use a basic back door threat called Trojan.Scieron to drop Trojan.Scieron.B onto the computer. Trojan.Scieron.B has a rootkit-like component that hides some of its network activity and features more enhanced back door functionality.
Who are the Scarab attackers?
	Based on our research, the Scarab attackers are a technically capable group, judging on how they have custom-developed several malicious tools for these campaigns. However, they are not highly skilled or well resourced, as they rely on older exploits and executables stored in compressed archives to distribute their threats.
There are some indications (based on language resources) that the attackers are familiar with Chinese-language characters, and they seem to mostly target Russian speakers located in Russia and other regions around the world.

Figure 1. Scarab victims based on Symantec telemetry
The group conducts command-and-control (C&C) operations almost exclusively through the use of dynamic domain name system (DNS) domains. The C&C servers are usually hosted in South Korea; however, there have been instances where servers were located in other countries.
For the majority of 2012, there was not much information about Scarab’s victims. However from October 2012, a number of emails used by Scarab were blocked by Symantec .Cloud. All of the emails were sent from @yandex.ru email addresses.
Early attacks
	On October 29, 2012, an email with the Russian-language subject “Экспериментальное определение эффективно” was sent to two individuals working for a large retail organization. Translated to English, the email’s subject is “Experimental definition is effective.”
These emails contained Microsoft Word attachments that triggered an exploit taking advantage of the Microsoft Windows Common Controls ActiveX Control Remote Code Execution Vulnerability (CVE-2012-0158). Once triggered, the exploit dropped a copy of Trojan.Scieron onto the victim’s computer. The attackers continued to intermittently send emails with .doc malware droppers until August 2013.
On January 22, 2013, the Scarab attackers sent an email with the English-language subject “Joint Call For Papers - Conferences / Journal Special Issues, January 2013” to two individuals. The attackers sent the message to email accounts associated with an Australian-funded academic research project that had concluded in 2010. It is possible that the researchers were continuing to use the email accounts for unrelated topics and this was why the attackers chose to target them. Seven days later, another email was sent to the same two individuals, this time with a Russian-language subject of “Информация по обслуживанию высвобожденны,” which translates to “Service-related information are released” (sic).
G20 summit focus
	From this point on, at least until January of 2014, the attackers moved to finance-related lures and targets. In April, the attackers sent an email with the subject “G20 receives clean bill of health at Boao” to a European government target.
In August, they sent another email to six people working for an international economic organization. This email had the Russian language subject of “G20 на 2013 г” which translates to “G20 for 2013.”
In August, a final G20-related email was sent to two individuals working in the Economic Ministry of a European government. That email had the English-language subject “About G20 details.”
Russian news lures
	There were no further emails discovered and no active infections detected until January 2014, when Scarab’s activity resumed and continued up to now. From that month on, the attackers have been using “.scr” files to drop Trojan.Scieron. The titles of these .scr files are usually in Russian, and are a hint as to the nature of the targets. It’s very likely that the .scr files are being delivered by email; however, this has not been confirmed. It is also likely and again, unconfirmed that the .scr files are embedded in .rar files.
One example of the group’s malicious .scr file names is “Россия к 2016 году проведет испытания газовых турбин для военных кораблей.” This translates to “Russian Federation to 2016 will test gas turbines for warships.” The title comes from an article, published in June 2014, on a Russian media website.

Figure 2. The attackers used the titles of news articles from a Russian media site for their malicious files’ names
Another more recent file name was “план работы на июнь 2014 года.doc.scr” which translates to the quite generic “work plan for June 2014 year.doc.src.”
Looking at the total number of infections per country in Figure 1 based on Symantec telemetry, it’s clear that Russia, or at least Russian speakers, are the primary targets of the Scarab attackers, although non-Russian speakers have been targeted as well.
Scarab’s malware
	In all of these campaigns, the attackers have attempted to compromise victims’ computers with a variant of Trojan.Scieron. This is a basic back door threat that is used to download additional malware onto the target’s computer.
The main payload of Trojan.Scieron is within a DLL file. This file is dropped either from a Trojanized Microsoft Word document or from other PE files.
Once the Trojan compromises the victim’s computer, it is able to perform the following actions:

Gather system information, such as the computer name, host name, operating system version, and drive type
Download additional files
Execute files
Retrieve specific files from the victim’s computer
List directories
Delete files
Move files to other folders

In most of the investigated incidents, Trojan.Scieron has been used to download an enhanced version of itself, which Symantec detects as Trojan.Scieron.B. This threat includes a basic ‘rootkit-like’ tool which hides some of its network activity.
Trojan.Scieron.B’s file names seen to date are usually seclog32.dll (back door) and hidsvc.dat (rootkit). The back door’s functionality includes the following features:

Create, list, and terminate processes
Read, set, and delete registry entries
Read, write, list, and delete files and directories
Gather cached URLs
Launch remote shell
Gather recent active files
Retrieve details from its configuration file

Trojan.Scieron.B’s ‘rootkit’ functionality allows it to hide a Transmission Control Protocol (TCP) port in communications.
Symantec and Norton protection
	The Scarab attackers have been consistently targeting a select number of victims with custom malware over the last few years. While the group uses older exploits, their campaigns seem to have had some success, judging on how they have continued to operate similar campaigns over the years. The attackers’ focus on Russian speakers shows that they have specific targets in mind and they continue to adjust the subject of their email campaigns to successfully compromise their victims.
Symantec .Cloud blocks emails that come from the Scarab attackers. Symantec and Norton products also offer the following detections against Scarab’s custom malware:

Trojan.Scieron
Trojan.Scieron.B

In general, you should adhere to the following best practices to prevent Scarab’s attacks from compromising your computer:

Exercise caution when receiving unsolicited, unexpected, or suspicious emails.
Avoid clicking on links in unsolicited, unexpected, or suspicious emails.
Avoid opening attachments in unsolicited, unexpected, or suspicious emails.
Update the software, operating system, and browser plugins on your computer to prevent attackers from exploiting known vulnerabilities.
Use comprehensive security software, such as Norton Security, to protect yourself from malware.

Indicators of compromise (IoC)
	For a full list of IoCs, please check out our indicators of compromise document.





Blog Entry Filed Under:
Security, Security Response, Endpoint Protection (AntiVirus), APT, G20 Summit, Russia, Scarab, targeted attacks, Trojan.Scieron
















Upcoming Events




 Philadelphia Security & Compliance User Group Meeting - January 28, 2015 
 28 Jan, 2015 - 9:00 EST  

 Symantec Control Compliance Suite 11.0: Administration 
 02 Feb, 2015 - 11:00 EST  

 End of Support Should Not End Your Business: Planning for Windows Server 2003 End of Life 
 19 Feb, 2015 - 10:00 PST  

 Symantec Control Compliance Suite (CCS) 11.0 Administration 
 02 Mar, 2015 - 9:00 CST  

 


 


Links


Technical Support


Symantec Training


Symantec.com


Purchase Endpoint Protection Small Business Edition


Purchase SSL Certificates


Website Security Solutions Knowledge Base




 


About Security Response Blog


Our security research centers around the world provide unparalleled analysis of and protection from malware, security risks, vulnerabilities, and spam.



 


Recent Blog Posts

Scarab attackers took aim at select Russian targets since 2012 • Gavin O Gorman • 23 Jan 2015 01:33:47 GMT
Unconfirmed zero-day vulnerability discovered in Adobe Flash Player  • Symantec Security Response • 23 Jan 2015 14:38:42 GMT
Tubrosa threat drives millions of views to scammers’ YouTube gaming videos • Christian Tripputi • 23 Jan 2015 13:14:15 GMT
LinkedIn Alert: Scammers use security update to phish for credentials • Satnam Narang • 14 Jan 2015 15:59:28 GMT
Japanese one-click fraud evolves to lock smartphone browsers • Joji Hamada • 14 Jan 2015 03:06:06 GMT
 


 


Filter by:



Author
Alan Neville
Amado Hidalgo
Amanda Grady
Anand Muralidharan
Andrea DelMiglio
Andrea Lelli
Ashish Diwakar
Avdhoot Patil
Ben Greenbaum
Ben Nahorney
Binny Kuriakose
Brian Ewell
Brian Hernacki
Candid Wueest
Cathal Mullaney
Christopher Mendes
Daniel Regalado
Dave Cole
David McKinney
Dermot Harnett
Dick O'Brien
Dinesh Theerthagiri
Dylan Morss
Elia Florio
Eric Chien
Eric Park
Flora Liu
Fred Gutierrez
Gavin O Gorman
Greg Ahmad
Henry Bell
Hiroshi Shinotsuka
Hon Lau
Irfan Asrar
Jeet Morparia
Jeremy  Ward
Jim Hoagland
Jitender Sarda
John-Paul Power
John McDonald
John  McDonald
Joji Hamada
Joseph Blackbird
Kaoru Hayashi
Karthikeyan Kasiviswanathan
Karthik Selvaraj
Kazumasa Itabashi
Kelly Conley
Kevin Savage
khaley
Laura O'Brien
Liam O Murchu
Lionel Payet
Livian Ge
M.K. Low
Marc Fossi
Mario Ballano
Masaki Suenaga
Mathew Maniyara
Mayur Kulkarni
Mimi Hoang
Mircea Ciubotariu
Nick Johnston
Nicolas Falliere
Nishant Doshi
Oliver  Friedrichs
Ollie  Whitehouse
Orla Cox
Parveen Vashishtha
Patrick Fitzgerald
Pavlo Prodanchuk
Peter Coogan
Peter Ferrie
PraveenSingh
Robert Keith
Roberto Sponchioni
Ron Bowes
Samir_Patil
Sammy Chu
Santiago Cortes
Sarah Gordon
Satnam Narang
Sean Butler
Sean Hittel
Security Intel Analysis Team
Shravan Shashikant
Shunichi Imano
Silas Barnes
Stephen Doherty
Suyog Sainkar
Symantec Security Response
Takako Yoshida
Takashi Katsuki
Téo Adams
Val S
Vikram Thakur
Vincent Weafer
Vivian Ho
Yazan Gable
Zulfikar Ramzan




Language
English
Japanese
Chinese, Simplified
Spanish
Portuguese, Brazil
Korean
Chinese, Traditional
Russian
German
French
Italian
Turkish





 


Recently on Twitter

threatintel 

Kids develop tool to educate others about cybersecurity http://t.co/zBNE4JU9IK23 Jan 2015
Google hands out more than US$88,000 for #Chrome bug discoveries http://t.co/RkB4VwIqcm (@darrenpauli)23 Jan 2015
We updated our blog on unconfirmed Flash #0day with additional info on protection & mitigation http://t.co/4dFTLM8mND http://t.co/S7qhNqxDsJ22 Jan 2015
Find out how the Scarab group attacked select Russian-speaking targets with back door #Trojans http://t.co/KoTYaDD4SM http://t.co/f5biIW1Azk22 Jan 2015
Microsoft to offer Windows 10 for free to Windows 7, 8, and 8.1 users http://t.co/Z6Zx1HihLc (@maryjofoley) #Windows1022 Jan 2015





 


Blog Tags



Endpoint Protection (AntiVirus) Spam Online Fraud phishing Malicious Code Messaging Gateway Message Filter Symantec Protection Suites (SPS) Mail Security for Exchange/Domino Vulnerabilities & Exploits Email Security.cloud Encryption Desktop Email Encryption Symantec Endpoint Encryption - Device Control Security Risks Emerging Threats Android Microsoft Patch Tuesday Evolution of Security Trojan.Zbot facebook Mobile & Wireless W32.Stuxnet scam Malware
 


 


Security Response Blog Archive





January 2015
              (7)
          
December 2014
              (8)
          
November 2014
              (11)
          
October 2014
              (12)
          
September 2014
              (11)
          
August 2014
              (14)
          
July 2014
              (13)
          
June 2014
              (19)
          
May 2014
              (18)
          
April 2014
              (20)
          
March 2014
              (15)
          
February 2014
              (22)
          
January 2014
              (17)
          
December 2013
              (16)
          
November 2013
              (24)
          
October 2013
              (20)
          
September 2013
              (14)
          
August 2013
              (16)
          
July 2013
              (34)
          
June 2013
              (32)
          
May 2013
              (27)
          
April 2013
              (23)
          
March 2013
              (23)
          
February 2013
              (26)
          
January 2013
              (22)
          
December 2012
              (17)
          
November 2012
              (19)
          
October 2012
              (14)
          
September 2012
              (15)
          
August 2012
              (29)
          
July 2012
              (26)
          
June 2012
              (22)
          
May 2012
              (26)
          
April 2012
              (16)
          
March 2012
              (23)
          
February 2012
              (18)
          
January 2012
              (17)
          
December 2011
              (12)
          
November 2011
              (11)
          
October 2011
              (20)
          
September 2011
              (13)
          
August 2011
              (20)
          
July 2011
              (19)
          
June 2011
              (28)
          
May 2011
              (26)
          
April 2011
              (18)
          
March 2011
              (31)
          
February 2011
              (23)
          
January 2011
              (19)
          
December 2010
              (11)
          
November 2010
              (17)
          
October 2010
              (24)
          
September 2010
              (30)
          
August 2010
              (26)
          
July 2010
              (32)
          
June 2010
              (26)
          
May 2010
              (26)
          
April 2010
              (32)
          
March 2010
              (31)
          
February 2010
              (30)
          
January 2010
              (26)
          
December 2009
              (21)
          
November 2009
              (32)
          
October 2009
              (38)
          
September 2009
              (21)
          
August 2009
              (31)
          
July 2009
              (36)
          
June 2009
              (24)
          
May 2009
              (23)
          
April 2009
              (35)
          
March 2009
              (43)
          
February 2009
              (25)
          
January 2009
              (29)
          
December 2008
              (17)
          
November 2008
              (21)
          
October 2008
              (22)
          
September 2008
              (17)
          
August 2008
              (22)
          
July 2008
              (8)
          
June 2008
              (8)
          
May 2008
              (9)
          
April 2008
              (18)
          
March 2008
              (20)
          
February 2008
              (30)
          
January 2008
              (29)
          
December 2007
              (34)
          
November 2007
              (42)
          
October 2007
              (45)
          
September 2007
              (31)
          
August 2007
              (41)
          
July 2007
              (35)
          
June 2007
              (34)
          
May 2007
              (38)
          
April 2007
              (41)
          
March 2007
              (55)
          
February 2007
              (45)
          
January 2007
              (43)
          
December 2006
              (43)
          
November 2006
              (40)
          
October 2006
              (30)
          
September 2006
              (26)
          
August 2006
              (31)
          
July 2006
              (33)
          
June 2006
              (14)
          
May 2006
              (19)
          
April 2006
              (1)
          



 


 







 














 










 







