
Report 1

Malformed report





Report 2

Winter Vivern is an Advanced Persistent Threat (APT) group with pro-Russian objectives that has been active since 2021. The group has been relatively underreported but has recently targeted Ukraine, with attacks reported by the Polish CBZC and Ukraine CERT as UAC-0114. Winter Vivern is resource-limited but highly creative, showing restraint in the scope of their attacks. Their activities align closely with global objectives supporting the interests of Belarus and Russia. They have targeted victims in the defense and government sectors in countries such as India, Lithuania, Moldova, Poland, Slovakia, Tunisia, Ukraine, USA, and Europe. Winter Vivern has used novel tools like APERETIF and exploited vulnerabilities in Zimbra and Roundcube Webmail servers in 2023. Their motivation is information theft and espionage. The threat actor's country of origin is unknown.





Report 3

Summary:
The threat actor Winter Vivern, also known as TA473, has been targeting NATO-aligned governments in Europe by exploiting a Zimbra vulnerability (CVE-2022-27926) in publicly facing webmail portals since at least February 2023. The threat actor conducts reconnaissance and reverse engineers bespoke JavaScript payloads to steal usernames, passwords, and CSRF tokens from government entities' webmail portals. TA473's targeting aligns with Russian and/or Belarussian geopolitical goals related to the Russia-Ukraine War. The threat actor has been observed targeting US elected officials and staffers as well. TA473's phishing campaigns involve sending emails from compromised addresses, spoofing the from field, and including benign URLs that redirect to malicious actor-controlled resources. The threat actor's persistent approach to vulnerability scanning and exploitation demonstrates a focus on compromising specific targets in the European government sector. Proofpoint researchers recommend patching Zimbra Collaboration versions and restricting resources on publicly facing webmail portals to prevent such attacks. TA473's custom JavaScript payloads and phishing techniques indicate a level of sophistication and persistence in targeting high-profile organizations. The threat actor's tactics, techniques, and procedures (TTPs) are tracked by security vendors and have been observed since at least 2021. TA473's activities highlight the importance of proactive cybersecurity measures to mitigate the risk of targeted attacks.





Report 4

Winter Vivern is an Advanced Persistent Threat (APT) group with pro-Russian objectives that has been active since early 2021. The threat actor has targeted government organizations in Lithuania, India, Vatican, Slovakia, Poland, Ukraine, Italy, and private telecommunications organizations supporting Ukraine. Winter Vivern employs tactics such as phishing websites, credential phishing, and deployment of malicious documents tailored to specific organizations. The threat actor uses custom loaders and malicious documents to gain unauthorized access to sensitive systems and information. Winter Vivern's novel techniques include mimicking government domains to distribute malicious downloads and utilizing batch scripts disguised as virus scanners to prompt malware downloads. The group's malware family, APERETIF, automates victim data collection and maintains access, beaconing outbound to actor-controlled domains. Winter Vivern's resourcefulness, flexibility, and creativity in their attacks make them a formidable force in the cyber domain. The threat actor's operations have been ongoing since early 2021, with recent activity reported in March 2023.





Report 5

Winter Vivern, a threat actor, was identified in July 2021 targeting European governments with an active infection campaign. The threat actor utilized XLM macros in Excel files to execute malicious commands, potentially created using SharpShooter. The actor established persistence through scheduled tasks and implemented a minimal RAT for command execution and data exfiltration. The actor's domain was registered on July 1st and associated with IROKO Networks Corporation/Scalaxy B.V. The actor targeted government institutions from various countries, including the Vatican, Lithuania, and Slovakia. The threat actor evolved its techniques over time, with indicators of compromise including specific IP addresses and domain names. The actor's TTPs indicate a high level of sophistication and persistence in targeting specific entities. The report provides detailed insights into the actor's capabilities and novel techniques used in the campaign.





Report 6

Summary:
In June 2023, Google's Threat Analysis Group (TAG) discovered an in-the-wild 0-day exploit targeting Zimbra Collaboration, an email server used by many organizations. The exploit, now patched as CVE-2023-37580, was used by four different threat groups to steal email data, user credentials, and authentication tokens. The vulnerability was a reflected cross-site scripting (XSS) issue. Campaigns targeted government organizations in Greece, Moldova, Tunisia, Vietnam, and Pakistan. Winter Vivern (UNC4907), an APT group, exploited the vulnerability before the official patch was released. The exploitation of this vulnerability highlights the need for organizations to apply security updates promptly. The discovery of multiple campaigns exploiting the vulnerability demonstrates the importance of timely patching and the monitoring of open-source repositories for opportunistic exploitation. TAG urges users and organizations to keep software up-to-date for protection. The report includes indicators of compromise (IoCs) for tracking malicious activity. The exploitation of XSS vulnerabilities in mail servers underscores the need for thorough code auditing. TAG will continue to focus on detecting and preventing 0-day exploitation.


