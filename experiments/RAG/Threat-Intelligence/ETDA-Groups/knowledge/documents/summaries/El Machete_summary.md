
Report 1

Summary:
- Threat actor "El Machete" is a Spanish-speaking cyber espionage campaign targeting victims in Latin America, Russia, Cuba, and Spain, including high-level profiles such as intelligence services, military, embassies, and government institutions.
- The campaign started in 2010 and was renewed in 2012, with capabilities including logging keystrokes, capturing audio, screenshots, geolocation data, webcam photos, file copying, and clipboard hijacking.
- The malware is distributed through social engineering techniques like spear-phishing emails and fake blog websites, with no evidence of zero-day exploits.
- Notable is the use of Python embedded in Windows executables, with preparations for Mac OS X and Unix victims, as well as a mobile (Android) component.
- Indicators of compromise include specific domains, infection artifacts, and traces on infected machines.
- The campaign's language consistency in Spanish suggests both attackers and victims are Spanish-speaking.
- Kaspersky Lab products detect related samples as Trojan-Spy.Python.Ragua.
- The report provides detailed technical analysis and is available to Kaspersky Intelligent Services customers.





Report 2

Summary:
- Threat actor "El Machete" has been operating predominantly in Latin America since 2014, targeting high-profile entities such as intelligence services, military, utility providers, embassies, and government institutions.
- The threat actor has targeted victims in countries like Ecuador, Venezuela, Peru, Argentina, and Colombia, as well as in Korea, the United States, and several European countries.
- El Machete uses phishing emails with links to ZIP or RAR archives containing malicious executables with SCR extensions.
- The threat actor employs obfuscation techniques using NSIS and self-extracting RAR executables for malware delivery.
- El Machete uses Python scripts encoded with PY2EXE for various functions like screen capture, keystroke logging, and data exfiltration.
- The group relies on TLS-encrypted FTP for data transfer and free dynamic DNS domains for Command and Control (C2) infrastructure.
- Persistence is achieved through scheduled tasks and the startup folder, with droppers commonly named 'jsx.scr' or 'RAVBg.scr'.
- El Machete's malware employs AES encryption for file exfiltration and uses XOR encoding for configuration files.
- The threat actor has low detection rates by antivirus solutions and continues to operate successfully despite publicly available indicators.
- El Machete's use of custom malware and sophisticated techniques indicates a high level of capability and persistence.

Date: 03.22.17

Region: Latin America

Operating Sector: Intelligence, military, utility providers, embassies, government institutions

Type of Company: Various high-profile entities





Report 3

Summary:
The threat actor known as El Machete, also identified as TEMP.Andromeda, APT-C-43, ATK 97, and TAG-NS1, has been active since 2010 with a focus on information theft and espionage. Operating primarily in Spanish-speaking regions, the group targets sectors such as Defense, Education, Embassies, Energy, Government, and Telecommunications across multiple countries including Argentina, Russia, Spain, and the USA. The malware is distributed through social engineering tactics like spear-phishing emails and fake websites, with no evidence of zero-day exploits being used. El Machete has been observed using tools like LokiBot, Machete, Pyark, and Living off the Land, with operations reported as recently as March 2022 targeting financial organizations in Nicaragua. The threat actor has shown the capability to evade detection by frequently changing C2 infrastructure and making minimal changes to malware. Their use of novel tools like Pyark and sophisticated spear-phishing tactics demonstrate an ongoing threat to organizations globally.





Report 4

Summary:
A threat actor known as "El Machete" has been conducting cyberespionage operations targeting Venezuelan government institutions, particularly the military forces, education, police, and foreign affairs sectors, as well as other countries in Latin America. The group behind the attacks has stolen gigabytes of confidential documents and remains active, regularly updating its malware, infrastructure, and spearphishing campaigns. The threat actor uses a Python-based toolset called Machete, which has evolved with new features since its first appearance in April 2018. The group employs effective spearphishing techniques, sending specific emails containing links or attachments to decoy documents to victims. The malware components include a downloader, backdoor, and dropper, with capabilities such as data exfiltration, geolocation tracking, and remote file execution. The threat actor has shown resilience and adaptability, introducing changes to its tools and techniques despite public exposure. The group's activities demonstrate a high level of sophistication and persistence in targeting government organizations in Latin America. The report provides detailed technical analysis and indicators of compromise for further investigation.





Report 5

Summary:
The threat actor "El Machete" identified as APT-C-43 targeted Venezuelan military institutions to steal military secrets in support of the reactionaries during the HpReact campaign. The attack coincided with Venezuelan political turmoil, with assets deployed in Colombia and Venezuela. The threat actor, linked to the APT group Machete with Spanish roots, has been active since 2019 targeting military, embassies, and government agencies in Latin America. APT-C-43 used a new backdoor Pyark written in Python and deployed phishing emails to infiltrate victim machines, utilizing FTP and HTTP protocols for network communication. The threat actor demonstrated advanced capabilities in monitoring, stealing sensitive data, and deploying backdoor components, showcasing innovation in attack techniques. The campaign posed a significant national security threat to Venezuela, highlighting the importance of cybersecurity in the face of escalating cyber warfare. The attack was detected and analyzed by 360 Total Security, with the Baize Lab focusing on APT testing and research. The operation timeframe was approximately two years, with evidence of ongoing cyber warfare activities in Latin America.


