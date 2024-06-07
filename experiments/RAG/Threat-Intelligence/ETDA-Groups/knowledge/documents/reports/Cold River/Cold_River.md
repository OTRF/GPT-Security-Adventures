# Threat actor: Cold River

**UUID**: 00b16489-daf4-4c61-90bf-0ffba2400e98

**First seen**: 2019

**Source last modified**: 2024-01-16

## Threat actor aliases

Cold River (Lastline), Nahr el bared (original place), Nahr Elbard (transliteration), Cobalt Edgewater (SecureWorks), TA446 (Proofpoint), Seaborgium (Microsoft), TAG-53 (Recorded Future), BlueCharlie (Recorded Future), Blue Callisto (PWC), Calisto (Sekoia), Star Blizzard (Microsoft)

## Description

(Lastline) While reviewing some network anomalies, we recently uncovered Cold River, a sophisticated threat actor making malicious use of DNS tunneling for command and control activities. We have been able to decode the raw traffic in command and control, find sophisticated lure documents used in the campaign, connect other previously unknown samples, and associate a number of legitimate organizations whose infrastructure is referenced and used in the campaign.

The campaign targets Middle Eastern organizations largely from the Lebanon and United Arab Emirates, though, Indian and Canadian companies with interests in those Middle Eastern countries are also targeted. There are new TTPs used in this attack – for example Agent_Drable is leveraging the Django python framework for command and control infrastructure, the technical details of which are outlined later in the blog.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

Russia

## Observed attacked sectors where victims operate in

Defense, NGOs, Think Tanks

## Observed attacked countries where victims operate in

Canada, India, Lebanon, UAE, Ukraine, USA, NATO

## Observed usage of tools

DNSpionage

## Reported hacking operations

2022-02: Blue Callisto orbits around US Laboratories in 2022
https://www.pwc.com/gx/en/issues/cybersecurity/cyber-threat-intelligence/blue-callisto-orbits-around-us.html

2022-03: COLDRIVER, a Russian-based threat actor sometimes referred to as Calisto, has launched credential phishing campaigns, targeting several US based NGOs and think tanks, the military of a Balkans country, and a Ukraine based defense contractor. However, for the first time, TAG has observed COLDRIVER campaigns targeting the military of multiple Eastern European countries, as well as a NATO Centre of Excellence.
https://blog.google/threat-analysis-group/tracking-cyber-activity-eastern-europe/

2022-04: COLDRIVER, a Russian-based threat actor sometimes referred to as Callisto, continues to use Gmail accounts to send credential phishing emails to a variety of Google and non-Google accounts.
https://blog.google/threat-analysis-group/update-on-cyber-activity-in-eastern-europe/

2022-07: Exposing TAG- 53’s Credential Harvesting Infrastructure Used for Russia-Aligned Espionage Operations
https://go.recordedfuture.com/hubfs/reports/cta-2022-1205.pdf

2022-08: Russian hackers targeted U.S. nuclear scientists
https://www.reuters.com/world/europe/russian-hackers-targeted-us-nuclear-scientists-2023-01-06/

2023-03: BlueCharlie, Previously Tracked as TAG 53, Continues to Deploy New Infrastructure in 2023
https://go.recordedfuture.com/hubfs/reports/cta-2023-0802.pdf

## Reported counter operations against threat actor

2022-08: Disrupting SEABORGIUM’s ongoing phishing operations
https://www.microsoft.com/security/blog/2022/08/15/disrupting-seaborgiums-ongoing-phishing-operations/



