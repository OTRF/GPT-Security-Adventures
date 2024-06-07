# Reference for threat actor for "Molerats, Extreme Jackal, Gaza Cybergang"

**Title**: Moonlight – Targeted Attacks in the Middle East by Vectra AI Security Research team

**Source**: https://blog.vectra.ai/blog/moonlight-middle-east-targeted-attacks

## Content
Moonlight – Targeted Attacks in the Middle East by Vectra AI Security Research team


























Test your Microsoft environment before a breach occurs.Sign up for a complimentary consultation now









Platform












AI Platform

The integrated signal for extended detection and response (XDR). Detect – Prioritize – Investigate – RespondPublic Cloud

SaaS

Identity

Network

Managed Extended Detection & Response Services

See our integrations

Our AI

Arm your security analysts with intel to stop attacks fast. Attack Signal Intelligence analyzes in real-time to show where you’re compromised right now.SOC Use Cases

SOC ModernizationSIEM / SOAR Optimization

IDS replacement

EDR extension

Cyber ResilienceCloud Identity Protection

Cloud Control Plane Protection

Cloud Posture Improvement

Risk ManagementCritical Infrastructure Risk

OT Environment Risk

Remote Workforce Risk

See all use cases

Hybrid Attack TypesAccount Takeover

Advanced Persistant Threats

Data Breach

Ransomware

Supply Chain Attacks

Nation State Attacks

Hybrid Attacks ProgressionsZero-day exploit

Spear Phishing

MFA Bypass

Live off the Land

Credential Stuffing

IndustriesBanking and Finance

Government/Federal

Telecom

Manufacturing

Pharmaceuticals

Energy & Utilities

Healthcare

Higher Education

Real Estate

Retail & Wholesale

Customers

Support HubCustomer Stories

Knowledge Center

Product Releases

Professional ServicesManaged Detection & Response Services

It’s back! Two exciting locations. Charlotte, North Carolina 03/11-14/2024; Lisbon, Portugal 03/25-28/2024Register now


Customer login

Research  & InsightsResources

Blog

Breaking news and expert insightsEvents & Webinars

Blue Team Workshops, on-demand webinars and global events near youResource Center

Research reports, attack anatomies, white papers, guides, datasheets and customer storiesProduct in actionVectra AI Platform Demo

CDR Product Tour (AWS)

NDR Product Tour (Ransomware)

CDR/IDR Product Tour (Azure AD, M365)

See the Vectra AI Platform in action.See how integrated signal from Vectra AI lets you see and stop sophisticated attacks other technologies miss.Take the interactive tour

Partners

Find a PartnerStrategic AlliancesTechnology partners

Become a PartnerOverview

Managed Services Provider (MSSP)

Value Added Reseller (VAR)


Partner portal login

Company

About Us

See why we’re the world leader in AI securityLeadership

Board of Directors

Investors

Media Coverage

Contact Us

Request an intro with a Vectra AI security expertSupport

Deployment guides, knowledge base, release notes and security announcementsCareers

Join the team behind the world’s first AI-based cybersecurity platformNews releases

Breaking news from Vectra AIVectra AI Blog

Expert insight from security researchers, data scientists and engineersMedia Room

Take the first step to an open XDR solution with Vectra AI Platform IntegrationsTechnology integrations are the answer to achieving an open XDR solution. Read how Vectra AI Platform Integrations can help you accomplish an XDR strategy with your current security technology stack.Read more

Contact UsFree Demo

English

FrançaisDeutsch日本語EspañolItalianoTürkçe













Platform

Customers

Research & InsightsResources

Partners

Company

English

FrançaisDeutsch日本語EspañolItalianoTürkçeLog inFree Demo

BackPlatformThe integrated signal for extended detection and response (XDR). Detect – Prioritize – Investigate – RespondPublic CloudSaaSIdentityNetworkManaged Extended Detection & Response ServicesSee our IntegrationsOur AIArm your security analysts with intel to stop attacks fast. Attack Signal Intelligence analyzes in real-time to show where you’re compromised right now.Use Cases

Attack Types

