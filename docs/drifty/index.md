---
layout: page
title: Drifty
parent: Generelle ressurser
nav_order: 77
date: 2026-02-22
author: Geir Aalberg
---

![Drivbane illustrasjon](sphx_glr_example_depth_001.png)

Drifty er en tjeneste fra MET for drivbanesimulering, som brukes bl.a. av
redningstjenester for å se hvordan ting i havet beveger seg. Eksempler:

- oljeutslipp
- personer som har falt i sjøen
- skip i havsnød
- isfjell

Outputformat er enten bilder eller NetCDF-filer. For sistnevnte må man i Kotlin bruke
Java-biblioteket [netcdf-java](https://www.unidata.ucar.edu/software/netcdf-java/) fra Unidata.

Tjenesten krever registrering. Når vi får tilsendt oversikt fra IFI over hvilke
team som har valgt caset vil dere få tilsendt brukernavn og passord.

## Datakilder:

- <https://in2000.drifty.met.no/> Drifty testserver
  - Autentisering med HTTP Basic Auth, send epost til [Vegard Bønes](mailto:vegardb@met.no) for passord
  - Tilgjengelige objekt- og oljetyper kan finnes i <https://in2000.drifty.met.no/openapi.yaml>
- <https://opendrift.github.io/> - kildekode til Drifty

## Eksempel:

- Kall: se [kildekode](https://opendrift.github.io/)
- Resultat: <https://in2000.drifty.met.no/api/simulation/ccaf8347-a819-438d-aa80-1ec57f6341a4/result>

## Programvare for debugging av NetCDF på PC:

- ncdump (vis data og metadata - se [eksempel](https://docs.api.met.no/doc/thredds))
- fimex (nedlasting og konvertering)
