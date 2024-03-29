
Report 1

Summary:
The threat actor known as "SideWinder, Rattlesnake" has been identified targeting Pakistan military infrastructure, specifically the Navy, with a focus on the National Database and Registration Authority (NADRA) website. The attack involves a sophisticated chain of execution involving a malicious RTF file exploiting CVE-2017-11882, PowerShell scripts, VBScript, and JavaScript. The threat actor uses novel techniques such as anti-forensics and execution side loading to evade detection. The attack involves the deployment of a RAT named Winset.exe and a modified DLL named cmpbk32.dll for persistence. The threat actor's infrastructure includes a malicious domain www.nadra.gov.pk.d-dns.co. The attack is attributed to an Indian group with a strong capability to target sensitive military infrastructure. The report provides IOCs for further investigation. The operation was observed on Jul 16, 2018.





Report 2

Summary:
In the APT Trends report Q1 2018 by Kaspersky, a threat actor named SideWinder was identified targeting Pakistan military targets since at least 2012. The threat actor showed low confidence in being potentially authored by an Indian company and used unique implementations to leverage known vulnerabilities like CVE-2017-11882. The report highlighted the threat actor's capability to deploy Powershell payloads in the final stages of the attack. The report also mentioned the threat actor's focus on routers and networking hardware, using Mikrotik routers as an infection vector. The report identified three new threat actors in the Asia region, including Shaggypanther, Sidewinder, and CardinalLizard, each with specific targeting and techniques. The report emphasized the increasing interest of threat actors in targeting routers and networking hardware, as well as the novel techniques and tools used by the threat actors. The report was published on April 12, 2018, by Kaspersky's Global Research and Analysis Team (GReAT).





Report 3

Malformed report.





Report 4

Summary:
The threat actor known as SideWinder, also identified as Rattlesnake, has been active since at least 2012, primarily targeting Pakistan military entities. There is speculation that the malware used by this actor may have been developed by an Indian company. Their motivation appears to be information theft and espionage. SideWinder employs unique techniques to exploit vulnerabilities like CVE-2017-11882 and deploys Powershell payloads. The victims of their attacks are mainly in the defense and government sectors across countries such as Afghanistan, Bangladesh, and China. The threat actor has been linked to various hacking operations, with the most recent activity targeting Pakistan and Turkey. Novel tools used by SideWinder include BroStealer, callCam, and Capriccio RAT. The latest report on their activities was in 2023, indicating ongoing threat actor operations.





Report 5

The threat actor known as SideWinder (aka Rattlesnake, Hardcore Nationalist, RAZOR TIGER, T-APT-04, and APT-C-17) has been identified by Group-IB Threat Intelligence researchers as originating from India and primarily targeting Pakistan. The newly discovered custom tool, SideWinder.AntiBot.Script, is being used in phishing attacks against Pakistani targets, particularly government organizations. The group has been using an anti-bot script to filter victims, focusing solely on Pakistani users. They distribute malicious files in ZIP archives with an LNK file inside, which downloads an HTA file from a remote server. SideWinder has been targeting government, military, and economic sectors in Southeast Asia, with Pakistan being their primary target since 2012. The group has been seen cloning government websites to collect user credentials. The SideWinder.AntiBot.Script tool checks the client browser environment to decide whether to issue a malicious file or redirect to a legitimate resource, using techniques to avoid detection by threat researchers. The group's use of HTAs for downloading files and executing backdoors has been noted, with the final backdoor allowing the attacker to collect system information and update commands and C2 addresses. The Group-IB Threat Intelligence team shared their findings to help potential targets in Pakistan identify and contain attacks by SideWinder in early stages.





Report 6

The SideWinder APT group, also known as Razor Tiger, Rattlesnake, and T-APT-04, has been actively targeting Pakistan government organizations since at least 2012, with a focus on military, government, and business entities in Pakistan, Afghanistan, China, and Nepal. The group utilizes email spear-phishing, document exploitation, and DLL side-loading techniques to deliver targeted implants. In a recent campaign targeting Pakistan government officials, SideWinder used server-side polymorphism to deliver the next stage payload, bypassing traditional signature-based antivirus detection. The campaign began in late November 2022 and included malicious documents designed to trick officials with convincing content. Notably, the threat actor exploited the CVE-2017-0199 vulnerability for remote template injection instead of using embedded malicious macro code. The campaign also targeted Turkey in early March 2023, indicating a shift in the threat actor's focus. The threat actor's network infrastructure and command-and-control (C2) tactics have shown longevity, with predictable URL structures used for hosting malicious files. The threat actor's use of server-side polymorphism and obfuscated JavaScript in the payload demonstrates advanced capabilities to evade detection. The BlackBerry Threat Research & Intelligence team continues to monitor the threat group's activities and provides indicators of compromise (IoCs) for defenders and cybersecurity professionals.





Report 7

SideWinder, also known as "响尾蛇" APT group (T-APT-04), has been identified as a threat actor targeting military objectives in South Asia, particularly Pakistan, since as early as 2012. The group utilizes a combination of CVE-2017-11882 vulnerability and RunHTMLApplication backdoor techniques to deliver payloads through malicious documents. The malware, written in pure VB language, leverages white exploitation techniques to increase detection evasion. The RAT (Remote Access Trojan) deployed by SideWinder installs keyboard and mouse hooks to record keystrokes and collects system information, storing it in specific directories for exfiltration to C2 servers. The threat actor's capability is evidenced by the sophisticated techniques used in the attack, indicating a high level of technical proficiency. The attack was detected and blocked by Tencent's advanced threat detection system, highlighting the importance of deploying robust security measures to protect against such threats. (Date: 2018-05-23)





Report 8

Malformed report.


