# Threat actor: Operation Domino, Operation Kremlin

**UUID**: 99a751ba-5585-44b1-b9d3-993fc2ddc8fc

**First seen**: 2019

**Source last modified**: 2021-01-20

## Threat actor aliases

Operation Domino (Hunting Shadow Lab), Operation Kremlin (Clearsky)

## Description

(Clearsky) ClearSky researchers identified a malicious “.docx” file that was uploaded to VirusTotal from Russia in mid-December. The file contains an obfuscated URL to a remote template which contains malicious VBA, eventually leading to the execution of VBS on the infected machine. The attack’s purpose is to stealthily exfiltrate information without running any external executables on the system.

Notably, the process is escalated on a certain day of the week, suggesting a possible familiarity with the intended victim or victims.

We estimate with medium confidence that the same threat actor responsible for the attacks described in this paper also conducted an attack named “Operation Domino” that occurred earlier in 2020.

We decided to name the operation “Kremlin” due to the use of a parameter named “kreml” in the “poslai” (meaning send in Russian) function that exfiltrates the data.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

Russia

## Observed attacked sectors where victims operate in



## Observed attacked countries where victims operate in

Belarus

## Observed usage of tools



## Reported hacking operations

2020-09: Operation “Domino”
https://ti.dbappsecurity.com.cn/blog/index.php/2020/09/18/operation-domino/

2020-12: Operation “Kremlin”
https://www.clearskysec.com/operation-kremlin/

## Reported counter operations against threat actor





