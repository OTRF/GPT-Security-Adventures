# Threat actor: Hurricane Panda

**UUID**: 14545b70-34d1-4034-a41e-5533fa30be7f

**First seen**: 2013

**Source last modified**: 2020-04-14

## Threat actor aliases

Hurricane Panda (CrowdStrike)

## Description

(CrowdStrike) We have investigated their intrusions since 2013 and have been battling them nonstop over the last year at several large telecommunications and technology companies. The determination of this China-based adversary is truly impressive: they are like a dog with a bone.

Hurricane Panda’s preferred initial vector of compromise and persistence is a China Chopper webshell – a tiny and easily obfuscated 70 byte text file that consists of an ‘eval()’ command, which is then used to provide full command execution and file upload/download capabilities to the attackers. This script is typically uploaded to a web server via a SQL injection or WebDAV vulnerability, which is often trivial to uncover in a company with a large external web presence.

Once inside, the adversary immediately moves on to execution of a credential theft tool such as Mimikatz (repacked to avoid AV detection). If they are lucky to have caught an administrator who might be logged into that web server at the time, they will have gained domain administrator credentials and can now roam your network at will via ‘net use’ and ‘wmic’ commands executed through the webshell terminal.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Technology, Telecommunications

## Observed attacked countries where victims operate in



## Observed usage of tools

China Chopper, Mimikatz

## Reported hacking operations

2014-03: Operation “Poisoned Hurricane”
https://www.fireeye.com/blog/threat-research/2014/08/operation-poisoned-hurricane.html

## Reported counter operations against threat actor





