---
layout: page
title: Frost
parent: Generelle ressurser
date: 2024-02-15
author: Geir Aalberg
---

## Frost v0

Frost er et API for observasjons- og klimadata, og fungerer ganske annerledes
enn api.met.no. Her kan man ikke spørre etter data for tilfeldige koordinater,
men må først finne en målestasjon med de data man ønsker for gitt periode.

- [Frost API](https://frost.met.no/)

Kursledelsen ved IFI har satt opp en egen proxy som dere bør bruke for å
kommunisere med apiet, nærmere detaljer blir gitt på forelesning.

Vanligvis krever Frost brukerregistrering og HTTP Basic Auth, men så lenge dere
bruker IFI-proxy trenger dere ikke tenke på dette.


## Havvarsel-Frost

Det er også satt opp en egen instans av Frost-systemet for maritime
observasjoner kalt [Havvarsel-Frost](/havvarsel), som kjører en nyere versjon av
Frost-koden (v1) som ikke er tilgjengelig på Frost ennå.
