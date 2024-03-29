
Report 1

Summary:
- Threat actor named Operation WizardOpium used a Chrome 0-day exploit CVE-2019-13720 targeting Google Chrome browser users.
- The attack leveraged a waterhole-style injection on a Korean-language news portal.
- The exploit was used to download an encrypted binary payload that dropped a malware module named updata.exe to disk.
- The malware installed tasks in Windows Task Scheduler for persistence.
- The attack was named Operation WizardOpium, with weak code similarities to Lazarus attacks and possible false flag tactics.
- The threat actor's capability was demonstrated through the use of advanced techniques like exploiting a race condition bug and creating an arbitrary read/write primitive.
- The attack was detected by Kaspersky Exploit Prevention component.
- The threat actor's novelty was in using a combination of techniques like heap spraying, heap layout manipulation, and WebAssembly for code execution.
- The attack was reported on November 1, 2019, and more details were available to customers of Kaspersky Intelligence Reporting.
- IoCs included domains behindcorona[.]com and code.jquery.cdn.behindcorona[.]com, as well as MD5 and SHA256 hashes of malicious files.





Report 2

Summary:
The threat actor known as Operation WizardOpium, first seen in 2019, has been identified by Kaspersky for exploiting a zero-day vulnerability in Google Chrome browser (CVE-2019-13720). The attacks have weak code similarities with known threat actors like Lazarus Group and Hidden Cobra, but could be false flags. The targeted websites resemble those attacked by DarkHotel previously. The threat actor's motivation is information theft and espionage, with North Korea being identified as the country of origin. Victims operate in South Korea, with reported hacking operations and counter operations against the threat actor. The tools and techniques used by Operation WizardOpium show a level of sophistication and novelty. 

Date: 2019 - Present





Report 3

Summary:
Operation WizardOpium was a sophisticated cyber attack involving zero-day exploits targeting Google Chrome and Microsoft Windows. The attack utilized a chain of exploits to compromise systems, with the Google Chrome exploit focusing on a vulnerability in the WebAudio component. The exploit involved complex techniques such as obfuscation and memory manipulation to achieve remote code execution. The Microsoft Windows exploit targeted a vulnerability in the win32k component, allowing for elevation of privileges. The attack leveraged techniques to bypass security features and steal system tokens. The operation demonstrated the capabilities of the threat actor in using novel tools and techniques to target victims. The attack was notable for its combination of browser and operating system exploits, showcasing a high level of sophistication. The report provides detailed technical insights into the exploits used in Operation WizardOpium.





Report 4

Summary:
The threat actor behind "Operation WizardOpium" used a Windows 0-day exploit CVE-2019-1458 in November 2019 to target victims. The exploit allowed the threat actor to gain higher privileges on infected machines and escape the Chrome process sandbox. The exploit consisted of a two-stage process involving a PE loader and the actual exploit. The vulnerability exploited belonged to the win32k.sys driver and was considered a 0-day exploit as it worked on patched versions of Windows 7 and some builds of Windows 10. The threat actor used sophisticated techniques to achieve arbitrary kernel read/write primitives and perform privilege escalation on the target system. Kaspersky products detected this exploit with the verdict PDM:Exploit.Win32.Generic. The threat actor's capability and the novelty of the tools and techniques used in this operation demonstrate a high level of sophistication and pose a significant risk to organizations.


