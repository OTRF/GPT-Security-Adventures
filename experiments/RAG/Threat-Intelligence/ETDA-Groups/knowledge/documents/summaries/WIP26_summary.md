
Report 1

Summary:

Threat actor WIP26, operating in collaboration with QGroup GmbH, has been targeting telecommunication providers in the Middle East since 2022. They utilize public Cloud infrastructure such as Microsoft 365 Mail, Microsoft Azure, Google Firebase, and Dropbox for malware delivery, data exfiltration, and C2 purposes. WIP26 initiates activity by targeting employees through WhatsApp messages containing Dropbox links to a malware loader, leading to the deployment of backdoors CMD365 and CMDEmber. These backdoors leverage Microsoft 365 Mail and Google Firebase instances as C2 servers for executing system commands. The threat actor's motivation is information theft and espionage. The observed attacked sector is telecommunications in the Middle East. The tools used by WIP26 are CMD365 and CMDEmber. The report does not specify the country of origin of the threat actor. The report was last modified on 2023-02-17.





Report 2

Summary:
- Threat actor WIP26 targeted telecommunication providers in the Middle East, likely for espionage purposes.
- WIP26 used public Cloud infrastructure, including Microsoft 365 Mail, Microsoft Azure, Google Firebase, and Dropbox, for malware delivery, data exfiltration, and C2 purposes.
- Backdoors CMD365 and CMDEmber were used for C2, with CMD365 masquerading as utility software and using Microsoft 365 Mail for communication.
- CMDEmber used Google Firebase for C2, exfiltrating machine information and executing system commands.
- Evidence suggests WIP26 made OPSEC errors, with public access to Firebase C2 server data.
- Threat actor innovation includes using public Cloud infrastructure for C2 to evade detection.
- Similar threat groups have leveraged Microsoft Graph API and Google Firebase for C2 purposes.
- Report provides IOCs for detection and tracking of WIP26 activity.
- Date: February 16, 2023.


