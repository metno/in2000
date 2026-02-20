---
layout: page
title: EDR
parent: Generelle ressurser
nav_order: 90
date: 2024-02-15
author: Geir Aalberg
---

En nye standard som holder på å etablere seg innen geofag er **Environmental
Data Retrieval** fra [OGC](https://www.ogc.org/). Dette er en del av et sett av
tilhørende standarder kalt [OGC API](https://ogcapi.ogc.org/), hvorav EDR er
spesielt beregnet for søk i geodata med standardiserte spørringer for tid og sted.
Som offentlig institutt er vi derfor pålagt
å implementere denne på bakgrunn av EUs
[INSPIRE-direktiv](https://knowledge-base.inspire.ec.europa.eu/legislation/inspire-directive_en).

En EDR-tjeneste er [REST-basert](https://en.wikipedia.org/wiki/REST) og tilbyr
forskjellige datasett kalt `/collections`. Det hvor man produserer mange forskjellige
varianter av én type data for samme tid og sted (typisk repeterende simuleringer)
kan hver av disse listes opp som egne instanser under `/collections/CCC/instance`.

Enten man bruker en instans eller går direkte mot en collection kan man bruke
flere typer metoder for spørring, avhengig av hva tjenesten tilbyr. For alt annet
enn locations må man angi koordinater på [WKT-format](https://en.wikipedia.org/wiki/Well-known_text_representation_of_geometry).
Noen eksempler:

- **locations** - navngitte lokasjoner (`/locations/andoya`)
- **position** - lengde/breddegrad og høyde (`/position?coords=POINT(10.72 59.9423)&z=91` - Blindern)
- **area** - område som polygon (`/area?coords=POLYGON((20.82 61.46,25.83 61.73,30.62 61.56,28.08 60.08,24.96 59.86,22.36 59.73,20.91 60.58,20.82 61.46))` - sørlige Finland)
- **cube** - bounding box og høyde (`/cube?bbox=5.0,52.0,6.0,52.1&z=1000/..` - luftrommet over sentrale Nederland 1000 moh)

For å se hvilke metoder som støttes av en collection må man se på `data_queries`
i responsen.

Dersom tjenesten støtter det kan man også avgrense spørringer i tid:

- `?datetime=2026-02-20T11:00:00Z`
- `?datetime=2026-02-17T11:00:00Z/2026-02-20T11:00:00Z`

Eller filtrere output på en eller flere parametre:

- `?parameter-name=air_temperature:0:mean:-P1M`
- `?parameter-name=surface_snow_thickness:0:point:PT0S,precipitation_amount:2:sum:-PT1H`

Dette eksemplet henter månedlig middeltemperatur for Blindern mellom 1935 og 1956 (da stasjonen var i drift)

- <https://frost-rc.met.no/edr/collections/observations/locations/0-20000-0-01492?parameter-name=air_temperature:0:mean:-P1M>

Nedbør per time for Majavatn for siste tre dager (da teksten ble skrevet):

- <https://frost-rc.met.no/edr/collections/observations/locations/0-20000-0-01132?parameter-name=precipitation_amount:2:sum:-PT1H&datetime=2026-02-17T00:00:00Z/2026-02-20T00:00:00Z>

## Standarder

- [Innføring i EDR](https://opengeospatial.github.io/e-learning/ogcapi-edr/text/basic-main.html)
- [EDR spesifikasjon](https://www.ogc.org/standard/ogcapi-edr/)

## EDR-tjenester hos MET

- [interpol](https://interpol-b.met.no/) - diverse værvarsler
- [SWiM](https://aviation.met.no/) - SIGMET, AIRMET og TAF for flytrafikk
- [EDRisobaric](https://edrisobaric.k8s.met.no/) - EDR-server for flyværdata med [kildekode](https://github.com/metno/edrisobaric)
- [Frost v1](https://frost-rc.met.no/edr/collections/observations) - EDR-grensesnitt for observasjoner

## Testverktøy

- [EDR browser](https://ogcbrowser.rauhala.app/) fra Mikko Rauhala på FMI
- [Kartklient](https://labs.metoffice.gov.uk/edr/static/html/query.html) fra UK Met Office
