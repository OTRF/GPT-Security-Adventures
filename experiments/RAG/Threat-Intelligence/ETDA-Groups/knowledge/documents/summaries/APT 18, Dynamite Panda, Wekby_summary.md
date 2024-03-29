
Report 1

Summary:
APT 18, also known as Dynamite Panda or Wekby, is a state-sponsored threat actor believed to be linked to the PLA Navy in China. Operating since 2009, they target various sectors such as aerospace, defense, healthcare, and high-tech in the USA. They are known for quickly leveraging new exploits, like the Flash zero-day exploit. Their tools include Gh0st RAT, HTTPBrowser, and 0-day exploits for Flash. Notable operations include the 2014 Community Health Systems data breach and using DNS requests as a command and control mechanism in 2015 and 2016. The threat actor's capability and use of novel techniques make them a significant threat in the cyber espionage landscape.





Report 2

APT 18, also known as Dynamite Panda or Wekby, is a Chinese threat actor group that has been conducting cyberespionage bootcamps for over a decade, focusing on training recruits in the art of supply chain attacks. The group, unique among China-based threat actors, utilizes specially crafted, non-public malware for financial gain, targeting code signing keys and certificates to authenticate code. APT 18's strategic focus on compromising code signing certificates has allowed them to successfully target high-value victims across various industries, including healthcare, pharmaceuticals, and telecommunications. The threat actor group has been observed targeting commercial software vendors to gain access to specific victims for cyberespionage purposes. APT 18 actively manages a library of stolen or purchased code signing certificates and keys to support their attacks. The group's use of compromised code signing machine identities and supply chain attacks has set a blueprint for sophisticated attacks that are difficult to detect. Businesses are advised to be prepared for similar threat groups utilizing these methods. The report was published on November 18, 2021, by Venafi, a leading provider of machine identity management solutions.





Report 3

APT 18, also known as Dynamite Panda or Wekby, targeted multiple companies in various industries such as aerospace and defense, construction and engineering, education, energy, health and biotechnology, high tech, non-profit, telecommunications, and transportation. The threat actor quickly exploited a zero-day vulnerability (CVE-2015-5119) following the Hacking Team leak, demonstrating flexibility, organization, and awareness of information security developments. APT 18 used a malicious Adobe Flash file to deliver a GH0ST RAT variant backdoor to victims' systems, allowing for extensive control over the compromised systems. The threat actor's capability to adapt and capitalize on new exploits was evident in this operation. The campaign showed that APT 18 likely works independently and has the resources to procure infrastructure for their attacks. The use of public source code for the backdoor suggests that threat groups like APT 18 may customize their tools to suit their specific objectives. The report does not specify a date or operation time window for this activity.





Report 4

Summary:
- Threat actor: APT 18, Dynamite Panda, Wekby
- Region: US-based organization targeted
- Operating sector: Various industries such as healthcare, telecommunications, aerospace, defense, and high tech
- Date: May 24, 2016
- Capability: Wekby group uses DNS requests as a command and control mechanism, leverages recently released exploits, and employs obfuscation techniques to evade detection
- Novelty: Pisloader malware family discovered, uses DNS as a C2 protocol, return-oriented programming, and anti-analysis tactics
- Tools: HTTPBrowser malware family ties, malware delivered via HTTP from specific URLs, and specific commands supported by the malware
- Infrastructure: Domains and IP resolutions observed in the attack
- Protection: Palo Alto Networks customers protected against the threat with WildFire identification, AutoFocus tag creation, flagging malicious domains/IPs, and creation of an IPS rule for detecting pisloader DNS traffic.


