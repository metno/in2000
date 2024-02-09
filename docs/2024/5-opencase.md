---
layout: page
title: Case 5. Åpent case
parent: Årets caser
date: 2024-01-26
author: Geir Aalberg
---



Samme hva, men må bruke en eller flere fra en liste av apier.


Ellers er vi i gang med å implementere OGC API EDR, som er en ny standard for
søking i geodata. Selve standarden er nesten uleselig og vanskelig å
implementere, men vi har håp om at å konsumere data skal være relativt lett. Vi
ønsker derfor å stille som krav at studentene må bruke EDR alle steder hvor det
er tilgjengelig, inkl api.met.no når dette er klart. I praksis vil det kun bety
noe annerledes URLer, fx

locationforecast/edr/collections/complete/location?coord=POINT(60+10)

i stedet for

locationforecast/complete?lat=60&lon=10



- [Tilgjengelige produkter med EDR](https://api.met.no/swagger2-ui/index.html)


<https://www.ogc.org/standard/ogcapi-edr/>

