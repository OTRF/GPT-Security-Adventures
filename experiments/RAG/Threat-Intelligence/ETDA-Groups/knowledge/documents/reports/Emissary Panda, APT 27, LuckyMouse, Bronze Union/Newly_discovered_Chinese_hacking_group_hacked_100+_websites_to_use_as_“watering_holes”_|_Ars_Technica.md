# Reference for threat actor for "Emissary Panda, APT 27, LuckyMouse, Bronze Union"

**Title**: Newly discovered Chinese hacking group hacked 100+ websites to use as “watering holes” | Ars Technica

**Source**: https://arstechnica.com/information-technology/2015/08/newly-discovered-chinese-hacking-group-hacked-100-websites-to-use-as-watering-holes/

## Content



Newly discovered Chinese hacking group hacked 100+ websites to use as “watering holes” | Ars Technica

























































































Skip to main content









Biz & IT
Tech
Science
Policy
Cars
Gaming & Culture
Store
Forums


Subscribe









Close










    Navigate
  

Store
Subscribe
Videos
Features
Reviews


RSS Feeds
Mobile Site


About Ars
Staff Directory
Contact Us


Advertise with Ars
Reprints





    Filter by topic
  

Biz & IT
Tech
Science
Policy
Cars
Gaming & Culture
Store
Forums





    Settings
  


Front page layout



    Grid
    





    List
    




Site theme


light





dark









      Sign in
    









      Biz & IT    —

Newly discovered Chinese hacking group hacked 100+ websites to use as “watering holes”
Emissary Panda group penetrated the networks of industrial espionage targets.


Sean Gallagher
    -    Aug 5, 2015 7:00 pm UTC

 




Emissary Panda wants to eat all the industrial data—and has hacked hundreds of sites to target people with access to it.Chen Wu 


reader comments
23



LAS VEGAS—Today at the Black Hat information security conference, Dell SecureWorks researchers unveiled a report on a newly detected hacking group that has targeted companies around the world while stealing massive amounts of industrial data. The majority of the targets of the hacking group were in the automotive, electronic, aerospace, energy, and pharmaceutical industries. The group, believed to be based in China, has also targeted defense contractors, colleges and universities, law firms, and political organizations—including organizations related to Chinese minority ethnic groups.
Designated as Threat Group 3390 and nicknamed "Emissary Panda" by researchers, the hacking group has compromised victims' networks largely through "watering hole" attacks launched from over 100 compromised legitimate websites, sites picked because they were known to be frequented by those targeted in the attack.
At least 50 organizations in those industries in the US and the United Kingdom had data stolen by members of Emissary Panda. Sites targeted included the website of the Embassy of the Russian Federation in the US (as well as those of other embassies and non-governmental organizations); government agency websites around the world; manufacturing companies, many of whom were suppliers to defense contractors; and the Spanish defense manufacturer Amper. A cultural site for the Chinese Uyghur ethnic group was also used, apparently to target members of the Muslim minority for surveillance.
No zero-day vulnerabilities were used to breach targeted networks, instead "the group relied on old vulnerabilities such as CVE-2011-3544"—a near-year-old Java security hole—"and CVE-2010-0738 to compromise their targets," Dell SecureWorks' researchers reported. The group used a number of tools common to other Chinese hacking groups, but they had a few unique tools of their own with interfaces developed for Standard (Simplified) Chinese. One of these is the PlugX remote access tool, "a notorious piece of malware linked to a number of attacks and to another Threat Group, which researchers believe is also likely based out of China," according to Dell SecureWorks researchers. It also appears the group used China's Baidu search engine to perform reconnaissance on targets. 
Advertisement 


Visitors to sites exploited by Emissary Panda are directed by code embedded in the sites to a malicious webpage, which screens their IP address. If the address falls within ranges that the attackers are interested in, the malicious site waits for their next page view to drop an exploit on the desirable target's PC. (There has also been at least one victim targeted by a spear-phishing attack.) A variety of malware, including the PlugX tool, was shared with other known Chinese threat groups. But two tools used were unique to the group: ASPXTool, an Internet Information Services (IIS) specific "Web shell" used to gain access to servers inside a target's network; and the OwaAuth credential stealing tool and Web shell, used to attack Microsoft Exchange servers running the Web Outlook interface.
Once inside networks, the group generally targeted Windows network domain controllers and Exchange e-mail servers, targeting user credentials to allow them to move to other systems throughout the targeted network. They used an exploit of Internet Information Server to inject keylogger and backdoor malware onto the Exchange server. Getting into domain controller and Exchange servers gave the attackers an opportunity to steal administrator and other high-level credentials, and they could then quickly identify other points of interest and move to compromise other systems on the network—often within just two hours of the initial compromise.














reader comments
23


 



Sean Gallagher
        Sean was previously Ars Technica's IT and National Security Editor, and is now a Principal Threat Researcher at SophosLabs.  A former Navy officer, systems administrator, and network systems integrator with 20 years of IT journalism experience, he lives and works in Baltimore, Maryland.      







Advertisement 























Channel Ars Technica




← Previous story Next story →




Related Stories









Today on Ars












Store
Subscribe
About Us
RSS Feeds
View Mobile Site




Contact Us
Staff
Advertise with us
Reprints





Newsletter Signup

Join the Ars Orbital Transmission mailing list to get weekly updates delivered to your inbox. Sign me up →



















































































































  CNMN Collection
  WIRED Media Group
  © 2024 Condé Nast. All rights reserved. Use of and/or registration on any portion of this site constitutes acceptance of our User Agreement (updated 1/1/20) and Privacy Policy and Cookie Statement (updated 1/1/20) and Ars Technica Addendum (effective 8/21/2018). Ars may earn compensation on sales from links on this site. Read our affiliate link policy.
Your California Privacy Rights |  Do Not Sell My Personal Information
  The material on this site may not be reproduced, distributed, transmitted, cached or otherwise used, except with the prior written permission of Condé Nast.
Ad Choices

























