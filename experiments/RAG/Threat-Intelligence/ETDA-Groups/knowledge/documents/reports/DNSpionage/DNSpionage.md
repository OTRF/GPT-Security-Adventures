# Threat actor: DNSpionage

**UUID**: bada63ae-9429-4f84-b141-2970799ac9d5

**First seen**: 2019

**Source last modified**: 2020-04-15

## Threat actor aliases

DNSpionage (Talos)

## Description

(Talos) Cisco Talos recently discovered a new campaign targeting Lebanon and the United Arab Emirates (UAE) affecting .gov domains, as well as a private Lebanese airline company. Based on our research, it’s clear that this adversary spent time understanding the victims’ network infrastructure in order to remain under the radar and act as inconspicuous as possible during their attacks.

Based on this actor’s infrastructure and TTPs, we haven’t been able to connect them with any other campaign or actor that’s been observed recently. This particular campaign utilizes two fake, malicious websites containing job postings that are used to compromise targets via malicious Microsoft Office documents with embedded macros. The malware utilized by this actor, which we are calling “DNSpionage,” supports HTTP and DNS communication with the attackers.

Talos found a possible relationship between DNSpionage and {{OilRig, APT 34, Helix Kitten, Chrysene}}.

## Sponsor type and motivation

**Sponsor**: State-sponsored

**Motivation**: Information theft and espionage


## Country of origin

Iran

## Observed attacked sectors where victims operate in

Aviation, Government, Law enforcement, Telecommunications, Internet infrastructure

## Observed attacked countries where victims operate in

Albania, Cyprus, Egypt, Iraq, Jordan, Kuwait, Lebanon, Libya, Sweden, UAE, USA, North Africa

## Observed usage of tools

DNSpionage, Karkoff

## Reported hacking operations

2019-04: DNSpionage brings out the Karkoff
https://blog.talosintelligence.com/2019/04/dnspionage-brings-out-karkoff.html

## Reported counter operations against threat actor





