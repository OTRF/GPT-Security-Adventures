# Reference for threat actor for "Magic Hound, APT 35, Cobalt Illusion, Charming Kitten"

**Title**: Iranian PupyRAT Bites Middle Eastern Organizations | Secureworks

**Source**: https://www.secureworks.com/blog/iranian-pupyrat-bites-middle-eastern-organizations

## Content
Iranian PupyRAT Bites Middle Eastern Organizations | SecureworksSkip to Main ContentSkip to Footer2023 State of the Threat: A Year In Review - Read the ReportExperiencing a Breach?Contact UsSupportBlogEnglishProductsServicesSolutionsAboutPartnersResourcesRequest DemoResearchIranian PupyRAT Bites Middle Eastern OrganizationsCustomized phishing lures distribute PupyRAT malwareCounter Threat Unit Research Team February 15, 2017SecureWorks® Counter Threat Unit™ (CTU) researchers analyzed a phishing campaign that targeted a Middle Eastern organization in early January 2017. Some of messages were sent from legitimate email addresses belonging to several Middle Eastern organizations.
Campaign details
The threat actor used shortened URLs in the body of the phishing emails that redirected to several spoofed domains (See Table 1).




Spoofed domain


Legitimate domain


Associated organization




            ntg-sa . com
            

            ntg . com . sa
            

            National Technology Group, a Saudi Arabian telecommunications company
            



            itworx . com-ho . me
            

            itworx . com
            

            ITWorx, an Egyptian information technology services firm
            



            mci . com-ho . me
            

            mci . gov . sa
            

            Saudi Ministry of Commerce
            



            moh . com-ho . me
            

            moh . gov . sa
            

            Saudi Ministry of Health
            



            mol . com-ho . me
            

            mol . gov . sa
            

            Saudi Ministry of Labor
            



Table 1. Spoofed domains hosted on 45 . 32 . 186 . 33. (Source: SecureWorks)
Recipients who clicked the URL were presented a Microsoft Office document related to the phishing theme (see Figures 1 and 2).


Figure 1. Job offer lure (MD5: 43fad2d62bc23ffdc6d301571135222c). (Source: SecureWorks)


Figure 2. Ministry of Health lure (MD5: 1b5e33e5a244d2d67d7a09c4ccf16e56). (Source: SecureWorks)
The downloaded document attempts to run a macro that then runs a PowerShell command. This command downloads two additional PowerShell scripts that install PupyRAT, an open-source remote access trojan (RAT). According to the developer, PupyRAT is a “multi-platform (Windows, Linux, OSX, Android), multi-function RAT and post-exploitation tool mainly written in Python.” CTU™ analysis confirms that PupyRAT can give the threat actor full access to the victim's system.
Conclusion
CTU analysis suggests this activity is related to Iranian threat actors closely aligned with or acting on behalf of the COBALT GYPSY threat group (formerly labeled Threat Group-2889). CTU researchers assess with high confidence that COBALT GYPSY is associated with Iranian government-directed cyber operations, and it has used tactics similar to this campaign:

targeting Saudi financial, oil, and technology organizations
using job-themed lures to infect systems
registering spoofed domains
spearphishing new victims using legitimate email addresses


This campaign highlights the need for organizations to educate users about the risks of spearphishing and shortened links. CTU researchers recommend that organizations disable macros in Microsoft Office products to prevent attacks that leverage this functionality. Organizations should also incorporate advanced malware prevention technology and endpoint threat detection tools as part of their mitigation strategies.
Threat indicators
The indicators in Table 2 are associated with the PupyRAT campaign. The IP addresses and domains may contain malicious content, so consider the risks before opening them in a browser.




Indicator


Type


