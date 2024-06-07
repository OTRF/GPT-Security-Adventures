# Reference for threat actor for "Desert Falcons"

**Title**: New Variants of Android Spyware Linked to APT C-23 Enhanced for Stealth and Persistence, Sophos Research Reveals | Sophos

**Source**: https://www.sophos.com/en-us/press-office/press-releases/2021/11/new-variants-of-android-spyware-linked-to-apt-c-23-enhanced-for-stealth-and-persistence.aspx

## Content






























New Variants of Android Spyware Linked to APT C-23 Enhanced for Stealth and Persistence, Sophos Research Reveals | Sophos







      Skip to main content
    












Primary Menu


Services & Products


Solutions


Partners


About


Support











Cybersecurity as a Service
Managed Services





24/7 Threat Detection and Response
Sophos Managed Detection and Response





Experiencing a Cyberattack?
Sophos Incident Response Services




Get Started




Managed Services
Sophos Managed Detection and Response
Sophos Incident Response Services






Sophos Central Platform
Products





Endpoint


Sophos Endpoint (EDR)


Sophos Workload Protection


Sophos Mobile


Sophos Encryption




Network


Sophos Firewall


Sophos Wireless


Sophos Switch


Sophos Zero Trust Network




Email & Cloud


Sophos Email


Sophos Phish Threat


Cloud Native Security


Cloud Workload Protection




Security Operations


Sophos MDR


Sophos XDR


Sophos Factory




For Small Business


Sophos Small Business




For Home


Sophos Home























Sophos Global Partner Program
Profitable. Powerful. Adaptive.
Become a Partner Partner Portal Sign In








Partner Program


Overview


Managed Service Provider (MSP)


Cloud Security Provider (CSP)


Partner Care




Technology


Marketplace


OEM




Partner Tools


Partner Portal


Sophos Central Partner


Partner Locator


Partner Blog


Partner Training
















Sophos Support
Support Portal








Get Help


Support Plans


Downloads & Updates


Documentation


Sophos Training


Contact Support


Support Portal




Resources


Join the Community


Twitter Support


Knowledge Base


Techvids


Sophos Central Status


Submit a Threat




Product Support


Sophos Firewall


Sophos Endpoint


Sophos Server


Sophos Central


Sophos Email


More Products
















Superior cybersecurity outcomes for real-world organizations.
Read the Reviews








Company


About Us


Press


Sophos Events


Careers


Contact




News


Sophos Blog


Sophos AI


Sophos X-Ops




Sign In


Sophos Home


Sophos Central


Partner Portal


Licenses & Account




Why Sophos


Sophos vs the Competition


Read the Reviews
















Secure your small business.
Enterprise-grade cybersecurity that's cost-effective for small businesses.
Get Started








Industries


Education


Finance and Banking


US Federal


Healthcare


Manufacturing


Retail


More




Compliance


NIS2 Directive


HIPAA


PCI DSS


GDPR


NIST SP800-171


ISO/IEC 27001:2022


More




Use Cases


Cloud Security


SASE


Ransomware Protection


Supply Chain Security


Securing Remote Workers


Cyber Insurance Optimization


More



















Toggle Language menu





Services & Products





Cybersecurity as a Service
Managed Services





24/7 Threat Detection and Response
Sophos Managed Detection and Response





Experiencing a Cyberattack?
Sophos Incident Response Services




Get Started




Managed Services
Sophos Managed Detection and Response
Sophos Incident Response Services



Products


Endpoint


Sophos Endpoint (EDR)


Sophos Workload Protection


Sophos Mobile


Sophos Encryption




Network


Sophos Firewall


Sophos Wireless


Sophos Switch


Sophos Zero Trust Network




Email & Cloud


Sophos Email


Sophos Phish Threat


Cloud Native Security


Cloud Workload Protection




Security Operations


Sophos MDR


Sophos XDR


Sophos Factory




For Small Business


Sophos Small Business




For Home


Sophos Home








Solutions


Industries


Education


Finance and Banking


US Federal


Healthcare


Manufacturing


Retail


More




Compliance


NIS2 Directive


HIPAA


