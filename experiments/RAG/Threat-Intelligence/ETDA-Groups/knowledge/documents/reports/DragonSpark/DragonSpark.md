# Threat actor: DragonSpark

**UUID**: dae132d6-19c7-422d-9c36-0c71ff4aecf3

**First seen**: 2022

**Source last modified**: 2023-02-15

## Threat actor aliases

DragonSpark (SentinelLabs)

## Description

(SentinelLabs) SentinelLabs has been monitoring recent attacks against East Asian organizations we track as ‘DragonSpark’. The attacks are characterized by the use of the little known open source SparkRAT and malware that attempts to evade detection through Golang source code interpretation.

The DragonSpark attacks represent the first concrete malicious activity where we observe the consistent use of the open source SparkRAT, a relatively new occurrence on the threat landscape. SparkRAT is multi-platform, feature-rich, and frequently updated with new features, making the RAT attractive to threat actors.

The Microsoft Security Threat Intelligence team reported in late December 2022 on indications of threat actors using SparkRAT. However, we have not observed concrete evidence linking DragonSpark to the activity documented in the report by Microsoft.

We observed that the threat actor behind the DragonSpark attacks uses Golang malware that interprets embedded Golang source code at runtime as a technique for hindering static analysis and evading detection by static analysis mechanisms. This uncommon technique provides threat actors with yet another means to evade detection mechanisms by obfuscating malware implementations.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in



## Observed attacked countries where victims operate in



## Observed usage of tools

BadPotato, China Chopper, GotoHTTP, SharpToken, SparkRAT

## Reported hacking operations



## Reported counter operations against threat actor





