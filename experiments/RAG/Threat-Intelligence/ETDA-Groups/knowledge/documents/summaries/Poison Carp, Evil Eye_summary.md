
Report 1

Summary:
- Threat actor named "Evil Eye" targeted Uyghur individuals and organizations, primarily those outside of China, through a series of cyber attacks.
- The attacks involved compromising at least 11 Uyghur and East Turkistan websites to track and target visitors, including the use of a 64-bit ARM executable exploit targeting Android OS users.
- Tools and techniques used by the threat actor included Scanbox profiling and exploitation framework, Google Applications for accessing Gmail accounts, and doppelganger domains emulating legitimate sites.
- The threat actor, identified as "Evil Eye," was responsible for ongoing campaigns against Uyghurs, with evidence of at least two Chinese APT groups involved in the attacks.
- Volexity, a cybersecurity company, observed the attacks and identified the threat actor as "Evil Eye," tracking their activity under this moniker.
- The attacks were part of a wider digital surveillance and exploitation campaign against the Uyghur diaspora, with a focus on compromising websites catering to Uyghurs.
- The report detailed the use of malicious code on compromised websites, including instances targeting Android users and utilizing obfuscated URLs.
- The threat actor also leveraged Scanbox framework for data collection and transmission, with ties to targeting Google OAuth access to Gmail accounts.
- The attacks were ongoing and targeted Uyghur individuals and organizations, highlighting the advanced and persistent nature of the threat actor.
- Date of the report: September 2, 2019.





Report 2

EvilBamboo, a threat actor tracked by Volexity, has been conducting multi-year campaigns targeting Tibetan, Uyghur, and Taiwanese individuals and organizations, representing CCP adversaries. The threat actor has been active for over five years, deploying custom Android and iOS malware, as well as a JavaScript profiling framework to target specific devices running iOS. They have developed three custom Android malware families, created fake websites and social media profiles to distribute malware, and built communities on platforms like Telegram for malware distribution. EvilBamboo has also targeted Taiwanese users through APK sharing forums and utilized fake websites to distribute backdoored versions of popular apps like Signal and Telegram. The threat actor has been observed using sophisticated techniques like real-time SMS stealing and browser fingerprinting. Volexity attributes this activity to EvilBamboo, operating in the interest of the Chinese state. The report provides detailed analysis of the capabilities and distribution methods of the three malware families employed by EvilBamboo. The threat actor's use of novel tools and techniques, along with their long-running campaigns and targeting of specific ethnic groups, demonstrate their advanced capabilities and persistence in conducting cyber espionage operations. The report was published on September 22, 2023, by Volexity.





Report 3

Evil Eye threat actor resurfaced on April 21, 2020, targeting Uyghur websites with an iOS exploit using an open-source framework called IRONSQUIRREL. The threat actor leveraged a vulnerability in WebKit to install a new version of the implant named INSOMNIA on iOS versions 12.3, 12.3.1, and 12.3.2. The exploit chain was observed across multiple compromised Uyghur websites, with six different exploit sites and five instances of the malware implant identified. The implant communicated securely over HTTPS, employed obfuscation techniques, and targeted apps like Signal and ProtonMail. The threat actor lacked persistence mechanisms, indicating a need for quick data extraction. Despite patched vulnerabilities, a significant number of potentially vulnerable devices remain, highlighting the threat actor's ongoing success. The threat actor's capability to target multiple platforms and maintain surveillance on the Uyghur population demonstrates a sophisticated and persistent threat.





Report 4

Summary:
- Threat actor: Poison Carp, Evil Eye
- Region: China
- Operating sector: Surveillance campaigns targeting Uyghurs
- Type of company of victims: Uyghur minorities in China, Muslim populations in Turkey and Afghanistan
- Evidence of capability: Extensive data collection capabilities, targeting pre-criminal activities indicative of religious extremism or separatism
- Novelty of tools and techniques: BadBazaar surveillanceware family attributed to Chinese-backed hacking group APT15, iOS variant targeting Tibetans, Android variant targeting Uyghurs, exfiltration of personal data, use of SSL pinning, deployment through social messaging app Telegram
- Date: January 22, 2024
- Operation time window: Ongoing surveillance campaigns since late 2018
- Source: Lookout Threat Intelligence Lab

