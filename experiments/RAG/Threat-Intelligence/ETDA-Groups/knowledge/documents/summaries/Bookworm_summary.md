
Report 1

Summary:
- Threat actor named "Bookworm" targeted the government of Thailand since July 2015.
- Operating sector: Government entities in Thailand.
- The threat actor used the Bookworm Trojan as the payload in attacks.
- Tactics included spear-phishing and compromised web servers for strategic web compromise.
- Novelty: Used standalone Flash Player for decoy documents with pictures of current events in Thailand.
- Date codes were used for campaign tracking or Trojan version identification.
- Majority of compromised hosts were in Thailand, with some in South Korea.
- Infrastructure overlap with other malware families like Poison Ivy, PlugX, FFRAT, and Scieron.
- Threat actors had unauthorized access to legitimate servers hosting Bookworm.
- Conclusion: Threat actors likely to target other governments in future campaigns with Bookworm.





Report 2

Summary:
The threat actor known as Bookworm, first seen in 2015, has been targeting organizations in Thailand, specifically branches of government, with a focus on information theft and espionage. The threat actor has been observed using a variety of tools including Bookworm, FormerFirstRAT, Poison Ivy, PlugX, and Scieron. The attacks have been linked to China as the country of origin. The novel aspect of this threat actor lies in the use of dynamic DNS domain names containing references to Thailand and the majority of compromised systems being located within Thailand. The attacks have been ongoing with the latest source modification in April 2020. The victims targeted operate in the defense and government sectors.





Report 3

The threat actor known as Bookworm has been targeting victims primarily in Thailand, utilizing a Trojan with a unique modular architecture that allows for the loading of additional modules directly from its command and control server. The Trojan, initially mistaken for PlugX RAT, has a complex installation process involving DLL side-loading and shellcode execution. Bookworm's main functionality includes keystroke and clipboard content theft, with the ability to expand its capabilities through loaded modules. The threat actor behind Bookworm has employed various encryption and decryption algorithms, such as RC4 and AES, to obfuscate network communications and evade detection. The Trojan's keylogging functionality is facilitated by the KBLogger module, which operates stealthily by creating hidden windows and encrypting captured data. Bookworm's developers have created a sophisticated anti-analysis framework, making static analysis challenging due to the modular structure and indirect API function calls. The threat actor has demonstrated a high level of effort in developing Bookworm, indicating a likelihood of continued use and development in future attacks. (Date: November 10, 2015)


