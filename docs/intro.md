---
layout: page
title: api.met.no
parent: Generelle ressurser
nav_order: 1
date: 2024-02-15
author: Geir Aalberg
---

De fleste av METs operasjonelle data leveres via api.met.no.

## Hvordan bruke APIet

- [Betingelser for bruk av APIet](https://docs.api.met.no/doc/TermsOfService).
  Bruk IFI-proxy mot APIet så slipper dere å tenke på autentisering, throttling og `If-Modified-Since`, og vi kan spore trafikken lettere.
- [Start her](https://docs.api.met.no/doc/GettingStarted): Test ut APIet fra kommandolinjen
- [Generell bruk av APIet](https://docs.api.met.no/doc/usage): Hvordan APIet fungerer, statuskoder o.l.
- [FAQ](https://docs.api.met.no/doc/FAQ): Ofte stilte spørsmål ("hvorfor fungerer ikke...")
- [Yr Utviklerportal](https://developer.yr.no/) inneholder også mye nyttig informasjon

Kursledelsen ved IFI har satt opp en egen proxy som dere bør bruke for å
kommunisere med apiet, nærmere detaljer blir gitt på forelesning. **NB:
IFI-proxyene håndterer ikke `If-Modified-Since`.** Ignorer alt som står om dette
i Terms of Service og HOWTO. Det er heller ikke nødvendig å sette User-Agent så
lenge dere bruker IFI-proxy.

## Produkter

### Locationforecast

Globalt værvarsel i 1-times (neste to døgn) og 6-timers (3-10 døgn) intervaller.
**Vær obs på at det i overgangen mellom disse kan mangle enkelte variabler.**

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

### Subseasonal

Nytt 21-dagers varsel som nylig er lagt ut på Yr:

- [Subseasonal/1.0](https://api.met.no/weatherapi/subseasonal/1.0/documentation)
- [Datamodell](https://docs.api.met.no/doc/subseasonal/datamodel) med forklaring av variabler

### Oceanforecast

Havvarsel for Norskekysten.

- [Oceanforecast/2.0](https://api.met.no/weatherapi/oceanforecast/2.0/documentation): JSON versjon
- [Datamodell](https://docs.api.met.no/doc/oceanforecast/datamodel) med forklaring av variabler

### Tekstvarsler

Generelle tekstlige varsler for spesifiserte områder. Kan være nyttig bl.a. for opplesing.

- [Textforecast 2.0](https://api.met.no/weatherapi/textforecast/2.0/documentation) (XML)
- [Textforecast 3.0](https://api.met.no/weatherapi/textforecast/3.0/documentation) (GeoJSON - kun land og kyst, ikke hav)

### Farevarsler

Vi jobber denne våren med en ny versjon 2.0 (beta) som dere skal bruke i stedet for 1.1.

- [MetAlerts](https://api.met.no/weatherapi/metalerts/2.0/documentation)

Denne leverer data enten som XML (RSS/CAP) eller GeoJSON (beta):

#### XML

Denne leverer primært en [RSS-feed](https://api.met.no/weatherapi/metalerts/2.0/current.rss)
med linker til gjeldende varsler i CAP-format. Begge er basert på XML, så dere
trenger en parser for å kunne lese disse.

CAP-filene inneholder lat/lon-polygoner som er laget for å kunne plottes i kartløsninger.
Kombiner gjerne med simulert GPS-posisjon for å finne farevarsel på nåværende
sted. Versjon 2.0 bruker en ny
[CAP-profil](https://docs.api.met.no/doc/metalerts/CAP-v2-profile.html) som har
noen presiseringer i forhold til den forrige (dagens versjon 1.1).

#### GeoJSON

Vi jobber dessuten med en [eksperimentell versjon av
farevarsler](https://api.met.no/weatherapi/metalerts/2.0/current.json)
som pakker alt inn i GeoJSON uten at man trenger å laste ned CAP. Test gjerne
begge versjoner og gi tilbakemelding i rapporten over hvilken metode dere synes
er greiest å bruke.

#### Arkiv

Historiske varsler er tilgjengelige per måned fom januar 2020.
Siden det ikke er så mange farevarsler om våren (hovedsaklig skogbrannfare) kan
dette være nyttig for å se andre typer farevarsler som er vanlige resten av
året.

Bruk `/metalerts/2.0/archive?period=...` for å hente disse, enten som RSS eller GeoJSON.

{: .warning }
Dersom dere ønsker å bruke [farevarselikoner](https://github.com/nrkno/yr-warning-icons)
som vist på Yr må disse konverteres fra "vanlig" SVG til "Androidsk".
Dette gjøres vha et verktøy som heter "Vector Assets" i Android Studio.

### Sunrise

Viser når sol og måne går opp/ned over horisonten, samt krysser (anti)meridianen.

- [Sunrise](https://api.met.no/weatherapi/sunrise/3.0/documentation) [(dokumentasjon)](/api/sunrise)

### Luftkvalitet

Denne tjenesten viser prognoser (varsler) om luftkvalitet fram til neste dag for
de fleste områder i Norge, i motsetning til NILU som kun har faktiske observasjoner
for et sett målestasjoner.

- [AirQualityForecast](https://api.met.no/weatherapi/airqualityforecast/0.1/documentation)

### IsobaricGRIB

Nedlastningstjeneste for rasterdata for luftfart:

- [IsobaricGRIB](/api/isobaricgrib)
