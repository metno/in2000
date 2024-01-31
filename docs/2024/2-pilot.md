---
layout: page
title: Case 2. Småflypiloter
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

## Krav

Teamene må utrede behovet for meteorologiske data blant hobbypiloter for å
planlegge flyturer. Her spiller faktorer som vind en stor rolle for å beregne
reell fart over en strekning, men også behov for å unngå farlig vær som
cumulunimbus-skyer.

Luftfartsverket stiller også krav til at man alltid må
befinne seg innen en viss avstand fra en flyplass i tilfelle nødlanding.
Dette gjør at man ofte må fly store omveier for å komme fra A til B, og ikke
kan fly lengre etapper over hav. Det er ønskelig med funksjonalitet i appen
for å beregne kortest mulig rute under gjeldene omstendigheter.

Oppgaven må også inkludere en rapport som beskriver behov, ønsker og
konsekvenser av at data (ikke) er tilgjengelige, men denne kan godt flere team
være med på å utforme. Her kan alle team gjerne gjøre et felles intervju med
Sola Flyklubb så de slipper å svare på samme spørsmål flere ganger.

[Sola Flyklubb](https://www.solaflyklubb.no/)

Kontaktperson: [Lars Vagle](https://www.solaflyklubb.no/kontakt-oss)

## Obligatoriske datakilder

En av følgende atmosfæriske produkter fra MET

- [Isobarcgrib](https://api.met.no/weatherapi/isobaricgrib/1.0/documentation) (GRIB2 for southern_norway)
- THREDDS (vanskelig å bruke direkte fra Android)
