# Threat actor: Indrik Spider

**UUID**: a13e6ede-eb86-499f-837e-820845da04a6

**First seen**: 2007

**Source last modified**: 2023-04-26

## Threat actor aliases

Indrik Spider (CrowdStrike), Gold Drake (SecureWorks), Gold Winter (SecureWorks), Evil Corp (self given), UNC2165 (Mandiant), DEV-0243 (Microsoft), Manatee Tempest (Microsoft)

## Description

(CrowdStrike) Indrik Spider is a sophisticated eCrime group that has been operating Dridex since June 2014. In 2015 and 2016, Dridex was one of the most prolific eCrime banking  rojans on the market and, since 2014, those efforts are thought to have netted Indrik Spider millions of dollars in criminal profits. Throughout its years of operation, Dridex has received multiple updates with new modules developed and new anti-analysis features added to the malware.

In August 2017, a new ransomware variant identified as BitPaymer was reported to have ransomed the U.K.’s National Health Service (NHS), with a high ransom demand of 53 BTC (approximately $200,000 USD). The targeting of an organization rather than individuals, and the high ransom demands, made BitPaymer stand out from other contemporary ransomware at the time. Though the encryption and ransom functionality of BitPaymer was not technically sophisticated, the malware contained multiple anti-analysis features that overlapped with Dridex. Later technical analysis of BitPaymer indicated that it had been developed by Indrik Spider, suggesting the group had expanded its criminal operation to include ransomware as a monetization strategy.

Indrik Spider appears to be a subgroup of {{TA505, Graceful Spider, Gold Evergreen}}. In 2019, a subgroup of Indrik Spider split off into {{Doppel Spider}}.

Dridex has been observed to be distributed via Necurs (operated by {{Monty Spider}}) and Emotet (operated by {{Mummy Spider, TA542}}).

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Financial crime, Financial gain


## Country of origin

Russia

## Observed attacked sectors where victims operate in

Financial, Government, Healthcare, Media

## Observed attacked countries where victims operate in

Worldwide

## Observed usage of tools

Advanced Port Scanner, Babuk Locker, BitPaymer, Cobalt Strike, Cridex, Dridex, EmpireProject, Hades, Macaw Locker, MEGAsync, Metasploit, Mimikatz, PayloadBIN, Phoenix, PowerSploit, PsExec, Raspberry Robin, SocGholish, WastedLoader, WastedLocker

## Reported hacking operations

2017-08: Several hospitals part of the NHS Lanarkshire board were hit on Friday by a version of the Bit Paymer ransomware.
The NHS Lanarkshire board includes hospitals such as Hairmyres Hospital in East Kilbride, Monklands Hospital in Airdrie and Wishaw General Hospital.
https://www.bleepingcomputer.com/news/security/bit-paymer-ransomware-hits-scottish-hospitals/

2018-07: BitPaymer Ransomware Paralyzes IT Systems of the Alaskan Town
https://socprime.com/en/news/bitpaymer-ransomware-paralyzes-it-systems-of-the-alaskan-town/

2019-01: Arizona Beverages knocked offline by ransomware attack
https://techcrunch.com/2019/04/02/arizona-beverages-ransomware/

2019-05: BitPaymer Ransomware Leveraging New Custom Packer Framework Against Targets Across the U.S.
https://blog.morphisec.com/bitpaymer-ransomware-with-new-custom-packer-framework

2019-08: Apple Zero-Day Exploited in New BitPaymer Campaign
https://blog.morphisec.com/apple-zero-day-exploited-in-bitpaymer-campaign

2019-10: Pilz, one of the world's largest producers of automation tools, has been down for more than a week after suffering a ransomware infection.
https://www.zdnet.com/article/major-german-manufacturer-still-down-a-week-after-getting-hit-by-ransomware/

2019-11: Everis, an NTT DATA company and one of Spain's largest managed service providers (MSP), had its computer systems encrypted today in a ransomware attack, just as it happened to Spain's largest radio station Cadena SER (Sociedad Española de Radiodifusión).
https://www.bleepingcomputer.com/news/security/ransomware-attacks-hit-everis-and-spains-largest-radio-network/

2020-05: WastedLocker: A New Ransomware Variant Developed By The Evil Corp Group
https://research.nccgroup.com/2020/06/23/wastedlocker-a-new-ransomware-variant-developed-by-the-evil-corp-group/

2020-07: Garmin services and production go down after ransomware attack
https://www.zdnet.com/article/garmin-services-and-production-go-down-after-ransomware-attack/

2020-12: INDRIK SPIDER Supersedes WastedLocker with Hades Ransomware to Circumvent OFAC Sanctions
https://www.crowdstrike.com/blog/hades-ransomware-successor-to-indrik-spiders-wastedlocker/

2021-03: Insurance giant CNA hit by new Phoenix CryptoLocker ransomware
https://www.bleepingcomputer.com/news/security/insurance-giant-cna-hit-by-new-phoenix-cryptolocker-ransomware/

2021-05: RIG Exploit Kit delivers WastedLoader malware
https://www.bitdefender.com/files/News/CaseStudies/study/397/Bitdefender-PR-Whitepaper-RIG-creat5362-en-EN.pdf

2021-06: New Evil Corp ransomware mimics PayloadBin gang to evade US sanctions
https://www.bleepingcomputer.com/news/security/new-evil-corp-ransomware-mimics-payloadbin-gang-to-evade-us-sanctions/

2021-09: Trucking giant Forward Air reports ransomware data breach
https://www.bleepingcomputer.com/news/security/trucking-giant-forward-air-reports-ransomware-data-breach/

2021-10: Sinclair Broadcast Hack Linked to Notorious Russian Cybergang
https://www.bloomberg.com/news/articles/2021-10-20/sinclair-broadcast-hack-linked-to-notorious-russian-cybergang

2021-10: Olympus US systems hit by cyberattack over the weekend
https://www.bleepingcomputer.com/news/security/olympus-us-systems-hit-by-cyberattack-over-the-weekend/

2021-12: Dridex malware trolls employees with fake job termination emails
https://www.bleepingcomputer.com/news/security/dridex-malware-trolls-employees-with-fake-job-termination-emails/

2021-12: Dridex Omicron phishing taunts with funeral helpline number
https://www.bleepingcomputer.com/news/security/dridex-omicron-phishing-taunts-with-funeral-helpline-number/

## Reported counter operations against threat actor

2015-10: In the fall of 2015, the Dell SecureWorks Counter Threat Unit (CTU) research team collaborated with the UK National Crime Agency (NCA), the U.S. Federal Bureau of Investigation (FBI), and the Shadowserver Foundation to take over the Dridex banking trojan.
https://www.secureworks.com/research/dridex-bugat-v5-botnet-takeover-operation

2019-12: Russian National Charged with Decade-Long Series of Hacking and Bank Fraud Offenses Resulting in Tens of Millions in Losses and Second Russian National Charged with Involvement in Deployment of “Bugat” Malware
https://www.justice.gov/opa/pr/russian-national-charged-decade-long-series-hacking-and-bank-fraud-offenses-resulting-tens

2019-12: Treasury Sanctions Evil Corp, the Russia-Based Cybercriminal Group Behind Dridex Malware
https://home.treasury.gov/news/press-releases/sm845



