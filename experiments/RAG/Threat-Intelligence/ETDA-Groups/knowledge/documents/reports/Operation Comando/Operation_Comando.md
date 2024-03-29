# Threat actor: Operation Comando

**UUID**: 06343cf4-1911-4cc4-8e5d-501194314650

**First seen**: 2018

**Source last modified**: 2020-04-14

## Threat actor aliases

Operation Comando (Palo Alto)

## Description

(Palo Alto) In December 2018, Palo Alto Networks Unit 42 researchers identified an ongoing campaign with a strong focus on the hospitality sector, specifically on hotel reservations. Although our initial analysis didn’t show any novel or advanced techniques, we did observe strong persistence during the campaign that triggered our curiosity.

We followed network traces and pivoted on the information left behind by this actor, such as open directories, document metadata, and binary peculiarities, which enabled us to find a custom-made piece of malware, that we named “CapturaTela”. Our discovery of this malware family shows the reason for the persistent focus on hotel reservations as a primary vector: stealing credit card information from customers.

We profiled this threat actor and that has resulted in uncovering not only their delivery mechanisms, but also their arsenal of remote access tools and info-stealing trojans, both acquired from underground forums as well as open source tools found in GitHub repositories.

## Sponsor type and motivation

**Sponsor**: 

**Motivation**: Financial crime


## Country of origin

[Unknown]

## Observed attacked sectors where victims operate in

Hospitality, specifically on hotel reservations

## Observed attacked countries where victims operate in

Brazil

## Observed usage of tools

AsyncRAT, CapturaTela, LimeRAT, NanoCore RAT, njRAT, RemcosRAT, RevengeRAT

## Reported hacking operations



## Reported counter operations against threat actor





