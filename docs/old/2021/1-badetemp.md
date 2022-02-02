---
layout: default
#title: IN2000: Case 1. Badetemperatur
date: 2021-02-19
author: Geir Aalberg
---

# Case 1. Badetemperatur

Lag en app som viser badetemperaturer på badeplasser langs Norskekysten.

Til våren vil det bli samlet inn "live" observasjoner fra bøyer plassert ved populære
badesteder i Oslo og omegn, og i Bergen. Observasjonene kan så hentes
fra en egen Frost-server hos Meteorologisk institutt.

Inntil bøyene legges ut så kan det gjøres testing med historiske observasjone,
for eksempel fra i fjor sommer. Ved å kombinere observasjoner med
varsler/prognoser fra api.met.no så kan det lages en rekke forskjellige
funksjonalitet rundt temaet badetemperaturer.

Vi ønsker også å tilgjengeliggjøre observasjoner som publikum sender
inn til yr.no i samarbeid med
[Reiseradioen](https://www.yr.no/nb/badetemperaturer​). Dette er noe som kanskje
blir lagt til som en ekstra datakilde på havvarsel-frost.met.no i løpet av
våren, i tillegg til flere bøyer.

## Noen ideer til inspirasjon:

 - Kart med "live" badetemperaturer plottet inn på kjente badesteder.
 - Rangering av strender etter vanntemperatur, lufttemperatur, minste forskjell i vanntemperatur og lufttemperatur osv.
 - Hvilken tid på døgnet er det mest behagelig å bade?
 - Hvor gode er varslene/prognosene fra api.met.no til å predikere
   badetemperaturer? Sammenligning av Oceanforecast-varsler og observasjoner. (Det nærmeste
   punktet som det gis varsel for ligger ofte et godt stykke ut i
   fjorden/havet, så bruk Oceanforecast 2.0 beta som automatisk "snapper" til nærmeste punkt)

## Datakilder

Primære (obligatisk):

- [Havvarsel-Frost](http://havvarsel-frost.met.no) (med observasjoner fra [Badevann.no](https://badevann.no/) og [Badetassen.no](https://badetassen.no/))
- Oceanforecast (se generelt)
- Det kan bli lagt inn flere datasett på Havvarsel-Frost-serveren i løpet av semesteret. Da vil vi i så fall oppdatere denne dokumentasjonen.

Sekundære (valgfritt):

- Locationforecast (se generelt)
- Nowcast (se generelt)
- [Oslo Kommune](https://www.oslo.kommune.no/natur-kultur-og-fritid/tur-og-friluftsliv/badeplasser-og-temperaturer/)

## Eksempler på spørring mot Havvarsel-Frost-server

Disse spørringene er laget interaktivt ved å bruke Swagger-dokumentasjonen for "/api/v1/obs/badevann/get", som er tilgjengelig på [http://havvarsel-frost.met.no/docs/apiref#/obs/badevann](http://havvarsel-frost.met.no/docs/apiref#/obs/badevann)

### Returner alle bøyer som har tidsserier i perioden 2016–2020 (uten observasjoner, kun metadata/informasjon om bøyene)

[http://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=false&buoyids=%2A&parameters=%2A](http://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=false&buoyids=%2A&parameters=%2A)

eller med `curl`:

`curl -X GET "http://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=false&buoyids=%2A&parameters=%2A" -H "accept: application/json"`

### Returner alle observasjoner gjort av bøye med ID 2 i perioden 2016–2020 (uten observasjoner, kun metadata/informasjon om bøyene)

[http://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=true&buoyids=2&parameters=%2A](http://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=true&buoyids=2&parameters=%2A)

eller med `curl`:

`curl -X GET "http://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=true&buoyids=2&parameters=%2A" -H "accept: application/json"`

## Kontakt

Havvarselprosjektet v/ [Martin Lilleeng Sætra](mailto:martinls@met.no) (for tekniske spørsmål rundt Havvarsel-Frost)

