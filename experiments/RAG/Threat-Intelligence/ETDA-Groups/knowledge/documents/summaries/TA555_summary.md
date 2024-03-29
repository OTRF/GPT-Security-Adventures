
Report 1

Summary:
- Threat actor TA555 has been observed distributing a new modular downloader called AdvisorsBot targeting hotels, restaurants, and telecommunications sectors primarily in the Americas.
- The malware is under active development and has been observed using anti-analysis features such as junk code, stack strings, and Windows API function hashing.
- AdvisorsBot communicates with its C&C server using HTTPS and can receive commands to load modules or execute shellcode.
- A system fingerprinting module has been observed extracting Outlook account details, running system commands, and taking screenshots.
- In August 2018, a variant of AdvisorsBot called PoshAdvisor was discovered, rewritten in PowerShell and .NET, showcasing the threat actor's capability to adapt and innovate.
- The threat actor has shown sophistication in distribution techniques and anti-analysis measures, indicating a growing trend of versatile malware for future attacks.
- Indicators of Compromise (IOCs) include SHA256 hashes, URLs, and C&C domains associated with AdvisorsBot and PoshAdvisor.
- The threat actor's focus on small, flexible malware highlights the need for further investigation into their activities.





Report 2

TA555, also known as AdvisorsBot, is a threat actor first seen in 2018 targeting hotels, restaurants, and telecommunications companies primarily in the hospitality and telecommunications sectors. The actor is believed to be motivated by financial crime. The malware used by TA555, AdvisorsBot, is continuously evolving, with a newer version rewritten in PowerShell and .NET. The threat actor is known to use tools such as AdvisorsBot and PoshAdvisor. The activities of TA555 have been observed in various countries, with evidence of active development and novel techniques in their malware. The threat actor's operations have been ongoing since at least 2018, with the latest source modification in April 2020.


