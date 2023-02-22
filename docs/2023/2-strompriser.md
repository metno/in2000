---
layout: page
title: Case 2. Strømpriskalkulator
date: 2022-02-02
---

Strømpriser er et aktuelt tema om dagen, og mange lurer på hvordan de kan spare
på bruken av strøm. Denne er naturlig nok delvis avhengig av været for oppvarming.
Det kan derfor være interessant forutsi hvordan strømforbruket og -prisen vil variere
etterhvert som været forandrer seg de neste dagene. Man kan også forsøke å finne
en sammenheng mellom historisk vær og tidligere priser.

Noen aktuelle datakilder:

- Locationforecast [API](/general) - værvarsel
- Frost [API](/general) - observasjoner, målinger og klimastatistikk
- [SeKlima](http://seklima.met.no/) - utforsk Frost-databasen og plot tidsserier

- [Hva Koster Strømmen](https://www.hvakosterstrommen.no/strompris-api) - gratis strømpris API
- [Nettleie API](https://data.norge.no/dataservices/937a0466-3f12-3219-8552-18689cf8d606)

![SeKlima eksempel](/images/examples/seklima.png)
[Link til graf på SeKlima](https://seklima.met.no/years/mean(air_temperature P1Y),max(air_temperature P1Y),best_estimate_sum(precipitation_amount P1Y)/custom_period/SN18701,SN18700,SN18703/nb/1980-01-01T00:00:00+01:00;2022-12-31T23:59:59+01:00)
