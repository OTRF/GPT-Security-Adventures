# Threat actor: Sprite Spider, Gold Dupont

**UUID**: 20947960-7770-472c-8152-4f88a1f7ea69

**First seen**: 2015

**Source last modified**: 2022-12-27

## Threat actor aliases

Sprite Spider (CrowdStrike), Gold Dupont (SecureWorks)

## Description

(CrowdStrike) In 2020, CrowdStrike Intelligence observed both SPRITE SPIDER (the operators of Defray777) and {{Carbanak, Anunak}} (the operators of DarkSide) deploy Linux versions of their respective ransomware families on ESXi hosts during BGH operations. While ransomware for Linux has existed for many years, BGH actors have historically not targeted Linux, much less ESXi specifically. ESXi is a type of hypervisor that runs on dedicated hardware and manages multiple virtual machines (VMs). With more organizations migrating to virtualization solutions to consolidate legacy IT systems, this is a natural target for ransomware operators looking to increase the impact against a victim.

All identified incidents were enabled by the acquisition of valid credentials. In four separate Defray777 incidents, SPRITE SPIDER used administrator credentials to log in through the vCenter web interface. In one instance, SPRITE SPIDER likely used the PyXie remote access trojan (RAT) LaZagne module to harvest vCenter administrator credentials stored in a web browser.

By targeting these hosts, ransomware operators are able to quickly encrypt multiple systems with relatively few actual ransomware deployments. Encrypting one ESXi server inflicts the same amount of damage as individually deploying ransomware on each VM hosted on a given server. Consequently, targeting ESXi hosts can also improve the speed of BGH operations. Additionally, due to their lack of conventional operating systems, ESXi hosts lack endpoint protection software that could prevent or detect ransomware attacks.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Financial crime, Financial gain


## Country of origin

[Unknown]

## Observed attacked sectors where victims operate in

Education, Healthcare, Manufacturing, Technology

## Observed attacked countries where victims operate in



## Observed usage of tools

Cobalt Strike, Defray777, LaZagne, Metasploit, PyXie, SharpHound, Shifu, SystemBC, Vatet

## Reported hacking operations

2017-08: New Defray Ransomware Targets Education and Healthcare Verticals
https://www.proofpoint.com/us/blog/threat-insight/new-defray-ransomware-targets-education-and-healthcare-verticals

2020-05: Texas Courts hit by ransomware, network disabled to limit spread
https://www.bleepingcomputer.com/news/security/texas-courts-hit-by-ransomware-network-disabled-to-limit-spread/

2020-06: New Ransom X Ransomware used in Texas TxDOT cyberattack
https://www.bleepingcomputer.com/news/security/new-ransom-x-ransomware-used-in-texas-txdot-cyberattack/

2020-08: Business technology giant Konica Minolta hit by new ransomware
https://www.bleepingcomputer.com/news/security/business-technology-giant-konica-minolta-hit-by-new-ransomware/

2020-09: SoftServe hit by ransomware, Windows customization tool exploited
https://www.bleepingcomputer.com/news/security/softserve-hit-by-ransomware-windows-customization-tool-exploited/

2020-09: Leading U.S. laser developer IPG Photonics hit with ransomware
https://www.bleepingcomputer.com/news/security/leading-us-laser-developer-ipg-photonics-hit-with-ransomware/

2020-09: Government software provider Tyler Technologies hit by ransomware
https://www.bleepingcomputer.com/news/security/government-software-provider-tyler-technologies-hit-by-ransomware/

2020-10: Montreal's STM public transport system hit by ransomware attack
https://www.bleepingcomputer.com/news/security/montreals-stm-public-transport-system-hit-by-ransomware-attack/

2020-11: Brazil's court system under massive RansomExx ransomware attack
https://www.bleepingcomputer.com/news/security/brazils-court-system-under-massive-ransomexx-ransomware-attack/

2020-11: RansomExx ransomware also encrypts Linux systems
https://www.bleepingcomputer.com/news/security/ransomexx-ransomware-also-encrypts-linux-systems/

2020-12: Hackers leak data from Embraer, world's third-largest airplane maker
https://www.zdnet.com/article/hackers-leak-data-from-embraer-worlds-third-largest-airplane-maker/

2021-02: French MNH health insurance company hit by RansomExx ransomware
https://www.bleepingcomputer.com/news/security/french-mnh-health-insurance-company-hit-by-ransomexx-ransomware/

2021-02: Hypervisor Jackpotting: CARBON SPIDER and SPRITE SPIDER Target ESXi Servers With Ransomware to Maximize Impact
https://www.crowdstrike.com/blog/carbon-spider-sprite-spider-target-esxi-servers-with-ransomware/

2021-07: Ecuador's state-run CNT telco hit by RansomEXX ransomware
https://www.bleepingcomputer.com/news/security/ecuadors-state-run-cnt-telco-hit-by-ransomexx-ransomware/

2021-08: RansomEXX ransomware leaks files stolen from Italian luxury brand Zegna
https://securityaffairs.co/wordpress/120898/data-breach/ransomexx-ransomware-zegna.html

2021-08: Computer hardware giant GIGABYTE hit by RansomEXX ransomware
https://www.bleepingcomputer.com/news/security/computer-hardware-giant-gigabyte-hit-by-ransomexx-ransomware/

2021-08: Ransomware hits Lojas Renner, Brazil’s largest clothing store chain
https://therecord.media/ransomware-hits-lojas-renner-brazils-largest-clothing-store-chain/

2022-03: Ransomware group attacks Scottish mental health charity
https://therecord.media/ransomware-group-attacks-scottish-mental-health-charity/

2022-10: RansomExx Leaks 52GB of Barcelona Health Centers' Data
https://www.bankinfosecurity.com/ransomexx-leaks-52-gb-barcelona-health-centers-data-a-20260

2022-11: RansomExx Upgrades to Rust
https://securityintelligence.com/posts/ransomexx-upgrades-rust/

## Reported counter operations against threat actor





