
Report 1

BlackOasis is a Middle Eastern threat group with a history of targeting prominent figures in the United Nations, opposition bloggers, activists, regional news correspondents, and think tanks. The group is believed to be a customer of Gamma Group and has been associated closely with a group known as Neodymium. Their motivation is information theft and espionage, with observed attacks in sectors such as media, think tanks, activists, and the UN in countries like Afghanistan, Angola, Bahrain, Iran, Iraq, Jordan, Libya, Netherlands, Nigeria, Russia, Saudi Arabia, Tunisia, and the UK. BlackOasis has been known to use tools like FinFisher, Wingbird, and exploit zero-day vulnerabilities in Flash. They have conducted hacking operations dating back to 2015, leveraging zero-day exploits like CVE-2015-5119, CVE-2016-0984, CVE-2016-4117, and CVE-2017-8759 to deliver FinSpy malware. The group's use of novel tools and techniques, along with their targeted approach, demonstrates their advanced capabilities in cyber espionage.





Report 2

BlackOasis APT, a threat actor, has been targeting victims in various regions, including Russia, Iraq, Afghanistan, Nigeria, and others. The threat actor has been active since at least May 2016, utilizing zero-day exploits such as CVE-2017-11292 and CVE-2017-8759. The attacks involve the delivery of an Office document containing an ActiveX object with Flash exploits, leading to the installation of FinSpy malware. BlackOasis has targeted individuals involved in Middle Eastern politics, United Nations figures, and regional news correspondents. The threat actor's tools and techniques, including a custom virtual machine and anti-analysis techniques, demonstrate advanced capabilities. The attacks have been highly targeted and linked to previous zero-day exploits, indicating a sophisticated and persistent threat actor. The report was published on October 16, 2017, by Kaspersky Lab.





Report 3

Summary:
- Threat actor "BlackOasis" utilized a zero-day vulnerability CVE-2017-8759 to distribute FINSPY malware targeting Russian speakers.
- The attack involved a malicious Microsoft Office RTF document that injected arbitrary code to download and execute a Visual Basic script containing PowerShell commands.
- FINSPY, also known as FinFisher or WingBird, is a commercially available malware used for cyber espionage purposes.
- The vulnerability allowed the threat actor to inject and execute arbitrary code through a code injection vulnerability in the WSDL parser module.
- The attack leveraged a Rich Text Format (RTF) document with embedded SOAP monikers to facilitate exploitation.
- The malware, disguised as a .jpg file, was actually an executable that was downloaded and executed after successful exploitation.
- The FINSPY variant used heavily obfuscated code and anti-analysis techniques to make reversing more difficult.
- This incident marks the second zero-day vulnerability used by BlackOasis to distribute FINSPY in 2017, highlighting the significant resources available to "lawful intercept" companies.
- The threat actor's capability to exploit zero-day vulnerabilities and use novel techniques underscores the sophistication and persistence of the BlackOasis group.
- The report was published on September 12, 2017, by FireEye, providing detailed insights into the tactics, techniques, and procedures employed by the threat actor.