Malformed report.





Report 5

Summary:
Between November 2018 and May 2019, Tibetan groups were targeted with 1-click mobile exploits by a threat actor known as POISON CARP. The threat actor posed as NGO workers, journalists, and other fake personas to send malicious links via WhatsApp, leading to the installation of spyware on iOS and Android devices. POISON CARP used a total of eight Android browser exploits, one Android spyware kit, and one iOS exploit chain and spyware. The Android malware used was a fully featured spyware kit not previously documented. The campaign marked the first documented case of one-click mobile exploits targeting Tibetan groups, showcasing an escalation in digital espionage sophistication. The threat actor's tactics included social engineering tailored to targets, with evidence of coordination with other campaigns targeting Uyghur groups. The report highlights the novelty of the tools and techniques used, emphasizing the need for increased digital security measures within civil society groups. The campaign represents a significant threat to the digital security of Tibetan organizations and civil society in general.





Report 6

Summary:
The threat actor known as Earth Empusa, also referred to as Poison Carp/Evil Eye, has been identified conducting phishing attacks to distribute an Android spyware named ActionSpy. The group targeted Uyghurs in Tibet, Turkey, and Taiwan, compromising Android and iOS mobile devices. Earth Empusa has been observed using phishing pages to deliver malware, with evidence of a phishing page disguised as a popular Android video application in Tibet. ActionSpy, the Android spyware, has capabilities to collect device information, spy on instant messages, and steal chat logs from messaging apps like WeChat, QQ, WhatsApp, and Viber. The threat actor uses social engineering lures and watering hole attacks to target victims, with recent injections on Uyghur-related sites and iOS exploit chain attacks. The malware is protected by Bangcle and uses Accessibility services to access chat logs indirectly. Earth Empusa's activity has been ongoing since at least 2017, with indicators of compromise and MITRE ATT&CK techniques associated with their operations. Users are advised to update devices, install apps from trusted sources, and consider security solutions like Trend Micro™ Mobile Security. Organizations can benefit from the Trend Micro™ Mobile Security for Enterprise suite for comprehensive protection against mobile threats.





Report 7

Summary:
The threat actor known as Poison Carp, also identified as Evil Eye, has been active since 2018, targeting Tibetan and Uyghur activists through sophisticated espionage campaigns. Operating from China, the threat actor used tailored WhatsApp messages to deliver spyware to iOS and Android devices, along with OAuth phishing pages. Poison Carp utilized a variety of Android browser exploits, iOS exploit chains, and spyware kits, including previously undocumented tools. The group's activities represent an escalation in digital espionage threats, with victims in countries like Australia, Canada, and the USA. The threat actor's motivation is information theft and espionage, with reported hacking operations dating back to 2018. Counter operations have been launched against the threat actor, highlighting the ongoing efforts to combat their activities.





Report 8

Summary:
- Threat actor named "Poison Carp, Evil Eye" targeted iPhone users through hacked websites in indiscriminate watering hole attacks.
- The attacks used iPhone 0-day exploits to install monitoring implants on devices, affecting users in certain communities over a two-year period.
- Five unique iPhone exploit chains were discovered, covering iOS versions from 10 to 12, indicating sustained hacking efforts.
- Fourteen vulnerabilities were exploited, including privilege escalation chains, browser exploits, kernel vulnerabilities, and sandbox escapes.
- At least one privilege escalation chain was unpatched at the time of discovery, prompting an out-of-band release by Apple.
- The threat actor's tools and techniques demonstrated advanced capabilities to steal private data like iMessages, photos, and GPS locations in real-time.
- The attacks highlighted vulnerabilities in Apple's software development lifecycle, with overlooked code and lack of testing.
- The threat actor's campaign showcased mass exploitation capabilities, targeting users based on geographic or ethnic factors.
- The report emphasized the need for users to be aware of mass exploitation risks and the potential for real-time monitoring of private activities.
- The findings suggest a shift in focus towards monitoring entire populations in real-time, rather than individual dissidents.


