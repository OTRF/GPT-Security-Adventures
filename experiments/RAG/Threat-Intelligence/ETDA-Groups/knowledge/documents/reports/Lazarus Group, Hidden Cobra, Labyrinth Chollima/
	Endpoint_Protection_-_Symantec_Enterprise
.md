# Reference for threat actor for "Lazarus Group, Hidden Cobra, Labyrinth Chollima"

**Title**: 
	Endpoint Protection - Symantec Enterprise


**Source**: https://www.symantec.com/connect/blogs/four-years-darkseoul-cyberattacks-against-south-korea-continue-anniversary-korean-war

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





            Four Years of DarkSeoul Cyberattacks Against South Korea Continue on Anniversary of Korean War 
            
        









1
Recommend



















                Jun 26, 2013 06:33 PM
            














A L Johnson








Yesterday, June 25, the Korean peninsula observed a series of cyberattacks coinciding with the 63rd anniversary of the start of the Korean War. While multiple attacks were conducted by multiple perpetrators, one of the distributed denial-of-service (DDoS) attacks observed yesterday against South Korean government websites can be directly linked to the DarkSeoul gang and Trojan.Castov.
We can now attribute multiple previous high-profile attacks to the DarkSeoul gang over the last 4 years against South Korea, in addition to yesterday’s attack. These attacks include the devastating Jokra attacks in March 2013 that wiped numerous computer hard drives at South Korean banks and television broadcasters, as well as the attacks on South Korean financial companies in May 2013.
Conducting DDoS attacks and hard disk wiping on key historical dates is not new for the DarkSeoul gang. They previously conducted DDoS and wiping attacks on the United States Independence Day as well.
	 


Figure 1. Four years of DarkSeoul activity
	 
The DarkSeoul gang’s attacks tend to follow similar methods of operation. Trademarks of their attacks include:

Multi-staged, coordinated attacks against high-profile targets in South Korea
Destructive payloads, such as hard disk wiping and DDoS attacks configured to trigger on historically significant dates
Overwriting disk sectors with politically-themed strings
Use of legitimate third-party patching mechanisms in order to spread across corporate networks
Specific encryption and obfuscation methods
Use of specific third-party webmailer servers to store files
Use of similar command-and-control structures

The attacks conducted by the DarkSeoul gang have required intelligence and coordination, and in some cases have demonstrated technical sophistication. While nation-state attribution is difficult, South Korean media reports have pointed to an investigation which concluded the attackers were working on behalf of North Korea. Symantec expects the DarkSeoul attacks to continue and, regardless of whether the gang is working on behalf of North Korea or not, the attacks are both politically motivated and have the necessary financial support to continue acts of cybersabotage on organizations in South Korea. Cybersabotage attacks on a national scale have been rare—Stuxnet and Shamoon (W32.Disttrack) are the other two main examples. However, the DarkSeoul gang is almost unique in its ability to carry out such high-profile and damaging attacks over several years.
	 

Figure 2. Castov DDoS attack
 
The Castov DDoS attack occurs in the following manner:

Compromised website leads to the download of SimDisk.exe (Trojan.Castov), a Trojanized version of a legitimate application.
SimDisk.exe drops two files onto the compromised system: SimDisk.exe (Clean), the legitimate non-Trojanized version, and SimDiskup.exe (Downloader.Castov).
Downloader.Castov connects to a second compromised server to download the C.jpg file (Downloader.Castov), an executable file which appears to be an image.
Threat uses the Tor network to download Sermgr.exe (Trojan.Castov).
Castov drops the Ole[VARIABLE].dll file (Trojan.Castov) in the Windows system folder.
Castov downloads the CT.jpg file from a Web server hosting a ICEWARP webmail, that has been compromised as a result of publicly known vulnerabilities in ICEWARP. The CT.jpg file contains a timestamp used by Castov to synchronize attacks.
Once this time is reached, Castov drops Wuauieop.exe (Trojan.Castdos).
Castdos begins to overload the Gcc.go.kr DNS server with DNS requests, effectively performing a DDoS attack affecting multiple websites.

























    Statistics
    




                    0
                    Favorited
                

                    1
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
















