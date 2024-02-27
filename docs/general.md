---
layout: page
title: Generelle ressurser
has_children: true
nav_order: 2
has_toc: false
date: 2023-02-27
author: Geir Aalberg
---

## Tjenester fra MET

Disse produktene kan være nyttige for alle caser. Data fra disse utgjør størsteparten av det som vises på Yr.
Alt som ligger på api.met.no og Frost skal hentes via IFI-proxy (hvis mulig).

- [api.met.no](intro)
- [Frost](frost)
- [Havvarsel](havvarsel)
- [THREDDS](thredds)

### Terminologi

Navn på variabler og parametre er forsøkt holdt seg innenfor CF-standarden hvis mulig.
Denne er ganske omfattende, dere kan finne forklaringer på termene på
[cfconventions.org](http://cfconventions.org/Data/cf-standard-names/70/build/cf-standard-name-table.html).

### Åpen datapolitikk

MET har som prinsipp at data og kode vi produserer i utgangspunktet skal være
[fritt tilgjengelig](https://www.met.no/frie-meteorologiske-data/frie-meteorologiske-data)
og kan brukes for andre i den grad det anses som samfunnsnyttig.

## Andre dataleverandører

### Kartverket

- [Adresse-API](https://data.norge.no/dataservices/ef13b2bc-26a3-42d4-afd0-a10ed6a9fd03)

### NILU - Norsk institutt for luftforskning

- [api.nilu.no](https://api.nilu.no/) - luftkvalitetsmålinger i større byer

Se også tidligere års caser for eksempler på mer spesialiserte data.
Det oppfordres til å være kreative med å finne datakilder, da dette vil kunne
være til nytte for senere års kurs.

## Hjelpemidler

Vi anbefaler å bruke flg verktøy for utvikling:

- [GeoJSON.io](https://geojson.io/) - testing av GeoJSON output
- [GNOME Maps](https://wiki.gnome.org/Apps/Maps) for Linux kan plotte GeoJSON-filer direkte i kartet
- [QGIS](https://qgis.org/en/site/) - generell desktop app for geodata, kan lese GeoJSON (Add Layer > Vector) og GRIB (Add Layer > Mesh)

