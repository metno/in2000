---
layout: page
title: Case 1. Rakettoppskytning
parent: Årets caser
#grand_parent: Tidligere års caser
date: 2025-01-26
author: Geir Aalberg
---

**Lag en app for planlegging av rakettoppskytninger!**
Kanskje blir det også anledning til å være med under oppskytingen mens dere
bruker appen?


## Funksjonelle krav

### Beregne bane vha Interpol




### Beregne bane fra vilkårlig sted vha IsobaricGRIB




## Datakilder

### Interpol (obligatorisk)

Interpol er et produkt som bl.a. er utviklet for Andøya Spaceport.
Tjenesten har et [EDR-grensesnitt](/edr/), hvor hver modellkjøring
legges ut som en egen instans. Det kjøres nye simuleringer hver tredje time,
og man kan finne kjøringer for tre dager tilbake. Det er normalt ingen grunn
til å bruke annet enn den nyeste (siste i listen).

- <https://interpol.met.no/collections/meps-det-vertical/instances> - liste over modellkjøringer
- <https://interpol.met.no/collections/meps-det-vdiv/instances/2026-02-20T06:00Z/locations/andoya> - eksempel for Andøya

### IsobaricGRIB

