
Report 1

Summary:
- Threat actor: TEMP_Heretic, also known as Operation EmailThief
- First seen: 2021
- Targeted spear-phishing campaigns against a customer using a zero-day XSS vulnerability in Zimbra email platform
- Two attack phases: reconnaissance and luring targets to click malicious links
- Exploitation allowed attacker to run arbitrary JavaScript in user's Zimbra session
- Motivation: Information theft and espionage
- Country of origin: China
- Observed attacked sectors: Government, Media
- Observed attacked countries: Europe
- Novelty: Exploiting zero-day XSS vulnerability in Zimbra platform
- Date of report modification: 2022-02-04





Report 2

Summary:
- Threat actor TEMP_Heretic exploited a zero-day XSS vulnerability in the Zimbra email platform in December 2021.
- The attacker targeted organizations in the European Government and Media sectors.
- The attack involved spear-phishing campaigns in two phases, with the second phase aiming to compromise email data.
- The attacker used unique subdomains and themes in phishing emails to lure targets.
- The exploit allowed the attacker to steal user mail data and attachments.
- The attacker's infrastructure was identified to be hosted on virtual private servers purchased via BitLaunch.
- Volexity believes the attacker is likely of Chinese origin based on observed factors.
- The vulnerability remains unpatched, affecting Zimbra versions 8.8.15 P29 & P30.
- Approximately 33,000 servers are running the Zimbra email server.
- Volexity recommends blocking indicators at the mail gateway and network level and upgrading to Zimbra version 9.0.0.