Context




            ntg-sa . com
            

            Domain name
            

            Attacker-controlled spoofed website 
            



            itworx . com-ho . me
            

            Domain name
            

            Attacker-controlled spoofed website 
            



            mci . com-ho . me
            

            Domain name
            

            Attacker-controlled spoofed website 
            



            moh . com-ho . me
            

            Domain name
            

            Attacker-controlled spoofed website 
            



            mol . com-ho . me
            

            Domain name
            

            Attacker-controlled spoofed website 
            



            45 . 32 . 186 . 33
            

            IP address
            

            Hosting spoofed domains used in PupyRAT phishing campaign
            



            139 . 59 . 46 . 154
            

            IP Address
            

            Hosting PowerShell stages of PupyRAT download
            



            89 . 107 . 62 . 39
            

            IP Address
            

            PupyRAT command and control server 
            



            43fad2d62bc23ffdc6d30157113
			5222c
            

            MD5 hash
            

            Job-themed Word document lure (qhtma) delivering PupyRAT
            



            735f5d7ef0c5129f0574bec3cf3
			d6b06b052744a
            

            SHA1 hash
            

            Job-themed Word document lure (qhtma) delivering PupyRAT
            



            e5b643cb6ec30d0d0b458e3f280
			0609f260a5f15c4ac66faf4ebf384f7976df6
            

            SHA256 hash
            

            Job-themed Word document lure (qhtma) delivering PupyRAT
            



            1b5e33e5a244d2d67d7a09c4ccf
			16e56
            

            MD5 hash
            

            Ministry of Health lure (Health_insurance_registration.doc) delivering PupyRAT
            



            934c51ff1ea00af2cb3b8465f0a
			3effcf759d866
            

            SHA1 hash
            

            Ministry of Health lure (Health_insurance_registration.doc) delivering PupyRAT
            



            66d24a529308d8ab7b27ddd43a6
			c2db84107b831257efb664044ec4437f9487b
            

            SHA256 hash
            

            Ministry of Health lure (Health_insurance_registration.doc) delivering PupyRAT
            



            03ea9457bf71d51d8109e737158
			be888
            

            MD5 hash
            

            Password-themed lure (Password_Policy.xlsm) delivering PupyRAT
            



            d20168c523058c7a82f6d79ef63
			ea546c794e57b
            

            SHA1 hash
            

            Password-themed lure (Password_Policy.xlsm) delivering PupyRAT
            



            6c195ea18c05bbf091f09873ed9
			cd533ec7c8de7a831b85690e48290b579634b
            

            SHA256 hash
            

            Password-themed lure (Password_Policy.xlsm) delivering PupyRAT
            



            97cb7dc1395918c2f3018c109ab
			4ea5b
            

            MD5 hash
            

            PupyRAT (pupyx86.dll)
            



            3215021976b933ff76ce3436e82
			8286e124e2527
            

            SHA1 hash
            

            PupyRAT (pupyx86.dll)
            



            8d89f53b0a6558d6bb9cdbc9f21
			8ef699f3c87dd06bc03dd042290dedc18cb71
            

            SHA256 hash
            

            PupyRAT (pupyx86.dll)
            



Table 2. Threat indicators for the Iranian PupyRAT campaign.

Gauging confidence level
CTU researchers have adopted the grading system published by the U.S. Office of the Director of National Intelligence to indicate confidence in their assessments:

High confidence generally indicates that judgments are based on high-quality information, and/or that the nature of the issue makes it possible to render a solid judgment. A "high confidence" judgment is not a fact or a certainty, however, and such judgments still carry a risk of being wrong.
Moderate confidence generally means that the information is credibly sourced and plausible but not of sufficient quality or corroborated sufficiently to warrant a higher level of confidence.
Low confidence generally means that the information's credibility and/or plausibility is questionable, or that the information is too fragmented or poorly corroborated to make solid analytic inferences, or that [there are] significant concerns or problems with the sources.
Tags:ResearchBlogBack to all BlogsNow Trending...XDR vs. SIEM: A Cybersecurity Leader's GuideModernize Your Security Operation Center with XDRMDR Done RightReport2023 State of the Threat ReportAccess NowAdditional ResourcesBlogUnravelling the Attack Surface of AI SystemsRead NowBlogInfinios Partners with Secureworks for Stronger CybersecurityRead NowBlogFive Keys to Maximizing MDR ValueRead NowBlogUnravelling the Attack Surface of AI SystemsRead NowBlogInfinios Partners with Secureworks for Stronger CybersecurityRead NowBlogFive Keys to Maximizing MDR ValueRead NowBlogUnravelling the Attack Surface of AI SystemsRead NowTRY TAEGIS TODAY!See for yourself: Request your demo to see how Taegis can reduce risk, optimize existing security investments, and fill talent gaps.Try TaegisGet the latest updates and news from Secureworks.Subscribe NowProductsDetection & ResponseXDRMDRThreat HuntingLog ManagementMITRE ATT&CK CoverageEndpoint SecurityEDRNGAVNetwork SecurityIDPSOT SecurityOperational TechnologyVulnerability ManagementVulnerability Risk PrioritizationWhy SecureworksWhy SecureworksAt Your SideCompare SecureworksArtifical IntelligenceROI CalculatorCorporate ResponsibilityCorporate OverviewCareersInvestor RelationsServicesAccess PlanThreat Hunting AssessmentVulnerability AssessmentRansomware Readiness AssessmentBattle Test ExercisePenetration TestingAdversary ExercisesApplication Security TestingIncident ResponseAbout Emergency Incident ResponseEmergency Breach HotlineSolutionsIndustriesEducation IndustryFinancial IndustryManufacturing IndustryNeedAccelerate Security MaturityConsolidate Security ToolsMicrosoft SecurityMonitor IT and OTReduce Teams BurdenResourcesBlogCybersecurity GlossaryResource LibraryCase StudiesData SheetsIndustry ReportsIn the NewsKnowledge Center LibraryLive EventsThreat Resource LibraryThreat ProfilesWhite PapersWebinarsPodcastsVideosGet In TouchExperiencing a BreachContactSupportLogin©2024 Secureworks, Inc.Privacy PolicySupply Chain TransparencyTerms and ConditionsAccessibility StatementUnsubscribeCookie Settings