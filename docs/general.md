---
layout: default
title: Generelle ressurser
date: 2021-02-19
author: Geir Aalberg
---

# Generelle ressurser

Disse produktene kan være nyttige for alle caser. Data fra disse utgjør størsteparten av det som vises på Yr.
Alt som ligger på api.met.no skal hentes via in2000-apiproxy.

**NB: IFI-proxyene håndterer ikke `If-Modified-Since`.** Ignorer alt som står om dette i Terms of Service og HOWTO.

## api.met.no

### Locationforecast

Globalt værvarsel i times (Norden neste 60 timer) og 6-timers intervaller.

- [Locationforecast/2.0](https://api.met.no/weatherapi/locationforecast/2.0/documentation). Bruk *complete* eller *compact* variant.
- [JSON dataformat](https://docs.api.met.no/doc/ForecastJSON) med
  [eksempel](https://api.met.no/weatherapi/locationforecast/2.0/complete?lat=60.10&lon=9.58)
- [Datamodell](https://docs.api.met.no/doc/locationforecast/datamodel) med forklaring av variabler
- [Locationforecast FAQ](https://docs.api.met.no/doc/locationforecast/FAQ): Ofte stilte spørsmål

### Nowcast

Værvarsel for Norge neste 15 minutter, basert på nedbørsradar og temperaturkorrigert med NetAtmo. Samme format som Locationforecast.

- [Nowcast/2.0](https://api.met.no/weatherapi/nowcast/2.0/documentation) med
  [eksempel](https://api.met.no/weatherapi/nowcast/2.0/complete?lat=59.9333&lon=10.7166)
- [Datamodell](https://docs.api.met.no/doc/nowcast/datamodel) med forklaring av variabler

### Oceanforecast

Havvarsel for Norskekysten.

- [Oceanforecast/2.0](https://api.met.no/weatherapi/oceanforecast/2.0/documentation): JSON versjon
- [Datamodell](https://docs.api.met.no/doc/oceanforecast/datamodel) med forklaring av variabler

### Farevarsler

- [MetAlerts](https://api.met.no/weatherapi/metalerts/1.1/documentation)

Denne leverer en [RSS-feed](https://api.met.no/weatherapi/metalerts/1.1/)
med linker til gjeldende varsler i CAP-format (XML).

CAP-filene inneholder lat/lon-polygoner som er laget for å kunne plottes i kartløsninger.
Kombiner gjerne med simulert GPS-posisjon for å finne farevarsel på nåværende
sted.

Historiske varsler er tilgjengelige per måned fom januar 2020. Bruk disse for å
vise sesongvariable varsler som er relevante for appen.

### Sunrise

Viser når sol og måne går opp/ned over horisonten. Kan også vise avanserte astronomiske
posisjoner for beregning av horoskop(!). Data leveres som XML eller JSON.

- [Sunrise API](https://api.met.no/weatherapi/sunrise/2.0/documentation)

### Luftkvalitet

- [AirQualityForecast](https://api.met.no/weatherapi/airqualityforecast/0.1/documentation)

## Frost

Eget API for observasjoner og klimadata fra MET

- [Frost API](https://frost.met.no/) - krever registrering og HTTP Basic Auth

For Frost er det satt opp en egen proxy dersom dere ønsker å bruke denne.

## Havvarsel-Frost

- [Havvarsel-Frost API](https://havvarsel-frost.met.no/)

Havvarsel-Frost fungerer noenlunde på samme måte som Frost, men er en nyere versjon.
Det er ikke nødvendig å bruke proxy for Havvarsel-Frost.

For eksempler på bruk av Havvarsel-Frost, se [egen side](/havvarsel/).

## THREDDS

- [Eksempler på bruk av THREDDS](/thredds/)
- [thredds.met.no](https://thredds.met.no/)
