# Threat actor: Rocke, Iron Group

**UUID**: bacc587d-719b-4555-bc37-db7a9455dc6a

**First seen**: 2018

**Source last modified**: 2022-12-30

## Threat actor aliases

Rocke (Talos), Iron Group (Intezer)

## Description

(Talos) This threat actor initially came to our attention in April 2018, leveraging both Western and Chinese Git repositories to deliver malware to honeypot systems vulnerable to an Apache Struts vulnerability.

In late July, we became aware that the same actor was engaged in another similar campaign. Through our investigation into this new campaign, we were able to uncover more details about the actor.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Financial gain


## Country of origin

China

## Observed attacked sectors where victims operate in



## Observed attacked countries where victims operate in



## Observed usage of tools

Godlua, Kerberods, LSD, Pro-Ocean, Xbash, several 0-day vulnerabilities

## Reported hacking operations

2018-04: This threat actor initially came to our attention in April 2018, leveraging both Western and Chinese Git repositories to deliver malware to honeypot systems vulnerable to an Apache Struts vulnerability.
https://blog.talosintelligence.com/2018/08/rocke-champion-of-monero-miners.html

2018-12: By analyzing NetFlow data from December 2018 to June 16, 2019, we found that 28.1% of the cloud environments we surveyed had at least one fully established network connection with at least one known Rocke command-and-control (C2) domain. Several of those organizations maintained near daily connections. Meanwhile, 20% of the organizations maintained hourly heartbeats consistent with Rocke tactics, techniques, and procedures (TTPs).
https://unit42.paloaltonetworks.com/rockein-the-netflow/

2019-01: Palo Alto Networks Unit 42 recently captured and investigated new samples of the Linux coin mining malware used by the Rocke group. The family was suspected to be developed by the Iron cybercrime group and it’s also associated with the Xbash malware we reported on in September of 2018. The threat actor Rocke was originally revealed by Talos in August of 2018 and many remarkable behaviors were disclosed in their blog post. The samples described in this report were collected in October of 2018, and since that time the command and control servers they use have been shut down.
https://unit42.paloaltonetworks.com/malware-used-by-rocke-group-evolves-to-evade-detection-by-cloud-security-products/

2019-05: {{Pacha Group}} Competing against Rocke Group for Cryptocurrency Mining Foothold on the Cloud
https://www.intezer.com/blog-technical-analysis-cryptocurrency-mining-war-on-the-cloud/

2019-05: Over the past month we have seen new features constantly being added to the malware. For instance, in their latest major update, they have added a function that exploits systems running the software development automation server Jenkins to increase their chance of infecting more systems, thereby generating more profits. In addition, they have also evolved their malware by adding new attack stages, as well as new redundancies in its multi-component execution to make it more dynamic and flexible.
https://www.fortinet.com/blog/threat-research/rocke-variant-ready-to-box-mining-challengers.html

2019 Summer: Rocke, a China-based cryptomining threat actor, has changed its Command and Control (C2) infrastructure away from Pastebin to a self-hosted solution during the summer of 2019.
https://www.anomali.com/blog/illicit-cryptomining-threat-actor-rocke-changes-tactics-now-more-difficult-to-detect#When:14:00:00Z

2021-01: Pro-Ocean: Rocke Group’s New Cryptojacking Malware
https://unit42.paloaltonetworks.com/pro-ocean-rocke-groups-new-cryptojacking-malware/

2021-04: Rocke Group Actively Targeting the Cloud: Wants Your SSH Keys
https://www.intezer.com/blog/cloud-security/rocke-group-actively-targeting-the-cloud-wants-your-ssh-keys/

## Reported counter operations against threat actor





