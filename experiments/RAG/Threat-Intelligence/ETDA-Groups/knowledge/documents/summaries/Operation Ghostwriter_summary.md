
Report 1

Summary:
- Threat actor activity observed by Google's Threat Analysis Group (TAG) in Ukraine and surrounding regions.
- FancyBear/APT28, attributed to Russia GRU, conducted large credential phishing campaigns targeting ukr.net users, a Ukrainian media company.
- Ghostwriter/UNC1151, a Belarusian threat actor, targeted Polish and Ukrainian government and military organizations with credential phishing campaigns.
- Mustang Panda or Temp.Hex, a China-based threat actor, targeted European entities with lures related to the Ukrainian invasion.
- DDoS attacks were observed against Ukrainian sites, with Project Shield offering protection against such attacks.
- TAG continues to monitor and share information to protect users globally.
- Date: March 7, 2022.

Note: Malformed report





Report 2

Summary:
The threat actor known as Asylum Ambuscade has been operating since at least 2020, targeting bank customers and cryptocurrency traders in North America and Europe, while also conducting cyberespionage against government entities in Europe and Central Asia. They were first publicly identified in March 2022 after targeting European government staff assisting Ukrainian refugees. The group uses implants developed in script languages like AutoHotkey, JavaScript, Lua, Python, and VBS. They have been observed using novel techniques such as leveraging the Follina vulnerability and developing a Node.js downloader named NODEBOT in March 2023. Asylum Ambuscade has targeted over 4,500 victims worldwide since January 2022, with a focus on individuals, cryptocurrency traders, and small to medium businesses. The group's toolset includes various plugins for their AutoHotkey-based downloader AHKBOT, allowing for activities like keylogging, screenshot capture, and password stealing. The threat actor is believed to be a cybercrime group with some cyberespionage activities on the side, operating in a wide range of regions and sectors. The report was published on June 8, 2023, by ESET Research.





Report 3

Summary: Russian state hackers targeted the German Parliament through a spearphishing attack, gaining access to the email accounts of several members. The attack, suspected to be carried out by the Ghostwriter hacking group, aimed to push narratives aligned with Russian security interests. The attackers used fabricated personas posing as journalists and analysts to target audiences in Lithuania, Latvia, and Poland with anti-NATO narratives. This attack follows similar incidents in Norway and Ukraine, where Russian state hackers targeted government entities. The novelty lies in the use of information operations tactics to promote specific narratives. The operation window for this attack was reported on March 26, 2021.





Report 4

Summary:
The GhostWriter APT group targeted state entities of Ukraine with a spear-phishing campaign using a Cobalt Strike Beacon. The attack involved a RAR-archive with a VBScript code that delivered the malicious program Cobalt Strike Beacon. The campaign was attributed to the GhostWriter APT group based on the code used in the attack. The GhostWriter APT group has been linked to the government of Belarus and has been involved in disinformation campaigns since at least 2017. The attack was detected by Ukraine CERT-UA, which also published Indicators of Compromise for the campaign.





Report 5

Summary:
Operation Ghostwriter, a state-sponsored threat actor originating from Belarus, has been conducting a long-standing influence campaign targeting Lithuania, Latvia, and Poland with anti-NATO narratives since at least 2017. The victims operate in sectors such as Defense, Education, Government, and Media across countries like Colombia, Estonia, France, Germany, and Ukraine. The threat actor has used tools like Cobalt Strike, HALFSHELL, and Impacket, with novel techniques such as 'Browser in the Browser' phishing. Ghostwriter has been involved in cyber espionage, information theft, and sabotage, with reported operations targeting Ukrainian military and public figures. The threat actor has been active in recent years, with counter operations being conducted to mitigate their activities.





Report 6

Summary:
- Threat actor "Ghostwriter," a Belarusian group, has been observed using novel phishing techniques in their campaigns.
- The group introduced a 'Browser in the Browser' phishing technique in mid-March, combining it with hosting credential phishing landing pages on compromised sites.
- Ghostwriter targeted victims with fake login pages appearing to be from legitimate domains like passport.i.ua.
- The threat actor's capability and adoption of new techniques demonstrate advanced phishing tactics.
- The victims targeted were not specified in the report.
- The report was published on March 30, 2022, by Google's Threat Analysis Group.
- The threat actor's activities were part of ongoing cyber activity in Eastern Europe, particularly related to the war in Ukraine.
- The report highlights the continuous monitoring and actions taken by Google to protect users from such threats.
- The report does not mention the specific operating sector or type of company targeted by the threat actor.
- The report provides insights into the evolving tactics and capabilities of threat actors in the region.





Report 7

