# Threat actor: FIN11

**UUID**: d6613f53-5694-4aa4-a5d9-c51c6cd9426e

**First seen**: 2016

**Source last modified**: 2024-01-16

## Threat actor aliases

FIN11 (FireEye), DEV-0950 (Microsoft), Lace Tempest (Microsoft)

## Description

(FireEye) Mandiant has also responded to numerous FIN11 intrusions, but we’ve only observed the group successfully monetize access in few instances. This could suggest that the actors cast a wide net during their phishing operations, then choose which victims to further exploit based on characteristics such as sector, geolocation or perceived security posture. Recently, FIN11 has deployed CLOP ransomware and threatened to publish exfiltrated data to pressure victims into paying ransom demands. The group’s shifting monetization methods—from point-of-sale (POS) malware in 2018, to ransomware in 2019, and hybrid extortion in 2020—is part of a larger trend in which criminal actors have increasingly focused on post-compromise ransomware deployment and data theft extortion.

Notably, FIN11 includes a subset of the activity security researchers call {{TA505, Graceful Spider, Gold Evergreen}}, but we do not attribute TA505’s early operations to FIN11 and caution against using the names interchangeably. Attribution of both historic TA505 activity and more recent FIN11 activity is complicated by the actors’ use of criminal service providers. Like most financially motivated actors, FIN11 doesn’t operate in a vacuum. We believe that the group has used services that provide anonymous domain registration, bulletproof hosting, code signing certificates, and private or semi-private malware. Outsourcing work to these criminal service providers likely enables FIN11 to increase the scale and sophistication of their operations.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Financial crime, Financial gain


## Country of origin

[Unknown]

## Observed attacked sectors where victims operate in

Defense, Education, Energy, Financial, Hospitality, Retail, Telecommunications, Technology, Transportation

## Observed attacked countries where victims operate in

Worldwide

## Observed usage of tools

Amadey, AndroMut, AZORult, BLUESTEAL, Clop, EMASTEAL, FlawedAmmyy, FLOWERPIPE, FORKBEARD, Get2, JESTBOT, Meterpreter, MINEBRIDGE, MINEDOOR, MIXLABEL, NAILGUN, POPFLASH, SALTLICK, SCRAPMINT, SHORTBENCH, SLOWROLL, SPOONBEARD, TinyMet, VIDAR

## Reported hacking operations

2019-12: Ransomware attack on Maastricht University
https://www.bleepingcomputer.com/news/security/ta505-hackers-behind-maastricht-university-ransomware-attack/

2020-03: U.S. pharmaceutical giant ExecuPharm has become the latest victim of data-stealing ransomware.
ExecuPharm said in a letter to the Vermont attorney general’s office that it was hit by a ransomware attack on March 13, and warned that Social Security numbers, financial information, driver licenses, passport numbers and other sensitive data may have been accessed.
But TechCrunch has now learned that the ransomware group behind the attack has published the data stolen from the company’s servers.
https://techcrunch.com/2020/04/27/execupharm-clop-ransomware/

2020-10: Software AG IT giant hit with $23 million ransom by Clop ransomware
https://www.bleepingcomputer.com/news/security/software-ag-it-giant-hit-with-23-million-ransom-by-clop-ransomware/

2020-12: Global Accellion data breaches linked to Clop ransomware gang
https://www.bleepingcomputer.com/news/security/global-accellion-data-breaches-linked-to-clop-ransomware-gang/

2020-12: Singtel, QIMR Berghofer report Accellion-related data breaches
https://www.bleepingcomputer.com/news/security/singtel-qimr-berghofer-report-accellion-related-data-breaches/

2020-12: New Zealand Reserve Bank breached using bug patched on Xmas Eve
https://www.bleepingcomputer.com/news/security/new-zealand-reserve-bank-breached-using-bug-patched-on-xmas-eve/

2021-01: Australian securities regulator discloses security breach
https://www.bleepingcomputer.com/news/security/australian-securities-regulator-discloses-security-breach/

2021-01: Data breach exposes 1.6 million Washington unemployment claims
https://www.bleepingcomputer.com/news/security/data-breach-exposes-16-million-washington-unemployment-claims/

2021-02: Hacker Claims to Have Stolen Files Belonging to Prominent Law Firm Jones Day
https://www.wsj.com/articles/hacker-claims-to-have-stolen-files-belonging-to-prominent-law-firm-jones-day-11613514532

2021-02: Clop ransomware gang leaks online what looks like stolen Bombardier blueprints of GlobalEye radar snoop jet
https://www.theregister.com/2021/02/23/bombardier_clop_ransomware_leaks/

2021-02: Kroger data breach exposes pharmacy and employee data
https://www.bleepingcomputer.com/news/security/kroger-data-breach-exposes-pharmacy-and-employee-data/

2021-03: Cybersecurity firm Qualys is the latest victim of Accellion hacks
https://www.bleepingcomputer.com/news/security/cybersecurity-firm-qualys-is-the-latest-victim-of-accellion-hacks/

