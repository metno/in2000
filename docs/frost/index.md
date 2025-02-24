---
layout: page
title: Frost
parent: Generelle ressurser
nav_order: 50
date: 2024-02-15
author: Geir Aalberg
---

## Frost v0

Frost er et API for observasjons- og klimadata:

- [Frost API](https://frost.met.no/)

Frost fungerer ganske annerledes enn api.met.no.
Her kan man ikke spørre etter data for tilfeldige koordinater,
men må først finne en målestasjon som har de datatypene man ønsker for gitt periode.
Ikke alle målestasjoner har f.eks. sensor for måling av nedbør, og siden stasjoner
legges ned og nye kommer opp vil måleserier også være begrenset i tid.

For å finne stasjoner som har de data man ønsker kan det ofte være enklest
å søke de opp på [Norsk Klimaservicesenter](https://klimaservicesenter.no/).

### Autentisering

Frost krever brukerregistrering ved at dere registrerer epostadresse og får
tilsendt en nøkkel som legges inn som brukernavn (HTTP Basic Auth) på alle kall.

## Havvarsel-Frost

Det er også satt opp en egen instans av Frost-systemet for maritime
observasjoner kalt [Havvarsel-Frost](/havvarsel), som kjører en nyere versjon av
Frost-koden (v1) som ikke er tilgjengelig på Frost ennå.
