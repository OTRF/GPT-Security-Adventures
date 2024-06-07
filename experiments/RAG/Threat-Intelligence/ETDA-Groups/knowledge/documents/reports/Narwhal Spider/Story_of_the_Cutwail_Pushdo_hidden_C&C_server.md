# Reference for threat actor for "Narwhal Spider"

**Title**: Story of the Cutwail/Pushdo hidden C&C server

**Source**: https://blog.avast.com/2013/06/25/15507/

## Content

































Story of the Cutwail/Pushdo hidden C&C server





































45954805351
Threat Intelligence Team
25-06-2013












Skip to main content
>Close




For home
For home
Products for PC and mobile phone protection


For business
For business
Protect your business with Avast


For partners
For partners
Partner with Avast and boost your business




About us
About us
Careers, investors, media, contact


Blogs
Academy, Blog, Decoded, Forum


Worldwide (English)




For home


Security







Free Antivirus













Basic protection for all your devices





Free Antivirus













Basic protection for all your devices





Free Antivirus













Basic protection for all your devices





Free Antivirus













Basic protection for all your devices







Premium Security













Complete protection against all internet
                                            threats







Ultimate













Our best security, privacy, and performance apps in
                                            one package



Looking for a product for your device? Free Antivirus for PC, Free Security for Android, Free Security for Mac, Free Security for iPhone/iPad


Looking for a product for your device?

Free Antivirus for PC
Free Security for Mac
Free Security for Android
Free Security for iPhone/iPad





Privacy







SecureLine VPN













Encrypt your connection to stay safe on public
                                            networks







AntiTrack













Disguise your digital fingerprint to avoid
                                            personalized ads







Secure Browser













Enjoy safer browsing that’s up to 4x faster







BreachGuard













Protect your personal info from being exposed and
                                            sold






Performance







Cleanup Premium













Boost your computer’s speed and performance





Cleanup Premium













Boost your computer’s speed and performance





Cleanup Premium













Boost your computer’s speed and performance





Cleanup Premium













Boost your computer’s speed and performance







Driver Updater













Automatically update drivers with a single
                                            click







Battery Saver













Maximize your battery life 









                                Store
                            








                                Home
                            







                                Support
                            






                                Store
                            







                                Account
                            




For business


Solutions






Endpoint Protection
                                    















Small Businesses
11-100

Safeguard your data, devices, and apps with Next-Gen
                                            Antivirus, Patch Management,
                                        and Cloud
                                            Backup.





All-In-One Protection
                                    















Medium and Large Businesses
101-1000+


Endpoint
                                            Protection
Backup and
                                            Recovery
Endpoint
                                            Optimization
Cloud Network
                                            Security
Business Hub Security
                                            Platform






Advanced All-In-One Protection
                                    















Channel Partners
MSPs, Resellers, Distributors


Endpoint
                                            Protection
Cloud Network
                                            Security
CloudCare Security
                                            Platform



Not sure which solution is right for your business? Help me choose



Business partners



Become a partner


MSP partners


Reseller partners


Distributor partners


Affiliates


Partner locator





Resources


Trials





                                Store
                            








                                Home
                            






                                Contact sales
                            







                                Support
                            





                                Store

                            







                            Account
                        


Business Hub
CloudCare
Reseller portal






For partners


Smart Life


Mobile Security


VPN


Threat Intelligence


Knowledge Center




About us


About Avast


Careers


Privacy





Privacy


Expert guides


Privacy blogs







Blog





Avast News



Business Security



Covid-19 Scams



Diversity & Inclusion



Elders



Privacy



Sandwich Generation



Security News



Threat Research



Tips & Advice








Press center





Press releases


Events


In the news


Media materials


PR contacts







Investors



Our story


At a glance


Strategy


Technology
                                                expertise


Leadership


History




Investors


Overview


Growth &
                                                competitive advantage


IPO information


Regulatory news


Share price &
                                                tools


Corporate
                                                governance


Investor contacts


Financial
                                                calendar


Results, reports
                                                & presentations

Analyst consensus


Shareholder
                                                information


Contact us









