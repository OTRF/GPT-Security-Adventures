
Report 1

Malformed report.





Report 2

Stealth Falcon, also known as FruityArmor, is a threat actor that has been conducting targeted spyware attacks since 2012, primarily against Emirati journalists, activists, and dissidents. Evidence suggests a link between Stealth Falcon and the UAE government, with digital artifacts traced back to government-controlled accounts. The threat actor has targeted individuals critical of the UAE government, using bait content and social media to lure victims. The victims operate in civil society groups and are based in countries such as the Netherlands, Saudi Arabia, Thailand, UAE, and the UK. Stealth Falcon has been observed using tools like Deadglyph, StealthFalcon, and 0-day exploits, with reports of zero-day exploits being used in targeted attacks. The threat actor's motivation is information theft and espionage, with reported hacking operations dating back to 2014. The latest report in 2023 indicates Stealth Falcon using Deadglyph in their operations.





Report 3

Summary:
Stealth Falcon, a threat actor group linked to the United Arab Emirates, has been targeting governmental entities in the Middle East for espionage purposes. They have been using a sophisticated backdoor named Deadglyph, which has an unusual architecture with cooperating components in native x64 binary and .NET assembly. The backdoor's commands are received dynamically from a command and control server, and it features capabilities to avoid detection. Deadglyph is attributed with high confidence to the Stealth Falcon group, known for targeting political activists, journalists, and dissidents in the region. The backdoor's novelty lies in its unique architecture, counter-detection mechanisms, and the use of additional modules for its full functionality. The victims of the analyzed infiltration were a governmental entity in the Middle East, with related samples uploaded from Qatar. The report provides detailed technical analysis of Deadglyph and its components, as well as a related shellcode downloader chain discovered during the investigation. The report was published on September 22, 2023, by ESET Research.





Report 4

Summary:
The threat actor known as FruityArmor APT was reported to have used a Windows zero-day exploit in targeted attacks, with one of the vulnerabilities being CVE-2016-3393. The exploit was discovered by Kaspersky Lab in September 2016. FruityArmor is unique in that it leverages an attack platform built entirely around PowerShell, with its primary malware implant and operator commands being in the form of PowerShell scripts. The attack chain typically involves a browser exploit followed by an EoP exploit, with the CVE-2016-3393 exploit being unpacked from a specially crafted TTF font. The vulnerability is located in the Win32k.sys system module and involves an integer overflow leading to memory corruption. The exploit was detected crashing fontdrvhost.exe in Windows 10. Kaspersky Lab detects this exploit as HEUR:Exploit.Win32.Generic and PDM:Exploit.Win32.Generic. The report was published on October 20, 2016, and more information about the FruityArmor APT group is available to customers of Kaspersky Intelligence Services.





Report 5

Summary:
- Threat actor: Stealth Falcon, FruityArmor
- Date: October 10, 2018
- Region: Middle East
- Victims: Small number of victims in the Middle East region
- Operating sector: Not specified
- Type of company: Not specified
- Evidence of capability: Exploited zero-day vulnerability (CVE-2018-8453) in win32k.sys, high-quality code targeting multiple Windows builds, limited number of attacks detected
- Novelty of tools and techniques: Advanced exploit techniques, use of PowerShell backdoor previously associated with FruityArmor APT, sophisticated implant for persistent access
- Attribution: FruityArmor assessed with medium confidence as responsible for attacks
- Conclusion: Highly targeted campaign with low number of victims, indicates resources and sophistication of threat actor.





Report 6

Summary:
- Threat actor: Stealth Falcon, FruityArmor
- Region: Global
- Operating sector: Various industries including National Cybersecurity, Industrial Cybersecurity, Finance Services Cybersecurity, Healthcare Cybersecurity, Transportation Cybersecurity, Retail Cybersecurity, and Telecom Cybersecurity
- Type of company targeted: Small, medium, and enterprise businesses
- Date: October 2018
- Evidence of capability: Discovered zero-day vulnerability in Windows Kernel Transaction Manager (CVE-2018-8611) that can lead to Remote Command Execution exploit chain in modern web browsers
- Novelty of tools and techniques: Exploit heavily relies on C++ exception handling mechanisms with custom error codes, bypasses modern process mitigation policies, and can be used by multiple threat actors including FruityArmor and SandCat
- Detection: Kaspersky Lab products detected the exploit proactively through various technologies
- Verdicts for artifacts: HEUR:Exploit.Win32.Generic, HEUR:Trojan.Win32.Generic, PDM:Exploit.Win32.Generic
- Additional information: Proof of concept provided to Microsoft, shared through Microsoft Active Protections Program (MAPP), more details available to customers of Kaspersky Intelligence Reports.