Emerging Attack Methods

Industries



Back / PlatformUse CasesSOC ModernizationSIEM / SOAR OptimizationIDS replacementEDR ExtensionCyber ResilienceCloud Identity ProtectionCloud Control Plane ProtectionCloud Posture ImprovementRisk ManagementCritical Infrastructure RiskOT Environment RiskRemote Workforce RiskSee all use cases

Attack TypesAccount TakeoverAdvanced Persistant ThreatsData BreachRansomwareSupply Chain AttacksNation State AttacksEmerging Attack MethodsHybrid CloudLazarus GroupLapsus$Volt TyphoonMicrosoft SaaSIndustriesBanking and FinanceGovernment/FederalTelecomManufacturingPharmaceuticalsEnergy & UtilitiesHealthcareHigher EducationReal EstateRetail & Wholesale

BackCustomersSupport HubCustomer StoriesKnowledge CenterProduct ReleasesProfessional ServicesManaged Detection & Response ServicesResourcesBlogEvents & WebinarsResource CenterProduct in actionVectra AI Platform DemoCDR Product Tour (AWS)NDR Product Tour (Ransomware)CDR/IDR Product Tour (Azure AD, M365)Find a PartnerStrategic AlliancesTechnology partners

Become a PartnerOverviewManaged Services Provider (MSSP)Value Added Reseller (VAR)About UsSee why we’re the world leader in AI securityLeadershipBoard of DirectorsInvestorsMedia CoverageContact Us

Support

Careers

News releases

Vectra AI Blog

Media Room

CyberattackMoonlight – Targeted Attacks in the Middle EastOctober 26, 2016Vectra AI Security Research teamCybersecurity

































