# Threat actor: Longhorn, The Lamberts

**UUID**: aecce739-abe2-427f-8afc-78eb3b7ebd0b

**First seen**: 2009

**Source last modified**: 2022-04-04

## Threat actor aliases

Longhorn (Symantec), The Lamberts (Kaspersky), Platinum Terminal (SecureWorks), APT-C-39 (Qihoo 360)

## Description

A subgroup of the {{CIA}}.

Some operations and tooling used by this group were exposed in the {{[Vault 7/8]}} leaks on WikiLeaks in 2017.

(Symantec) Longhorn has been active since at least 2011. It has used a range of back door Trojans in addition to zero-day vulnerabilities to compromise its targets. Longhorn has infiltrated governments and internationally operating organizations, in addition to targets in the financial, telecoms, energy, aerospace, information technology, education, and natural resources sectors. All of the organizations targeted would be of interest to a nation-state attacker.

Longhorn has infected 40 targets in at least 16 countries across the Middle East, Europe, Asia, and Africa. On one occasion a computer in the United States was compromised but, following infection, an uninstaller was launched within hours, which may indicate this victim was infected unintentionally.

Longhorn’s malware appears to be specifically built for espionage-type operations, with detailed system fingerprinting, discovery, and exfiltration capabilities. The malware uses a high degree of operational security, communicating externally at only select times, with upload limits on exfiltrated data, and randomization of communication intervals—all attempts to stay under the radar during intrusions.

For C&C servers, Longhorn typically configures a specific domain and IP address combination per target. The domains appear to be registered by the attackers; however they use privacy services to hide their real identity. The IP addresses are typically owned by legitimate companies offering virtual private server (VPS) or webhosting services. The malware communicates with C&C servers over HTTPS using a custom underlying cryptographic protocol to protect communications from identification.

## Sponsor type and motivation

**Sponsor**: State-sponsored, CIA

**Motivation**: Information theft and espionage


## Country of origin

USA

## Observed attacked sectors where victims operate in

Aerospace, Aviation, Education, Energy, Financial, Government, IT, Oil and gas, Research, Telecommunications

## Observed attacked countries where victims operate in

China, 16 countries in the Middle East, Europe, Asia and Africa

## Observed usage of tools

Black Lambert, Blue Lambert, Corentry, Cyan Lambert, Gray Lambert, Green Lambert, Lambert, Magenta Lambert, Pink Lambert, Purple Lambert, Silver Lambert, Violet Lambert, White Lambert, everything in the {{[Vault 7/8]}} archives

## Reported hacking operations



## Reported counter operations against threat actor