2021-03: Ransomware gang leaks data stolen from Colorado, Miami universities
https://www.bleepingcomputer.com/news/security/ransomware-gang-leaks-data-stolen-from-colorado-miami-universities/

2021-03: Energy giant Shell discloses data breach after Accellion hack
https://www.bleepingcomputer.com/news/security/energy-giant-shell-discloses-data-breach-after-accellion-hack/

2021-03: Ransomware gang urges victims’ customers to demand a ransom payment
https://www.bleepingcomputer.com/news/security/ransomware-gang-urges-victims-customers-to-demand-a-ransom-payment/

2021-03: Ransomware group targets universities in Maryland, California in new data leaks
https://www.zdnet.com/article/ransomware-group-targets-universities-of-maryland-california-in-new-data-leaks/

2021-03: Ransomware gang leaks data from Stanford, Maryland universities
https://www.bleepingcomputer.com/news/security/ransomware-gang-leaks-data-from-stanford-maryland-universities/

2021-04: More Accellion Health Data Breaches Revealed
https://www.healthcareinfosecurity.com/more-accellion-health-data-breaches-revealed-a-16350

2021-06: Clop ransomware is back in business after recent arrests
https://www.bleepingcomputer.com/news/security/clop-ransomware-is-back-in-business-after-recent-arrests/

2021-10: Clop ransomware gang is leaking confidential data from the UK police
https://securityaffairs.co/wordpress/125792/cyber-crime/clop-ransomware-uk-police.html

2021-11: Marine services provider Swire Pacific Offshore hit by ransomware
https://www.bleepingcomputer.com/news/security/marine-services-provider-swire-pacific-offshore-hit-by-ransomware/

2022-04: Clop ransomware gang is back, hits 21 victims in a single month
https://www.bleepingcomputer.com/news/security/clop-ransomware-gang-is-back-hits-21-victims-in-a-single-month/

2022-08: Hackers attack UK water supplier but extort wrong company
https://www.bleepingcomputer.com/news/security/hackers-attack-uk-water-supplier-but-extort-wrong-company/
https://therecord.media/ransomware-group-may-have-stolen-customer-bank-details-from-british-water-company/

2022-09: FIN11 is Back : Impersonates Popular Video Conference Application
https://www.cyfirma.com/outofband/fin11-is-back-impersonates-popular-video-conference-application/

2022-12: Cl0p Ransomware Targets Linux Systems with Flawed Encryption
https://www.sentinelone.com/labs/cl0p-ransomware-targets-linux-systems-with-flawed-encryption-decryptor-available/

2023-02: Clop ransomware claims it breached 130 orgs using GoAnywhere zero-day
https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-it-breached-130-orgs-using-goanywhere-zero-day/

2023-03: Clop ransomware gang begins extorting GoAnywhere zero-day victims
https://www.bleepingcomputer.com/news/security/clop-ransomware-gang-begins-extorting-goanywhere-zero-day-victims/

2023-03: Clop ransomware claims Saks Fifth Avenue, retailer says mock data stolen
https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-saks-fifth-avenue-retailer-says-mock-data-stolen/

2023-03: City of Toronto confirms data theft, Clop claims responsibility
https://www.bleepingcomputer.com/news/security/city-of-toronto-confirms-data-theft-clop-claims-responsibility/

2023-03: Procter & Gamble confirms data theft via GoAnywhere zero-day
https://www.bleepingcomputer.com/news/security/procter-and-gamble-confirms-data-theft-via-goanywhere-zero-day/

2023-03: UK Pension Protection Fund latest victim of GoAnywhere hack
https://therecord.media/uk-pension-protection-fund-clop-goanywhere-fortra

2023-03: Crown Resorts confirms ransom demand after GoAnywhere breach
https://www.bleepingcomputer.com/news/security/crown-resorts-confirms-ransom-demand-after-goanywhere-breach/

2023-03: Tasmania officials: 16,000 student documents leaked by Clop ransomware group
https://therecord.media/tasmania-government-ransomware-clop-student-documents

2023-04: Microsoft: Clop and LockBit ransomware behind PaperCut server hacks
https://www.bleepingcomputer.com/news/security/microsoft-clop-and-lockbit-ransomware-behind-papercut-server-hacks/

2023-05: Microsoft links Clop ransomware gang to MOVEit data-theft attacks
https://www.bleepingcomputer.com/news/security/microsoft-links-clop-ransomware-gang-to-moveit-data-theft-attacks/
https://www.bleepingcomputer.com/news/security/clop-ransomware-gang-starts-extorting-moveit-data-theft-victims/

2023-05: Missouri warns that health info was stolen in IBM MOVEit data breach
https://www.bleepingcomputer.com/news/security/missouri-warns-that-health-info-was-stolen-in-ibm-moveit-data-breach/

