
Report 1

FIN5 is a financially motivated threat group that has been active since at least 2008. They target personally identifiable information and payment card information, focusing on the restaurant, gaming, and hotel industries. The group, likely Russian-speaking, does not use zero-days or spear-phishing techniques. Instead, they employ legitimate user credentials to access their targets' networks. One of their notable tools is the RawPOS memory scraper malware, which targets point-of-sale systems. FIN5 has been observed using tools such as FLIPSIDE, pwdump, SDelete, and Windows Credentials Editor. Their unique approach of using real credentials obtained from third parties associated with the victims' POS systems sets them apart. The threat actor's operations have been ongoing for years, with reported counter operations against them. (Report last modified: 2020-04-22)





Report 2

Summary:
- Threat actor identified as FIN5, a cybercrime gang known for using legitimate user credentials to access target networks.
- Operating since at least 2008, FIN5 targets payment card data in the lodging industry and has been associated with breaches in companies like Goodwill.
- The group uses real credentials from victim organizations' VPN, Remote Desktop Protocol, Citrix, or VNC, obtained through third parties.
- FIN5 employs tools like GET2 Penetrator for brute force scanning and EssentialNet for network reconnaissance.
- The malware used by FIN5, RawPOS, includes components like Duebrew, Fiendcry, and Driftwood, which encode stolen payment card data.
- The malware code is well-commented, indicating a possible ecosystem for advertising or support.
- FIN5 targets Active Directory for card data and uses tools like Windows Credentials Editor to obtain legitimate credentials.
- The group has custom tools for covering tracks, cleaning up malware traces, and accessing segregated network segments.
- FIN5's malware, RawPOS, is notable for evolving to target various types of POS software.
- FireEye has partnered with Visa to provide a new threat intelligence service for merchants and card issuers.

Date: October 13, 2015
Region: Global
Operating Sector: Payment card industry, lodging industry
Type of Company: Casinos, hotels, merchants, payment processors.


