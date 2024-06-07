# Threat actor: Chimera

**UUID**: 1b8fc69c-574a-4c14-9603-0c3a0de08b6f

**First seen**: 2018

**Source last modified**: 2023-11-30

## Threat actor aliases

Chimera (CyCraft)

## Description

(CyCraft) For nearly two years, our team monitored several attacks that targeted Taiwan’s semiconductor vendors. We believe these attacks originated from the same threat actor – Chimera – as  these attacks utilized similar tactics, techniques and even the same customized malware. The actor likely harvested various valid credentials via phishing emails or data breaches as their starting point to conduct their cyber attack on the vendors. Cobalt Strike was later used as their main RAT tool. To avoid detection, the Cobalt Strike RAT was often masqueraded as a Google Chrome Update. The RAT would then connect back to their C2 server. As these servers were in a public cloud server, it made it difficult to track. Subsequently, by compromising the AD server, the delicate malware – SkeletonKeyInjector – was invoked to implant a general key to allow LM, persistence and defense evasion. Although this malware was discovered for the first time, we have high confidence that these attacks were conducted by the same threat actor. Based on the stolen data, we infer that the actor’s goal was to harvest company trade secrets. The motive may be related to business competition or a country’s industrial strategy.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Aviation, High-Tech

## Observed attacked countries where victims operate in

Netherlands, Taiwan, different geographical areas

## Observed usage of tools

Cobalt Strike, SkeletonKeyInjector

## Reported hacking operations

2017 Late: Hackers spent 2+ years looting secrets of chipmaker NXP before being detected
https://arstechnica.com/security/2023/11/hackers-spent-2-years-looting-secrets-of-chipmaker-nxp-before-being-detected/

2018 Late: Operation “Skeleton Key”
https://cycraft.com/download/%5BTLP-White%5D20200415%20Chimera_V4.1.pdf

2019-10: NCC Group and Fox-IT have been tracking a threat group with a wide set of interests, from intellectual property (IP) from victims in the semiconductors industry through to passenger data from the airline industry.
https://blog.fox-it.com/2021/01/12/abusing-cloud-services-to-fly-under-the-radar/

## Reported counter operations against threat actor





