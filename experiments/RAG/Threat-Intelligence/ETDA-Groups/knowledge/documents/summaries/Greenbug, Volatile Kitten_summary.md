
Report 1

Greenbug, a threat actor targeting organizations in the Middle East, including aviation, energy, government, investment, and education sectors, was discovered by Symantec during an investigation into Shamoon attacks. Greenbug uses a custom information-stealing RAT called Trojan.Ismdoor and various hacking tools to steal credentials. The group has been active since at least June 2016 and likely uses email as an initial attack vector. They utilize Windows Alternate Data Streams to hide malware in RAR archives, with the Ismdoor Trojan being executed when victims open a .chm file. Greenbug has been observed downloading tools to log keystrokes and collect sensitive data. While there is no definitive link between Greenbug and Shamoon, the presence of Greenbug within a targeted organization prior to a Shamoon attack raises suspicions. Symantec is investigating new Shamoon activity in the region. The report provides evidence of Greenbug's capability and the novelty of using ADS to hide malware. Date: June-November 2016.





Report 2

Greenbug, also known as Volatile Kitten, is a subgroup of the larger threat actor group including OilRig, APT 34, Helix Kitten, and Chrysene. The group has been active since at least 2016 and is believed to be sponsored by Iran with motivations of information theft and espionage. Greenbug has been observed targeting organizations in the Middle East, particularly in Saudi Arabia, with a possible link to the Shamoon attacks. The group is known for using novel tools and techniques, such as the ISMdoor variant, to compromise targets and steal user credentials. Evidence suggests that Greenbug has been registering domains similar to those of Israeli high-tech and cybersecurity companies, indicating a broad range of targets. Counter operations against Greenbug have been reported, but the group continues to pose a significant threat in the cybersecurity landscape.





Report 3

Summary:
- Threat actor "Greenbug" possibly linked to OilRig campaign
- Discovered activity in July 2017 targeting a Middle Eastern technology organization
- Attack involved new variants of delivery documents named Clayslide and payload named ISMAgent
- Delivery document contained fake invoice decoy to hide malicious activity
- ISMAgent payload used DNS tunneling for C2 communications
- Command line options available for configuring ISMAgent
- ISMAgent communicated with C2 server using HTTP requests and DNS tunneling
- Infrastructure of ISMAgent included C2 domains like ntpupdateserver[.]com and adobeproduct[.]com
- ISMAgent differentiated from ISMDoor by architecture, communication methods, and command set
- ISMAgent found to be an iterative tool in the OilRig campaign
- Palo Alto Networks customers protected against identified indicators of compromise

Date: July 27, 2017

Region: Middle East
Operating Sector: Technology
Type of Company: Middle Eastern technology organization

Malformed report.





Report 4

Summary:
- Threat actor identified as Greenbug, believed to collaborate with Shamoon in attacks against Saudi organizations.
- Greenbug uses a new communication tool, a DNS-based attack technique, to cloak command and control communications with malware.
- The tool, Ismdoor RAT, allows bidirectional command and control channel through DNS TXT record queries and responses.
- Greenbug uses DNS tunneling to administer the RAT, exfiltrate data, and steal credentials.
- The use of DNS-based message attacks is novel and requires a dedicated programmer to implement.
- The threat group behind Shamoon attacks is advancing malware capabilities with sophisticated communication techniques.
- The report was published on May 2, 2017, by Threatpost.
- The victims targeted are Saudi organizations in the government sector.
- The report provides evidence of the threat actor's capability to develop and utilize advanced tools and techniques for cyber attacks.
- The novelty of the DNS-based attack technique used by Greenbug sets them apart in the cyber threat landscape.


