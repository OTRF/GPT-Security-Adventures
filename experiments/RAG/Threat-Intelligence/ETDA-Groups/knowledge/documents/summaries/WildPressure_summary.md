
Report 1

Summary:
The threat actor WildPressure, first seen in 2019, targeted organizations in the Middle East, particularly in the industrial sector, with a C++ Trojan named Milum. The attacks were considered targeted as only three unique samples were found in one country. The motivation behind the attacks was information theft and espionage. WildPressure was reported to have targeted the macOS platform in the Spring of 2021, showing a novel approach in their operations. The threat actor's capabilities include using sophisticated tools like Milum, with no code similarities to known campaigns, indicating a high level of sophistication. The victims targeted by WildPressure operate in the industrial and oil and gas sectors in the Middle East.





Report 2

Summary:
- Threat actor named WildPressure targeted industrial-related entities in the Middle East in a campaign discovered by Kaspersky in August 2019.
- The threat actor used a fully-fledged C++ Trojan named Milum, with victims exclusively from the Middle East, some related to the industrial sector.
- The campaign was considered targeted as only three unique samples were found in one country, indicating a novel operation named WildPressure.
- The malware used JSON format for configuration data and RC4 encryption for communication over HTTP.
- The malware version was 1.0.1, suggesting early development stages with plans for non-C++ versions.
- The threat actor used rented OVH and Netzbetrieb VPS for campaign infrastructure and left RTTI data inside the files.
- The campaign targeted entities in the Middle East since at least May 2019, with indicators of compromise provided.
- Attribution of the threat actor remains unclear, with no strong code or victim-based similarities to known actors.
- The campaign's targeting nature is clear, but the true scope and motives are still being monitored.
- The malware was not exclusively designed for specific victims and may be reused in other operations.
- Indicators of compromise include file MD5 hashes, URLs, and encryption methods used by the threat actor.





Report 3

WildPressure, a threat actor, targeted macOS operating systems with a new version of their malware containing the C++ Milum Trojan, a VBScript variant, and multiple modules. The threat actor used Python for Windows and macOS malware development, showing a recognizable coding style and communication protocol across different programming languages. The malware is still under active development and utilizes compromised legitimate WordPress websites for operations. The threat actor's targets, with low confidence, are believed to be in the oil and gas industry. The malware uses various persistence methods and fingerprinting techniques for Windows and macOS systems. WildPressure's activity shows minor similarities with other threat actors in the region, but not enough for attribution. The threat actor's campaign infrastructure includes VPS and compromised servers, mainly WordPress websites. The report provides indicators of compromise for the different malware variants used by WildPressure. The report was published on July 7, 2021, by Kaspersky's Denis Legezo.


