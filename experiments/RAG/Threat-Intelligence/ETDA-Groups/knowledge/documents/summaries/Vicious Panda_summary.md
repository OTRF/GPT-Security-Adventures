
Report 1

Summary:
- Threat actor "Vicious Panda" targeted various offices of the Mongolian government between August 2015 and February 2016.
- The threat actor used spear phishing emails, weaponized document files, and payloads leveraging geopolitically sensitive subjects as lures.
- The tools used, such as Cmstar and BBSRAT, showed significant overlaps with previously reported adversary groups, indicating a Digital Quartermaster scenario.
- The attack campaign demonstrated a consistent playbook using weaponized Microsoft Word documents with exploits for CVE-2012-0158 and CVE-2014-1761.
- The newer tools and techniques used by the threat actor, including the obfuscation routines and command and control infrastructure, showed a level of sophistication and novelty.
- The infrastructure analysis revealed reuse of domains and consistent patterns in the malware's behavior.
- The evidence suggests a singular entity responsible for deploying and maintaining the tools used, with separate operator groups executing the cyber espionage operations.
- Palo Alto Networks' security platform provides protection against the identified threats.
- Indicators of compromise, including SHA256 hashes and C2 servers, were identified for tracking and mitigation purposes.





Report 2

Summary:
- Threat actor "Vicious Panda" targeted the government of Belarus using the CMSTAR Trojan.
- The campaign involved phishing emails with updated CMSTAR malware variants between June and August of 2017.
- The emails targeted various government entities in Belarus related to the joint military exercises with Russia known as Zapad 2017.
- The malware variants included CMSTAR.A, CMSTAR.B, and CMSTAR.C, with minor modifications in string obfuscation routines.
- Two new payloads named BYEBY and PYLOT were discovered, acting as backdoors for executing commands on victim machines.
- BYEBY malware was loaded as a DLL with capabilities to bypass sandboxing systems and establish C2 communication.
- PYLOT malware collected system information, communicated with a remote C2 server using HTTP, and accepted various commands.
- Indicators of compromise included SHA256 hashes, download locations, and C2 servers for the identified malware variants.
- Palo Alto Networks provided protection measures for customers against the threat.
- The report was published on September 28, 2017, by Palo Alto Networks Unit 42.





Report 3

Summary:
The threat actor Vicious Panda, also known as Bronze Dudley, has been active since at least 2015, with the latest campaign discovered in 2020 targeting the Mongolian public sector using a previously unknown malware implant. The group has targeted government sectors in countries like Belarus, Mongolia, Russia, and Ukraine, with a focus on information theft and espionage. The threat actor has been linked to various operations using tools such as 8.t Dropper, BBSRAT, Byeby, Cmstar, Enfal, and Pylot. The group's activities have been documented in reports dating back to 2015, showcasing their capability and persistence in carrying out cyber attacks.