PCI DSS


GDPR


NIST SP800-171


ISO/IEC 27001:2022


More




Use Cases


Cloud Security


SASE


Ransomware Protection


Supply Chain Security


Securing Remote Workers


Cyber Insurance Optimization


More






Partners


Partner Program


Overview


Managed Service Provider (MSP)


Cloud Security Provider (CSP)


Partner Care




Technology


Marketplace


OEM




Partner Tools


Partner Portal


Sophos Central Partner


Partner Locator


Partner Blog


Partner Training






About


Company


About Us


Press


Sophos Events


Careers


Contact




News


Sophos Blog


Sophos AI


Sophos X-Ops




Sign In


Sophos Home


Sophos Central


Partner Portal


Licenses & Account




Why Sophos


Sophos vs the Competition


Read the Reviews






Support


Get Help


Support Plans


Downloads & Updates


Documentation


Sophos Training


Contact Support


Support Portal




Resources


Join the Community


Twitter Support


Knowledge Base


Techvids


Sophos Central Status


Submit a Threat




Product Support


Sophos Firewall


Sophos Endpoint


Sophos Server


Sophos Central


Sophos Email


More Products










All Products


Cybersecurity for Home


Free Tools




















Toggle Search


Toggle Language menu


Toggle Mobile menu





Toggle Section menu

Company




Overview


Press


Threat News


Events


Careers


Contact


News











Switch Language


English简体中文FrançaisDeutschItaliano日本語Português, BrasilEspañol





Breadcrumb


Home


Company


Press


New Variants of Android Spyware Linked To APT C-23 Enhanced For Stealth and Persistence, Sophos Research Reveals







New Variants of Android Spyware Linked to APT C-23 Enhanced for Stealth and Persistence, Sophos Research Reveals
















OXFORD, U.K.  —
November 23, 2021 —

Sophos, a global leader in next-generation cybersecurity, has published, “Android APT Spyware, Targeting Middle East Victims, Enhances Evasiveness,” detailing new variants of Android spyware linked to C-23, an advanced persistent threat (APT) adversary that has been active in the Middle East since 2017. The new variants are enhanced for stealth and persistence.
The spyware presents itself as an update app with a generic icon and name, such as “App Updates.” Sophos researchers believe the attackers distribute the spyware app by sending a download link in the form of a text message to the target's phone. The first time a target runs the spyware app, it asks for permissions to control various aspects of the phone. The attackers use social engineering techniques to convince the target these permissions are essential for the app to function. After the target has granted the necessary rights, the spyware then disguises itself using the name and icon of a legitimate app. This makes it harder for the phone's user to find and manually remove the spyware.
The New Variants
The new variants use more, and more varied, disguises than previous versions, hiding behind popular app icons such as Chrome, Google, Google Play, YouTube, or the BOTIM voice-over-IP service. If targets click a fraudulent icon, the spyware launches the legitimate version of the app, while maintaining surveillance in the background. 
Previous versions of the spyware relied on a single command-and-control domain that was hardcoded into the app and operated by the attackers. If a defender found and took down the domain, the spyware was disabled. Sophos researchers believe that the attackers have tried to address this potential point of weakness in the new variants, which can switch the command-and-control server to a different domain. This allows the spyware to continue operating even after a domain takedown. 
The new variants share code with other malware samples attributed to APT C-23. Sophos researchers also found Arabic language strings in the code and observed that some of the text could be presented in either English or Arabic, depending on the language setting of a victim’s phone.
Nefarious features from previous versions of the spyware remain unchanged, such as: collecting text from SMS or other apps, contacts, call logs, images, and documents; recording ambient audio and incoming and outgoing calls, including WhatsApp calls; taking pictures and screen shots using a phone’s camera and recording videos of the screen; reading notifications from social media and messaging apps; and canceling notifications from built-in security apps, as well as from Android system apps. The spyware can also supress its own notifications.
“Spyware is a growing threat in an increasingly connected world,” said Pankaj Kohli, threat researcher at Sophos. “The Android spyware linked to APT C-23 has been around for at least four years, and attackers continue to develop it with new techniques that evade detection and removal. The attackers also use social engineering to lure victims into granting the permissions needed to see into every corner of their digital life. Fortunately, there are practical steps that people can take to protect against spyware and many of them are worth applying even if users don’t believe they’re a target for surveillance.”
Sophos recommends the following actions for anyone concerned about spyware or Potentially Unwanted Applications (PUAs):
Users should be wary of apps asking for sensitive permissions, such as device admin or notification access, or those requiring superuser/root access. Users can view apps with device admin and notification access permissions by browsing “Settings” and searching for "device admin apps" and "notification access," respectively
The sudden disappearance of an app icon after running it for the first time, which is often an indicator of an unwanted or malicious application
Targets of this family of spyware can remove the apps manually by navigating to the list of installed apps, selecting “Settings->Apps” and then scrolling to find the name the app used when it was first installed (such as "App Updates," “System Apps Updates” or “Android Update Intelligence”)
However, many other forms of mobile malware conceal themselves from the list of installed apps. To remove these, users need the help of an anti-malware application
Sophos also advises users to install a mobile security solution, such as Intercept X for Mobile, to automatically detect spyware and malware
To avoid falling prey to malicious apps, users should only install mobile apps from trusted sources, such as Google Play. Update Android OS and other apps via Android Settings and Google Play respectively, instead of relying on third parties
SophosLabs has published indicators of compromise on its Github page.
To learn more about the Android spyware, read the article on SophosLabs Uncut.








