# Threat actor: Operation Red Signature

**UUID**: b097cbfd-9d8d-4899-9e51-c3d673cdd74d

**First seen**: 2018

**Source last modified**: 2020-04-29

## Threat actor aliases

Operation Red Signature (Trend Micro)

## Description

(Trend Micro) Together with our colleagues at IssueMakersLab, we uncovered Operation Red Signature, an information theft-driven supply chain attack targeting organizations in South Korea. We discovered the attacks around the end of July, while the media reported the attack in South Korea on August 6.

The threat actors compromised the update server of a remote support solutions provider to deliver a remote access tool called 9002 RAT to their targets of interest through the update process. They carried this out by first stealing the company’s certificate then using it to sign the malware. They also configured the update server to only deliver malicious files if the client is located in the range of IP addresses of their target organizations.

9002 RAT also installed additional malicious tools: an exploit tool for Internet Information Services (IIS) 6 WebDav (exploiting CVE-2017-7269) and an SQL database password dumper. These tools hint at how the attackers are also after data stored in their target’s web server and database.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in



## Observed attacked countries where victims operate in

South Korea

## Observed usage of tools

9002 RAT

## Reported hacking operations



## Reported counter operations against threat actor





