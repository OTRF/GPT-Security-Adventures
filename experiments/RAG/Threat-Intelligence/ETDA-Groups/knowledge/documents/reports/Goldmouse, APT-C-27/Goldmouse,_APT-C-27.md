# Threat actor: Goldmouse, APT-C-27

**UUID**: a9039e6e-531f-4b17-9c0d-ba8905ce5293

**First seen**: 2014

**Source last modified**: 2020-04-20

## Threat actor aliases

Goldmouse (Qihoo 360), Golden Rat (Qihoo 360), APT-C-27 (Qihoo 360), ATK 80 (Thales)

## Description

A subgroup of {{Syrian Electronic Army (SEA), Deadeye Jackal}}.

(Qihoo 360) On March 17, 2019, 360 Threat Intelligence Center captured a target attack sample against the Middle East by exploiting WinRAR vulnerability (CVE-2018-20250), and it seems that the attack is carried out by the Goldmouse APT group (APT-C-27). There is a decoy Word document inside the archive regarding terrorist attacks to lure the victim into decompressing. When the archive gets decompressed on the vulnerable computer, the embedded njRAT backdoor (Telegram Desktop.exe) will be extracted to the startup folder and then triggered into execution if the victim restarts the computer or performs re-login. After that, the attacker is capable to control the compromised device.

## Sponsor type and motivation

**Sponsor**: Syrian Electronic Army

**Motivation**: Information theft and espionage


## Country of origin

Syria

## Observed attacked sectors where victims operate in



## Observed attacked countries where victims operate in

Syria, Middle East

## Observed usage of tools

GoldenRAT, njRAT, a WinRAR exploit

## Reported hacking operations



## Reported counter operations against threat actor