2023-05: US govt contractor Serco discloses data breach after MoveIT attacks
https://www.bleepingcomputer.com/news/security/us-govt-contractor-serco-discloses-data-breach-after-moveit-attacks/

2023-05: Colorado warns 4 million of data stolen in IBM MOVEit breach
https://www.bleepingcomputer.com/news/security/colorado-warns-4-million-of-data-stolen-in-ibm-moveit-breach/

2023-05: Russian cyber thieves linked to personal data breach at North Carolina hospitals
https://news.yahoo.com/russian-cyber-thieves-linked-personal-202630737.html

2023-05: Sony confirms data breach impacting thousands in the U.S.
https://www.bleepingcomputer.com/news/security/sony-confirms-data-breach-impacting-thousands-in-the-us/

2023-05: Third Flagstar Bank data breach since 2021 affects 800,000 customers
https://www.bleepingcomputer.com/news/security/third-flagstar-bank-data-breach-since-2021-affects-800-000-customers/

2023-05: Maine govt notifies 1.3 million people of MOVEit data breach
https://www.bleepingcomputer.com/news/security/maine-govt-notifies-13-million-people-of-moveit-data-breach/

2023-05: Auto parts giant AutoZone warns of MOVEit data breach
https://www.bleepingcomputer.com/news/security/auto-parts-giant-autozone-warns-of-moveit-data-breach/

2023-06: Delta Dental of California data breach exposed info of 7 million people
https://www.bleepingcomputer.com/news/security/delta-dental-of-california-data-breach-exposed-info-of-7-million-people/

2023-06: MOVEIt breach impacts GenWorth, CalPERS as data for 3.2 million exposed
https://www.bleepingcomputer.com/news/security/moveit-breach-impacts-genworth-calpers-as-data-for-32-million-exposed/

2023-06: Hackers steal data of 45,000 New York City students in MOVEit breach
https://www.bleepingcomputer.com/news/security/hackers-steal-data-of-45-000-new-york-city-students-in-moveit-breach/

2023-06: Siemens Energy confirms data breach after MOVEit data-theft attack
https://www.bleepingcomputer.com/news/security/siemens-energy-confirms-data-breach-after-moveit-data-theft-attack/

2023-07: Shell Becomes Latest Cl0p MOVEit Victim
https://www.darkreading.com/attacks-breaches/shell-latest-cl0p-moveit-victim

2023-07: Radisson Hotels, major insurance firms become latest MOVEit victims to disclose breaches
https://therecord.media/radisson-hotels-major-insurance-firms-disclose-moveit-incidents

2023-07: Shutterfly says Clop ransomware attack did not impact customer data
https://www.bleepingcomputer.com/news/security/shutterfly-says-clop-ransomware-attack-did-not-impact-customer-data/

2023-07: BlackCat, Clop claim ransomware attack on cosmetics maker Estée Lauder
https://therecord.media/blackcat-clop-claim-cyberattack-on-estee-lauder

2023-07: Clop now leaks data stolen in MOVEit attacks on clearweb sites
https://www.bleepingcomputer.com/news/security/clop-now-leaks-data-stolen-in-moveit-attacks-on-clearweb-sites/

2023-07: Medical files of 8M-plus people fall into hands of Clop via MOVEit mega-bug
https://www.theregister.com/2023/07/27/maximus_deloitte_moveit_hack/

2023-07: Welltok data breach exposes data of 8.5 million US patients
https://www.bleepingcomputer.com/news/security/welltok-data-breach-exposes-data-of-85-million-us-patients/

2023-08: Clop ransomware now uses torrents to leak data and evade takedowns
https://www.bleepingcomputer.com/news/security/clop-ransomware-now-uses-torrents-to-leak-data-and-evade-takedowns/

2023-09: Johnson & Johnson discloses IBM data breach impacting patients
https://www.bleepingcomputer.com/news/security/johnson-and-johnson-discloses-ibm-data-breach-impacting-patients/

2023-09: CL0P Seeds ^_- Gotta Catch Em All!
https://unit42.paloaltonetworks.com/cl0p-group-distributes-ransomware-data-with-torrents/

2023-11: Microsoft: SysAid zero-day flaw exploited in Clop ransomware attacks
https://www.bleepingcomputer.com/news/security/microsoft-sysaid-zero-day-flaw-exploited-in-clop-ransomware-attacks/

## Reported counter operations against threat actor

2021-06: Operation “Cyclone”
Ukraine arrests Clop ransomware gang members, seizes servers
https://www.bleepingcomputer.com/news/security/ukraine-arrests-clop-ransomware-gang-members-seizes-servers/
https://www.interpol.int/News-and-Events/News/2021/INTERPOL-led-operation-takes-down-prolific-cybercrime-ring

2023-06: US govt offers $10 million bounty for info on Clop ransomware
https://www.bleepingcomputer.com/news/security/us-govt-offers-10-million-bounty-for-info-on-clop-ransomware/



