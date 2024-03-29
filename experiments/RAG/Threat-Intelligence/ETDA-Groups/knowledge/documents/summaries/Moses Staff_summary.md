
Report 1

Summary:
- Threat actor identified as the Iranian COBALT SAPLING group likely operates personas Moses Staff and Abraham's Ax.
- Moses Staff targets Israeli companies and individuals, using custom PyDCrypt loader and DCSrv cryptographic wiper for disruption and intimidation.
- Abraham's Ax, linked to Hezbollah Ummah, targets Saudi Arabian government ministries in response to perceived threats to Iran's interests.
- Both groups use similar iconography, leak sites, and hosting infrastructure, indicating a common entity.
- Novelty in tools and techniques includes the use of StrifeWater RAT and DriveGuard alongside customized ASPX web shells.
- Videos released by both groups depict Hollywood-style hacking scenarios with intercepted phone conversations and visual themes.
- Abraham's Ax does not replace Moses Staff, indicating potential ongoing operations by COBALT SAPLING.
- Recommendations for organizations to mitigate exposure to malware include reviewing and restricting access using provided indicators.
- Date of emergence for Abraham's Ax: November 8, 2022.
- Operating sectors of victims targeted: Israeli companies and individuals, Saudi Arabian government ministries.

Date: January 26, 2023.





Report 2

Summary:
- Threat actor named Moses Staff targeted Israeli organizations in a campaign spanning several months.
- The threat group is believed to be sponsored by the Iranian government and has been active for over a year.
- They used a custom multi-component toolset for conducting espionage, including a new backdoor for data exfiltration.
- The backdoor component, loader, and web shell were attributed to Moses Staff.
- The group used ProxyShell exploit in Microsoft Exchange servers for initial infiltration.
- The backdoor communicated with C2 servers, executed commands, and had various functionalities like keylogging and file exfiltration.
- The threat actor showed capability in evading security products and maintaining low detection rates.
- The campaign has been operational since late 2020, with a focus on Israeli entities.
- FortiEDR blocked earlier stages of the attack, preventing potential ransomware or destructive measures.
- Fortinet's FortiGuard Labs shared threat details with Cyber Threat Alliance for better protections.
- MITRE ATT&CK techniques used by the threat actor included exploitation, credential dumping, and exfiltration over C2 channels.





Report 3

Summary:
The threat actor known as Moses Staff, operating since 2021, has targeted Israeli organizations with the goal of causing damage by leaking sensitive data and encrypting networks, without demanding ransom. Unlike other groups, their motivation is to expose crimes in the occupied territories. They have been linked to attacks in various sectors including Energy, Financial, Government, Manufacturing, Transportation, and Utilities in countries like Chile, Germany, India, Israel, Italy, Turkey, UAE, and USA. The threat actor has been observed using tools like DCSrv, PyDCrypt, and StrifeWater. The group's unique motivation and tactics set them apart from other threat actors in the region. The report also mentions a likely link between Moses Staff and Abraham's Ax in a hacking operation in 2022.





Report 4

Summary:
The threat actor known as Moses Staff, an Iranian APT group, has been targeting organizations primarily in Israel but also in other countries such as Italy, India, Germany, Chile, Turkey, UAE, and the US across various sectors including Government, Finance, Travel, Energy, Manufacturing, and Utilities. They have been observed using a new Remote Access Trojan (RAT) called StrifeWater in their attacks, which has capabilities such as command execution, screen capturing, and downloading additional extensions. Unlike typical ransomware groups, Moses Staff's goal seems to be politically motivated rather than financial, aiming to disrupt operations and advance Iran's geopolitical goals. The RAT is used in the initial stages of the attack and is later replaced with other tools to cover their tracks. The group's tactics include masquerading their tools as legitimate Windows software and removing initial persistence and reconnaissance tools to avoid detection. The Cybereason Nocturnus Team has been tracking and analyzing the activities of Moses Staff, highlighting the group's advanced TTPs and the use of StrifeWater RAT in their operations. The report provides indicators of compromise for the StrifeWater RAT and insights into the group's modus operandi. The threat actor's activities align with Iran's cyber warfare doctrine, focusing on sabotage and espionage rather than financial gain. The emergence of new malware samples indicates that Moses Staff continues to develop its attack arsenal. The Cybereason XDR Platform is capable of detecting and blocking the StrifeWater RAT and other advanced TTPs used by the threat actor.


