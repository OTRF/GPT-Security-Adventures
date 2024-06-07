
Report 1

Summary:
- Threat actor "Roaming Tiger" targeted Russian organizations with espionage and information stealing objectives.
- A new tool named "BBSRAT" was discovered in August 2015, using similar exploits to PlugX but with unique behavior patterns and architecture.
- Victims included Russian organizations like Vigstar, a research organization for defense and security agencies.
- BBSRAT used decoy documents exploiting Microsoft Office vulnerability CVE-2012-0158 for infection.
- Command and control infrastructure included domains like transactiona[.]com and futuresgold[.]com.
- BBSRAT deployment techniques involved sideloading malicious DLLs and using PowerSploit framework for downloading.
- BBSRAT executed various commands for data exfiltration and network communication.
- Persistence was ensured through registry key writes and dynamic loading of functions.
- IOCs included hashes, compile times, network protocols, C2 servers, and domains.
- The threat actor continued operations despite public exposure, emphasizing the need for proactive security measures.





Report 2

Roaming Tiger, also known as Rotten Tomato or CTG-7273, is a threat actor first seen in 2014 targeting Russia and other Russian-speaking nations. The attack campaign heavily relies on RTF exploits and the PlugX malware family. The threat actor's motivation is information theft and espionage, with a country of origin in China. Victims operate in sectors such as Belarus, Kazakhstan, Kyrgyzstan, Russia, Tajikistan, Ukraine, and Uzbekistan. Roaming Tiger has been observed using tools like BBSRAT, Gh0st RAT, and PlugX. A reported hacking operation linked to Roaming Tiger occurred in 2015. The threat actor's capabilities and novel techniques pose a significant risk to organizations in the region.


