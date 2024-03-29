# Reference for threat actor for "SaintBear, Lorec53"

**Title**: Ukraine’s CERT Warns Threat Actors For Fake AV Updates - Security Investigation

**Source**: https://www.socinvestigation.com/ukraines-cert-warns-russian-threat-actors-for-fake-av-updates/

## Content






Ukraine’s CERT Warns Threat Actors For Fake AV Updates - Security Investigation
































































Facebook





Instagram





Linkedin

 





Home
Active Directory Attack
Network Attack
SIEM
TOOLS
IOC
Mitre Att&ck
E-Mail Attack
 









Search















Security Investigation

Be the first to investigate









Home
Active Directory Attack




 

CVE-2023-21554 – Hunt For MSMQ QueueJumper In The Environment 




 

OS Credential Dumping- LSASS Memory vs Windows Logs 




 

Credential Dumping using Windows Network Providers – How to Respond 




 

The Flow of Event Telemetry Blocking – Detection & Response 




 

UEFI Persistence via WPBBIN – Detection & Response 

 


Network Attack




 

Recovering SAP Data Breaches Caused by Ransomware 




 

How Does DGA Malware Operate And How To Detect In A… 




 

What is Port Forwarding and the Security Risks? 




 

CVE-2021-4034 – Polkit Vulnerability Exploit Detection 




 

DNSSEC – Domain Name System Security Extensions Explained 

 


SIEM




 

Remote Desktop Gateway – What Is It 




 

How to Detect Malware C2 with DNS Status Codes 




 

How to Bypass DLP Policies & General Defense Strategies 




 

The Most Important Data Exfiltration Techniques for a Soc Analyst to… 




 

Top Most Asked Splunk Interview Questions and Answers 2023 

 


TOOLS




 

ProcDOT- A Revolutionary Visual Malware Analysis Tool 




 

The Interactive Disassembler – IDA Pro 




 

Pestudio: Initial Malware Assessment Made Simple 




 

Wireshark Filters for Security Analyst 




 

How to Perform Static Code Analysis on Packed Malware ? 

 


IOC




 

Phishing Scam Alert: Fraudulent Emails Requesting to Clear Email Storage Space… 




 

Vidar Infostealer Malware Returns with new TTPS – Detection & Response 




 

New WhiskerSpy Backdoor via Watering Hole Attack -Detection & Response 




 

RedLine Stealer returns with New TTPS – Detection & Response 




 

Understanding Microsoft Defender Threat Intelligence (Defender TI) 

 


Mitre Att&ck




 

Threat Hunting Playbooks For MITRE TACTICS 




 

Masquerade Attack Part 2 – Suspicious Services and File Names 




 

Masquerade Attack – Everything You Need To Know in 2022 




 

MITRE D3FEND Knowledge Guides to Design Better Cyber Defenses 




 

Mapping MITRE ATT&CK with Window Event Log IDs 

 


E-Mail Attack




 

How To Check Malicious Phishing Links 




 

Emotet Malware with Microsoft OneNote- How to Block emails based on… 




 

How DMARC is used to reduce spoofed emails ? 




 

Hackers Use New Static Expressway Phishing Technique on Lucidchart 




 

Weird Trick to Block Password-Protected Files to Combat Ransomware 

 


 





















Home  IOC  Ukraine’s CERT Warns Threat Actors For Fake AV Updates





IOC

Ukraine’s CERT Warns Threat Actors For Fake AV Updates

By BalaGanesh -   March 15, 2022 0 




Ukraine’s Computer Emergency Response Team is cautioning that threat actors are dispersing counterfeit Windows antivirus updates that introduce Cobalt Strike and other malware. The phishing messages imitate Ukrainian government offices offering ways of expanding network security and encourage beneficiaries to download “security updates,” which come as a 60 MB record named “BitdefenderWindowsUpdatePackage.exe.”
CERT-UA
These messages contain a connection to a French site (presently disconnected) that offers download buttons for the supposed Antivirus updates. Another site, nirsoft[.]me, was likewise found by MalwareHunterTeam to be going about as the command and control server for this mission.

When a victim downloads and run this fake BitDefender Windows update [VirusTotal], the screen below will be shown prompting the users to install a ‘Windows Update Package.’ In any case, this ‘update’ really downloads and introduces the one.exe document [VirusTotal] from the Discord CDN, which is a Cobalt Strike reference point.
In any case, this ‘update’ really downloads and introduces the one.exe document [VirusTotal] from the Discord CDN, which is a Cobalt Strike reference point.
Cobalt Strike is a penetration testing suite that offers hostile security capacities, works with sidelong organization development, and guarantees perseverance.
A similar interaction gets a Go downloader (dropper.exe) which disentangles and executes a base-64-encoded record (java-sdk.exe).
This document adds another Windows registry key for persistence and furthermore downloads two additional payloads, the GraphSteel backdoor (microsoft-cortana.exe) and GrimPlant indirect access (oracle-java.exe).
All executables in the mission are pressed on the Themida tool, which shields them from reverse engineering, detection, and analysis.
The infection chain of the uncovered campaign (CERT-UA)
GraphSteel and GrimPlant Malware payloads are written in GO. This program has minimal impression and low AV identification rates.
The capabilities of the two tools cover network reconnaissance, command execution, and file operations, so the fact that both are deployed in the same system is likely done for redundancy.
GraphSteel features:
Gather hostname, username, and IP address informationExecute commandsSteal account credentialsUse WebSocket and GraphQL to communicate with C2 using AES and base64 encryption
GrimPlant capabilities:
Gather IP address, hostname, OS, username, home dirExecute commands received remotely and return results to C2Use gRPC (HTTP/2+SSL) for C2 communication
Indicator of Compromise:
https://forkscenter[.]fr/Sdghrt_umrj6/wisw[.]exehttps://forkscenter[.]fr/https://cdn[.]discordapp[.]com/attachments/947916 997713358890/949978571680673802/cesdf[.]exehttp://45[.]84[.]0[.]116:443/ihttp://45[.]84[.]0[.]116:443/mhttp://45[.]84[.]0[.]116:443/phttps://cdn[.]discordapp[.]com/attachments/947916997713358890/949948174838165524/dropper[.]exehttps://cdn[.]discordapp[.]com/attachments/947916997713358898/949948174636830761/one[.]exe
C:\ProgramData\dropper[.]exeC:\ProgramData\one[.]exe
The Ukrainian Computer Emergency Response Team connects the recognized movement with the UAC-0056 gathering with medium certainty.UAC-0056, otherwise called “Lorec53”, is a modern Russian-speaking APT that utilizes a blend of phishing messages and custom backdoors to gather data from Ukrainian associations.
( Source: Bleeping computer & CERT-UA )







TAGSfake antivirus updates russia ukrainelatest ukraine threat intellatest ukraine threats 




Share
FacebookLinkedinTwitterPinterestTelegramReddItWhatsApp

 Previous articleSplunk Commands – Append , Chart and DedupNext articleFree Ransomware Decryption tool -No More Ransom BalaGaneshhttps://www.socinvestigation.comBalaganesh is a Incident Responder. Certified Ethical Hacker, Penetration Tester, Security blogger, Founder & Author of Soc Investigation.  




LEAVE A REPLY Cancel reply


Please enter your comment!


Please enter your name here



You have entered an incorrect email address!
Please enter your email address here




Save my name, email, and website in this browser for the next time I comment.
 

 















About Us
Contact Us
Privacy Policy
 

© Newspaper WordPress Theme by TagDiv






























