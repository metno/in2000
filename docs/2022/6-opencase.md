---
layout: page
title: Case 6. Åpent case
date: 2022-02-02
---

Her er noen forslag til mulige apper:


## Nordlysvarsel

**Lag en app som varsler om mulighetene for å se nordlys.** Dette er en ny tjeneste
på Yr som har blitt svært populær.

Selve varselet kan hentes ut fra
[NOAA](https://www.swpc.noaa.gov/products/3-day-forecast). Så må man se på
Kp-tallet og justere dette etter breddegrad (må være høyere i Oslo enn i Tromsø
for at det skal være synlig). Til sist må dere bruke `locationforecast` for å
sjekke at det er klar himmel uten skydekke, og `sunrise` for å vise når det er
mørkt nok til å se fenomenet.
Kan gjerne også kombineres med stjernehimmel og lokalisering av planeter, slik
et tidligere team gjorde.


## Seiling i småbåt

- `oceanforecast`: strøm- og bølgeforhold
- `locationforecast`: vind og nedbør
- `sunrise`: seiling i mørke krever ekstra forhåndsregler


## Klimastatistikk

- <frost.met.no>