# Reference for threat actor for "Tropic Trooper, Pirate Panda, APT 23, KeyBoy"

**Title**: Tropic Trooper Goes Mobile With Titan Surveillanceware | Lookout Threat Intelligence

**Source**: https://blog.lookout.com/titan-mobile-threat

## Content
Tropic Trooper Goes Mobile With Titan Surveillanceware | Lookout Threat Intelligence





























Lookout ResearchThreat GuidancesThreat DataResourcesAbout UsContact UsAndroidLookoutThreat SummarySpywareNovember 16, 2017Tropic Trooper Goes Mobile With Titan SurveillancewareLookout researchers have recently observed cybercriminals evolving the way they operate to reflect the multitude of platforms people now use to access information: you may read and triage email on a smartphone, switch to a laptop to crank out some work, then flip over to a tablet to catch up on social media or watch a video. To the attackers, it's a numbers game. The more devices they can reach, the more likely they are to compromise a target. Given the rise of mobile productivity, this means that we are seeing a growing number of attackers add mobile capabilities to their toolkits.The latest threat to follow this trend is Titan, a family of sophisticated Android surveillanceware apps surfaced by Lookout's automated analysis that, based on command and control infrastructure, is linked to the same actors behind Operation Tropic Trooper. Tropic Trooper is a long running campaign, first reported in 2016, that executed targeted desktop attacks against enterprises and military units in Taiwan and the Philippines. All Lookout customers are protected from Titan.CapabilitiesTitan usually comes with busybox and various native libraries that provide a range of functionality, from automated gathering of a user's data to being able to execute attacker specified instructions as superuser. Over time, Titan has evolved considerably with a distinct trend of malicious code shifting first from Java to native libraries, then moving into second stage components. Analysis of Titan variants found that they contained the following capabilities:Retrieve call historyRetrieve text messagesRetrieve contact informationRetrieve a list of Installed packagesTrack device locationTake a photo with the device camera when a user is first present or when instructed by an attackerRecord all calls or only calls to attacker specified numbersBlock text messages to attacker specified numbersTake a screenshotSend a text messageExecute attacker specified commands as rootUpload specific filesDownload attacker specified filesTitan hasn't been seen to trojanize legitimate applications and doesn't contain any legitimate functionality. The authors of Titan have instead opted to simply use the icon of a legitimate app. Application icons used included:Zalo - a vietnamese Messaging Application,91 - an unofficial Chinese App Store that was bought by Baidu in 2013 for 1.9 billion,YY - a popular Chinese social network,Renren - formerly Xiaonei Network, this is a social network primarily used by Chinese college students,58 - an online Chinese marketplace,WeChat - a popular Chinese messaging app, andFloatingMenu - an application for handling shortcuts and gestures.InfrastructureSeveral domains and IP addresses associated to this family are no longer live however further research is being conducted into 108.61.xxx.xxx which, at the time of writing, is live, running PHP, and exposing information that may provide additional leads. Some Titan variants have been seen to iterate through a list of possible command and control servers when beaconing out. Domains and IPs that Titan has, or is currently, using are listed below.Domain / IPPortmysupport.dnset.com3350 or 3351mysupport.zyns.com3350 or 3351122.10.94.643350 or 3351202.153.193.739006androidshome.com9006www.mark40.25u.com9006113.10.221.899006108.61.xxx.xxx80As a family that is actively being improved, and given its links to targeted attacks against enterprises and defense institutions, Lookout is continuing to track Titan variants, associated server infrastructure, and geographical regions where they're being deployed.SHA-1se9d4a39e763471c406490e19c22b98d9fa5a91513373a1a3151c3ae67903b7503828055c339e988fdbc73a8cc28fa0bab441ed75e51da206e49cf9e21a50b9853e0dc9cc9d7e90e5076dda632589fe9f80b303c0e09c36084b1e91367465ad621c29c0adbfc6390f016715f9adb0876840a76079df4ae3dd843df2fd5d9c86bd08c90b9e405481ec75d1eb906f68376cda0578a6df6ec3059ffda85cda7a0bec75be9cdcbc3cdcf1bede3c80214995758d5b9c61ef2dd1b8ce479276c72e17da217e74f1ce9a2ee12af65847aad4a976ed72a67c489daf3a100c0d655df3b5f59709a3e02386e9297ae2f1b1ef1a6ac32aa2f48ea856803b19925a7d0abb3a443f31d0953ec97bd2e8105fcb530b249e86a4aa7e35e52e44a2e60c28259e0982a1eb7768fa2433f84e64a817Want to learn more about threats like Titan and our Threat Advisory services? Contact Lookout today.AuthorsMichael FlossmanHead of Threat IntelligenceMichael is Head of Threat Intelligence at Lookout where he works on reverse engineering sophisticated mobile threats while tracking their evolution, the campaigns they are used in, and the actors behind them. He has hands-on experience in vulnerability research, incident response, security assessments, pen-testing, reverse engineering and the prototyping of automated analysis solutions. When not analysing malware there’s a good chance he’s off snowboarding, diving, or looking for flaws in popular mobile apps.Platform(s) AffectedAndroidDiscovered ByLookoutEntry TypeThreat SummaryThreat TypeSpywarePlatform(s) AffectedAndroidLookoutThreat SummarySpywareRelated ContentBadBazaar: iOS and Android Surveillanceware by China’s APT15 Used to Target Tibetans and UyghursResearchers from Lookout have uncovered two new surveillance campaigns, BadBazaar and MOONSHINE, targeting Uyghurs in the People’s Republic of China and abroad.Read More

MOONSHINE: Evolving Android Surveillanceware by Chinese APT POISON CARP To Target Tibetans and UyghursMOONSHINE is a family of Android surveillanceware that is attributed to the Chinese-backed hacking group POISON CARP, also known as Evil Eye and Earth Empusa.Read More

 CVE-2023-7024Google recently disclosed a critical vulnerability in Chromium that adversely affects both Google Chrome and Microsoft Edge browsers across desktop and mobile devices.Read More

Stop Cyberattacks Before They Start With Industry-Leading Threat Intelligence.



Schedule DemoLookout Cloud SecurityCloud SecurityLookout Secure Cloud AccessLookout Secure Internet AccessLookout Secure Private AccessLookout Endpoint SecurityEndpoint SecurityLookout Mobile Endpoint SecurityLookout Threat IntelligenceSolutionsSecure Hybrid WorkMeet Compliance & Privacy RegulationsPromote Collaboration SafelyDetect & Mitigate ThreatsAdopt the Cloud FasterAccelerate Mergers & AcquisitionsIndustriesHealthcareEducationFederal GovernmentState & Local GovernmentFinancial ServicesManufacturing


















(844) 371-5665LegalPrivacy PolicyCookie PolicyTransparency ReportDo not sell or share my personal informationCompliance InfoCompliance Info (Gov)Sitemap© 2024 Lookout, Inc. LOOKOUT®, the Lookout Shield Design®, LOOKOUT with Shield Design® and the Lookout multi-color/multi-shaded Wingspan Design® are registered trademarks of Lookout, Inc. in the United States and other countries. DAY OF SHECURITY®, LOOKOUT MOBILE SECURITY®, and POWERED BY LOOKOUT® are registered trademarks of Lookout, Inc. in the United States. Lookout, Inc. maintains common law trademark rights in EVERYTHING IS OK, PROTECTED BY LOOKOUT, CIPHERCLOUD, and the 4 Bar Shield Design.HeaderHeaderHeaderHeaderCellCellCellCellCellCellCellCellCellCellCellCellCellCellCellCell