Vectra Threat Labs researchers have uncovered the activities of a group of individuals currently engaged in targeted attacks against entities in the Middle East. We identified over 200 samples of malware generated by the group over the last two years. These attacks are themed around Middle Eastern political issues and the motivation appears to relate to espionage, as opposed to opportunistic or criminal intentions.These are not technically sophisticated attackers. However, they do deploy some novel tactics, detailed below, and the implications of these attacks could be significant. Both the tools and targets of Moonlight are reminiscent of “Gaza Hacker Team,” a group of attackers that are said to be politically aligned to the Hamas[1]. In spite of these commonalities, we have not identified any firm links between the two groups.We refer to this group of attackers as Moonlight, after the name the attackers chose for one of their command-and-control domains.[1] http://www.securityweek.com/gaza-cybergang-attacks-attributed-hamasMoonlight’s targetsVectra Networks worked with providers to sinkhole Moonlight’s command-and-control infrastructure. The hosts seen via our sinkhole show a clear targeting of Middle Eastern victims:Figure 1: Moonlight’s victims of attacksMost of these victims are connecting from home networks, and are therefore unidentifiable, though one notable victim is a Palestinian news organization.Vectra believes the victims from the United States and China are outliers. These infected machines were primarily from university networks and were likely either security researchers sandboxing malware or overseas students targeted for links to their homeland.Indirect targeting data from to the online virus scanning site VirusTotal, and traffic statistics from the URL linking services the attackers use indicate many of these attacks are targeted towards either small groups or individual targets:Figure 2: The statistics show one of the attacker’s malicious files, registering only two clicksOpenMe.docx.exeThe attackers name their malware as documents of interest to their victims, to entice them to open them. The malicious decoy documents display themes relevant to Middle Eastern politics, and provide some indication as to who the intended targets may be:20160611-NCRI-AR-Rajavi-Syria-Ramadan.docx.exeAssassination of Talal of Jordan YouTube.exeAudio recording of the meeting of Egyptian Emirati. MP3.exeBrigadier Alleno behind moral projection of Zakaria al-Agha.docx.exeexeFatah foreign conspiracies.exeWapons and ammunition stores found while digging a waterway in Egyptian Rafah.exeHamas and Fatah agree to the following.exeHamas and the Egyptian army.exeHamas and the Salafist jihadist in the Gaza Strip.scrHamas Betrayal.exeImportant leaking security meeting Arab Emirates.exescrLeaked audio recording of the meeting of Egyptian security Emirates.mp3.exeLeaking important Arab Emirates security meeting.mp3.exeMeeting of the Executive Committee of the PLO.exePresident sources oust Fatah leadership in Gaza and the cost Abu Samhadana to lead the organization.doc.exeSawiris and the project of the Suez Canal.exeSinai Bombings.docx.exeThe full truth behind Abu Ghussains disease.exeThe grandson of President Abbas in the festival of love, and what response was Mr. Samir Mashharawi him.exeThe names of the perpetrators of the bombings in the Gaza Strip.exeThe son of Mufti takfiri Hamas fist anti-drug police.docx.exeMoonlight demonstrates that 0-days, or even exploits, aren’t required to successfully compromise machines. Instead, they show a preference for the classic social engineering approach of sending e-mails with attachments or links to files with the filename [legitimate file-extension].exe, for example:scrSecrets documents Panama.docx.exedoc.exeAudio recording of the meeting of Egyptian Emirati.mp3.exeMoonlight typically makes good on the promised theme of the lures, and present the victim with a relevant “decoy document”:Figure 3:"Meeting of the Executive Committee of the PLO" - Decoy documents opened on victim machines by the malwareFigure 4: Decoy video about women trafficked to SyriaImpersonated new organizationsThe attackers typically deploy malicious files via shortened URLs, presumably to look more innocuous. Many of the links and domains impersonate Middle Eastern media organizations such as Eln News and Wattan TV:http://bit[.]do/www-elnnews-comhttp://wattan.tep[.]su/deaf.rarhttp://www.aman-news[.]com/arab/betrayal%20of%20Hamas.%20exeOne domain impersonating the media, Alwatenvoice[.]com, also hosts “landing pages” to encourage victims to download the malware, described below.DistributionOne Facebook user has shared a number of posts from the malicious Alwatenvoice[.]com:Figure 5: Two pages containing malware shared by the user on FacebookThe second post is of particular interest. The Facebook information box says the article is from All4Syria[.]info, a popular independent news outlet reporting on Syria, but in fact it leads to Alwatenvoice[.]com:Figure 6: The link to All4Syria[.]info that actually leads to Alwatenvoice[.]comThe user is then presented with a page that looks very much like the real All4Syria website:Figure 7: The malicious page on Alwatenvoice[.]com on the left, and the legitimate site All4Syria[.]nfo on the rightIf a user clicks “play,” they are asked to download malware named شبكات الدعارة السورية.mp4.exe (“Syrian Prostitution Rings.mp4.exe”).The profile posting these malicious links has a very small number of public posts. The first post from 2015 shows the user setting their wallpaper to the logo of Fatah. There are two celebrations of Facebook friendship displayed publicly, one of whom can be identified from the name and Facebook profile information. Their details match that of a senior Fatah militant who Reuters reported was targeted for assassination during violent struggles between Hamas in Fatah in 2007.We would stress that even if the account is controlled by the attackers it could be an account that they have compromised, or impersonates an innocent and unconnected person. It is also possible that the account sharing the malicious links belongs to a user who is unknowingly spreading malicious content.H-WormMoonlight typically delivers an obfuscated version of the widely available H-Worm[2], a malicious Visual Basic Script worm, as their first stage backdoor. Moonlight deploy an ever-changing range of deployment scripts to evade anti-virus software. Many of these use basic scripts within self-extracting RAR archives to install the malware:[2] https://www.fireeye.com/blog/threat-research/2013/09/now-you-see-me-h-worm-by-houdini.htmlFigure 8: Some of the malicious scripts used by Moonlight to deploy H-WormIn these excerpts, we see the Moonlight make some strange choices in deploying their malware such as:Opening a decoy document from the Windows System folderPreventing users from deleting any files (including the installed malware) from the C:\temp\ folderThere is a large amount of variation in the scripts used to install malware, and it’s likely that the large number of samples have been produced by hand, rather than a more productionised process of using build tools that is preferred by more sophisticated groups.njRatRecords to URLs that users have submitted to VirusTotal record the attackers installing additional malware using the access they gained with the first stage H-Worm malware. Examples of this are recorded in URLs submitted to VirusTotal[3] for the domain fun2[.]dynu.com:DateLocation2016-05-24C:/Users/Administrator/Desktop/service.exe2016-05-31C:/Users/Administrator/Desktop/WindowsService1.exe2016-08-10C:/users/administrator/desktop/k.exe2016-08-10C:/users/administrator/desktop/service.exe[3] https://www.virustotal.com/en/domain/fun2.dynu.com/information/As with earlier stages, the attackers employ a number of methods to deploy the well-known[4] njRat which seems to vary from sample to sample. In one example the malware stores a program within a base64 compressed blob. This is then loaded into memory, and executed using EntryPoint.Invoke():Figure 9: An example loader for njRat deployed by Moonlight[4] http://www.symantec.com/connect/blogs/simple-njrat-fuels-nascent-middle-east-cybercrime-scene and http://threatgeek.typepad.com/files/fta-1009---njrat-uncovered.pdfThe 24 Kb of code this decodes to is another .NET application – njRat. Other droppers also decrypt the blob, before it is executed. Both njRat and code obfuscators such as this are freely available, and there are a plethora of tutorials available online to help budding hackers use them with limited technical knowledge.A significant operationMoonlight’s command-and-control infrastructure is very simple. It consists of dynamic domains controlled via home internet connections in the West Bank of Palestine. We were surprised to identify a very large number of varied malware samples (over 200) attached to this simple infrastructure:Figure 10: Moonlight’s infrastructureAttacker evolutionThe earliest attacks appear to be non-targeted, opportunistically inviting victims to click links on Youtube videos and social media posts typical of Middle-Eastern “hacktivists.” Later attacks appear to target particular groups or individuals. Moonlight’s usage of the Google URL shortening service allows us to roughly compare attacks over time:Figure 11: One attack from December 2014 (left), and one from December 2015 (right)Who are the attackers?In general, the assigned IP-location of command and control servers is a poor indication[5] of attacker locations. However, in this case the provided locations of home networks in the Gaza strip are likely to be accurate and fits with other details from the attacks. The attackers also demonstrate low operational security, particularly in their earlier attacks. Domain Whois records and social media posts provide strong ideas as to the identities of some of those involved. It would not be prudent to publish the identities of the possible attackers in a conflict zone.Perhaps a more interesting question is "What are the attackers’ aims?" Or if they are being directed, who is ultimately funding and tasking them?[5] With reference to http://www.csoonline.com/article/3028788/techology-business/norse-corp-deconstructing-threat-intelligence-on-iran.html and https://threatbutt.com/map/Countering attacksAttacks such as these are often overlooked due to their low technical sophistication. But the stakes of these attacks are high, even if the attacker skill level is low. If the motivation behind these attacks is indeed political, the consequences could mean loss of life. Violence between rival political factions in Palestine has resulted in the deaths of hundreds of people.Individuals and organizations outside of the Middle East are unlikely to encounter the attacks by Moonlight. However, the tools and techniques deployed are typical of low-skilled but determined attackers within the Middle East and serve as an example of the kinds of attacks that often slip through. Moonlight’s strategy of obfuscating well known malware appears to be fairly successful at evading host-based security mechanisms. The network communications of the well-known malware families such as H-Worm and njRat should still trigger existing network signature base detection tools.Vectra customers are protected through the following generic detections:Suspicious HTTP – Provides generic detection of HTTP based malware such as H-WormExternal Remote Access –Provides generic detection of RATs such as njRatMalware Update – Provides generic detection of secondary malware over HTTP(S)Security professionals can review the Appendix for a full listing of file-hashes and domains employed in these attackers.Vectra Threat Labs operates at the precise intersection of security research and data science. We take unexplained phenomena seen in customer networks and dig deeper to find the underlying reasons for the observed behavior. {{cta('c55c408c-ddec-4ebb-a41f-666d25face78')}}AppendixDomainsAny traffic to the following domains on your network should be investigated. Please note that many of these domains have been sinkholed by Vectra .alwatenvoice[.]comelnnewscom.duckdns[.]orgfun1.dynu[.]comfun2.dynu[.]comfun3.dynu[.]comfun4.dynu[.]comfun5.dynu[.]comh.safeteamdyndns[.]seh0tmail.duckdns[.]orghackteam1.spdns[.]dehema200.publicvm[.]comhema200.safeteamdyndns[.]sehema2000.dynu[.]comhp200.spdns[.]euhp500.linkpc[.]nethp600.spdns[.]eumoonlights.linkpc[.]netnew4.spdns[.]euopstin.spdns[.]eurun500.linkpc[.]netrun900.linkpc[.]netwattan24.duckdns[.]orgaman-news[.]comMD5 HashesABD8F478FAF299F8684A517DCB1DF997003F460F6EA6B446F31AA4DC57F3B027568218BB07C021BBAB3B6D6560D7208CAC19A1E5D604D82EF81E35756F3A10D10392F8BE82A297242BAAD10A9A2912EB573138482B185F493B49D3966650CDADAC3918287452FEBD3855FF4BC3D82A0704A4CC757B4D283FF8DE246C19E8D2305947BBAD60D4D00EF545E2FB3B1FD03EAC89E42EE593CEA80030820618F2BCF604B2D3F38055B2B821B30E82C44D604059E18D4ED3C97279DB16984C07213EB1ACAB47BB5E8ED34056905FF63353CABC0512F533BF2E8E5EC9637B804C101C2B5BF5BE6B45292FBA0C0EDC415F248922ACCF82FC29467C08CE087072FEA3D14A05618077C03B80ACE066B9851966FBB15CC9964DD41BE3D9DACBD0425EC032A9ACD58BB34BB275DE1570917624ADE6090606FEE55F39784E9889C1AAA0F278825CFD542A561F1EE679FCD6AA81991F3AAE238D1E52CD4A9DECFE769FE5844747064F0A5FCC869F6EB77405D3FE98AF875E59ACF240E2881B1C1E2F5586C9CA6FAE9E9E3C73483E8B6C6E58E5629DC4D007EB24224A722EA9D8A3DC610B834D7A5F0437C7DC45D4C10A045954DB77DD31B053BBB499D68CCE1782B33FDE7B43FF0975222DE39433A25E672595B1960CDB61381610E76266423ACE96670DE45DC0B0B9332082E98D51CB7265A45A945A220A38DDCC3431BAE448E38C99562162EF6212E9A07225D6B71769D2BBBC20CD04B184FA51604D7EAA5A45350D1E08E5B70A49531FC0C00E991E51F34398F3AB886218A61D18F5A74F82ABC31A5F073C4BB3FB8253595FED348464B5C9A01AD4AD0ABBD2765B563F2B8748485FA84DA07062C0B9EA3638BEF977A7D33970E52E38B532676D6A5A6684B62A078BFBCBBD0B0AED206FC534C310724E122BF6BCDF7F63D933310CFB26EC9913A26BEF230A99B77A14A594A59C3B86EDD940FB35AB5E0B2023BC4ADFBB8157DA9147B9FAFACB64ACAFF36681B16C5717741E17DCB329B82DE5F1C26143083D988B06F6C927C30B40D67579AF550C0A3AEE359C2C71BA64AF25B42E21F01A213C32CC66CFD749B841E134EC7FE48095754742C8A2B8D70BD3B5C667878830DA088527D1B753EC655F56F880655198962CA8DD746431E8B929FC62DB2B3C8CC6A03063767BE1250C15603B17FA333189AB5ED06E0993F7696232159428BCB2BDA5AC2C755E8FEDBB15E754AE3B85A12447B448F6F7E43E0CA048153AC96E5C41243B364092AF0769A042C9ED90A30444606407F77E199FBBF576CF704B71C739E8777EB6C9FF820D67422BA42D4A548E807B0298E372C76C4B69C19F2C3AC23AC392B8631E31BBBD2234DAE56580AAA7F880A7DB0F397D0E9B363DE7DD2B10AFD5D1947FA0E0066C4D355411B8D7DA56A2C7C14693A3AEBE23B3AFD1FD32C900F012CB2A8BA7550F83377C44ADBA238FD0F0EB241981A66D418227FEB7A60727326583B52187E6C28376FC9EE627B51E3F52503397E2DC114B805F977E17558DD89E8029E29DF06E2E488CDDF1D15D0411F3838ED04683C291CFAC28F323F9808D633A8558A35A118A606FB131C082B55A5625661B666A6EE7264D4A974D0FFFED7F39652D1DADC64052167D6A183A3ECC259EE0F3A0C6129F4B0A1F209784BF7071C14119BF9F71B00CBD186B1C168FD207B8F43FC8E0C8D912CF5BF526E551972EBB5454DD3F1325AB5DCA14B58A8A7B9A8F5A1EE4DC72076B1B2D9CB0507E5C94C2B422CCE7C92E26AC3145718E531330B87772D21613AF6A3C3A3908FD4E606A1F19B0571472BEA803A834F7736679781A1D729B1FCB539DFAEECC4BAF875A1E431701FF9D148A3E3CC76CF6753B15070FE3514DAE7681AE3933F3E13EB8E2A9BE281A5763CC9FAEC3F39EDAF7A59E9D9A7577451C14C1E03DE25811C3D6D467837A16BB2976A68FE73FFF571F257A1B0F100ACA1DCCFA1B31C47C9F124FEFE206301B3A5F15F7682A178F789EDB40CEAABA9E510377D02BE92D052F35604CAA9885DD9A77CD10D61A0D2D43A6AB16A9F50B1AD8941673583BC5B7A485119D4A1342D6ADA87840F2473B3A0E0960A1925F3CD0C3B1CF51142459F7B40E751E91179C00129917D70C318C6D16EA599E39550C44FA7F7A4588DC14AE38505662B75DA93CA8A7CFE26B57E168B6C6A18C668E36A3E9391856F46DA93C3B152C358E0F6DB534027AEFB825277764CD9F31BC1F2370D18DD179427D46D38D78A7A60512A45954961966F3B1D4ADEC25AB866C4E061A1E507C14974DD39B071558C619D16C4216DBD24B6317064DA37D31CE4459AC7F4B691C4AB6CF907175D114C48C30A38BF3797D1F1FED52745D36D737EFA7D43F4B95D297E0DB6D63A952B08B6F0E3FE101E71D693473FF431C7CEA3E7AB0130EAA3D7D27548E3F56FA532C571FB409ECD7B6D3C8ECF591381B31D3AA796471B5B0F11F644DE33D57C12A393B12F92A7C44C57DD199B0C678EF409A7DC461DE850849D5DFF6DB76B75D346D3B33BBA5B7CBFA215556AF1A5FEF7E08A6124D94487D2F7ED4897B11798F4639C73D57F901A661D5EEE8DC2507D46E1DC11F7B7441F50621CE82DB335964B8624F8EB0668B539F833B3AF9BD8FFD0390BCA1D43EE78CC3D817FD5A442C7668607AE895D429804022CC7CE1E17852B6D09D5641B6ABCA0D83AD97BF1D5A9044AAFBA6AAC4B7387ED9EACFF28841C51ACE9712AF78BCBDD024D2CE38D2886A00E678E8C23AD8D1CA841C3AFAA8CAF0AC33BF783D5FEAEADBDD2D6B625E7ADD1528311A0CF5FD5EAE276E54A5E32BEF12367C5B31BF9C179E8492C3111C7C0998F0DC1B63967E5C65DDD73E73BE2CC934D5721D4FC62CD98C27A1891DB06D316B43A48DDEFEBF73BF853A53CF799E2E3E1FC244A0751A4E96DDEEE52C00A95167353215D14B3AAA682851685F217EB1CE573FC2BAE79188018799B3D6B2CE50D4DD5F5114635A4B96DE2E753D12CE07F7B3F97C498D3477F828FBFD2AD1B500B62377DDE5795CDF8587E5555CFF74D41551D6D29B9C01C0CBDF38B1562E4F0B735B3E10BAE78DF2A92930596D4E1328B79C349455E71EE1B08943A561F0839D43B8BD476357992540E1B56D70FA5397509F901ED72724A5E929771C26BFDD125E7427CD57A98730FF897061CD7F0BBAE1B024ED9C1C1998A1E3E2CD771C8183464737233D17CD6A092993B77D82622D665F9B2F06C89741BE8A2E5662ED22D0D555E6B90FE5E1C902E42CD849370F2BE67F40B97B5D741B372A0F5D8C5BC021A1CEFED7442B02DF528AD4C22449B98339548D38BF87BF50AAE613FBAAF0E64B1CA740F9859D5CAF0B2AB91CEDD813E306248E545075C608668BE6FBAD0618D6A398966AF3D20F5418E61732ADD06F5EB98FE6AD42CE9682F62C8C94E85EF8C757586590E8D1ABDC6C8F8E5A9553A27A9341ED6022028B231DE8909F06EF95B222121B72E12DB2111D2CBD8E0EB9DF67E7D304F28803D4529E8FDD4BA7920B3D6AB2F0106FDF4ED702E8C4A336C901A8799525EA30486838B32DC30F736F1A485DBBEED63EC92597268FF5EF99FAF5E17B7D5B46585BAC7B43EA788C263E04B93D36E0D82BB7D1BC052E49F5BD50A4E82DB05B4E42F18536F390C49D0CEF0DFCFF3C09723A9918688DEB7B7C974A66E7F9A0EAD3113F949EC82F352CD6486C518DDC61B7EBBEAB5F01927DBA3C9B98FD749017E3DEE270136BECB97F19AB0568CD0536567A7DEF44FF348D6C08F155F0781574C34E573B6F1F940A1B2C537FA2F764283795E9B665BAEF53161673CA4CAA7E9C4B33A0D02A9036E3307F26E5B8BDBA30D7EA7CA62CD8968EF6CB0DFB082DF7A68C3B8869C57BEFCA552B3CA4B8FF8686FD313FF2D48E37CB0DF3AF8D3CA2086EEDAF3479D21C974037C602A559C471BBDA3D07F50650EFE54DF820FA8434CF14A5A8F55F52B739581B22FB078851D6DAA492C4F5BE9797AA47094205DF17C15ED216227C4DA8F007B759A30EDF46FD921E2D87A39D5D3CE01AD1B116943F5FB1B2925C5DCAF199215ADB3D924F52D69BEAB6981791EBF17CD2526A0E46D806863E1320A2CF5B3D2E266B9FDAD45AEF7D83164BEB7A37992D434A726B9C50851B809FB95C169BF33B62D496F58E752BB190296781CFF93EAA4C1C6716133612CBA0EA4A6905B59A9D01BCB93EF99E1B8EBF727D72E91FF48AAB23D1DEF618449D70514615396640E9ED913857D5196368A64D9972FCB89EF41A195932EDE4E9E6800E7D272A2EF59453D2FF8F29617DB23201C568017C4484EB027D30C4705717CDE931245827A12EB4CD0CAD629FCE59AE5120B82133F7CF132313438115B0BBED035078FB1C476764A1E6E121CF59C7F101F0E14968A1E60D076CC9488EB7D86BD70FF70154F8AD6A207BEE8C042220CC52AF2DAC294791667A4935718C4A55FA23EB18A520A2E82ED55692BF64B819117C48F13F62F8FF494B1C0403C3C99C6D67BEF7069A48A8E95E79787EB27465AAD52855788AA3296E4D931583415C2B1B7A68C96508F93A95668040E143F19F94210CA18D884C325C62D2CD9A69AA2CCF920A61B4C1A3DFD16AC5E2E0343E61E19C13FCFF2BFA428FEF017B496DCAE6428889114FCC4E3925ABF0CB66CE4476DFFC41131396A62DE1A146EEC778344600F8EEE86DA9FA8C119B3F0B1F9C2AA9F5D8908C95364EB6B5F6E3CB72869F29D567AC888C05A7BF176D5BD80C2AD3815EC41E9BA6E6FBB0BA6E2E570CA1B4F495F3040B6F6D50B1E6E24A1DB4D68A2D51BD7115BAA3A7F58A9D83CA22846282994A0393FB82FE71389ACD3EE1B42A0895668C73DC21517822AF63D640DFE8C6590B36AD8F80A803F9914141F2CA72EB0C2162E2BA36FE742125449AFABB37B21844171FBC9951817D6FA9F1BA398176ABE63230568AA866F515362066AEA4BBEF0B6C1BDB13FF295CF738DE580E2EE41D0100C848AE53BADCB66F848805E781716F95CF10ABAA45A3DFD4E7329DF37D8C74F0DA01B4FFE598B9C3DE334571881035D478ABE4AA4774F70E080AB0A33C6B8F83C70589Want to learn more?Vectra® is the leader in Security AI-driven hybrid cloud threat detection and response. The Vectra platform and services cover public cloud, SaaS applications, identity systems and network infrastructure – both on-premises and cloud-based. Organizations worldwide rely on the Vectra platform and services for resilience to ransomware, supply chain compromise, identity takeovers, and other cyberattacks impacting their organization.If you’d like to hear more, contact us and we’ll show you exactly how we do this and what you can do to protect your data. We can also put you in contact with one of our customers to hear directly from them about their experiences with our solution.Contact us

