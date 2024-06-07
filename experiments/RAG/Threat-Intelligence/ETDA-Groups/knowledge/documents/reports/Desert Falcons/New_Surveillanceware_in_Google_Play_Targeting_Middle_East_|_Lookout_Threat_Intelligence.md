# Reference for threat actor for "Desert Falcons"

**Title**: New Surveillanceware in Google Play Targeting Middle East | Lookout Threat Intelligence

**Source**: https://blog.lookout.com/desert-scorpion-google-play

## Content
New Surveillanceware in Google Play Targeting Middle East | Lookout Threat Intelligence





























Lookout ResearchThreat GuidancesThreat DataResourcesAbout UsContact UsLookoutAndroidThreat SummarySpywareMalwareApril 16, 2018New Surveillanceware in Google Play Targeting Middle EastLookout researchers have identified a new, highly targeted surveillanceware family known as Desert Scorpion in the Google Play Store. Lookout notified Google of the finding and Google removed the app immediately while also taking action on it in Google Play Protect. The app ties together two malware families - Desert Scorpion and another targeted surveillanceware family named FrozenCell - that we believe are being developed by a single, evolving surveillanceware actor called APT-C-23 targeting individuals in the Middle East.We've seen this actor rely heavily on phishing campaigns to trick victims into downloading their malicious apps, specifically on Facebook. Even sophisticated actors are using lower cost, less technologically impressive means like phishing to spread their malware because it's cheap and very effective, especially on mobile devices where there are more ways to interact with a victim (messaging apps, social media apps, etc.), and less screen real estate for victims to identify potential indicators of a threat.Lookout customers are protected against this threat and additionally we have included a list of IOCs at the end of this report.‍‍The Dardesh app associated with Desert Scorpion.‍The potential actor and who they targetOur current analysis strongly suggests Desert Scorpion is being deployed in targeted attacks against Middle Eastern individuals of interest specifically those in Palestine and has also been highlighted by other researchers. We have been able to tie the malware to a long-running Facebook profile that we observed promoting the first stage of this family, a malicious chat application called Dardesh via links to Google Play. The Lookout Threat Intelligence team identified that this same Facebook profile has also posted Google Drive links to Android malware belonging to the FrozenCell family attributed to APT-C-27. These factors, in combination with the fact that the command and control infrastructure used by Frozen Cell and Desert Scorpion resides in similar IP blocks, supports the theory that the same actor is responsible for operating, if not developing, both families.‍‍‍What it doesThe surveillance functionality of Desert Scorpion resides in a second stage payload that can only be downloaded if the victim has downloaded, installed, and interacted with the first-stage chat application. The chat application acts as a dropper for this second-stage payload app. At the time of writing Lookout has observed two updates to the Dardesh application, the first on February 26 and the second on March 28. The malicious capabilities observed in the second stage include the following:Upload attacker-specified files to C2 serversGet list of installed applicationsGet device metadataInspect itself to get a list of launchable activitiesRetrieves PDF, txt, doc, xls, xlsx, ppt, pptx files found on external storageSend SMSRetrieve text messagesTrack device locationHandle limited attacker commands via out of band text messagesRecord surrounding audioRecord callsRecord videoRetrieve account information such as email addressesRetrieve contactsRemoves copies of itself if any additional APKs are downloaded to external storage.Call an attacker-specified numberUninstall appsCheck if a device is rootedHide its iconRetrieve list of files on external storageIf running on a Huawei device it will attempt to add itself to the protected list of apps able to run with the screen offEncrypts some exfiltrated dataDesert Scorpion's second stage masquerades as a generic "settings" application. Curiously, several of these have included the world "Fateh" in their package name, which may be referring to the Fatah political party. Such references would be in line with FrozenCell's phishing tactics in which they used file names to lure people associated with the political party to open malicious documents. Desert Scorpion's second stage is capable of installing another non-malicious application (included in the second stage) which is highly specific to the Fatah political party and supports the targeting theory.‍‍‍The Lookout Threat Intelligence team is increasingly seeing the same tradecraft, tactics, and procedures that APT-C-23 favors being used by other actors. The approach of separating malicious functionality out into separate stages that are later downloaded during execution and not present in the initial app published to the Google Play Store, combined with social engineering delivered via social media platforms like Facebook, requires minimal investment in comparison to premium tooling like Pegasus or FinFisher. As we've seen with actors like Dark Caracal, this low cost, low sophistication approach that relies heavily upon social engineering has still been shown to be highly successful for those operating such campaigns. Given previous operational security errors from this actor in the past which resulted in exfiltrated content being publicly accessible Lookout Threat Intelligence is continuing to map out infrastructure and closely monitor their continued evolution.AuthorsAndrew BlaichHead of Device IntelligenceAndrew Blaich is Head of Device Intelligence at Lookout where he is focused on mobile threat hunting and vulnerability research. Prior to Lookout, Andrew was the Lead Security Analyst at Bluebox Security. He holds a Ph.D. in computer science, and engineering from the University of Notre Dame in enterprise security and wireless networking. In the past Andrew has worked at both Samsung and Qualcomm Research. Andrew is a regular presenter at security conferences including BlackHat, RSA, Kaspersky SAS, SecTor, SANS DFIR, Interop, and ACSC. In his free time he loves to run and hack on IoT.Michael FlossmanHead of Threat IntelligenceMichael is Head of Threat Intelligence at Lookout where he works on reverse engineering sophisticated mobile threats while tracking their evolution, the campaigns they are used in, and the actors behind them. He has hands-on experience in vulnerability research, incident response, security assessments, pen-testing, reverse engineering and the prototyping of automated analysis solutions. When not analysing malware there’s a good chance he’s off snowboarding, diving, or looking for flaws in popular mobile apps.Discovered ByLookoutPlatform(s) AffectedAndroidEntry TypeThreat SummaryThreat TypeSpywareThreat TypeMalwarePlatform(s) AffectedLookoutAndroidThreat SummarySpywareMalwareRelated ContentBadBazaar: iOS and Android Surveillanceware by China’s APT15 Used to Target Tibetans and UyghursResearchers from Lookout have uncovered two new surveillance campaigns, BadBazaar and MOONSHINE, targeting Uyghurs in the People’s Republic of China and abroad.Read More

