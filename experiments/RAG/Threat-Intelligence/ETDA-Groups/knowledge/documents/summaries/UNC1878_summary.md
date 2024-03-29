
Report 1

Summary:
- Threat actor: UNC1878, also known as "WIZARD SPIDER," "Team9"
- Targeted victims: Hospitals in the United States
- Operating sector: Healthcare
- Date: Mid-October
- Evidence of capability: Utilized BazarLoader/BazarBackdoor for initial access, followed by Cobalt Strike deployment, and potential Ryuk ransomware deployment
- Novel tools and techniques: Process hollowing, domain trust enumeration, lateral movement via WMI + PowerShell + Cobalt Strike, Bloodhound execution, Adfind for Active Directory reconnaissance
- Detection opportunities: Process hollowing of cmd.exe, domain trust enumeration with nltest.exe, lateral movement via Cobalt Strike's SMB PsExec module, credential access using lsass from regsvr32, Bloodhound execution, Adfind extraction from Active Directory
- Recommendations: Maintain updated systems, backups, educate users, have a disaster recovery plan, consider incident response partners, act quickly in case of infection

Overall, UNC1878 utilized sophisticated tools and techniques, including BazarLoader and Cobalt Strike, to target hospitals in the US with the potential deployment of Ryuk ransomware. The threat actor's tactics were detected and thwarted through a series of detection opportunities, highlighting the importance of proactive security measures in the healthcare sector.





Report 2

Summary:
The threat actor UNC1878 targeted Brooklyn & Vermont hospitals with Ryuk ransomware attacks. The attacks were part of a spree across the U.S. healthcare industry, with evidence pointing to an Eastern European hacking group. UNC1878 intends to target hundreds of hospitals, as seen in previous attacks on Sky Lakes Medical Center and St. Lawrence Health System. Check Point reported a 71% increase in ransomware attacks in October targeting the U.S. healthcare sector. The University of Vermont Health Network was also affected, with varying impacts on affiliated hospitals. The FBI is investigating the attack, and cybersecurity firm Emsisoft is offering free ransomware recovery services to healthcare organizations. The attacks highlight the increasing threat posed by ransomware to the healthcare sector. (Date: October 29, 2020)





Report 3

UNC1878, a threat actor first seen in 2020, has been targeting the healthcare sector in the USA, with victims including Wyckoff Heights Medical Center and the University of Vermont Health Network. The group is known for deploying the Ryuk ransomware and has been identified by Mandiant as an Eastern European hacking group. UNC1878's motivation is financial gain, and they have been observed using tools such as BazarBackdoor, Cobalt Strike, and Ryuk. The U.S. government has issued warnings about the imminent cybercrime threat posed by UNC1878 to hospitals and healthcare providers, with the group intending to attack hundreds of hospitals. The threat actor's activities have been ongoing, with the latest source modification date in January 2021.


