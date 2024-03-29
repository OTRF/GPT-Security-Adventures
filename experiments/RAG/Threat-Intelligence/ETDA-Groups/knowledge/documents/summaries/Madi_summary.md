
Report 1

Summary:
The threat actor known as Madi has been active since December 2011, utilizing a Trojan capable of stealing information and keylogging. The Trojan can update itself and has been observed communicating with command-and-control servers in Iran and Azerbaijan. Targets of the Madi campaign include oil companies, US-based think tanks, a foreign consulate, and governmental agencies, including those in the energy sector. While Madi has been seen targeting various Middle Eastern countries, it has also been found globally. Unlike other high-profile attacks, Madi relies on social engineering techniques rather than zero-day exploits. The attacks are believed to be conducted by an unknown Farsi-speaking hacker with a broad agenda. The report was last updated on July 18, 2012, to reflect telemetry data.





Report 2

Summary:
The threat actor Madi, originating from Iran, has been involved in information theft and espionage activities since at least 2011. Madi targeted victims primarily in Iran, Israel, and other countries across the globe, focusing on sectors such as education, engineering, finance, government, oil and gas, and think tanks. The victims were business people, students, and government agencies involved in critical infrastructure projects. Madi's spying activities included monitoring email accounts, social media platforms, and financial management systems. The threat actor's tools and techniques have shown novelty, with a reported resurgence in a spyware campaign in 2012. Kaspersky and Seculert conducted counter operations by sinkholing Madi's Command & Control servers to monitor the campaign.





Report 3

Summary:
The threat actor known as "Madi" has resurfaced with an updated spyware campaign targeting Middle Eastern critical infrastructure engineering firms, government agencies, financial houses, and academia. The new iteration of the Madi spyware, discovered by Kaspersky Lab researcher Nicolas Brulez, no longer waits for instructions from the Command and Control server but uploads data directly. This version of Madi can monitor the Russian social network VK and Jabber messaging platform for specific keywords and capture screenshots of user activity. The C&C server for this version of Madi is located in Montreal, a shift from previous associations with Iran. The spyware is named after a Shiite religious concept and is known for capturing screens, recording audio, and stealing sensitive information. The novel techniques used by Madi include the ability to stay silent for two days before initiating malicious activities. The report was published on July 25, 2012, by Threatpost.





Report 4

The Madi Campaign, reported on July 26, 2012, targeted victims mainly in the Middle East, with some scattered in the US and EU. The threat actor utilized a simple infrastructure with five command and control web servers running Microsoft IIS v7.0 and custom C# server manager software. The stolen data was poorly organized, requiring manual investigation by multiple operators. The majority of the victims were professionals and academia, including students and staff. The threat actor's activities were primarily traced back to Iran, with some activity in Pakistan, the US, and other countries. The threat actor used hard-coded IP addresses for communication, avoiding DNS resolution. The campaign involved infostealers and downloaders with update functionality to switch C2 servers. The timeline of activity indicated spikes in December 2011, February and March 2012, and June 2012. The report highlighted the novelty of the threat actor's approach and the ongoing investigation into new variants of the campaign.





Report 5

The Madi Campaign, targeting individuals in the Middle East, including Iran, Israel, and Afghanistan, has been ongoing for almost a year. The threat actor, named Madi, focuses on critical infrastructure engineering firms, government agencies, financial houses, and academia in the region. The attackers use social engineering techniques, such as PowerPoint slide shows with embedded trojan downloaders, to distribute spyware. They also employ the "Right to Left Override" technique to trick users into running malicious executables disguised as harmless files. The backdoors delivered to victims are coded in Delphi and packed with the UPX packer to evade security products. The campaign continues to operate, with Kaspersky products detecting the malware as Trojan.Win32.Madi. The threat actor's infrastructure includes web servers and ICMP PING packets for communication. The report provides MD5 hashes of related malware variants. The second part of the blogpost will delve into the broader infrastructure, communications, data collection, and victims of the Madi Campaign.