Awards


Diversity & Inclusion





Diversity & Inclusion


Accessibility







Contact us




Blogs


Avast Blog
Read about recent news from the security world




Avast Academy
Expert tips and guides about digital security and
                            privacy




Avast Decoded
In-depth technical articles regarding security
                            threats




Avast Forum
Discuss with the community







 
List of available regions


Main regions

Worldwide (English)
Europe (English)
América Latina (español)




AMERICAS


Argentina
Brasil
Canada (English)
Canada (français)
Chile
Colombia
EE.UU. (español)
México
USA (English)


América Latina (español)




EUROPE, MIDDLE EAST & AFRICA


België (Nederlands)
Belgique (français)
Česká republika
Danmark
Deutschland 
España
France
Italia 
Magyarország
Nederland
Norge
Polska
Portugal
Schweiz (Deutsch)
Slovensko (česky)
South Africa


Suisse (français)
Suomi
Sverige
Türkiye
United Arab Emirates
United Kingdom
Ελλάδα
ישראל
Казахстан
România
Россия
Україна
                            (українська)
Украина
                            (русский)
المملكة العربية السعودية

الدول العربية


Europe (English)




ASIA & PACIFIC


Australia
India
इंडिया (हिंदी)
Indonesia (English)
Indonesia (Bahasa
                            Indonesia)
Malaysia (English)
Malaysia (Bahasa Melayu)

New Zealand
Philippines (English)
Pilipinas (Filipino)


Singapore
Việt Nam
日本語 
대한민국
简体中文
繁體中文
ประเทศไทย


Worldwide (English)









Close
Sections

All
business security 
Avast News 
Security News 
Tips & Advice 
Viewpoints 
Privacy 
Threat Research 
Diversity & Inclusion 
Diversity & Inclusion 

Blog Authors
Visit Avast website
Change language

English
Deutsch
Čeština
Español
Français
Polski
Português
Русский
日本語











Avast Blog






Story of the Cutwail/Pushdo hidden C&C server









Story of the Cutwail/Pushdo hidden C&C server








Threat Intelligence Team  25 Jun 2013






Story of the Cutwail/Pushdo hidden C&C server
This is a loose sequel to the Cutwail botnet analysis blogpost published on the malwaremustdie.blogspot.com. In this blogpost I will primarily focus on the downloaded PE executable itself (SHA256: 5F8FCC9C56BF959041B28E97BFB5DB9659B20A6E6076CFBA8CB2D591184C9164) and the network traffic that it generates. I will also reveal a hidden C&C server.
But first let's quickly go through the things it does at the beginning:
- It registers an exception handler that will only start the process again using CreateProcess().
- It performs a check whether it has admin privileges.
- It checks or creates a mutex named "xoxkycomvoly" (hardcoded identifier used on multiple occasions).
- It checks or creates couple of registry entries under HKCU\Software\Microsoft\Windows\CurrentVersion.
- It checks if the process image filename is "xoxkycomvoly.exe" (it restarts for the first time).
- It nests into the system by creating autorun entry in registry under HKCU\Software\Microsoft\Windows\CurrentVersion\Run.
- It copies itself to the user's profile directory named as "xoxkycomvoly.exe".
Then on the first time an exception occurs and the sample is restarted from the user's profile location named as "xoxkycomvoly.exe".
 Initial startup activities
After these initial steps, the sample starts communicating heavily over the network.

The sample contains number of hardcoded hostnames in a plain text form, making a little bit of an impression that it is a simple program, but those are rather only decoys. Let's go chronologicaly and see what it does exactly.
The first group of hardcoded hostnames that takes place is the following list of 6 SMTP servers:
smtp.live.com
smtp.mail.yahoo.com
smtp.sbcglobal.yahoo.com
smtp.directcon.net
mail.airmail.net
smtp.compuserve.com

