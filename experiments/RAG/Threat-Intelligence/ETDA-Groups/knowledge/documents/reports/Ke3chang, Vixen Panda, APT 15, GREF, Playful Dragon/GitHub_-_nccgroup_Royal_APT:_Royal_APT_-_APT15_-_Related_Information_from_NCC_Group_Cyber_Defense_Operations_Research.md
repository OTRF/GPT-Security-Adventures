# Reference for threat actor for "Ke3chang, Vixen Panda, APT 15, GREF, Playful Dragon"

**Title**: GitHub - nccgroup/Royal_APT: Royal APT - APT15 - Related Information from NCC Group Cyber Defense Operations Research

**Source**: https://github.com/nccgroup/Royal_APT

## Content




























































GitHub - nccgroup/Royal_APT: Royal APT - APT15 - Related Information from NCC Group Cyber Defense Operations Research

















































Skip to content













Toggle navigation










          Sign in
        


 













        Product
        












Actions
        Automate any workflow
      







Packages
        Host and manage packages
      







Security
        Find and fix vulnerabilities
      







Codespaces
        Instant dev environments
      







Copilot
        Write better code with AI
      







Code review
        Manage code changes
      







Issues
        Plan and track work
      







Discussions
        Collaborate outside of code
      




Explore



      All features

    



      Documentation

    





      GitHub Skills

    





      Blog

    









        Solutions
        





For



      Enterprise

    



      Teams

    



      Startups

    



      Education

    






By Solution



      CI/CD & Automation

    



      DevOps

    





      DevSecOps

    






Resources



      Learning Pathways

    





      White papers, Ebooks, Webinars

    





      Customer Stories

    



      Partners

    









        Open Source
        









GitHub Sponsors
        Fund open source developers
      








The ReadME Project
        GitHub community articles
      




Repositories



      Topics

    



      Trending

    



      Collections

    






Pricing












Search or jump to...







Search code, repositories, users, issues, pull requests...

 




        Search
      













Clear
 



























 




              Search syntax tips
 














        Provide feedback
      









 
We read every piece of feedback, and take your input very seriously.


Include my email address so I can be contacted


     Cancel

    Submit feedback










        Saved searches
      
Use saved searches to filter your results more quickly









 





Name






Query



            To see all available qualifiers, see our documentation.
          
 





     Cancel

    Create saved search








              Sign in
            


              Sign up
            









You signed in with another tab or window. Reload to refresh your session.
You signed out in another tab or window. Reload to refresh your session.
You switched accounts on another tab or window. Reload to refresh your session.
 


Dismiss alert



















        nccgroup
 
/

Royal_APT

Public





 

Notifications



 

Fork
    11




 


          Star
 53
  












        Royal APT - APT15 - Related Information from NCC Group Cyber Defense Operations Research
      





53
          stars
 



11
          forks
 



Branches
 



Tags
 



Activity
 



 


          Star

  





 

Notifications














Code







Issues
0






Pull requests
0






Actions







Projects
0






Security







Insights



 

 


Additional navigation options


 









          Code










          Issues










          Pull requests










          Actions










          Projects










          Security










          Insights





 





nccgroup/Royal_APT







This commit does not belong to any branch on this repository, and may belong to a fork outside of the repository.



 



















    masterBranchesTagsGo to fileCodeFolders and filesNameNameLast commit messageLast commit dateLatest commit History13 Commitsimagesimages  scriptsscripts  signaturessignatures  README.mdREADME.md  View all filesRepository files navigationREADMERoyal_APT
Royal APT - APT15 - Related Information from NCC Group Cyber Defense Operations Research
Sharepoint tool
Among the tools developed by the group for the victim, APT15 created a .net tool to enumerate the victim's sharepoint database. Below is an screen-shot from the decompiled binary.

Decoding scripts
Decoder scripts for BS2005 and RoyalCLI samples found by NCC Group can be found in the scripts directory.
BS2005
bs_decoder.py will extract and decrypt commands included in html files sent to the sample 6ea9cc475d41ca07fa206eb84b10cf2bbd2392366890de5ae67241afa2f4269f; namely Alive.htm and Contents.htm. It will also decode beacons sent to the C2.
Usage:
bs2005_decoder.py html <htmlPath>/<htmlsDir>
bs2005_decoder.py beacon <beaconString>
RoyalCLI
rcli_decoder.py will decode RoyalCli config, RoyalCli html commands and the uris.
Usage:
royalcli_decoder.py html <htmlPath>/<htmlsDir>
royalcli_decoder.py cfg <configPath>
royalcli_decoder.py uri <beaconString>
`
Yara signatures
Yara signatures for the RoyalCLI, RoyalDNS and BS2005 samples found by NCC Group can be found in apt15.yara in the signatures folder.
Suricata Signatures
Suricata signatures for RoyalCLI, RoyalDNS and BS2005 samples found by NCC Group can be found in ids_signatures_apt15_royal.txt in the signatures folder.
   








About

        Royal APT - APT15 - Related Information from NCC Group Cyber Defense Operations Research
      
Resources





        Readme
 







Activity
 





Custom properties
 
Stars





53
      stars
 
Watchers





15
      watching
 
Forks





11
      forks
 


          Report repository
 







    Releases

No releases published






    Packages
      0


        No packages published 











Languages










Python
100.0%















Footer








        © 2024 GitHub, Inc.
      


Footer navigation


Terms


Privacy


Security


Status


Docs


Contact




      Manage cookies
    





      Do not share my personal information
    
















    You can’t perform that action at this time.
  












