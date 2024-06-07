# Threat actor: LookBack, TA410

**UUID**: 0cd75659-1c39-4647-8781-3e65d79f2cd5

**First seen**: 2019

**Source last modified**: 2023-11-29

## Threat actor aliases

LookBack (Proofpoint), TA410 (Proofpoint), Witchetty (Symantec), LookingFrog (ESET), FlowingFrog (ESET)

## Description

(Proofpoint) Between July 19 and July 25, 2019, several spear phishing emails were identified targeting three US companies in the utilities sector. The phishing emails appeared to impersonate a US-based engineering licensing board with emails originating from what appears to be an actor-controlled domain, nceess[.]com. Nceess[.]com is believed to be an impersonation of a domain owned by the US National Council of Examiners for Engineering and Surveying. The emails contain a malicious Microsoft Word attachment that uses macros to install and run malware that Proofpoint researchers have dubbed “LookBack.” This malware consists of a remote access Trojan (RAT) module and a proxy mechanism used for command and control (C&C) communication.  We believe this may be the work of a state-sponsored APT actor based on overlaps with historical campaigns and macros utilized. The utilization of this distinct delivery methodology coupled with unique LookBack malware highlights the continuing threats posed by sophisticated adversaries to utilities systems and critical infrastructure providers.

Proofpoint found similarities in malware delivery with {{Stone Panda, APT 10, menuPass}}, but those may have been false flags.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

[Unknown]

## Observed attacked sectors where victims operate in

Energy, Utilities

## Observed attacked countries where victims operate in

USA, Middle East and Africa

## Observed usage of tools

FlowCloud, GUP Proxy Tool, SodomMain, SodomNormal

## Reported hacking operations

2019-07: At the same time as the LookBack campaigns, Proofpoint researchers identified a new, additional malware family named FlowCloud that was also being delivered to U.S. utilities providers.
https://www.proofpoint.com/us/blog/threat-insight/ta410-group-behind-lookback-attacks-against-us-utilities-sector-returns-new

2019-08: LookBack Forges Ahead: Continued Targeting of the United States’ Utilities Sector Reveals Additional Adversary TTPs
https://www.proofpoint.com/us/threat-insight/post/lookback-forges-ahead-continued-targeting-united-states-utilities-sector-reveals

2022-02: Witchetty: Group Uses Updated Toolset in Attacks on Governments in Middle East
https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/witchetty-steganography-espionage

## Reported counter operations against threat actor





