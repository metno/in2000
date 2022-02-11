---
layout: page
title: Case 4 - Badetemperaturer
date: 2022-02-09
---

Lag en app som viser badetemperaturer på badeplasser langs Norskekysten.
Det samles inn “live” observasjoner fra bøyer plassert ved populære badesteder rundt omkring i hele landet. Flere aktører står for innsamlingen, men alle observasjonene kan hentes ut fra en egen Frost-server hos Meteorologisk institutt, som vi kaller Havvarsel-Frost.

Utover våren vil det komme observasjoner fra stadig flere bøyer. En del av bøyene fungerer også hele året, slik at det vil være data tilgjengelig helt fra begynnelsen av semesteret. I tillegg kan en teste ved å bruke historiske data, som også er tilgjengelig fra Havvarsel-Frost. Ved å kombinere observasjoner med varsler/prognoser fra api.met.no så kan det lages en rekke forskjellige funksjonalitet rundt temaet badetemperaturer.

## Noen ideer til inspirasjon
 * Kart med “live” badetemperaturer plottet inn på kjente badesteder.
 * Rangering av strender etter vanntemperatur, lufttemperatur, minste forskjell i vanntemperatur og lufttemperatur osv.
 * Hvilken tid på døgnet er det mest behagelig å bade?
 * Legge til flere parametre, som for eksempel soloppgang og solnedgang, eller flo og fjære.
 * Hvor gode er varslene/prognosene fra api.met.no til å predikere badetemperaturer? Sammenligning av Oceanforecast-varsler og observasjoner.
 * Kombinere observasjoner og varsler – inkludert “nowcasting”?
 * Offshore operasjoner – mulighetsvinduer for vedlikehold osv.

## Datakilder
 Primære (obligatisk):
 * Havvarsel-Frost (observasjoner av badetemperaturer finner dere her)

Sekundære (valgfritt) – se [Generelle ressurser](../general):
 * Oceanforecast
 * Locationforecast
 * Nowcast

## Eksempler på spørring mot Havvarsel-Frost-server
Disse spørringene er laget interaktivt ved å bruke Swagger-dokumentasjonen for “/api/v1/obs/badevann/get”, som er tilgjengelig på <https://havvarsel-frost.met.no/docs/apiref#/obs/badevann>

### Returner alle bøyer som har tidsserier i perioden 2016–2020 (uten observasjoner, kun metadata/informasjon om bøyene)

<https://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=false&buoyids=%2A&parameters=%2A>

eller med curl (for testing):

curl -X GET "https://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=false&buoyids=%2A&parameters=%2A" -H "accept: application/json"

### Returner alle observasjoner gjort av bøye med ID 5 i perioden 2016–2020 fra badetassen.no

<https://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2021-12-31T23%3A59%3A59Z&incobs=true&buoyids=5&sources=badetassen%2Eno&parameters=%2A>

eller med curl (for testing):

curl -X GET "https://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2021-12-31T23%3A59%3A59Z&incobs=true&buoyids=5&sources=badetassen%2Eno&parameters=%2A" -H "accept: application/json"

## Mest relevante interessenter
Solstrand fjordhotell, Altibox (badetassen.no) og VG