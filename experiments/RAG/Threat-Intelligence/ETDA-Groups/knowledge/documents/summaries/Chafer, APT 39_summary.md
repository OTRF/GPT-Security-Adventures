
Report 1

Summary:
The threat actor known as Chafer, APT 39, consists of two Iran-based attacker groups named Cadelle and Chafer. They have been conducting targeted surveillance on domestic and international targets, primarily in Iran, but also compromising airlines and telecom providers in the Middle East region. The groups use custom-made backdoor threats such as Backdoor.Cadelspy and Backdoor.Remexi to steal information from victims' computers. Evidence suggests that the groups have been active since at least 2011, with a focus on similar targets and working hours. Victims include individual users in Iran and organizations in the Middle East region, particularly airlines and telecom companies. The threat actors may be based in Iran based on their activity patterns and the use of the Solar Hijri calendar in their malware. The malware used by Cadelle and Chafer, such as Cadelspy and Remexi, allows for keystroke logging, data theft, audio recording, and remote access. Mitigation strategies include updating software, being cautious of unsolicited emails, and keeping security software up-to-date. Symantec security products provide protection against these threats. The threat actors are still active, and organizations should be vigilant to avoid compromise.





Report 2

APT39, also known as Chafer, is an Iranian threat group focused on the theft of personal information, operating primarily in the Middle East. The group targets telecommunications, travel, and IT firms supporting these sectors, with a global scope but concentrated activities in the Middle East. APT39 uses SEAWEED, CACHEMONEY, and a variant of POWBAT backdoors for operations. The group leverages spear phishing emails, web shells, and stolen credentials for initial compromise, followed by the use of custom backdoors for foothold establishment and lateral movement. APT39 demonstrates operational security measures to evade detection, such as repacking tools to bypass antivirus detection. The group's activities suggest a focus on surveillance and data collection for future operations, showcasing Iran's global operational reach in cyber espionage. The report was last updated on August 10, 2023.





Report 3

APT39, also known as Chafer, is a state-sponsored threat actor sponsored by the Rana Intelligence Computing Company in Iran. First seen in 2014, APT39 primarily targets the telecommunications sector, travel industry, and IT firms in the Middle East, with a focus on information theft and espionage. The threat actor uses tools such as SEAWEED, CACHEMONEY, and POWBAT backdoors, as well as novel techniques like the Python-based MechaFlounder payload. APT39 has been observed targeting victims in sectors like aviation, engineering, government, high-tech, IT, shipping, and telecommunications, operating in countries including Israel, Jordan, Kuwait, Saudi Arabia, Spain, Turkey, UAE, and the USA. The threat actor has been active in hacking operations since 2017, with reported attacks on organizations in the Middle East and beyond, including government entities and foreign diplomatic entities based in Iran. Counter operations against APT39 were reported in 2020 when the Treasury sanctioned cyber actors backed by the Iranian Intelligence Ministry.





Report 4

Summary:

The threat actor Chafer, also known as APT 39, utilized the Remexi malware to conduct cyber-espionage activities primarily targeting foreign diplomatic entities based in Iran. The malware, associated with the APT actor Chafer by Symantec, exfiltrates keystrokes, screenshots, browser data, and executes remote commands. The attackers heavily rely on Microsoft technologies, using BITS to communicate with the C2 server over HTTP. The malware developers use C programming language and GCC compiler on Windows in the MinGW environment. Persistence mechanisms include scheduled tasks and registry keys. The malware uses XOR and RC4 encryption with unique keys for different samples. The victims targeted by Chafer using Remexi appear to have Iranian IP addresses, with some being foreign diplomatic entities in Iran. The campaign has been active since at least 2015, focusing on targets inside Iran and possibly other countries in the Middle East. The malware is detected by Kaspersky Lab products as Trojan.Win32.Remexi and Trojan.Win32.Agent. The report was originally shared with APT Intelligence Reporting customers in November 2018.





Report 5

Malformed report





Report 6

Summary:
- Threat actor: Chafer, APT 39
- Region: Middle East
- Operating sector: Private and public sector entities
- Type of company: Turkish government entities
- Date: March 4, 2019
- Evidence of capability: Chafer targeted a Turkish government entity using a new Python-based payload named MechaFlounder, compiled using PyInstaller, marking the first instance of Python-based payload use by Chafer. The payload acts as a backdoor allowing file upload/download and command execution on compromised systems. Code overlap with OilRig's Clayside VBScript was observed, but the threat groups are tracked separately. The threat actor likely created a custom C2 server to handle network traffic, with evidence of code sharing between Chafer and OilRig.
- Novelty of tools and techniques: MechaFlounder uses anomalous HTTP requests for communication with the C2 server, and the threat actor developed custom functionalities for file upload/download. The threat actor also used common parameters in URLs shared with OilRig, suggesting potential code sharing. Palo Alto Networks customers are protected against this threat, and indicators of compromise have been shared with the Cyber Threat Alliance for broader protection measures.





Report 7

Summary:
The threat actor ITG07, also known as Chafer or APT39, has been targeting organizations in the transportation sector globally over the past nine months. They have been observed using a combination of legacy adversarial behaviors and newer tactics, such as a customized version of mimikatz named mnl.exe/mnl32.exe, legitimate Citrix connections for access, webshells like JSPSPY and ASPXSPY, and the TREKX custom remote access Trojan (RAT). The TREKX RAT communicates with a C&C server via HTTP requests and has a configuration file with specific parameters. ITG07 has also been observed using tools like NBTScan, Navicat, and PsExec for lateral movement and data exfiltration. The threat actor's attack framework shows their ability to gain systemic footholds, advance laterally, and exfiltrate data from targeted networks. The transportation industry is a high-value target for ITG07 due to its reliance on IT infrastructure and potential for data theft. The report provides indicators of compromise (IoCs) related to ITG07's activities. The report was published on June 14, 2019, by IBM X-Force Incident Response and Intelligence Services (IRIS).


