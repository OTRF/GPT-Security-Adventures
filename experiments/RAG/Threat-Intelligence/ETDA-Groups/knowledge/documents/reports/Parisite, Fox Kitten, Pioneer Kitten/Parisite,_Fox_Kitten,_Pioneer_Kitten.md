# Threat actor: Parisite, Fox Kitten, Pioneer Kitten

**UUID**: 9d13d133-e25a-4de0-8952-6b0cbdb92899

**First seen**: 2017

**Source last modified**: 2023-04-26

## Threat actor aliases

Parisite (Dragos), Fox Kitten (ClearSky), Pioneer Kitten (Crowdstrike), Cobalt Foxglove (SecureWorks), Rubidium (Microsoft), UNC757 (?), Lemon Sandstorm (Microsoft)

## Description

“This group has operated since at least 2017 based on infrastructure Dragos identified,” the report explained. “Parisite serves as the initial access group and enables further operations for {{APT 33, Elfin, Magnallium}}.”

(ClearSky) During the last quarter of 2019, ClearSky research team has uncovered a widespread Iranian offensive campaign which we call “Fox Kitten Campaign”; this campaign is being conducted in the last three years against dozens of companies and organizations in Israel and around the world. Though the campaign, the attackers succeeded in gaining access and persistent foothold in the networks of numerous companies and organizations from the IT,Telecommunication,Oil and Gas, Aviation, Government, and Security sectors around the world.

During our analysis, we have found an overlap, with medium-high probability, between this campaign’s infrastructure and the activity of an Iranian offensive group {{OilRig, APT 34, Helix Kitten, Chrysene}}. Additionally, we have identified, with medium probability, a connection between this campaign and the {{APT 33, Elfin, Magnallium}} and {{Chafer, APT 39}} groups.The campaign was first revealed by Dragos, named “Parisite”and attributed to APT33; we call the comprehensive campaign revealed in this report “Fox Kitten”.

The initial breach of the targeted organizations was performed, in most cases, by exploiting 1-day vulnerabilities in different VPN services such as: Pulse Secure VPN, Fortinet VPN, and Global Protect by Palo Alto Networks. Upon gaining foothold at the target, the attackers tried to maintain the access to the networks by opening a variety of communication tools, including opening RDP links over SSH tunneling, in order to camouflage and encrypt the communication with the targets. At the final stage, after successfully infiltrating the organization, the attackers have performed a routine process of identification, examination, and filtering of sensitive, valuable information from every targeted organization.The valuable information was sent back to the attackers for reconnaissance, espionage, or further infection of connected networks.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

Iran

## Observed attacked sectors where victims operate in

Aviation, Chemical, Energy, Defense, Engineering, Financial, Government, Healthcare, IT, Media, Manufacturing, Oil and gas, Retail, Telecommunications

## Observed attacked countries where victims operate in

Australia, Austria, Finland, France, Germany, Hungary, Israel, Italy, Kuwait, Lebanon, Malaysia, Poland, Saudi Arabia, UAE, USA

## Observed usage of tools

FRP, Invoke the Hash, JuicyPotato, Ngrok, Pay2Key, Port.exe, POWSSHNET, Plink, PuTTY, Serveo, SSHMinion, STSRCheck

## Reported hacking operations

2019 Late: “Fox Kitten” Campaign
https://www.clearskysec.com/wp-content/uploads/2020/02/ClearSky-Fox-Kitten-Campaign-v1.pdf

2020-07: In late July 2020, an actor assessed to be associated with PIONEER KITTEN was identified as advertising to sell access to compromised networks on an underground forum.
https://www.crowdstrike.com/blog/who-is-pioneer-kitten/

2020-09: This threat actor has been observed exploiting several publicly known Common Vulnerabilities and Exposures (CVEs) dealing with Pulse Secure virtual private network (VPN), Citrix NetScaler, and F5 vulnerabilities.
https://us-cert.cisa.gov/ncas/alerts/aa20-259a

2020-11: Pay2Kitten – Fox Kitten 2
https://www.clearskysec.com/wp-content/uploads/2020/12/Pay2Kitten.pdf

## Reported counter operations against threat actor