MOONSHINE: Evolving Android Surveillanceware by Chinese APT POISON CARP To Target Tibetans and UyghursMOONSHINE is a family of Android surveillanceware that is attributed to the Chinese-backed hacking group POISON CARP, also known as Evil Eye and Earth Empusa.Read More

 CVE-2023-7024Google recently disclosed a critical vulnerability in Chromium that adversely affects both Google Chrome and Microsoft Edge browsers across desktop and mobile devices.Read More

Stop Cyberattacks Before They Start With Industry-Leading Threat Intelligence.



Schedule DemoLookout Cloud SecurityCloud SecurityLookout Secure Cloud AccessLookout Secure Internet AccessLookout Secure Private AccessLookout Endpoint SecurityEndpoint SecurityLookout Mobile Endpoint SecurityLookout Threat IntelligenceSolutionsSecure Hybrid WorkMeet Compliance & Privacy RegulationsPromote Collaboration SafelyDetect & Mitigate ThreatsAdopt the Cloud FasterAccelerate Mergers & AcquisitionsIndustriesHealthcareEducationFederal GovernmentState & Local GovernmentFinancial ServicesManufacturing


















(844) 371-5665LegalPrivacy PolicyCookie PolicyTransparency ReportDo not sell or share my personal informationCompliance InfoCompliance Info (Gov)Sitemap© 2024 Lookout, Inc. LOOKOUT®, the Lookout Shield Design®, LOOKOUT with Shield Design® and the Lookout multi-color/multi-shaded Wingspan Design® are registered trademarks of Lookout, Inc. in the United States and other countries. DAY OF SHECURITY®, LOOKOUT MOBILE SECURITY®, and POWERED BY LOOKOUT® are registered trademarks of Lookout, Inc. in the United States. Lookout, Inc. maintains common law trademark rights in EVERYTHING IS OK, PROTECTED BY LOOKOUT, CIPHERCLOUD, and the 4 Bar Shield Design.HeaderHeaderHeaderHeaderCellCellCellCellCellCellCellCellCellCellCellCellCellCellCellCell













