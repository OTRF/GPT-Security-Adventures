# Reference for threat actor for "OilRig, APT 34, Helix Kitten, Chrysene"

**Title**: 
	Endpoint Protection - Symantec Enterprise


**Source**: https://www.symantec.com/connect/blogs/shamoon-attacks

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





            The Shamoon Attacks 
            
        









1
Recommend



















                Aug 16, 2012 11:37 AM
            














A L Johnson








W32.Disttrack is a new threat that is being used in specific targeted attacks against at least one organization in the energy sector.  It is a destructive malware that corrupts files on a compromised computer and overwrites the MBR (Master Boot Record) in an effort to render a computer unusable.
W32.Disttrack consists of several components:

Dropper—the main component and source of the original infection. It drops a number of other modules.
Wiper—this module is responsible for the destructive functionality of the threat.
Reporter—this module is responsible for reporting infection information back to the attacker.

		 

Dropper Component
The Dropper component performs the following actions:

Copies itself to %System%\trksvr.exe
Drops the following files embedded into resources:
		
A 64-bit version of the dropper component: %System%\trksrv.exe (contained in the “X509” resource)
Reporter component: %System%\netinit.exe (contained in the "PKCS7" resource)
Wiper component: %System%\[NAME SELECTED FROM LIST].exe (contained in the "PKCS12" resource)
Note: The name of the component is selected from the following list:
				
caclsrv
certutl
clean
ctrl
dfrag
dnslookup
dvdquery
event
extract
findfile
fsutl
gpget
iissrv
ipsecure
msinit
ntx
ntdsutl
ntfrsutil
ntnw
power
rdsadmin
regsys
routeman
rrasrv
sacses
sfmsc
sigver
smbinit
wcscript




Copies itself to the following network shares:
		
ADMIN$
C$\\WINDOWS
D$\\WINDOWS
E$\\WINDOWS


Creates a task to execute itself
Creates the following service to start itself whenever Windows starts:
		
Service name: TrkSvr
Display name: Distributed Link Tracking Server
Image path: %System%\trksvr.exe



 
Wiper Component
The Wiper component includes the following functionality:

Deletes an existing driver from the following location and overwrites it with another legitimate driver:
		
%System%\drivers\drdisk.sys
The device driver is a clean disk driver that enables user-mode applications to read and write to disk sectors. The driver is used to overwrite the computer’s MBR but may be used for legitimate purposes.
The file is digitally signed


Executes the following commands that collect file names, which will be overwritten and writes them to f1.inf and f2.inf:


 

Files from the f1.inf and f2.inf will be overwritten with the JPEG image shown below. Overwritten files are thus rendered useless.


Figure 1. Image used to overwrite files

Finally, the component will overwrite the MBR so that the compromised computer can no longer start

The following string that points to the location of debug symbols was left in the Wiper component of this threat and gives an idea of where the component was located on the developer’s computer:
	C:\Shamoon\ArabianGulf\wiper\release\wiper.pdb
 
Reporter Component
The Reporter component is responsible for sending infection information back to the attacker. Information is sent as a HTTP GET request and is structured as follows:
	http://[DOMAIN]/ajax_modal/modal/data.asp?mydata=[MYDATA]&uid=[UID]&state=[STATE]
The following data is sent to the attacker:

[DOMAIN]—a domain name
[MYDATA]—a number that specifies how many files were overwritten
[UID]—the IP address of the compromised computer
[STATE]—a random number

Threats with such destructive payloads are unusual and are not typical of targeted attacks. Symantec Security Response is continuing to analyze this threat and will post more information as it becomes available. Symantec customers are protected from this threat, which our security products detect as W32.Disttrack.
























    Statistics
    




                    0
                    Favorited
                

                    0
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
















