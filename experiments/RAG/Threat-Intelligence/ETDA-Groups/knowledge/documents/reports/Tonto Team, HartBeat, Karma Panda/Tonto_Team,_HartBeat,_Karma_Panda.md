# Threat actor: Tonto Team, HartBeat, Karma Panda

**UUID**: 85b77804-7780-4bd9-9332-f250525122a8

**First seen**: 2009

**Source last modified**: 2023-10-12

## Threat actor aliases

Tonto Team (FireEye), HeartBeat (Trend Micro), Karma Panda (CrowdStrike), CactusPete (Kaspersky), Bronze Huntley (SecureWorks), Earth Akhlut (Trend Micro), LoneRanger (?), TAG-74 (Recorded Future)

## Description

(Trend Micro) The first HeartBeat campaign remote access tool (RAT) component was discovered in June 2012 in a Korean newspaper company network. Further investigation revealed that the campaign has been actively distributing their RAT component to their targets in 2011 and the first half of 2012. Furthermore, we uncovered one malware component that dates back to November 2009. This indicates that the campaign started during that time or earlier.

The HeartBeat campaign appears to target government organizations and institutions or communities that are in some way related to the South Korean government. Specifically, we were able to identify the following targets:

• Political parties
• Media outfits
• A national policy research institute
• A military branch of South Korean armed forces
• A small business sector organization
• Branches of South Korean government

The profile of their targets suggests that the motive behind the campaign may be politically motivated.

(Kaspersky) The actor has quite likely relied on much the same codebase and implant variants for the past six years. However these have broadened substantially since 2018. The group spear-phishes its targets, deploys Word and Equation Editor exploits and an appropriated/repackaged {{DarkHotel}} VBScript zero-day, delivers modified and compiled unique Mimikatz variants, GSEC and WCE credential stealers, a keylogger, various Escalation of Privilege exploits, various older utilities and an updated set of backdoors, and what appear to be new variants of custom downloader and backdoor modules.

## Sponsor type and motivation

**Sponsor**: State-sponsored, Shenyang Military Region Technical Reconnaissance Bureau, possibly Unit 65017

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Defense, Financial, Government, IT, Media

## Observed attacked countries where victims operate in

India, Japan, Mongolia, Russia, South Korea, Taiwan, USA, Eastern Europe

## Observed usage of tools

8.t Dropper, Bioazih, Bisonal, Dexbia, DoubleT, Flapjack, Mimikatz, ShadowPad Winnti, Living off the Land

## Reported hacking operations

2009-11: Operation “Bitter Biscuit”
https://asec.ahnlab.com/1078

2017-02: FireEye's director of cyber-espionage analysis John Hultquist told the Wall Street Journal that FireEye had detected a surge in attacks against South Korean targets from China since February, when South Korea announced it would deploy THAAD in response to North Korean missile tests.
https://arstechnica.com/information-technology/2017/04/researchers-claim-china-trying-to-hack-south-korea-missile-defense-efforts/

2019-03: CactusPete APT group’s updated Bisonal backdoor
The backdoor was used to target financial and military organizations in Eastern Europe
https://securelist.com/cactuspete-apt-groups-updated-bisonal-backdoor/97962/

2019 Late: At the end of 2019 the group seemed to shift towards a heavier focus on Mongolian and Russian organizations.
https://securelist.com/apt-trends-report-q1-2020/96826/

2019-12: In this campaign, the CactusPete threat actor used a new method to drop an updated version of the DoubleT backdoor onto the computers.
https://securelist.com/apt-trends-report-q2-2020/97937/

2020: Multi-year Chinese APT Campaign Targets South Korean Academic, Government, and Political Entities
https://go.recordedfuture.com/hubfs/reports/cta-2023-0919.pdf

2021-03: Exchange servers under siege from at least 10 APT groups
https://www.welivesecurity.com/2021/03/10/exchange-servers-under-siege-10-apt-groups/

2022-06: Nice Try Tonto Team
https://www.group-ib.com/blog/tonto-team/

2023-04: Tonto Team Using Anti-Malware Related Files for DLL Side-Loading
https://asec.ahnlab.com/en/51746/

## Reported counter operations against threat actor





