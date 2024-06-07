# Threat actor: Pusikurac

**UUID**: e34230e0-182e-402d-a351-0479525fa0eb

**First seen**: 2019

**Source last modified**: 2020-04-29

## Threat actor aliases

Pusikurac (Morphisec)

## Description

(Morphisec) A new, highly sophisticated campaign that delivers the Orcus Remote Access Trojan is hitting victims in ongoing, targeted attacks. Morphisec identified the campaign after receiving notifications from its advanced prevention solution at several deployment sites. (Morphisec’s Moving Target Defense technology immediately stopped the threat.) The attack uses multiple advanced evasive techniques to bypass security tools. In a successful attack, the Orcus RAT can steal browser cookies and passwords, launch server stress tests (DDoS attacks), disable the webcam activity light, record microphone input, spoof file extensions, log keystrokes and more.

The forensic data captured by Morphisec from the attack showed a high correlation to additional samples in the wild, indicating a single threat actor is behind multiple campaigns, including this one.

This threat actor specifically focuses on information stealing and .NET evasion. Based on unique strings in the malware, we have dubbed the actor PUSIKURAC. Before executing the attacks, PUSIKURAC registers domains through FreeDns services. It also utilizes legitimate free text storage services like paste, signs its executables, heavily misuses commercial .NET packers and embeds payloads within video files and images.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

[Unknown]

## Observed attacked sectors where victims operate in



## Observed attacked countries where victims operate in



## Observed usage of tools

Orcus RAT

## Reported hacking operations



## Reported counter operations against threat actor





