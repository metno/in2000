---
layout: page
title: Case 2. Redd Titanic!
parent: Årets caser
#grand_parent: Tidligere års caser
date: 2026-01-30
author: Geir Aalberg
---

![Typer isfjell](https://upload.wikimedia.org/wikipedia/commons/8/8a/Iceberg_Shape.svg)

<small><a href="https://commons.wikimedia.org/wiki/File:Iceberg_Shape.svg">Romain</a>,
<a href="https://creativecommons.org/licenses/by-sa/4.0">CC BY-SA 4.0</a>, via Wikimedia Commons</small>

## Bakgrunn



## Funksjonelle krav

### Hente isfjellobservasjoner fra Iceberg








## Datakilder

### Obligatoriske

- [Iceberg](https://api.met.no/weatherapi/iceberg/0.1/documentation) - satellittobservasjoner av isfjell
- [Drifty](https://in2000.drifty.met.no/) openberg - drivbanesimuleringer (krever registrering)

### Andre kartlag

![iskant](https://victoria.met.no/wms?REQUEST=GetMap&SERVICE=WMS&VERSION=1.3.0&FORMAT=image%2Fpng&STYLES=icechart&TRANSPARENT=TRUE&TIME=2026-02-16T00%3A00%3A00Z&LAYERS=Met_Norway_Ice_Chart&WIDTH=3452&HEIGHT=1504&CRS=EPSG%3A3857&BBOX=-25144310.51397454%2C1908272.9190080315%2C17583880.838383913%2C20524495.33903906)

- [WMS iskart](https://victoria.met.no/wms?REQUEST=GetCapabilities&SERVICE=WMS&VERSION=1.3.0) (DIGER!)

Bruk LAYERS=Met_Norway_Ice_Chart og STYLES=icechart


## Kommentarer

### Beregning av dimensjoner på isfjell

Drifty krever lengde, bredde og dybde for isfjell i simuleringen, disse kan
beregnes ut fra flg variabler:

- `IA_BLN`: Maximum horizontal iceberg length in meters at waterline level
- `BRGARE`: Total iceberg area in square meters

> Ja, det er nok veldig vanskelig i praksis å måle høyde og dypgang på
> isfjell fra satellitt, og in-situ observasjoner finnes nok heller ikkje i
> nær sanntid. Men det er nok helt greit å bare anta en standard høyde (over
> vann) på feks 5 m, og tilsvarende dybde (under vann) på 50 m (typisk 10 ganger
> høyden). Evt at bruker kan overstyre dette manuelt i appen.
>
> Bredde kan man her beregne/estimere fra BRGARE / IA_BLN = 150598 / 679 = 222 m.
>
> Dimensjonene på isfjellet har ikkje veldig stor betydning på driften, men
> isfjell vil grunnstøte i modellen dersom havdyp er mindre enn isfjellets
> dybde.
>
> Drifty gir ikkje noen tydelig tilbakemelding om slik grunnstøting, og
> plottene vil bare vise at isfjellene stopper opp, men ikkje kva som er
> grunnen.
>
> Men i netCDF-fila som man kan laste ned vil man se at variabelen "moving"
> blir satt til 0 når isfjellene grunnstøter. Denne kan bli 1 igjen dersom
> tidevann hever isfjellet fra grunnen. — Knut Frode Dagestad


<!--

skalere opp staging <- ip alias in2000.drifty.met.no

brukernavn ?

geojson output ?

små filer

kontakt knut frode dagestad
- modelldata tilbake i tid? minst 2020
- hvem har laget isfjell?

icebox


- størrelse
- hele verden
- smelting?
- ma ti døgn frem i tid

default ridsskritt

4 dimensjoner

https://data.marine.copernicus.eu/product/SEAICE_ARC_SEAICE_L4_NRT_OBSERVATIONS_011_007/description

SAR Sea Ice Berg Concentration and Individual Icebergs Observed with Sentinel-1 & RCM | Copernicus Marine Service





-------------

omvendt oljedrift

-->