These SMTP servers are only used to try outgoing TCP connection on port 25, to see if it is filtered in any way (to see if it's gonna be able to send spam).
Then there is another list of plain text hostnames, which look somewhat suspiciously:
4darabians.nl
4dbenelux.be
accords-bilateraux.ch
4e-energiezentrale.de
4effect.ca
4egolifestyle.de
4elementos.cl
4-elements.ch
4elements.de
4elements.hu
4-elements.se
4emails.de
8wellesley.ca
8zsmost.cz
4enerchi.nl
4entertainmentgroup.tv
4ernila.de
4e-solutions.ch
accounting.ee
0daymusic.biz
0handicap.at
4dbabamozi.hu
accords-bilateraux.ch
0kommanix.de
4effect.ca
4egolifestyle.de
4elementos.cl
4-elements.ch
4elements.gr
4elements.pl

Almost all of these hostnames listen on port 25, giving a premature idea that they may be the SMTP relays through which it sends spam, but the sample doesn't really do anything much with these, they are only supposed to distract us from the real business!
The interesting thing that comes next is that the sample also contains several enxored data blobs, each one enxored with different xor key, and these blobs contain some very interesting things, hidden from the plain sight.
The first data blob that gets dexored is this list of hostnames:
1st group of hidden hostnames
4dmobil.at
4eternity.ch
4everandever.de
4everflashlight.de
4ever-hosting.de
4evernet.de
4evernails.nl
4every1.cc
4everything.pl
9online.fr
9welten.de
4everweb.nl
accountingtechs.biz

These dexored hostnames look like a good candidates for C&C servers to me. Indeed as the next step the sample is trying to connect to one of these hostnames on port 443 (HTTPS) possibly to obtain a command (Cutwail/Pushdo uses custom binary executable modules). Usage of the HTTPS protocol prevents the actual content to be inspectable in the network capture records, but through reverse engineering we can see that it requests GET /. If the server responds with a reasonable reply (at least 1024 bytes long), it proceeds to check whether the response contains the familiar HTML mark (which is also enxored btw):
<img src="data:image/jpeg;base64

If that's indeed found in the server response, the data after the mark (obviously not a jpeg) are decrypted with some interesting decryption routines and we get a binary executable (Cutwail/Pushdo module). Then a new svchost.exe process is started in a suspended state and the binary is injected into it and executed.
On the other hand, if the obtained server response does not contain the special HTML mark, no other C&C server from this list is tried. It is simply happy with a web server test page, having no orders from the C&C server. Seems a bit fishy!
Search for special "<img src" mark
Anyway, next enxored blob that comes to the program flow turns out to be this large list of domains:
2nd group of hidden hostnames
Pretty impressive list of 200 hostnames, actually only 176 unique:
accessus.net, accountant.com, actuslendlease.com, agilent.com, allstream.net, amazon.com, anetsbuys.com, aon.at, arcor.de, aruba.it, atkearney.com, aussiestockforums.com, axelero.hu, backaviation.com, badactor.us, bassettfurniture.com, beeone.de, bendcable.com, blackplanet.com, bluewin.ch, bluewin.com, bmw.com, boardermail.com, brettlarson.com, cablelan.net, caixa.gov.br, canada.com, cbunited.com, centrum.cz, cfl.rr.com, charter.com, chataddict.com, chickensys.com, claranet.fr, clarksville.com, clear.net.nz, cnet.com, col.com, colorado.edu, comcast.net, cox.com, cox.net, creighton.edu, cwnet.com, cytanet.com.cy, diamondcpu.com, doctor.com, dr.com, earthlink.com, earthlink.net, emailmsn.com, embarqmail.com, erzt.com, expn.com, feton.net, floodcity.net, free.fr, freenet.de, frisurf.no, frostburg.edu, gallatinriver.net, gatespeed.com, gcsu.edu, gmx.net, grar.com, gravityboard.com, happyhippo.com, hotmale.com, hoymail.com, ia.telecom.net, idea.com, idealcollectables.com, ig.com.br, imaginet.com, in.com, indosat.com, intelnet.net.gt, intuit.com, ipeg.com, itexas.net, iupui.edu, iw.com, iwon.com, juno.com, jwu.edu, kazza.com, kcrr.com, kw.com, lansdownecollege.com, machlink.com, mania.com, marchmail.com, maui.net, mediom.com, metallica.com, metrocast.net, mexico.com, microtek.com, midway.edu, migente.com, mindspring.com, ministryofsound.net, msu.edu, mts.net, music.com, mville.edu, mvts.com, mynet.com, mzsg.at, nccn.net, netsync.net, number1.net, o2.pl, oakland.edu, oakwood.org, optonline.net, orange.pl, oregonstate.edu, otakumail.com, pandora.be, parrotcay.como.bz, passagen.se, pchome.com.tw, penn.com, pga.com, picsnet.com, posten.se, potamkinmitsubishi.com, primeline.com, rcn.com, reactionsearch.com, ricochet.com, rockford.edu, rowdee.com, sexstories.com, shmais.com, south.net, springsips.com, sscomputing.com, stargate.net, stc.com.sa, surfglobal.net, suscom.net, t-mobel.com, talstar.com, tampabay.rr.com, tellmeimcute.com, the-beach.net, tiscali.co.uk, uakron.edu, ufl.edu, uga.edu, ukr.net, uplink.net, uymail.com, vail.com, vampirefreaks.com, verizonwireless.com, vodafone.com, vodafone.nl, voicestream.com, wcsu.edu, willinet.net, windermere.com, windstream.net, worldnetatt.net, worldonline.co.uk, www.aol.com, xtra.co.nz, yahoo.com.cn, yahoo.com.hk, yahoo.com.tw, yatroo.com, zdnetmail.com, zoomnet.net, zoomtown.com

The next thing is that it starts a pair of 8 threads. One pair will connect randomly to these hosts on port 80 and send bogus HTTP requests (like those infamous ptrxcz_ POST requests) and the other pair will connect randomly to those hosts on port 25 and just send some random data to it, not even SMTP traffic, not even waiting for the server banner. This goes on in an endless loop, in the background, 16 noisy threads sending bogus traffic, apparently trying to mask some activity, which is about to start soon.
Start 16 threads generating a bogus traffic noise
 Bogus HTTP traffic examples
 Bogus SMTP traffic examples
OT: Then the sample collects some informations about our client machine such as disk, network adapter info, operating system version etc, encrypts it and sends it to lyuchta.org over HTTP in the background:
Reporting client machine info to lyuchta.org
Now there is an interesting code block in the program, where it iterates through all those 200 dexored hostnames (victims of bogus traffic). It calculates some hash value from each one and then compares it to some strange hardcoded value, which only now started to make sense. The comparison condition triggers when comparing "anetsbuys.com" hostname, which happens to match the hash. This is the special C&C server, whose identity is primarily being masked. It's not only hidden in the traffic noise from those 16 annoying threads in the background, but also being supposedly one of the victims.
Iterate through all the hosts from 2nd group and find the special one
This special C&C server is then used to obtain commands (modules) from in the final stage of the malware, where it enters an endless loop and contacts the special C&C server for orders, modules to load. If it is unable to obtain an order from it, then it resorts to generate those characteristic KZ domain names with the DGAs and try to obtain an order from them. Personally I have seen orders to come only from the special C&C "anetsbuys.com". When an order comes and everything goes fine, the sample sleeps for 12 hours, otherwise it sleeps for 2 minutes to repeat the loop and get some command.
Communication with the C&C server:
Obtained 4 modules from this one
Cutwail/Pushdo module decrypted in the memory:
Looks like a typical executable file
The modules then perform actual spamming and other malicious activities.




























































Related articles







Subscribe to our newsletter


Subscribe





Most popular











Video: Accept all cookies? A recipe for online privacy this holiday season
11 Dec 2023

















How to use Discord’s ‘Family Center’ to help protect your child
24 Jul 2023

















The hidden pitfalls of travel apps
13 Jul 2023

















Avast researchers uncover disturbing crowdfunding scheme
28 Jun 2023



















Your essential cybersecurity checklist for safe summer travel
14 Jun 2023


























Never miss our news




Follow us


























1988 - 2024 Copyright © Avast Software s.r.o. | Sitemap Privacy policy

















 -->
       -->
      










