Related blogs

December 14, 2023

CyberattackWhat is a Hybrid Attack? Today’s Biggest Cyber ThreatDemystifying hybrid attacks begins with seeing that all attack vectors comprise a single, hybrid attack surface, all attacks are hybrid attacks and end with signal clarity.Read more



November 7, 2023

CyberattackTechnical analysis: Barracuda Email Security GatewayOn May 23rd, 2023, Barracuda announced a vulnerability (CVE-2023-2868) in their Email Security Gateway appliance that was being exploited in the wild as far back as October of 2022. Read more



February 15, 2023

CyberattackYou should get MAAD-AF about emulating attacks – it goes a long waySecurity teams need the right tools to test cloud security controls in ways that emulate real attacker behavior to understand the gaps and ensure they have the proper visibility to stop an attacker.Read more









PlatformPublic CloudSaaSIdentityNetworkEndpointManaged Extended Detection & Response ServicesSee our Integrations

Our AIVectra AI Detections

Use CasesSOC ModernizationEDR ExtensionIDS ReplacementPCAP ReplacementSIEM / SOAR OptimizationSignature + AI-driven DetectionCyber ResilienceCloud Identity ProtectionCloud Control Plane ProtectionCloud Posture ImprovementRisk ManagementCloud Identity ProtectionCloud Control Plane ProtectionCloud Posture ImprovementSee all Use Cases

Hybrid Attack TypesAccount TakeoverAdvanced Persistent ThreatsData BreachNation State AttacksRansomwareSupply Chain AttacksHybrid Attacks ProgressionsZero-day ExploitSpear PhishingMFA BypassCredential StuffingSunburstLive off the LandIndustriesCritical National InfrastructureEnergy & UtilitiesFinanceGovernment/FederalHealthcareHigher EducationManufacturingPharmaceutical & medicalReal EstateRetail & WholesaleTelecomVectra AI Topics

CustomersCustomer StoriesSupport HubKnowledge CenterProduct ReleasesProfessional ServicesManaged Extended Detection & Response ServicesResearch & InsightsResourcesBlogResource CenterEvents and WebinarsPartnersBecome a PartnerPartner OverviewMSSPsTechnology PartnersVARs & DistributorsPartner Portal Login

CompanyAbout UsLeadershipBoard of DirectorsInvestorsBlogCareersContact Ussupport@vectra.aiHeadquarters550 S. Winchester Blvd.Suite 200San Jose, CA, USA 95128











































Data Processing AgreementTerms of ServiceTerms of UseTrademarksTrust CenterPrivacy PolicyVectra Ethics Hotline© 2024 Vectra AI, Inc. All rights reserved.






















