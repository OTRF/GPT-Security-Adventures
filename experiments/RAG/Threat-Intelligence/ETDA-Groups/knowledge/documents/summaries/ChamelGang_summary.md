
Report 1

Summary:
The threat actor ChamelGang, first seen in 2021, has been identified as conducting data theft in an energy company by disguising malware and network infrastructure under legitimate services. The group, originating from China, targeted sectors such as aviation, energy, and government in countries like the USA, Russia, and Japan. ChamelGang used novel techniques like imitating legitimate domains and SSL certificates, as well as employing supply chain penetration methods. Their tools included 7-Zip, Cobalt Strike, and BeaconLoader. In 2023, they were reported to have used a DNS-over-HTTPS implant in their operations. Their motivation is information theft and espionage.





Report 2

ChamelGang, a threat actor with ties to China, has been targeting energy, aviation, and government organizations in Russia, the United States, Japan, Turkey, Taiwan, Vietnam, India, Afghanistan, Lithuania, and Nepal. The group has developed a sophisticated toolset for both Windows and Linux intrusions, with a focus on a DNS-over-HTTPS implant called ChamelDoH. This implant communicates with a command-and-control (C2) infrastructure via DNS-over-HTTPS tunneling, utilizing a modified base64 alphabet for encoding communication. ChamelDoH is capable of basic remote access operations and encrypts its communication using AES128. The threat actor has deployed multiple variants of ChamelDoH, with one sample publicly available on third-party malware repositories. Stairwell Threat Research assesses that ChamelDoH is likely developed by the same group known as ChamelGang, based on unique attribution markers. Ongoing analysis by the Stairwell Threat Research team aims to further understand the capabilities and tools used by this threat actor. This report provides the first in a series detailing the functionality of ChamelGang's toolset.





Report 3

Summary:
The threat actor "ChamelGang" is a new APT group that has demonstrated advanced capabilities in cyber attacks. They have targeted victims in various sectors, including fuel and energy, aviation production, and government agencies in multiple countries. The threat actor used novel tools and techniques, such as BeaconLoader, Cobalt Strike Beacon, ProxyT, and DoorMe backdoor, to gain access to and control over compromised networks. They employed tactics like DLL hijacking, network infrastructure disguise, and phishing domains to evade detection. The threat actor also exploited vulnerabilities like ProxyLogon and ProxyShell to compromise Microsoft Exchange Servers. The group's activities indicate a trend towards supply chain attacks and the adoption of new attack methods. The report provides detailed insights into the threat actor's operations and the impact on their victims.


