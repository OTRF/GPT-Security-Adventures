# Threat actor: Tiny Spider

**UUID**: ca6c6c94-9ef8-4aa4-8d9e-ad943b9fbe23

**First seen**: 2015

**Source last modified**: 2020-04-14

## Threat actor aliases

Tiny Spider (CrowdStrike)

## Description

(ForcePoint) It all starts with the delivery of a small loader called TinyLoader, an obfuscated executable withsimple–yet powerful –downloader functionality. Upon execution, it will first brute force its own decryption key (a 32-bit value, meaning this takes a fraction of second on modern PCs) before using this to decrypt the main program code.

The core functionality of the decrypted code is communication with a set of hardcoded C2 servers by IP and port. If the C2 is active, it will provide what is effectively a piece of shellcode, encrypted by another 32-bit constant. This shellcode is not ‘fire and forget’: it instead sees the loader establish a semi-interactive two-way communication with the C2. Note that the earliest traits and mentions of TinyLoader go back to as far as 2015.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Financial crime


## Country of origin

[Unknown]

## Observed attacked sectors where victims operate in

Retail

## Observed attacked countries where victims operate in

Worldwide

## Observed usage of tools

PinkKite, PsExec, TinyPOS, TinyLoader

## Reported hacking operations

2017: A new family of point-of-sale malware, dubbed PinkKite, has been identified by researchers who say the malware is tiny in size, but can delivered a hefty blow to POS endpoints.
https://threatpost.com/new-pos-malware-pinkkite-takes-flight/130428/

## Reported counter operations against threat actor





