# Threat actor: WIP26

**UUID**: 3561e787-a13e-4191-83c1-86d37fb63412

**First seen**: 2022

**Source last modified**: 2023-02-17

## Threat actor aliases

WIP26 (SentinelLabs)

## Description

(SentinelLabs) In collaboration with QGroup GmbH, SentinelLabs is monitoring a threat activity we track as WIP26. The threat actor behind WIP26 has been targeting telecommunication providers in the Middle East. WIP26 is characterized by the abuse of public Cloud infrastructure – Microsoft 365 Mail, Microsoft Azure, Google Firebase, and Dropbox – for malware delivery, data exfiltration, and C2 purposes.

The WIP26 activity is initiated by precision targeting of employees through WhatsApp messages that contain Dropbox links to a malware loader. Tricking employees into downloading and executing the loader ultimately leads to the deployment of backdoors that leverage Microsoft 365 Mail and Google Firebase instances as C2 servers. We refer to these backdoors as CMD365 and CMDEmber, respectively. The main functionality of CMD365 and CMDEmber is to execute attacker-provided system commands using the Windows command interpreter.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

[Unknown]

## Observed attacked sectors where victims operate in

Telecommunications

## Observed attacked countries where victims operate in

Middle East

## Observed usage of tools

CMD365, CMDEmber

## Reported hacking operations



## Reported counter operations against threat actor





