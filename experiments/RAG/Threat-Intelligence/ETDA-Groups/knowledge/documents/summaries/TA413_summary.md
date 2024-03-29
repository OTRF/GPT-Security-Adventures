
Report 1

Summary:
Chinese APT threat actor TA413 resumed targeting Tibet following a COVID-19 themed economic espionage campaign delivering Sepulcher malware to European targets. The campaign targeted European diplomatic and legislative bodies, non-profit policy research organizations, and global organizations dealing with economic affairs. The threat actor utilized known sender email addresses associated with historic Chinese APT campaigns targeting the Tibetan community. The Sepulcher malware, observed in March and July 2020, demonstrated basic RAT capabilities for intelligence gathering and reconnaissance. The threat actor's shift from targeting Western economies during the pandemic to resuming conventional Tibetan community targeting showcases a rapidly evolving cyber threat landscape in 2020. The reuse of known sender accounts and delivery methods, along with the recycling of delivery infrastructure, indicate a possible opsec failure in response to global crises. The campaign's focus on European entities and Tibetan dissidents highlights TA413's adaptability and persistence in cyber espionage activities. 

Date: September 01, 2020

Region: Europe (European targets), Tibet (Tibetan dissidents)

Operating Sector: Economic, diplomatic, legislative, non-profit policy research organizations

Type of Company: Global organizations dealing with economic affairs

Capability of Threat Actor: Utilized COVID-19 themed lures, historic sender email addresses, basic RAT capabilities for intelligence gathering and reconnaissance

Novelty of Tools and Techniques: Recycling of delivery methods, reuse of known sender accounts, shift in targeting from Western economies to Tibetan community, adaptation to global crises

Malformed report





Report 2

Chinese State-Sponsored Group TA413 has been targeting the Tibetan community for surveillance and intelligence-gathering purposes. They have been observed exploiting a zero-day vulnerability in Sophos Firewall (CVE-2022-1040) and using a custom backdoor named LOWZERO in campaigns targeting Tibetan entities. TA413 is likely conducting cyber espionage on behalf of the Chinese state and shares capabilities with other Chinese state-sponsored groups. They have also been observed using the Royal Road RTF weaponizer and adopting new techniques like the Follina vulnerability (CVE-2022-30190). The group has historical ties to Tropic Trooper activity and has been targeting organizations associated with the Tibetan community persistently. TA413's infrastructure procurement tendencies and tooling practices suggest separate teams involved in malware development and operations. The group's adoption of zero-day vulnerabilities and new techniques indicates a trend in Chinese cyber-espionage groups. The report covers activity observed in the first half of 2022 and provides detailed technical analysis of the group's custom backdoor LOWZERO. (Source: Recorded Future, 22nd September 2022)





Report 3

TA413, a threat actor also known as White Dev 9, has been active since 2019, with evidence of novel tactics observed in 2020 during the COVID-19 pandemic. The threat actor has been linked to phishing campaigns targeting European diplomatic bodies, non-profit organizations, and global economic entities using malware such as Sepulcher and ExileRAT. TA413 has shown a shift in targets from the Tibetan community to Western economies affected by COVID-19, indicating a strategic realignment of interests. The threat actor has been associated with Chinese state interests, focusing on information theft and espionage. TA413 has been observed operating in Tibet and Europe, with reported hacking operations targeting Tibetan organizations using tools like FriarFox browser extension and exploiting Microsoft Office zero-day vulnerabilities. The threat actor's capabilities have been evolving, as seen in their adoption of new tools and techniques to pursue Tibetan targets.





Report 4

Summary:
TA413, a threat actor aligned with the Chinese Communist Party, targeted the Gmail accounts of global Tibetan organizations using a new malicious browser extension named "FriarFox". The threat actor also delivered Scanbox and Sepulcher malware to Tibetan organizations. The campaign, observed since March 2020, continued in January and February 2021. TA413's activities are believed to be associated with espionage and civil dissident surveillance, particularly targeting the Tibetan Diaspora. The threat actor leveraged social engineering tactics, modified open source tools, and shared reconnaissance frameworks like Scanbox. The campaign demonstrated TA413's adaptability and persistence in targeting dissident communities. The report provides detailed technical analysis of the tools and techniques used by TA413, including indicators of compromise and links to previous campaigns. The campaign's delivery methods included phishing emails with COVID-19 and self-immolation themes, delivering malicious RTF files and browser extensions. TA413's use of modified open source tools and dated malware frameworks showcases their evolving tactics in targeting global dissident organizations. The report includes indicators of compromise and ET signatures for detection. The campaign highlights TA413's continued targeting of the Tibetan Diaspora with a variety of tools and techniques.





Report 5

Summary: Chinese APT hackers, specifically the TA413 group, have been actively exploiting a Microsoft Office zero-day vulnerability (CVE-2022-30190) in the Microsoft Windows Support Diagnostic Tool (MSDT) to execute remote code on Windows systems. The attacks target the international Tibetan community, using malicious Word documents delivered in ZIP archives. The threat actor has been observed using URLs to deliver these documents, impersonating the 'Women Empowerments Desk' of the Central Tibetan Administration. The vulnerability allows attackers to run arbitrary code with the privileges of the calling application, potentially leading to data theft or account creation. Mitigation measures include disabling the MSDT URL protocol and the Preview pane in Windows Explorer. The first attacks exploiting this vulnerability were reported over a month ago, using sextortion threats and invitations to Sputnik Radio interviews as lures. The report was published on May 31, 2022.


