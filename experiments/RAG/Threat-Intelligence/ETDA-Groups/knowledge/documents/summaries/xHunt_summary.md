
Report 1

xHunt, also known as SectorD01, Hive0081, and Cobalt Katana, is a threat actor group first observed in 2018. Operating out of Iran, xHunt has been targeting shipping and logistics companies in Kuwait. In a campaign between May and June 2019, xHunt used novel tools such as Hisoka, Sakabota, Netero, and Killua to carry out post-exploitation activities. These tools communicated via HTTP, DNS tunneling, and email, with the use of Exchange Web Services for C2 communications being a unique technique. The group's motivation appears to be information theft and espionage. The tools used by xHunt include BumbleBee, CASHY200, Gon, and EYE. The campaign has been ongoing, with reported hacking operations in 2018 and 2019. The threat actor's capability and use of novel techniques make them a significant concern for organizations in the shipping and logistics sector in Kuwait.





Report 2

Summary:
Between May and June 2019, Unit 42 observed a threat actor, known as xHunt, targeting transportation and shipping organizations in Kuwait. The threat actor used custom tools named Hisoka, Sakabota, Netero, Killua, Gon, and EYE, all created by the same developer. These tools utilized HTTP, DNS tunneling, and email-based command and control (C2) channels. The novelty of the threat actor's techniques included using email drafts via Exchange Web Services for C2 communications, a method not commonly observed. The tools showed overlaps in code, indicating a relationship between the 2018 and 2019 campaigns. The threat actor targeted organizations in the transportation and shipping sector in Kuwait, using tools with references to the anime series Hunter x Hunter. The campaign showed a high level of sophistication and capability, with tools evolving over time. The report provides detailed analysis of the tools, infrastructure, and indicators of compromise associated with the xHunt campaign.





Report 3

Summary:
The xHunt campaign, operated by a threat actor, targeted Kuwaiti organizations in September 2020. The threat actor used a new webshell called BumbleBee to upload/download files, run commands, and move laterally within compromised servers. The BumbleBee webshell required two passwords for viewing and interacting. The threat actor used VPNs and SSH tunnels to access internal servers and evade detection. The actor's activities included network and account discovery, system time determination, creating SSH tunnels, using RDP, and removing evidence of presence. The actor reused infrastructure and focused on concealing their location and monitoring email alerts. Palo Alto Networks provides protection against xHunt-related attacks. The threat actor's infrastructure was categorized as malicious. The campaign continues with evolving tactics and tools. 

Date: September 2020
Region: Kuwait
Operating Sector: Organizations in Kuwait
Type of Company: Not specified





Report 4

Summary:
- Threat actor xHunt campaign observed in June 2019 using a new PowerShell backdoor named CASHY200 that utilized DNS tunneling to communicate with its C2 server.
- Evidence of capability shown through telemetry of a host in Kuwait beaconing to the C2 domain windows64x[.]com in September 2019.
- CASHY200 used randomly generated identifiers stored in the registry and the command value 200 to communicate with the C2 server.
- Threat actor targeted Kuwait government organizations starting in the spring of 2018 using CASHY200.
- Tools and techniques used by the threat actor were novel, with DNS tunneling protocol being a key feature.
- CASHY200 samples date back to May and June of 2018, targeting Kuwait government organizations.
- DNS tunneling protocol used by CASHY200 involved issuing DNS A queries to send and receive data from the C2 server.
- CASHY200 communicated with the C2 server using specific request types within DNS queries to transmit commands and receive results.
- Palo Alto Networks customers were protected from the tools mentioned through various security measures.
- Indicators of compromise include executable droppers, Word delivery documents, and CASHY200 samples with associated C2 domains.

Date: October 10, 2019
Region: Kuwait
Operating Sector: Government organizations, shipping, and transportation industries
Type of Company: Not specified

Source: https://unit42.paloaltonetworks.com/more-xhunt-new-powershell-backdoor-blocked-through-dns-tunnel-detection/


