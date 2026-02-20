---
layout: page
title: Case 1. Rakettoppskytning
parent: 2025
grand_parent: Tidligere års caser
date: 2024-01-26
author: Geir Aalberg
---


![Testfyring av rakett](rakett.png)

**Lag en app for planlegging av rakettoppskytninger!**
Kanskje blir det også anledning til å være med under oppskytingen mens dere
bruker appen?

## Bakgrunn

Etter et vellykket samarbeid i fjor mellom MET og rakettbyggegruppen
[PortalSpace](https://www.portalspace.no/) på UiO gjentar vi suksessen.
I fjor stakk ett av teamene med dette caset av med MET-prisen for sin
3D-visualisering av rakettbaner i kart – greier dere å gjenta bragden?

Ved en rakettoppskytning så er det mange faktorer som skal stemme, og en faktor
som vi ikke kan kontrollere er været. Derfor trenger vi kontinuerlig oppdatert
data på hvordan været kommet til å utvikle seg gjennom oppskytningsvinduet vårt.
Dette ville vanligvis vært jobben til en dedikert værstasjon, men vi ønsker å
undersøke om vi kan bruke åpen værdata til å gjøre et estimat.

## Funksjonelle krav

Se egen [kravspesifikasjon](./portalspace) for dette.

## Datakilder

### Obligatoriske datakilder

Følgende produkter skal brukes såfremt mulig. Dersom det er tekniske problemer
med å bruke en tjeneste skal det begrunnes og dokumenteres i detalj i rapporten.

- [Locationforecast](/intro) på api.met.no for bakkedata

Denne gir mye relevant data på flere av punkter under kravet, men inneholder
ikke informasjon om vindstyrke på høyder > 10 m over bakken. Til dette trenger vi et annet
API.

- [Isobarcgrib API](/api/grib) (GRIB2 for southern_norway)

Her kan man laste ned filer i GRIB2-format, som gir informasjon om vind og temperatur
på forskjellige nivåer i atmosføren. Merk at nivåene angis som trykkflater i hPa,
og at vind angis som vektor med x- og y-komponent (u og v).

For mer informasjon, se [dokumentasjon for GRIB-formatet](/api/grib).

### Andre mulige datakilder

- [Windy API](https://api.windy.com/)

har høydedata for gitte koordinater. Ved bruk, forklar i rapporten hvorfor deres
tjeneste fungerer bedre enn METs.

- [THREDDS](/thredds/) (MEPS post-processed)

Det er også mulig å laste ned
[MEPS-modelldata](https://thredds.met.no/thredds/catalog/metpplatest/catalog.html)
med høydedata direkte fra thredds.met.no, men filene er kjempestore (3+ GB) og
biblioteket for å hente data (NetCDF-Java) lar seg ikke kompilere på Android pga
manglende støtte for kryptering. Dette må i så fall løses ved å lage en
server-backend som henter og parser NetCDF-filene (eller snakker OPeNDAP med
THREDDS).

### IPPC

Dette er Avinor sitt kart over luftrommet i Norge. Det kan være vanskelig å bruke
siden det ikke finnes ett enkelt API, men man kommer langt med litt
web-scraping. Ellers henter de mange av dataene fra api.met.no.

- [https://www.ippc.no/ippc/index.jsp](https://www.ippc.no/ippc/index.jsp)

## Kontaktinformasjon / andre ressurser

- [Presentasjon fra forelesning](portalspace.pdf)
- [Portal Space nettside](https://www.portalspace.no/)
- [Instagram feed](https://www.piokok.com/profile/portalspaceno/)
- Håkon Offernes, Chief Electrical Officer, <haakono@portalspace.no>, +47 466 14 464
