---
layout: default
title: MET APIer
parent: Generelle ressurser
date: 2022-02-01
author: Geir Aalberg
---

# Introduksjon til MET sine APIer

## Bruke av api.met.no

- [Betingelser for bruk av APIet](https://docs.api.met.no/doc/TermsOfService).
  Bruk IFI-proxy mot APIet så slipper dere å tenke på autentisering, throttling og `If-Modified-Since`, og vi kan spore trafikken lettere.
- [Start her](https://docs.api.met.no/doc/GettingStarted): Test ut APIet fra kommandolinjen
- [Generell bruk av APIet](https://docs.api.met.no/doc/usage): Hvordan APIet fungerer, statuskoder o.l.
- [FAQ](https://docs.api.met.no/doc/FAQ): Ofte stilte spørsmål ("hvorfor fungerer ikke...")
- [Yr Utviklerportal](https://developer.yr.no/) inneholder også mye nyttig informasjon

**NB: IFI-proxyene håndterer ikke `If-Modified-Since`.** Ignorer alt som står om dette i Terms of Service og HOWTO.
Det er heller ikke nødvendig å sette User-Agent så lenge dere bruker IFI-proxy.

## Bruk av Frost

Frost er et API for observasjons- og klimadata, og fungerer ganske annerledes enn api.met.no,
bl.a. krever det brukerregistrering og HTTP Basic Auth, se dokumentasjonen:

- [Hvordan bruke Frost](https://frost.met.no/howto.html)

Det er også satt opp en egen instans av Frost-systemet for maritime observasjoner kalt [Havvarsel-Frost](/havvarsel),
som kjører en nyere versjon av Frost.

# Åpen datapolitikk

MET har som prinsipp at data og kode vi produserer i utgangspunktet skal være
fritt tilgjengelig og kan brukes for andre i den grad det anses som samfunnsnyttig.

- <https://www.met.no/frie-meteorologiske-data/frie-meteorologiske-data>
