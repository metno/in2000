---
layout: page
title: Case 2. Småfly-app
parent: Årets caser
date: 2024-01-26
author: Geir Aalberg
---

Lag en app for småflypiloter i Sør-Norge!

## Bakgrunn

MET sitter på mye data som potensielt kan være av interesse for private som
driver luftsport, men har ikke oversikt over behov og ønsker. Sola Flyklubb har
sagt seg villige til å være ressurspersoner og hjelpe studentene med å lage en
app for småflypiloter, evt andre luftsportsutøvere. Vi holder også på å legge ut
GRIB-filer for Avinor for hele Sør-Norge som kanskje kan brukes på mobil (har
brukt dette selv på båt).

## Funksjonelle krav

Teamene må utrede behovet for meteorologiske data blant hobbypiloter for å
planlegge flyturer. Her spiller faktorer som vind en stor rolle for å beregne
reell fart over en strekning, men også behov for å unngå farlig vær som
cumulunimbus-skyer.

Luftfartsverket stiller også krav til at man alltid må befinne seg innen en viss
avstand fra en flyplass i tilfelle nødlanding. Dette gjør at man ofte må fly
store omveier for å komme fra A til B, og ikke kan fly lengre etapper over hav.
Det er ønskelig med funksjonalitet i appen for å beregne kortest mulig rute
under gjeldene omstendigheter (vind, dårlig vær o.l).

Oppgaven må også inkludere en rapport som beskriver behov, ønsker og
konsekvenser av at data (ikke) er tilgjengelige, men denne kan godt flere team
være med på å utforme. Her kan alle team gjerne gjøre et felles intervju med
[Sola Flyklubb](https://www.solaflyklubb.no/) så de slipper å svare på samme
spørsmål flere ganger.

Kontaktperson: [Lars Vagle](https://www.solaflyklubb.no/kontakt-oss)

## Datakilder

En av følgende atmosfæriske produkter fra MET:

- [IsobaricGRIB](/api/isobaricgrib) (GRIB2 for southern_norway)

Her kan man laste ned filer i GRIB2-format som gir informasjon om trykk på
forskjellige nivåer. Dette kan vi bruke til å finne vind på forskjellige høyder.

- [THREDDS](/thredds/) (MEPS post-processed)

Det er også mulig å laste ned
[MEPS-modelldata](https://thredds.met.no/thredds/catalog/metpplatest/catalog.html)
med høydedata direkte, men filene er svært store (3+ GB) og det er ikke trivielt
å hente subset av data vha OPeNDAP på Android.

## Andre nyttige datakilder

- [TafMetar](https://api.met.no/weatherapi/tafmetar/1.0/documentation) værvarsler for flyplasser
- [Sigmets](https://api.met.no/weatherapi/sigmets/2.0/documentation) farevarsler for flytrafikk
- [Sigcharts](https://api.met.no/weatherapi/sigcharts/2.0/documentation) værkart for flytrafikk

Se også [liknende case for 2023](/2023/4-opencase-luft) for mer inspirasjon
