
Report 1

HAFNIUM, a threat actor operating out of China, has been targeting on-premises versions of Microsoft Exchange Server with multiple 0-day exploits, including CVE-2021-26855, CVE-2021-26857, CVE-2021-26858, and CVE-2021-27065. The attacks allowed access to email accounts and installation of additional malware for long-term access to victim environments. HAFNIUM primarily targets entities in the United States across various sectors, including infectious disease researchers, law firms, higher education institutions, defense contractors, policy think tanks, and NGOs. The threat actor has been observed using legitimate open-source frameworks like Covenant for command and control and exfiltrating data to file sharing sites like MEGA. HAFNIUM operates primarily from leased virtual private servers (VPS) in the United States. The tools and techniques used by HAFNIUM, such as web shell deployment, Procdump for dumping LSASS process memory, and PowerShell reverse shells, demonstrate the sophistication and capability of the threat actor. The novel techniques and tools used by HAFNIUM highlight the need for immediate patching of affected systems to prevent further exploitation. The report provides detailed technical information, indicators of compromise (IOCs), and detection guidance to help organizations investigate and defend against these attacks. Date of publication: March 2, 2021.





Report 2

Hafnium, a threat actor also known as Silk Typhoon, primarily targets entities in the United States across various sectors such as infectious disease researchers, law firms, higher education institutions, defense contractors, policy think tanks, and NGOs. They exploit vulnerabilities in internet-facing servers and use legitimate open-source frameworks like Covenant for command and control. Hafnium exfiltrates data to file sharing sites like MEGA once inside a victim network. They have been observed interacting with victim Office 365 tenants for reconnaissance purposes. The threat actor operates from leased virtual private servers (VPS) in the United States and is believed to be state-sponsored by the Ministry of State Security in China. Hafnium has been linked to attacks attributed to APT 31, Judgment Panda, Zirconium, Leviathan, APT 40, and TEMP.Periscope by cybersecurity experts. They have been reported using 4 MS Exchange 0-days and were involved in the Log4Shell attacks in 2021. Counter operations against Hafnium have been conducted by the United States and its allies.





Report 3

Summary:
Nation-state threat actors from China, Iran, North Korea, and Turkey have been exploiting the Log4Shell vulnerability (CVE-2021-44228) to target networks, as reported by Microsoft on December 15th, 2021. Known threat actors include Phosphorus from Iran and Hafnium from China. Hafnium, specifically, has been observed using the vulnerability to attack virtualization infrastructure in novel ways, extending their typical targeting. Microsoft has also noted multiple threat actors acting as initial access brokers for ransomware gangs using the Log4Shell exploit to gain network access. Concerns have been raised about a potential increase in ransomware attacks due to the exploitation of this vulnerability, with over 60 variations of the Log4Shell exploit observed in the wild. The first ransomware operation leveraging Log4Shell, named Khonsari, was identified as a low-effort skidware attempting to frame an individual of Iranian descent.





Report 4

Summary:
- Threat actor: Hafnium
- Region: Global, with a focus on the U.S.
- Operating sector: Government, private sector companies
- Date: July 19th, 2021
- The White House formally blamed China's Ministry of State Security for the Microsoft Exchange Hack, attributing the attack to Beijing-linked digital operators with high confidence.
- The Ministry of State Security utilized contract hackers for malicious cyber activities globally, including a ransomware attack on an American company.
- The attack impacted tens of thousands of organizations in the U.S. alone, showcasing the threat actor's capability.
- The U.S. and its allies condemned Chinese digital activities, marking a unified front against Beijing's cyber efforts.
- The threat actor used novel tactics and techniques, prompting the release of over 50 indicators of compromise by the FBI, NSA, and CISA.
- The DOJ also levied formal charges against four Chinese nationals for their role in the APT40 hacking group.


