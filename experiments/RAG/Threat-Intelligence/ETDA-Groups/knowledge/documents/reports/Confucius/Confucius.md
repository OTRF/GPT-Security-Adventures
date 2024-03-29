# Threat actor: Confucius

**UUID**: 5cfcb0a9-c819-4cc2-ad43-36fe47aca3d4

**First seen**: 2013

**Source last modified**: 2022-12-30

## Threat actor aliases

Confucius (Palo Alto)

## Description

(Trend Micro) Confucius’ campaigns were reportedly active as early as 2013, abusing Yahoo! And Quora forums as part of their command-and-control (C&C) communications. We stumbled upon Confucius, likely from South Asia, while delving into Patchwork’s cyberespionage operations.

Confucius’ operations include deploying bespoke backdoors and stealing files from their victim’s systems with tailored file stealers. The stolen files are then exfiltrated by abusing a cloud service provider. Some of these file stealers specifically target files from USB devices, probably to overcome air-gapped environments.

This group seems to be associated with {{Patchwork, Dropping Elephant}}.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

India

## Observed attacked sectors where victims operate in



## Observed attacked countries where victims operate in

Azerbaijan, Bangladesh, France, India, Indonesia, Iran, Italy, Mongolia, Pakistan, Poland, Russia, Slovakia, Spain, Trinidad and Tobago, UAE, UK, Ukraine, USA, most of the South and Southeast Asian countries, most of the Middle Eastern countries and most of the African countries

## Observed usage of tools

ApacheStealer, Confucius, Hornbill, MY24, sctrls, remote-access-c3, sip_telephone, SunBird, swissknife2, Sneepy

## Reported hacking operations

2017-10: In recent weeks, Unit 42 has discovered three documents crafted to exploit the InPage program. InPage is a word processor program that supports languages such as Urdu, Persian, Pashto, and Arabic. The three InPage exploit files are linked through their use of very similar shellcode, which suggests that either the same actor is behind these attacks, or the attackers have access to a shared builder.
https://unit42.paloaltonetworks.com/unit42-recent-inpage-exploits-lead-multiple-malware-families/

2017 Late: Probing Confucius’ infrastructure, we came across websites offering Windows and Android chat applications, most likely iterations of its predecessor, Simple Chat Point: Secret Chat Point, and Tweety Chat. We are admittedly uncertain of the extent — and success — of their use, but it’s one of the ingredients of the group’s operations.
https://blog.trendmicro.com/trendlabs-security-intelligence/deciphering-confucius-cyberespionage-operations/

2018-05: During their previous campaign, we found Confucius using fake romance websites to entice victims into installing malicious Android applications. This time, the threat actor seems to have a new modus operandi, setting up two new websites and new payloads with which to compromise its targets.
https://blog.trendmicro.com/trendlabs-security-intelligence/confucius-update-new-tools-and-techniques-further-connections-with-patchwork/

2021-08: Confucius Uses Pegasus Spyware-related Lures to Target Pakistani Military
https://www.trendmicro.com/en_us/research/21/h/confucius-uses-pegasus-spyware-related-lures-to-target-pakistani.html

## Reported counter operations against threat actor





