
Report 1

DragonOK is a threat group originating from China that has targeted Japanese organizations in the High-Tech and Manufacturing sectors with phishing emails since 2015. The group is believed to have connections with other threat groups like Moafee and Rancor due to overlapping TTPs and the use of similar custom tools. DragonOK's motivation is information theft and espionage. They have used a variety of malware such as Sysget/HelloBridge, PlugX, Poison Ivy, and others. The group has been observed targeting victims in countries like Cambodia, Japan, Russia, Taiwan, and Tibet. Their operations have involved multiple phishing attacks with variants of Sysget malware, including unique shellcode exploits. The threat actor has been linked to servers in different countries, with strong indications of being funded by China. The tools and techniques used by DragonOK have evolved over time, with new variants of malware being observed in recent attacks.





Report 2

DragonOK, a threat actor group, has been actively launching attacks targeting organizations in Japan, Taiwan, Tibet, and Russia. They have been observed using multiple new variants of the sysget malware family, delivered through phishing emails and malicious RTF documents exploiting vulnerabilities. The malware families deployed include Sysget version 2, Sysget version 3, TidePool, and IsSpace. DragonOK has updated their tools and tactics, making detection and analysis more difficult. The threat actor group is actively seeking victims in various regions, with Japan being the most heavily targeted. The C2 domains used by DragonOK include gtoimage[.]com, trend.gogolekr[.]com, and www.bestfiles[.]top. The malware samples associated with DragonOK have unique capabilities and utilize novel techniques to evade detection. The activity of DragonOK was observed in January 2017.





Report 3

Unit 42 identified a new backdoor malware named "FormerFirstRAT" deployed by the threat actor "DragonOK" against Japanese targets between January and March 2015. The attacks targeted Japanese high-tech and manufacturing firms, using phishing campaigns with Sysget malware variants. The malware communicated with a single command and control server hosted at biosnews[.]info using HTTP protocol. DragonOK also deployed five additional backdoors, including NFlog, PoisonIvy, NewCT, and PlugX, with a new custom-built tool named "FormerFirstRAT." The FormerFirstRAT communicated over unencrypted HTTP on port 443 and had capabilities such as modifying sleep timers, executing commands, browsing the file system, downloading files, and exfiltrating victim information. The threat actor used novel techniques like using decoy documents and icons to trick users into opening malicious attachments. The report provides detailed analysis of the malware functionalities and communication methods used by DragonOK.


