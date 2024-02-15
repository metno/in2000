---
layout: page
title: IsobaricGRIB
parent: Generelle ressurser
nav_order: 2
date: 2024-02-15
author: Geir Aalberg
---

GRIB er et format for å laste ned rasterdata, som er mye brukt innen meteorologi.
APIet leverer GRIB-filer både for luftfart og for ferdsel til sjøs.

- [Isobarcgrib](https://api.met.no/weatherapi/isobaricgrib/1.0/documentation)

Her kan man laste ned filer i GRIB1- (Europa) og GRIB2-format (Sør-Norge), som
gir informasjon om vind og temperatur på forskjellige nivåer i atmosføren.
Det er hovedsaklig GRIB2 som er av interesse siden GRIB1 har svært lav oppløsning.

## Parsing av data

Det finnes en rekke [GRIB-parsere for Java](https://github.com/search?q=grib2+language%3AJava&type=repositories&l=Java)
som potensielt burde kunne brukes til å parse GRIB2. Dog leverer IsobaricGRIB
filer på ca 1.3 MB, som kanskje er tungvint å lese inn i i en mobilapp. I såfall
er det mulig å bruke en backend-server for lesing/parsing som leverer data til appen.

MET har laget et open source Python-basert API som laster ned IsobaricGRIB-filer
fra apiet og leverer en vertikalprofil som CoverageJSON for et gitt punkt.
Koden kan være nyttig å lese for å finne ut hvordan man skal tolke dataene.
Dersom dere bruker denne får dere også litt trening i å bruke [EDR](/edr):

- <https://github.com/metno/edrisobaric> - kildekode i Python

## Beregning av høyde

I filene angis ikke høyde i meter men i trykkflater (isobarer), siden flyenes
høydemåler baserer seg på trykk og man flyr langs trykkflater i stedet for
på fast høyde over havet.

For å [regne ut](https://physics.stackexchange.com/questions/333475/how-to-calculate-altitude-from-current-temperature-and-pressure)
høyde over havet kan man bruke [den hydrostatiske
ligningen](https://en.wikipedia.org/wiki/Barometric_formula)
ut fra flg kjente variabler:

- trykk i høyden (GRIB)
- temperatur i høyden (GRIB)
- lufttrykk ved havnivå (locationforecast)
- (geopotensialet?)
