
Report 1

Summary:
The threat actor known as Iridium, attributed to Iran, has been active since 2018 and is linked to attacks on government agencies, oil and gas companies, and technology firms, including Citrix Systems Inc. They use proprietary techniques to bypass two-factor authentication for unauthorized access to critical applications and services. The group's motivation is information theft and espionage. They have been observed using tools such as China Chopper, LazyCat, and Powerkatz. Notable operations include attacks on the Australian government in December 2018 and a breach of Citrix. The threat actor's capabilities and novel techniques pose a significant risk to targeted sectors in the region.





Report 2

Summary:
- Threat actor: IRIDIUM
- Region: Iran
- Operating sector: Government agencies, oil and gas companies, technology companies
- Type of company: Citrix Systems Inc.
- Date: December 28, 2018
- Evidence of capability: IRIDIUM used proprietary techniques to bypass two-factor authentication for critical applications, accessed 6 terabytes of sensitive data, targeted over 200 organizations, including Citrix
- Novelty of tools and techniques: Leveraged weak password control, compromised Citrix employee accounts, accessed Global Access List, performed mass data exfiltration, used manual techniques including PowerShell, bypassed firewalls and VPN access
- Attribution: Resecurity linked the APT to the attack, Citrix confirmed the password-spraying attack but did not confirm other details
- Impact: Data breach involving email correspondence, network shares, project management, and procurement services
- Recommendations: Citrix could have implemented better password hygiene practices and automated checks for password complexity.





Report 3

Summary:
The threat actor "IRIDIUM" was identified by Resecurity as behind the Citrix data breach that occurred in December 2018. The attack targeted over 200 government agencies, oil and gas companies, and technology companies, including Citrix. Resecurity claimed that IRIDIUM had been lurking in Citrix's network for about 10 years and extracted sensitive data amounting to 6-10 terabytes. The hackers likely used password spraying to gain access and circumvent security layers. There is no evidence of direct penetration into U.S. government networks, but the breach poses a potential risk. Resecurity first alerted Citrix on December 28, 2018, about the targeted attack. The novelty lies in the long-term presence of IRIDIUM in Citrix's network and the sophisticated tactics used to extract data. The threat actor's capability is demonstrated by the successful breach of a high-profile company like Citrix and the extraction of significant amounts of sensitive data.





Report 4

Summary:
- Threat actor "Iridium" targeted the Australian Parliament House in the APAC region on 02/26/2019.
- The attack was sophisticated and state-sponsored, targeting ruling and opposition political parties.
- The threat actor used a post-exploitation phase with tools like LazyCat DLL, Powerkatz DLL, Recon Module, and Powershell Agent.
- The tools were written in C# on the .NET Framework, not belonging to open-source frameworks like Metasploit.
- LazyCat DLL had capabilities for memory inspection, TCP relay, and log erasure to cover tracks.
- Powerkatz DLL had functions for asynchronous task execution and evasion of antivirus detection.
- Recon Module included a port scanner for scanning network ports and services.
- Powershell Agent was used for executing Powershell commands stealthily.
- The threat actor customized open-source tools and techniques to create an evasive cyber arsenal.
- The tools did not use zero-day exploits but were effective in bypassing traditional security measures.
- Indicators of compromise included hashes and Yara rules for detection.
- The threat actor's strategy involved leveraging open-source tools for quick development without compromising effectiveness.


