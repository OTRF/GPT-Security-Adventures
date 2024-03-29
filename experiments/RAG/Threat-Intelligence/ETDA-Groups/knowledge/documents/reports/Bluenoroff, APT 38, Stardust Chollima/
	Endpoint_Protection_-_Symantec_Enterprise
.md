# Reference for threat actor for "Bluenoroff, APT 38, Stardust Chollima"

**Title**: 
	Endpoint Protection - Symantec Enterprise


**Source**: https://www.symantec.com/connect/blogs/swift-attackers-malware-linked-more-financial-attacks

## Content




	Endpoint Protection - Symantec Enterprise



















  
													









  


Products
Applications
Support
Company
How To Buy





  












Skip to main content (Press Enter).










Sign in






Skip auxiliary navigation (Press Enter).




Register













Skip main navigation (Press Enter).




Toggle navigation























Search Options

















HomeMy CommunitiesCommunities All CommunitiesEnterprise SoftwareMainframe SoftwareSymantec EnterpriseBlogs All BlogsEnterprise SoftwareMainframe SoftwareSymantec EnterpriseEvents All EventsEnterprise SoftwareMainframe SoftwareSymantec EnterpriseWater CoolerGroups Enterprise SoftwareMainframe SoftwareSymantec EnterpriseMembers



















							Endpoint Protection
						























 View Only

		


            Community Home
            
        

            Threads
            
        

            Library
            
        

            Events
            
        

            Members
            
        

























 Back to Library





            SWIFT attackers’ malware linked to more financial attacks 
            
        









1
Recommend



















                May 26, 2016 01:10 PM
            














A L Johnson









Symantec has found evidence that a bank in the Philippines has also been attacked by the group that stole US$81 million from the Bangladesh central bank and attempted to steal over $1 million from the Tien Phong Bank in Vietnam.
Malware used by the group was also deployed in targeted attacks against a bank in the Philippines. In addition to this, some of the tools used share code similarities with malware used in historic attacks linked to a threat group known as Lazarus. The attacks can be traced back as far as October 2015, two months prior to the discovery of the failed attack in Vietnam, which was hitherto the earliest known incident.
The attack against the Bangladesh central bank triggered an alert by payments network SWIFT, after it was found the attackers had used malware to cover up evidence of fraudulent transfers. SWIFT issued a further warning, saying that it had found evidence of malware being used against another bank in a similar fashion. Vietnam’s Tien Phong Bank subsequently stated that it intercepted a fraudulent transfer of over $1 million in the fourth quarter of last year. SWIFT concluded that the second attack indicates that a “wider and highly adaptive campaign” is underway targeting banks.
A third bank, Banco del Austro in Ecuador, was also reported to have lost $12 million to attackers using fraudulent SWIFT transactions. However, no details are currently known about the tools used in this incident or if there are any links to the attacks in Asia.
Discovery of additional tools used by attackers
	Symantec has identified three pieces of malware which were being used in limited targeted attacks against the financial industry in South-East Asia: Backdoor.Fimlis, Backdoor.Fimlis.B, and Backdoor.Contopee. At first, it was unclear what the motivation behind these attacks were, however code sharing between Trojan.Banswift (used in the Bangladesh attack used to manipulate SWIFT transactions) and early variants of Backdoor.Contopee provided a connection.
While analyzing samples of Trojan.Banswift, a distinct file wiping code was found. Some of the distinctive properties of the wiping code include:

Function takes two parameters: path of file to overwrite and number of iterations (max six)
It will initially overwrite the last byte of the target file with 0x5F
Six “control” bytes are supplied which dictate what bytes are used during the overwrite process

 

Figure 1. Unique wiping code found in Trojan.Banswift and additional Lazarus tools
Already this code looked fairly unique. What was even more interesting was that when we searched for additional malware containing the exact combination of “control” bytes, an early variant of Backdoor.Contopee and the “msoutc.exe” sample already discussed in the recent BAE blog analyzing the Bangladesh attack were also found.
Symantec believes distinctive code shared between families and the fact that Backdoor.Contopee was being used in limited targeted attacks against financial institutions in the region, means these tools can be attributed to the same group.
Historical attacks
	Backdoor.Contopee has been previously used by attackers associated with a broad threat group known as Lazarus. Lazarus has been linked to a string of aggressive attacks since 2009, largely focused on targets in the US and South Korea. The group was linked to Backdoor.Destover, a highly destructive Trojan that was the subject of an FBI warning after it was used in an attack against Sony Pictures Entertainment. The FBI concluded that the North Korean government was responsible for this attack.
The group was the target of a cross-industry initiative known as Operation Blockbuster earlier this year, which involved major security vendors sharing intelligence and resources in order to assist commercial and government organizations in protecting themselves against Lazarus. As part of the initiative, vendors are circulating malware signatures and other useful intelligence related to these attackers.
Ongoing danger
	The discovery of more attacks provides further evidence that the group involved is conducting a wide campaign against financial targets in the region. While awareness of the threat posed by the group has now been raised, its initial success may prompt other attack groups to launch similar attacks. Banks and other financial institutions should remain vigilant.
Protection
	Symantec and Norton products protect against these threats with the following detections:
Antivirus

Trojan.Banswift
Trojan.Banswift!gen1
Backdoor.Contopee
Backdoor.Fimlis
Backdoor.Fimlis.B

























    Statistics
    




                    0
                    Favorited
                

                    2
                    Views
                







                            0
                            Files
                        

                            0
                            Shares
                        

                            0
                            Downloads
                        










Tags and Keywords











                Related Entries and Links
                
            




                                    No Related Resource entered.
                                

























Products
Applications
Support
Company
How To Buy


Copyright © 2005-2024 Broadcom. All Rights Reserved. The term "Broadcom" refers to Broadcom Inc. and/or its subsidiaries. Hosted by Higher Logic, LLC on the behalf of Broadcom - Privacy Policy | Cookie Policy | Supply Chain Transparency


Terms of Use





  
  
  
  















							Copyright 2019. All rights reserved.
						









Powered by Higher Logic
















