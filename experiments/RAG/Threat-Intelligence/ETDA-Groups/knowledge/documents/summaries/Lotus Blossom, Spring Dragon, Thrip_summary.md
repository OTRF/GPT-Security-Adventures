
Report 1

Summary:
- Region: France, Taiwan
- Operating Sector: Diplomatic
- Type of Company: French Ministry of Foreign Affairs
- Date: November 10, 2015
- Threat Actor: Linked to Operation Lotus Blossom
- Evidence of Capability: Exploited CVE-2014-6332, used Trojan named Emissary, modified POC code, used custom algorithm for decryption
- Novelty of Tools and Techniques: Emissary Trojan version 5.3, related to Elise backdoor, unique command handler, use of rolling XOR encryption
- Conclusion: APT threat actors targeted French diplomat with spear-phishing email, attempting to install Emissary Trojan, related to Operation Lotus Blossom, separate infrastructure used to avoid detection.





Report 2

Malformed report





Report 3

Lotus Blossom, Spring Dragon, and Thrip are state-sponsored threat actors originating from China, known for conducting long-running APT campaigns primarily targeting high-profile governmental organizations, political parties, educational institutions, and companies in the telecommunications sector in countries around the South China Sea. They employ spear phishing and watering hole techniques, with tools like Catchamas, Elise, Mimikatz, and PsExec. Notable operations include "Operation Lotus Blossom" in 2015, targeting government and military organizations in Southeast Asia, and attacks on the Association of South East Asian Nations (ASEAN) countries in 2018. The threat actors have been active since at least 2012, with evidence of ongoing espionage activities in the region. Their novel tools and techniques have been analyzed by security researchers, indicating a high level of organization and sophistication in their operations. The threat actors have targeted sectors such as aerospace, defense, education, government, high-tech, satellites, and telecommunications, with victims operating in ASEAN countries, Taiwan, the USA, and others. The motivation behind their attacks is information theft and espionage.





Report 4

The threat actor known as "Lotus Blossom" has been identified as a persistent cyber espionage campaign targeting government and military organizations in Southeast Asia. The campaign, likely state-sponsored, has been operating for over three years and has targeted countries such as Hong Kong, Taiwan, Vietnam, the Philippines, and Indonesia. The attacks involve spearphishing as the initial attack vector, the use of a custom Trojan backdoor named "Elise," and the deployment of decoy files to trick users. The Elise malware, developed by the threat actor, is sophisticated and includes variants with capabilities to evade detection, connect to command-and-control servers, and exfiltrate data. The threat actor's use of advanced tools over an extended period demonstrates a well-resourced adversary with nation-state sponsorship. The report was published on June 16, 2015, by Unit 42 and recommends security practitioners to review the Indicators of Compromise (IoCs) to prevent future attacks.





Report 5

Spring Dragon is a long-running APT actor operating on a massive scale, targeting high-profile governmental organizations, political parties, education institutions, and companies in the telecommunications sector mainly in countries around the South China Sea since 2012. The threat actor is known for spear phishing and watering hole techniques, with a toolset consisting of various backdoor modules with unique functionalities. Spring Dragon's large C2 infrastructure comprises over 200 unique IP addresses and domains, with a focus on the Asia region. The threat actor's targets are primarily in Taiwan, Indonesia, Vietnam, the Philippines, Hong Kong, Malaysia, and Thailand. The threat actor's tools are designed for cyberespionage, with a focus on stealing files, downloading additional malware, and running system commands on victims' machines. The threat actor's activities suggest state-sponsored interests, with a possible time zone of GMT+8 based on malware compilation timestamps. Spring Dragon is expected to continue resurfacing in the Asian region, requiring robust detection mechanisms in place. The threat actor's operations are detailed in a private report available to Kaspersky Lab subscribers.


