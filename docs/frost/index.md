---
layout: page
title: Frost
parent: Generelle ressurser
nav_order: 50
date: 2024-02-15
author: Geir Aalberg
---

Frost er et API for observasjons- og klimadata.

Frost fungerer ganske annerledes enn api.met.no.
Her kan man ikke spørre etter data for tilfeldige koordinater,
men må først finne en målestasjon som har de datatypene man ønsker for gitt periode.
Ikke alle målestasjoner har f.eks. sensor for måling av nedbør, og siden stasjoner
legges ned og nye kommer opp vil måleserier også være begrenset i tid.

For å finne stasjoner som har de data man ønsker kan det ofte være enklest
å søke de opp på [Norsk Klimaservicesenter](https://klimaservicesenter.no/).

## Versjoner

### Frost v0

- [Frost API v0](https://frost.met.no/)

Frost v0 er planlagt å utfases høsten 2026.

### Frost v1

Den nye versjonen, som i vårsemesteret 2026 er i beta er planlagt å avløse v0 senere på året.
Endringer underveis må påregnes, men vi vil forsøke å kommunisere disse i god tid.

- [Frost API v1](https://frost-rc.met.no/)

### Havvarsel-Frost

Det er også satt opp en egen instans av Frost-systemet for maritime
observasjoner kalt [Havvarsel-Frost](/havvarsel). Denne kjører en noe eldre versjon
av Frost v1 og blir ikke lenger vedlikeholdt, så vil være noen forskjeller fra
den vanlige Frost v1.

## Autentisering

Frost krever brukerregistrering ved at dere registrerer epostadresse og får
tilsendt en nøkkel som legges inn som brukernavn (HTTP Basic Auth) på alle kall.

## Presentasjoner

- [2025-02-28](frost_preso_2025-02-28.pdf) - omhandler Frost v0
