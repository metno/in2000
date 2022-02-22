---
layout: page
title: Case 6. Åpent case
date: 2022-02-02
---

Her er det fritt valg, men forslaget bør ha godkjenning fra veileder / kursledelsen.
Alle apper må bruke minst ett av METs APIer.

Noen forslag basert på tidligere løsninger:

## Nordlysvarsel

**Lag en app som varsler om mulighetene for å se nordlys.** Dette er en ny tjeneste
på Yr som har blitt svært populær. Kan gjerne også kombineres med stjernehimmel
og lokalisering av planeter, slik et tidligere team gjorde.

Selve auroravarselet kan hentes ut fra
[NOAA](https://www.swpc.noaa.gov/products/3-day-forecast). Så må man se på
Kp-indeks og justere dette etter breddegrad (må være høyere i Oslo enn i Tromsø
for at det skal være synlig, 5 er minimum for Oslo).
Til sist må dere bruke `locationforecast` for å sjekke at det er klar himmel
uten skydekke, og `sunrise` for å vise når det er mørkt nok til å se fenomenet.

- [Locationforecast](/general) - skydekke
- [Sunrise](/general) - soloppgang og solnedgang
- [NOAA](https://www.swpc.noaa.gov/products/3-day-forecast)
- [Norwegian Centre for Space Weather (NOSWE)](https://site.uit.no/spaceweather/)

![Nordlysvarsel på Yr](/images/examples/yr-nordlys.png)

## Seiling i småbåt

**Lag en app for småbåtførere og seilere som viser vind og strøm langs kysten.**
De fleste båtførere har i dag navigasjonssystemer som viser sjøkart med
dybdeforhold og skipsleier, men disse inkluderer vanligvis ikke været.
Lag en app som viser vind- og strømforhold på sjøkart, gjerne også kombinert med
å regne ut effektiv fart og beregnet tid per distanse.

- Oceanforecast: strøm og bølger
- Locationforecast: vind og nedbør
- Sunrise: seiling i mørke krever ekstra forhåndsregler
- [OpenSeaMap](http://www.openseamap.org/index.php?id=openseamap&L=1) - frie sjøkart i WMS-format
- [Kartlag med værdata](/wms/) i WMS-format

![Eksempel fra 2020 (appen Fimafeng)](/images/examples/fimafeng.png)

## Klimastatistikk

Klimaet er i sterk forandring, noe statistikken over observasjoner tydelig viser.
Lag en app som illustrerer hvordan klimaet har endret seg de siste 50 årene basert
på observasjons- og klimadata fra Frost. Utforsk gjerne i SeKlima for å finne passende
målepunkter og tidsserier av data.

- <https://frost.met.no/>
- <http://seklima.met.no/>

![SeKlima eksempel](/images/examples/seklima.png)

[Link til graf på SeKlima](https://seklima.met.no/years/mean(air_temperature P1Y),max(air_temperature P1Y),best_estimate_sum(precipitation_amount P1Y)/custom_period/SN18701,SN18700,SN18703/nb/1980-01-01T00:00:00+01:00;2022-12-31T23:59:59+01:00)
