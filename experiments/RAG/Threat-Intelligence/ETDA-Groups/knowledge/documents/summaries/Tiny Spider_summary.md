
Report 1

Summary:
- Threat actor: PinkKite
- Region: Global
- Operating sector: Point of Sale (POS) endpoints
- Type of company: Not specified
- Date: March 14, 2018
- PinkKite is a newly discovered family of POS malware that is small in size but effective in siphoning credit card numbers.
- The malware uses memory-scraping and data validation tools, with a unique double-XOR encryption method for credit card numbers.
- PinkKite utilizes clearinghouses in South Korea, Canada, and the Netherlands for data exfiltration, deviating from the typical C2 server communication.
- The malware masquerades as legitimate Windows programs to avoid detection and employs obfuscation techniques to store and transmit credit card data.
- The threat actor behind PinkKite likely infiltrated systems using PsExec and Mimikatz to extract credentials and remove credit card data via Remote Desktop Protocol sessions.
- The PinkKite campaign was identified by researchers at Kroll Cyber Security during a nine-month investigation.





Report 2

Summary:
The threat actor known as Tiny Spider, first seen in 2015, utilizes a small loader called TinyLoader to deliver powerful downloader functionality. The loader communicates with hardcoded C2 servers and establishes semi-interactive two-way communication. The threat actor's motivation is financial crime, and they have targeted the retail sector worldwide. They have been observed using tools like PinkKite, PsExec, TinyPOS, and TinyLoader. In 2017, they were linked to a new family of point-of-sale malware called PinkKite. The threat actor's capabilities and novel techniques make them a significant concern in the cybersecurity landscape.


