# Threat actor: Sweed

**UUID**: ad9624e1-ffa9-42ca-abba-59c371e1ed53

**First seen**: 2017

**Source last modified**: 2020-04-14

## Threat actor aliases

Sweed (Talos)

## Description

(Talos) Cisco Talos recently identified a large number of ongoing malware distribution campaigns linked to a threat actor we’re calling “SWEED,” including such notable malware as Formbook, Lokibot and Agent Tesla. Based on our research, SWEED — which has been operating since at least 2017 — primarily targets their victims with stealers and remote access trojans.

SWEED remains consistent across most of their campaigns in their use of spear-phishing emails with malicious attachments. While these campaigns have featured a myriad of different types of malicious documents, the actor primarily tries to infect its victims with a packed version of Agent Tesla — an information stealer that’s been around since at least 2014. The version of Agent Tesla that SWEED is using differs slightly from what we’ve seen in the past in the way that it is packed, as well as how it infects the system. In this post, we’ll run down each campaign we’re able to connect to SWEED, and talk about some of the actor’s tactics, techniques and procedures (TTPs).

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

[Unknown]

## Observed attacked sectors where victims operate in

Defense, Energy, Financial, Shipping and Logistics, Manufacturing, Human Resources

## Observed attacked countries where victims operate in

Bosnia and Herzegovina, Canada, China, Djibouti, France, Germany, Hong Kong, India, Italy, Monaco, Russia, Qatar, Singapore, South Africa, South Korea, Switzerland, Taiwan, Turkey, UAE, UK, USA

## Observed usage of tools

Agent Tesla, Formbook, LokiBot, RDP

## Reported hacking operations

2017: Steganography
One of the earliest SWEED campaigns Talos identified dates back to 2017. In this attack, the actors placed droppers inside of ZIP archives, and then attached those ZIPs to emails. The attachments usually had file names similar to “Java_Updater.zip” or “P-O of Jun2017.zip”.

2018-01: In early 2018, we observed that SWEED began leveraging Java-based droppers. Similar to previous campaigns, the JAR was directly attached to emails and used file names such as “Order_2018.jar”. The purpose of the JAR was to obtain information about the infected system and facilitate the download of a packed version of Agent Tesla.

2018-04: In April 2018, SWEED began making use of a previously disclosed Office exploit. One of the documents featured in these email campaigns was notable because it was a PowerPoint document (PPXS). Code contained inside one of the slides triggers an exploit for CVE-2017-8759, a remote code execution vulnerability in Microsoft .NET framework.

2018-05: In May 2018, campaigns being conducted by SWEED began leveraging another vulnerability in Microsoft Office: CVE-2017-11882, a remote code execution bug in Microsoft Office that is commonly observed being leveraged in malicious documents used in commodity malware distribution.

2019: Beginning in 2019, the campaigns associated with SWEED began leveraging malicious Office macros. As with previous attacks, they are leveraging spear-phishing emails and malicious attachments to initiate the infection process.
https://blog.talosintelligence.com/2019/07/sweed-agent-tesla.html

## Reported counter operations against threat actor





