---
layout: page
title: Havvarsel
parent: Generelle ressurser
nav_order: 70
date: 2022-02-22
author: Martin L. Sætra
---


MET og Havforskningsinstituttet samarbeider om flere APIer med maritime data:

## Havvarsel.no

- [Havvarsel API](https://api.havvarsel.no/) - API som benyttes av bl.a. havvarsel.no

## Havvarsel-Frost

- [Havvarsel-Frost API](https://havvarsel-frost.met.no/)

Havvarsel-Frost fungerer noenlunde på samme måte som Frost, men er en nyere versjon.

Se også [presentasjonen om
Frost](https://docs.google.com/presentation/d/10iIwhAMuO-aWkndcIlYwl86kzm9b0CEeequ-Tc2viNk/edit?usp=sharing)
fra forelesning.

### Badetemperaturer

Det samles inn “live” observasjoner fra bøyer plassert ved populære badesteder
rundt omkring i hele landet. Flere aktører står for innsamlingen, men alle
observasjonene kan hentes ut fra en egen Frost-server hos Meteorologisk
institutt, som vi kaller Havvarsel-Frost.

Ved kursstart er det trolig færre “live” observasjoner som kommer inn, men utover
våren vil det komme observasjoner fra stadig flere bøyer. En del av
bøyene fungerer også hele året, slik at det vil være data tilgjengelig helt fra
begynnelsen av semesteret. I tillegg kan en teste ved å bruke historiske data,
som også er tilgjengelig fra Havvarsel-Frost. Ved å kombinere observasjoner med
varsler/prognoser fra api.met.no så kan det lages en rekke forskjellige
funksjonalitet rundt temaet badetemperaturer, men også andre typer applikasjoner
som har med hav og kyst å gjøre.

### Dokumentasjon

Spørringer til Havvarsel-Frost kan lages interaktivt ved å bruke Swagger-dokumentasjonen for
`/api/v1/obs/badevann/get`, som er tilgjengelig her:

- <https://havvarsel-frost.met.no/docs/apirefbasic#/obs%2Fbadevann/obsBadevannGet>

Se også eksempler på spørringer mot slutten av denne [presentasjonen om
Frost](https://docs.google.com/presentation/d/10iIwhAMuO-aWkndcIlYwl86kzm9b0CEeequ-Tc2viNk/edit?usp=sharing)
vist på forelesning.
