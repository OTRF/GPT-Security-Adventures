# Threat actor: PassCV

**UUID**: ffbdc428-4ee2-4402-b604-385bad6cb8ac

**First seen**: 2016

**Source last modified**: 2020-04-14

## Threat actor aliases

PassCV (Blue Coat Systems)

## Description

(Cylance) Snorre Fagerland of Blue Coat Systems first coined the term PassCV in a blog post. His post provides a good introduction to the group and covers some of the older infrastructure, stolen code-signing certificate reuse, and other connections associated with the PassCV malware. There are several clues alluding to the possibility that multiple groups may be utilizing the same stolen signing certificates, but at this time SPEAR believes the current attacks are more likely being perpetrated by a single group employing multiple publicly available Remote Administration Tools (RATs).

The PassCV group has been operating with continued success and has already started to expand their malware repertoire into different off-the-shelf RATs and custom code. SPEAR identified eighteen previously undisclosed stolen Authenticode certificates. These certificates were originally issued to companies and individuals scattered across China, Taiwan, Korea, Europe, the United States and Russia.

The PassCV group typically utilized publicly available RATs in addition to some custom code, which ultimately provided backdoor functionality to affected systems via phony resumes and curriculum vitae (CVs). PassCV continues to maintain a heavy reliance on obfuscated and signed versions of older RATs like ZxShell and Ghost RAT, which have remained a favorite of the wider Chinese criminal community since their initial public release.

## Sponsor type and motivation

**Sponsor**: State-sponsored

**Motivation**: Information theft and espionage


## Country of origin

China

## Observed attacked sectors where victims operate in

Online video game companies

## Observed attacked countries where victims operate in

China, Russia, South Korea, Taiwan, USA, Europe

## Observed usage of tools

Cobalt Strike, Excalibur, Gh0st RAT, Kitkiot, NetWire RC, Winnti, ZXShell

## Reported hacking operations



## Reported counter operations against threat actor





