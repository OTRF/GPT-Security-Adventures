# Threat actor: Nazar

**UUID**: 7bc83157-e747-4668-ab0d-f343aead75c1

**First seen**: 2008

**Source last modified**: 2020-05-07

## Threat actor aliases

Nazar (Epic Turla), SIG37 (NSA), Iron Tiger (CrySys)

## Description

(Epic Turla) It’s hard to understand the scope of this operation without access to victimology (e.g.: endpoint visibility or command-and-control sinkholing). Additionally, some possible timestomping muddies the water between this operation possible originating in 2008-2009 or actually coming into full force in 2010-2013 (the latter dates being corroborated by VT firstseen submission times and second-stage drop timestamps). There’s a level of variable developmental capability visible throughout the stages. Multiple components are abused commonly-available resources, while the orchestrator and two of the DLL drops actually display some developmental ingenuity (in the form of seemingly novel COM techniques). Far from the most advanced coding practices but definitely better than the sort of .NET garbage other ‘Farsi-speaking’ APTs have gotten away with in the past.

Somehow, this operation found its way onto the NSA’s radar pre-2013. As far as I can tell, it’s eluded specific coverage from the security industry. A possible scenario to account for the disparate visibility between the NSA and Western researchers when it comes to this cluster of activity is that these samples were exclusively encountered on Iranian boxes overlapping with EQGRP implants. Submissions of Nazar subcomponents from Iran (as well as privately shared visibility into historical and ongoing victimology clustered entirely on Iranian machines) could support that theory. Perhaps this is an internal monitoring framework (a la Attor) but given the sparse availability of historical data, I wouldn’t push that beyond a low-confidence assessment, at this time.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

Iran

## Observed attacked sectors where victims operate in



## Observed attacked countries where victims operate in



## Observed usage of tools

Distribute.exe, EYService, GpUpdates.exe, Microolap Packet Sniffer

## Reported hacking operations



## Reported counter operations against threat actor