UNC1151, assessed to have links to the Belarusian government, has been identified as the threat actor behind "Operation Ghostwriter." The threat actor has targeted a wide range of governmental and private sector entities, with a focus on Ukraine, Lithuania, Latvia, Poland, and Germany, as well as Belarusian dissidents, media entities, and journalists. UNC1151 has been active since at least 2016, utilizing credential theft domains to steal victim credentials and conducting malware-based intrusions primarily in Eastern Europe. The threat actor has targeted multiple Belarusian media entities and political opposition members, with evidence suggesting operational continuity and no links to previously tracked Russian groups. Technical evidence indicates that the operators behind UNC1151 are likely located in Minsk, Belarus, with a possible connection to the Belarusian military. UNC1151 has shown an improvement in technical skills over time, using a proprietary suite of malware and primarily employing GoPhish for email operations. The Ghostwriter campaign, aligned with Belarusian interests since mid-2020, has focused on promoting narratives critical of neighboring governments and NATO, with content published in multiple languages. While there is uncertainty around the sources of written content and malware used by UNC1151, Mandiant assesses with high confidence that both UNC1151 and Ghostwriter operations are linked to the Belarusian government. The threat actor's activities highlight the accessibility and deniability of provocative information operations, showcasing the impact of cyber operations in achieving governmental goals. (Source: https://www.mandiant.com/resources/unc1151-linked-to-belarus-government)





Report 8

Summary:
- Threat actor: UNC1151, linked to Belarusian government and military
- Region: Ukraine
- Operating sector: Military personnel and related individuals
- Date: February 25, 2022
- Evidence: Spearphishing campaign targeting Ukrainian armed forces personnel, using compromised accounts to send phishing emails to contacts
- Novelty: Use of domains i[.]ua-passport[.]space and id[.]bigmir[.]space, impersonating legitimate services
- Tools and techniques: Phishing emails asking targets to click embedded links for verification
- Capability: UNC1151 group identified as military cyberspies and officers of Belarus Ministry of Defense
- Hybrid warfare campaign: Phishing attacks part of larger cyber operations targeting Ukraine
- Additional information: Active phishing campaigns targeting Ukrainian citizens with malicious documents, impersonation of humanitarian organizations for scams.





Report 9

Summary:
- Threat actor: FROZENBARENTS (aka Sandworm), attributed to Russian Armed Forces’ Main Directorate of the General Staff (GRU) Unit 74455.
- Region: Ukraine, with a focus on the energy sector, defense industry, and regional webmail providers.
- Operating sector: Energy, defense, and regional webmail services in Eastern Europe.
- Novel tools and techniques: Utilized EXIM mail servers globally, deployed Adminer for data exfiltration, used reflected cross-site scripting (XSS) on Ukrainian government websites, and targeted users associated with popular channels on Telegram.
- Date: First quarter of 2023.
- Evidence of capability: Conducted phishing campaigns, hack and leak operations, information operations, and exploited vulnerabilities in various sectors.
- Source: Google Threat Analysis Group report titled "Ukraine remains Russia’s biggest cyber focus in 2023" dated April 19, 2023.





Report 10

Summary:
- Threat actor: Ghostwriter, a Belarusian threat actor
- Region: Eastern Europe, primarily targeting Ukraine and Lithuania
- Operating sector: Government, defense officials, politicians, NGOs, think tanks, journalists
- Novelty of tools and techniques: Using compromised websites for credential phishing, targeting high-risk individuals, and sending links to attacker-controlled domains
- Date: Mid-April 2022
- Evidence of capability: Successfully targeting high-risk individuals in Ukraine and Lithuania, using unique phishing domains and emails
- Collaboration: TAG worked with Yahoo! Paranoids Advanced Cyber Threats Team in the investigation
- Actions taken: Blocking phishing domains through Google Safe Browsing, alerting targeted users through government-backed attacker warnings
- Ongoing monitoring: TAG continues to actively monitor activity related to Ukraine and Russia, as well as other global threat actors.





Report 11

Summary:
- Threat actor identified as "Ghostwriter" targeted people in Ukraine, including military and public figures, through coordinated inauthentic behavior.
- The threat actor used fake personas across multiple social media platforms and websites, posing as independent news entities.
- The operation involved fake accounts with AI-generated profile pictures and websites masquerading as news outlets.
- Ghostwriter attempted to compromise accounts through email phishing and posted disinformation portraying Ukrainian troops negatively.
- Meta took down networks operated from Russia and Ukraine engaging in coordinated inauthentic behavior targeting Ukraine.
- The threat actor's activities were detected in February 2022.
- Meta rolled out additional privacy and security measures in response to the increased targeting of individuals in Ukraine and Russia.
- Recommendations were made for users in Ukraine and Russia to strengthen online account security, including avoiding password reuse and using two-factor authentication.
- Specific tools like locking profiles and limiting friend lists were implemented to enhance user security.
- The threat actor's activities were linked to previous operations removed in April 2020, involving individuals in Russia, Ukraine, and Crimea.


