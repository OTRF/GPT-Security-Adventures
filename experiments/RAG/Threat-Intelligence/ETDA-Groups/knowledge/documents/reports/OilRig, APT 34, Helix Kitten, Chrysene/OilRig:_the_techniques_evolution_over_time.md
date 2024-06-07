# Reference for threat actor for "OilRig, APT 34, Helix Kitten, Chrysene"

**Title**: OilRig: the techniques evolution over time

**Source**: https://marcoramilli.com/2019/08/07/oilrig-the-techniques-evolution-over-time/

## Content









OilRig: the techniques evolution over time

































































 
close sidebar


Skip to content





Marco Ramilli Web Corner
Marco Ramilli: cyber security expert, digital entrepreneur and writer 

menuPrimary Menu 
Home
CTI Feeds
AI Ransom Monitor
About
Books
Contact
Press and Media
Cyber Threats Observatory

Cyber Threat Trends
Potential APT Detection
Malware Static Analysis
Honey Feeds


 Menu





Search for:




Press Enter / Return to begin your search.

close search form




open search form






open sidebar





scroll to discover more
back to top










OilRig: the techniques evolution over timeapt cybersecurityAugust 7, 2019 








Today I’d like to share a comparative analysis on OilRig techniques mutation over time. In particular I will refer to great analyses made by Paloalto UNIT 42 plus my own ones (HERE, HERE, HERE, etc..) and more personal thoughts. I would define this group of references as reports. Those reports have been divided into 4 timing groups in order to simplify the evaluation process. I am perfectly aware that such a division could just be indicative, as a matter of fact there is not a strict division between timing groups, it’s really hard to give a strong and strict attribution (at least in my personal point of view) and very often it’s definitely not “black and white”. However in order to better evaluate OilRig and to offer a nice timeline on the group techniques I will refer to the following time frames: 1. group_a: from 2016 to August 20172. group_b: from August 2017 to January 20183. group_c: from January 2018 to February 20184. group_d: from March 2019 to August 2019The evaluation process would take care of the following Techniques: Delivery, Exploit, Install and Command. In order to better understand those technique definitions I would add official MITRE reference codes. 
OilRig Description:According to MITRE, OilRig is a threat group with suspected Iranian origins that has targeted Middle Eastern and international victims since at least 2014. The group has targeted a variety of industries, including financial, government, energy, chemical, and telecommunications, and has largely focused its operations within the Middle East. It appears the group carries out supply chain attacks, leveraging the trust relationship between organizations to attack their primary targets. FireEye assesses that the group works on behalf of the Iranian government based on infrastructure details that contain references to Iran, use of Iranian infrastructure, and targeting that aligns with nation-state interests. This group was previously tracked under two distinct groups, APT34 and OilRig, but was combined due to additional reporting giving higher confidence about the overlap of the activity.
Delivery:The main question to try to answer on the delivery stage is: “How does OilRig evolve in threat delivery over time ?” According to reports it looks like the attacker group made a nice direction change between group_a and group_b time frames. Indeed during the group_a, the main observed delivery techniques where about Phishing (rif.T1193) and Valid Accounts (rif.T1078). A Valid Account in this era (group_a) could be defined as the super-set of default credentials to exposed infrastructures or real user accounts found through alternative channels (such as: darknets, humint, etc.). From group_b to group_d time frame OilRig started a more sophisticated Spear Phishing (rif.T1193) campaigns within malicious attachments as their main threat delivery activity. The following image shows the threat delivery phases over timeline as described.
Delivery Technique Over Time
Exploit:The main question  to try to answer on the exploit section would be: “How does OilRig evolve in Exploit techniques over time ?”. According to reports it looks like the attack group made a quite big change from group_a to group_b time frames. Indeed on group_a the attacker mostly used to exploit Exposed Infrastructure (rif. T1388) , from group_b to group_d time frames OilRig used real Compromised User Accounts extracted by Malware (rif. T1386) and spread over spear phishing campaigns as shown on delivery section. The following image shows the evolution of the exploit phases over time.
Exploit Technique Over Time
Install:The main question to try to answer on the Install section would be: “How does OilRig evolve in Installing their artifacts over the victim machines ?”. According to reports It looks like we have four differences between the four time frame groups. Maybe this technique is one of the most group characterizing technique and it could be used for post identification if you wish.  The time frame group_a is definitely the most creative one in terms of used technique. Many techniques have been used since August 2017 such as: Command Line Interface (rif. T1059), Obfuscated Files (rif. T1027), WebShell (rif.  T1100) and Timestomp (rif. T1099) in order to install Malicious actors.The time frame group_b focused its activities mainly on: process Hollowing (rif. T1093) and Scheduled Tasks (rif. T1053). On time frame group_c OilRig moved its attention on Scheduled Tasks (rif. T1053) while on time frame group_dit re-introduced the Command Line Interface (rif. T1059).The following image shows the evolution of the four  classified time frames over time.
Install Technique Over Time
Command:the main question to try to answer on the Command section would be: “How does OilRig evolve in Command and Control communications over time ?”. Again according to reports it looks like in group_a time frame the OilRig was mostly focused on extracting direct data without any specific and/or crafted infrastructure, while from time frame group_b the group began to introduce a custom Command and Control Protocol (rif. T1094) mainly developed using DNS resolutions (which is actually one of the main characteristic of the attacker group). On group_c time frame looks like OilRig introduced a Fallback Channel (rif. T1008) in addition to the Custom Command and Control Protocol (rif.T1094). During group_d time frame the attacker group introduced additional two layers: Data Encoding (rif T1132) and Custom Cryptographic Protocol (rif. T1024) which took the group to have some of the most effective infrastructures known today. The following image shows the evolution of Command technique during the four classified time frames.
Command&Control Technique Over Time
The most interesting historical evolution happened on Install and Control techniques. Indeed the group made huge improvements in Control techniques by building up layers of security in their objective. The group looks very harmonious on this stage, actually they developed layered software in order to improve what was already developed without apparently forking too much dissipating efforts. They begun development by introducing crafted communication protocol over DNS and later they added, to such a layer, encoding and encryption self build protocols. On the Installation  phase the group followed the general trends even if the process Hollowing technique used on group_b is quite interesting and personally never seen, but according to reports (mostly from Unit42) they used such a technique even if it is generally attributed to Gorgon Group (which is another story..).
Share this:Click to share on Twitter (Opens in new window)Click to share on Facebook (Opens in new window)Click to share on Reddit (Opens in new window)Click to share on WhatsApp (Opens in new window)Click to share on LinkedIn (Opens in new window)Click to share on Telegram (Opens in new window)Click to email a link to a friend (Opens in new window)Like this:Like Loading...

Posted in apt cybersecurityTagged apt CyberSecurity oilrig Research






 


				Published by marcoramilli 


			Ethical Hacking, Advanced Targeted Attack Expert and Malware Evasion Expert			
				View all posts by marcoramilli			





Related


Post navigation
Scraping the TOR for rare contentsTOP 100 Cyber Security Blog
 



				2 thoughts on “ OilRig: the techniques evolution over time ” 



				Pingback: Daily NCSC-FI news followup 2019-08-07 – Kurittu.org 



				Pingback: OilRig APT group: the evolution of attack techniques over time | Deep Security News 


Comments are closed.












Marco Ramilli Web Corner


					
					
					Theme: Eris by Themes Kingdom.
				







 














 




















































































Loading Comments...



 


Write a Comment...




Email



Name



Website

















































%d


