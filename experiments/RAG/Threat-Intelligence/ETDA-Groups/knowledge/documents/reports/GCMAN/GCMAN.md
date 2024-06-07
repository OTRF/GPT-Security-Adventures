# Threat actor: GCMAN

**UUID**: e6eeb30a-a941-46f9-8340-20958f1d6cb0

**First seen**: 2016

**Source last modified**: 2020-04-22

## Threat actor aliases

GCMAN (Kaspersky)

## Description

(Kaspersky) A second group, which we call GCMAN because the malware is based on code compiled on the GCC compiler, emerged recently using similar techniques to the {{Corkow, Metel}} Group to infect banking institutions and attempt to transfer money to e-currency services.

The initial infection mechanism is handled by spear-phishing financial institution targets with e-mails carrying a malicious RAR archive to. Upon opening the RAR archive, an executable is started instead of a Microsoft Word document, resulting in infection.

Once inside the network, the GCMAN group uses legitimate and penetration testing tools such as Putty, VNC, and Meterpreter for lateral movement. Our investigation revealed an attack where the group then planted a cron script into bank’s server, sending financial transactions at the rate of $200 per minute. A time-based scheduler was invoking the script every minute to post new transactions directly to upstream payment processing system. This allowed the group to transfer money to multiple e-currency services without these transactions being reported to any system inside the bank.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Financial crime


## Country of origin

Russia

## Observed attacked sectors where victims operate in

Financial

## Observed attacked countries where victims operate in

Russia

## Observed usage of tools

GCMAN, Meterpreter, PuTTY, VNC, malicious RAR archives

## Reported hacking operations



## Reported counter operations against threat actor