About Sophos
Sophos is a worldwide leader and innovator of advanced cybersecurity solutions, including Managed Detection and Response (MDR) and incident response services and a broad portfolio of endpoint, network, email, and cloud security technologies that help organizations defeat cyberattacks. As one of the largest pure-play cybersecurity providers, Sophos defends more than 500,000 organizations and more than 100 million users globally from active adversaries, ransomware, phishing, malware, and more. Sophos’ services and products connect through its cloud-based Sophos Central management console and are powered by Sophos X-Ops, the company’s cross-domain threat intelligence unit. Sophos X-Ops intelligence optimizes the entire Sophos Adaptive Cybersecurity Ecosystem, which includes a centralized data lake that leverages a rich set of open APIs available to customers, partners, developers, and other cybersecurity and information technology vendors. Sophos provides cybersecurity-as-a-service to organizations needing fully-managed, turnkey security solutions. Customers can also manage their cybersecurity directly with Sophos’ security operations platform or use a hybrid approach by supplementing their in-house teams with Sophos’ services, including threat hunting and remediation. Sophos sells through reseller partners and managed service providers (MSPs) worldwide. Sophos is headquartered in Oxford, U.K. More information is available at www.sophos.com.










News


Overview


Press Releases


Sophos X-Ops Threat Research


Awards and Reviews


Press Contacts














Footer - Default


Column 1


Managed Services


MDR


Incident Response


NDR




ENDPOINT


Endpoint (XDR)


Server


Mobile


Encryption






Column 2


NETWORK


Firewall


Wireless


Switch


ZTNA




EMAIL & CLOUD


Email Protection


Anti-Phishing


Cloud Native Security


Workload Protection






Column 3


TRY FOR FREE


Free Trials


Product Demos


Free Tools




Solutions


Small and Medium Business




TRUST


Trust Center






Column 4


SUPPORT


Support Packages


Contact Support


Training


Downloads and Updates


Documentation




CYBER INSURANCE


Insurance Carriers




LEARN


Cybersecurity Explained


Ransomware Documentary






Column 5


Partners


MSP


Partner Training


Partner News


Become a Partner


OEM


Cloud Security


Partner Care


Find a Reseller




Why Sophos


Sophos vs the Competition


Read the Reviews






Column 6


About Us


Company


Careers




Contact


Overview


Find a Partner


Tech Support














Switch Language


English简体中文FrançaisDeutschItaliano日本語Português, BrasilEspañol










Terms


Privacy


Your Privacy Choices


Privacy Notice


Cookies




Legal


General


Modern Slavery Statement


Speak Out







        © 1997-2024 Sophos Ltd. All Rights Reserved.

















