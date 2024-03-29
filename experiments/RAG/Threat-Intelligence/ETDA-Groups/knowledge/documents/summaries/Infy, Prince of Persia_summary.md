
Report 1

Summary:
The threat actor known as Infy, also referred to as Prince of Persia, has been active since 2007 and is believed to be of Iranian origin with potential connections to the Iranian state. The group has targeted human rights activists and Iranian civil society, with a focus on information theft and espionage. They have been observed using malware tools such as Infy and Tonnerre, with new versions of their malware showing design failures. The victims targeted operate in government and private sectors across various countries including Azerbaijan, Canada, China, France, Germany, and the USA. Infy's activities have been reported in hacking operations such as sending malicious documents via email and evolving their malware to avoid detection and sinkholing of their Command and Control infrastructure. Counter operations against the threat actor have been conducted, with one operation known as "Prince of Persia - Game Over" reported in June 2016.





Report 2

Summary:
- Threat actor named "Infy" has been active in targeted attacks since 2007, with attacks still ongoing as of April 2016.
- The threat actor uses a malware family called "Infy" that is distributed through spear-phishing emails containing Word or PowerPoint documents with multi-layer Self-Extracting Executable Archives.
- The malware installs a DLL file that collects environment data, initiates a keylogger, steals browser passwords, and exfiltrates data to Command and Control (C2) servers.
- The threat actor uses specific geographic targeting in their attacks, with evidence of attacks against Israeli, U.S. Government, and Danish Government targets.
- The malware has evolved over the years, with the latest version supporting the Microsoft Edge browser.
- The threat actor has been linked to Iran based on the infrastructure and email accounts used in the attacks.
- The malware is named "Infy" based on strings found in filenames and C2 communications.
- Two variants of the malware, "Infy" and "Infy M," have been identified, with the latter targeting high-value victims and having additional features like screen capture and document upload.
- The threat actor has been able to evade detection by antivirus programs by using generic signatures.
- The activity is believed to be a decade-long operation focused on targeted espionage against governments, businesses, and citizens of multiple nations.
- Palo Alto Networks provides protection against this threat through WildFire, Threat Prevention, and AutoFocus.





Report 3

The threat actor known as "Infy" evolved into "Foudre" in February 2017, with new anti-takeover techniques to avoid sinkholing of their C2 domains. The malware, similar to its predecessors, is an information stealer with keylogging capabilities and system information collection. Foudre uses a Domain Generation Algorithm (DGA) to determine C2 domains and implements RSA signature verification for C2 domain authenticity. The malware uses spear-phishing emails for initial infection and has mechanisms to check for updates and exfiltrate stolen data. The threat actor targets victims in Iran, the United States, and Iraq, with a focus on non-financial motivations. The malware's C2 infrastructure is located in Canada, with DGA-generated domains and RSA signature verification for defense. The report details the malware's capabilities, infection vectors, and C2 mechanisms. The threat actor's persistence and use of novel techniques make them a significant threat. The report provides IOCs and hashes for detection and protection measures for Palo Alto Networks customers.


