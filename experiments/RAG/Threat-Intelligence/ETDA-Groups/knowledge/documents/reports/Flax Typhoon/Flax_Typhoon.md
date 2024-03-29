# Threat actor: Flax Typhoon

**UUID**: 653faab6-7686-4258-82ce-691c8c539a8b

**First seen**: 2021

**Source last modified**: 2023-09-06

## Threat actor aliases

Flax Typhoon (Microsoft), Ethereal Panda (CrowdStrike)

## Description

(Microsoft) Flax Typhoon has been active since mid-2021 and has targeted government agencies and education, critical manufacturing, and information technology organizations in Taiwan. Some victims have also been observed elsewhere in Southeast Asia, as well as in North America and Africa. Flax Typhoon focuses on persistence, lateral movement, and credential access. As with any observed nation-state actor activity, Microsoft has directly notified targeted or compromised customers, providing them with important information needed to secure their environments.

Flax Typhoon is known to use the China Chopper web shell, Metasploit, Juicy Potato privilege escalation tool, Mimikatz, and SoftEther virtual private network (VPN) client. However, Flax Typhoon primarily relies on living-off-the-land techniques and hands-on-keyboard activity. Flax Typhoon achieves initial access by exploiting known vulnerabilities in public-facing servers and deploying web shells like China Chopper. Following initial access, Flax Typhoon uses command-line tools to first establish persistent access over the remote desktop protocol, then deploy a VPN connection to actor-controlled network infrastructure, and finally collect credentials from compromised systems. Flax Typhoon further uses this VPN access to scan for vulnerabilities on targeted systems and organizations from the compromised systems.

## Sponsor type and motivation

**Sponsor**: State-sponsored

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Education, Government, IT, Manufacturing

## Observed attacked countries where victims operate in

Taiwan, Southeast Asia, North America and Africa

## Observed usage of tools

China Chopper, BadPotato, JuicyPotato, Metasploit, Mimikatz, SoftEther VPN, Living off the Land

## Reported hacking operations



## Reported counter operations against threat actor





