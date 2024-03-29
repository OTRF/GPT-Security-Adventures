# Reference for threat actor for "Roaming Mantis"

**Title**: Roaming Mantis infects smartphones through Wi-Fi routers | Kaspersky official blog

**Source**: https://www.kaspersky.com/blog/roaming-mantis-malware/22427/

## Content








Roaming Mantis infects smartphones through Wi-Fi routers | Kaspersky official blog



















































































Solutions for:Home Products
Small Business 1-50 employees
Medium Business 51-999 employees
Enterprise 1000+ employees
 











Kaspersky official blog



My Account

My Kaspersky
My Products / Subscriptions
My Orders




Products



PREMIUM PROTECTIONKaspersky PremiumComplete protection for your devices, online privacy & identity
ADVANCED PROTECTIONKaspersky PlusCombines security, performance & privacy features in one app
STANDARD PROTECTIONKaspersky StandardEnhanced protection with device performance booster



Privacy & Kids
Kaspersky Safe Kids
Kaspersky VPN Secure Connection
Kaspersky Password Manager
View All Solutions


Renew
Downloads
Support
Resource Center
Blog

Business 
News 
Privacy 
Products 
Special Projects 
Technology 
Threats 
Tips 
RSS
Newsletter subscription

Secure Futures











 





Solutions for:

Home

Security Solutions

Kaspersky Premium
Kaspersky Plus
Kaspersky Standard
View All Solutions
Privacy & Kids
Kaspersky Safe Kids
Kaspersky VPN Secure Connection
Kaspersky Password Manager

Renew Licence
Support
Trials&Update

Business

Small Business (1-50 employees)
Medium Business (51-999 employees)
Enterprise (1000+ employees)


Search blog posts
Blog

Business 
News 
Privacy 
Products 
Special Projects 
Technology 
Threats 
Tips 
RSS

About us

About company
Transparency
Corporate News
Press Center
Careers
Sponsorships
Policy blog
Contacts

Partners

Find a Partner
Partners

My Account

Personal

My Kaspersky
Renew your product

Business

KSOS portal
Kaspersky Business Hub
Renew your License















Search








 smartphones

Roaming Mantis infects smartphones through Wi-Fi routers 
Originally targeting users from Japan, Korea, and China, Roaming Mantis is quickly spreading worldwide, infecting smartphones through hacked wi-fi routers.







Alex Drozhzhin




May 18, 2018




 





Some time ago our experts investigated a piece of malware that they dubbed Roaming Mantis. Back then, the people affected were mainly users from Japan, Korea, China, India, and Bangladesh, so we didn’t discuss the malware in the context of other regions; it seemed to be a local threat.
However, in the month since the report was published, Roaming Mantis has added two dozen more languages and is rapidly spreading around the world.
The malware uses compromised routers to infect Android-based smartphones and tablets. It then redirects iOS devices to a phishing site and runs the CoinHive cryptomining script on desktops and laptops. It does so by means of DNS hijacking, making it hard for targeted users to detect that something’s amiss.
What is DNS hijacking
When you enter a site name in your browser address bar, the browser doesn’t actually send a request to that site. It can’t; the Internet operates on IP addresses, which are sets of numbers, whereas domain names with words are easier for people to remember and input.
When you enter a URL, your browser sends a request to a DNS-server (DNS is Domain Name System), which translates the human-friendly name into the IP address of the corresponding website. It is this IP address that the browser uses to locate and open the site.
DNS hijacking is a way of fooling the browser into thinking it has matched the domain name to the correct IP address when in fact it hasn’t. Although the IP address is wrong, the original URL entered by the user is displayed in the browser address bar, so nothing looks suspicious.
There are many DNS-hijacking techniques, but the creators of Roaming Mantis have chosen perhaps the simplest and most effective: They hijack the settings of compromised routers, forcing them to use their own rogue DNS servers. That means regardless of what is typed into the browser address bar of a device connected to this router, the user is redirected to a malicious site.
Roaming Mantis on Android
After the user is redirected to the malicious site, they are prompted to update the browser. That leads to the download of a malicious app named chrome.apk (there was another version as well, named facebook.apk).

The malware requests a bunch of permissions during the installation process, including rights to access account information, send and receive SMS messages, process voice calls, record audio, access files, display its own window on top of others, and so on. For a trusted application such as Google Chrome, the list doesn’t seem too suspicious — if the user considers this “browser update” legit, they are sure to grant permissions without even reading the list.
After the application is installed, the malware uses the right to access the list of accounts to find out which Google account is used on the device. Next, the user is shown a message (it appears on top of all other open windows, another permission the malware requested) saying that something is wrong with their account and that they need to sign in again. A page then opens and prompts the user to enter their name and date of birth.

It appears that this data, together with the SMS permissions that grant access to the one-time codes needed for two-factor authentication, is then used by the creators of Roaming Mantis to steal Google accounts.
Roaming Mantis: World tour, iOS debut, and mining
In the beginning, Roaming Mantis could display messages in four languages: English, Korean, Chinese, and Japanese. But somewhere along the line, its creators decided to expand and add another two dozen languages to their polyglot malware:

Arabic
Armenian
Bulgarian
Bengali
Czech
Georgian
German
Hebrew
Hindi
Indonesian
Italian
Malay
Polish
Portuguese
Russian
Serbo-Croat
Spanish
Tagalog
Thai
Turkish
Ukrainian
Vietnamese

While they were at it, the creators also improved Roaming Mantis, teaching it to attack devices running iOS. It’s a different scenario from the Android attacks. On iOS, Roaming Mantis skips downloading the application; instead, the malicious site displays a phishing page prompting the user to log back in to the App Store right away. To add credibility, the address bar shows the reassuring URL security.apple.com:

The cybercriminals do not confine their theft to Apple ID credentials; immediately after entering this data, the user is asked for a bank card number:

The third innovation our experts uncovered concerns desktop computers and laptops. On these devices, Roaming Mantis runs the CoinHive mining script, which mines cryptocurrency and dumps it straight into the pockets of the malware makers. The victim’s computer processor is loaded to the max, forcing the system to slow down and consume vast amounts of power.

You can find more details about Roaming Mantis in the original report and a fresh Securelist post with updated information about the malware.
How to protect from Roaming Mantis

Use antivirus protection on all devices: not just computers and laptops, but smartphones and tablets too.
Regularly update all installed software on your devices.
On Android devices, disable the installation of applications from unknown sources. You’ll find this option under Settings -> Security -> Unknown sources.



 Update your router firmware (check your router’s manual to find out how) as often as possible. Don’t use unofficial firmware downloaded from shady sites.
Always change the default administrator password on the router.


What to do if infected by Roaming Mantis
Kaspersky security products detect and remove Roaming Mantis, so your first step is to install antivirus on all of your devices and run a system scan. After you scrub Roaming Mantis from your computers and devices, you’ll need to do a bit of cleanup to avoid reinfection:

Change all passwords for accounts compromised by the malware. Cancel all bank cards for which you entered details on the Roaming Mantis phishing site. 
Change the router administrator password and update the firmware. In doing so, be sure to download it only from the official website of the router manufacturer. 
Navigate to your router’s settings and check the DNS server address. If it doesn’t match the one issued by your provider — you can find that on your ISP’s website (check it from a safe system!) or call them to find out — change it back to the right one. 


 






android
DNS hijacking
iOS
mining
phishing
Roaming Mantis
routers
smartphones




 

Related





 


Ambient light sensor as a spy tool 






 


Non-standard smartphone wiretapping 
















 




Read next


Transatlantic Cable podcast, episode 37 
In this week’s podcast, Jeff and Dave riff on the Chili’s data breach, Facebook’s internal reviews, police falling victim to ransomware, and more. 




 








Jeffrey Esposito




May 16, 2018










Tips






 Tips


Five cyberattacks on marketing departments 
Why cybercriminals want to attack PR and marketing staff and, crucially, how to protect your company from financial and reputational harm.









Stan Kaminsky




February 13, 2024












 Tips


Navigating the risks of online dating 
Online dating is great for those looking for love – but beware the risks!









David Buxton




February 12, 2024












 Tips


What to do when you receive unsolicited messages containing login codes 
One-time codes and two-factor authentication securely protect you from account theft. If you receive such a code or a request to enter it when you aren’t logging in, it may be an attempt to hack into your account.









Stan Kaminsky




February 8, 2024












 Tips


How to steal crypto via DNS 
Getting what you pay for: cracked macOS apps fetch malicious code from DNS records to steal crypto









Sergey Puzan




January 31, 2024













Sign up to receive our headlines in your inbox



Email Address*

*

I agree to provide my email address to “AO Kaspersky Lab” to receive information about new posts on the site. I understand that I can withdraw this consent at any time via e-mail by clicking the “unsubscribe” link that I find at the bottom of any e-mail sent to me for the purposes mentioned above.

  





















Home Solutions

Kaspersky Standard
Kaspersky Plus
Kaspersky Premium
All Solutions


Small Business Products1-100 EMPLOYEES

Kaspersky Small Office Security
Kaspersky Endpoint Security Cloud
All Products


Medium Business Products101-999 EMPLOYEES

Kaspersky Endpoint Security Cloud
Kaspersky Endpoint Security for Business Select
Kaspersky Endpoint Security for Business Advanced
All Products


Enterprise Solutions1000 EMPLOYEES

Cybersecurity Services
Threat Management and Defense
Endpoint Security
Hybrid Cloud Security
All Solutions


 





Copyright © 2024 AO Kaspersky Lab. All Rights Reserved.
Privacy Policy
Anti-Corruption Policy
License Agreement B2C
License Agreement B2B
 
Contact Us About Us Partners Blog Resource Center Press Releases Sitemap  

Securelist
Eugene Personal Blog
Encyclopedia
 









 

Global













Americas
Brasil
México
United States


Africa
South Africa


Middle East
Middle East
الشرق الأوسط




Western Europe
Deutschland & Schweiz
España
France & Suisse
Italia & Svizzera
Nederland & België
United Kingdom




Eastern Europe
Polska
Türkiye
Россия (Russia)
Kazakhstan




Asia & Pacific
Australia
India
中国 (China)
日本 (Japan)


For all other countries
Global






























