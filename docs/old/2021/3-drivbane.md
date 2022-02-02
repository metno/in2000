---
layout: default
#title: IN2000: Case 2. Farevarsler
date: 2021-02-19
author: Geir Aalberg
---

# Case 3. Søk til Havs

Bruk av drivbanesimuleringer for ting i havet

* Kontakt: Vegard Bønes
* Primære datakilder: Drifty
* Sekundære datakilder: Oceanforecast

Drifty ble bl.a. brukt hefting under Helge Ingstad-forliset. Kan brukers til å lokalisere
folk i sjøen ved redningsulykker, eller å simulere drivbaner til oljeutslipp eller store skip i havsnød.

## Ideer:

1. Berging av arbeider som faller ut fra oljeplattform. Denne må hentes opp med helikopter som flys fra land.
Eksempel på ressurser som kan brukes:

- Drifty til å simulere hvor søket bør gjøres
- Locationforecast og Nowcast for å vise vær på steder man søker
- Routeforecast for å vise værgrafer mellom flyplass og plattform

2. Oljeutslipp fra tankskip. Beregn hvor utslippet vil havne og assister båter å komme tid for opprydding.
Eksempel på ressurser som kan brukes:

- Drifty til å simulere hvor man forventer utslippet beveger seg
- Locationforecast og Nowcast for å vise vær på steder man søker
- Oceanforecast for å vise strøm- og bølgeforhold for navigasjon (fungerer best langs kysten)

Outputformat er enten bilder eller NetCDF-filer. For sistnevnte må man i Kotlin bruke
et [Java-bibliotek](https://www.unidata.ucar.edu/software/netcdf-java/) fra Unidata (har ikke testet hvordan dette fungerer sammen med Kotlin).
Vi jobber også med å få til output i GeoJSON de nærmeste ukene.

## Datakilder:

- <https://in2000.drifty.met.no/> Drifty testserver
  - Autentisering med HTTP Basic Auth, send epost til [in2000-help@met.no](mailto:in2000-help@met.no) for passord
  - Tilgjengelige objekt- og oljetyper kan finnes i <https://in2000.drifty.met.no/openapi.yaml>
- <https://opendrift.github.io/> - kildekode til Drifty
- Locationforecast, Nowcast, Oceanforecast, MetAlerts, Routeforecast fra WeatherAPI

## Eksempel:

- Kall: se [kildekode](https://opendrift.github.io/)
- Resultat: <https://in2000.drifty.met.no/api/simulation/ccaf8347-a819-438d-aa80-1ec57f6341a4/result>

## Programvare for debugging av NetCDF på PC:

- ncdump (vis data og metadata - se [eksempel](https://docs.api.met.no/doc/thredds))
- fimex (nedlasting og konvertering)
