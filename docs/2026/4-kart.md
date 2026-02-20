---
layout: page
title: Case 4. Kart til allmenheten
parent: Årets caser
#grand_parent: Tidligere års caser
date: 2026-02-18
author: Geir Aalberg
---

## Bakgrunn


## Funksjonelle krav

### Værkart  **(obligatorisk)**

Appen skal hente kartlag fra Victoria og vise i kartklient, litt som en mini-Yr.
De mest aktuelle lagene er:

- temperatur
- nedbør
- vind (styrke og retning)

Siden værvarslene gjelder for opptil 10 dager frem, må det lages animasjoner hvor
brukeren kan styre hvilket tidspunkt som vises.

Merk at det er forskjellige modeller som brukes for hhv Norden (MEPS), Arktis (AROME) og resten
av verden (EC). De to første har dessuten kun data for de neste 60 timene, etter det
må man bruke EC-data overalt.

### Farevarsler **(obligatorisk)**

Appen skal kunne vise gyldige farevarsler som polygoner på kartet. Det er ønskelig
at dere henter farevarsler for hele Europa fra MeteoGate, men hvis dere ikke får det
til kan dere bruke MetAlerts på api.met.no.

### Punktdata

Hvis man klikker på et punkt på kartet bør man få opp en liste med været fremover i tid
samt eventuelle farevarsler.
Dere kan med fordel også implementere kartsøk på stedsnavn (bruk fx Google Maps geolocation services).

### Annen nyttig funksjonalitet

Hvis dere har ekstra tid vil vi anbefale flg funksjoner:

- Lyndata fra Frost - vis gjerne nåtidsdata, men den har også [historiske data](https://frost-rc.met.no/api/v1/lightning/get?referencetime=2025-06-04T00%3A00%3A00Z%2F2025-07-14T00%3A00%3A00Z&format=json&geometry=POLYGON%28%2810%2059%2C%2010%2060%2C%2011%2060%2C%2011%2059%2C%2010%2059%29%29)
- Historiske observasjoner fra Frost (Norge) eller MeteoGate (Europa)

## Datakilder

- [Victoria WMS](/kart/victoria.html)
- [MeteoAlarm](https://api.meteoalarm.org/edr/v1) - farevarsler for hele Europa (krever registrering)
- [MetAlerts](https://api.met.no/weatherapi/metalerts/2.0/documentation) - norske farevarsler
- [Frost](https://frost-rc.met.no/api/v1) - observasjoner for Norge (inkludert lyn)
- [MeteoGate Surface Observations API](https://observations.meteogate.eu/) - europeiske observasjoner siste 24 timer
- [MeteoGate Climate API](https://api.meteogate.eu/eu-eumetnet-climate-observations/v1) - historiske observasjoner
- [MeteoGate portal](https://meteogate.eu/) - linker til dokumentasjon

Alt fra MeteoGate/MeteoAlarm bruker [EDR-grensesnitt](/edr).