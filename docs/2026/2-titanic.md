---
layout: page
title: Case 2. Redd Titanic!
parent: Årets caser
#grand_parent: Tidligere års caser
date: 2026-01-30
author: Geir Aalberg
---

![Willy Stöwer: Der Untergang der "Titanic"](titanic.jpg)


## Bakgrunn

Isfjell har alltid utgjort en fare for skipstrafikk i nordlige strøk, og med
global oppvarming øker bare antallet isfjell. For skipstrafikk i Arktis er det
viktig å kunne unngå disse, derfor har MET laget en tjeneste kalt
[Drifty](/drifty/) som bl.a. simulerer hvordan isfjell beveger seg gitt rådende
forhold som strøm og vind på havet. I tillegg har vi et api som formidler
satellittobservasjoner av isfjell fra [Copernicus Marine
Service](https://marine.copernicus.eu/).

## Funksjonelle krav

### 1. Plotte skipskurs

Man bør kunne legge inn punkter på kartet og beregne tidspunkt for når man
ankommer hvert veipunkt. Et containerskip bruker typisk 10-20 dager på å krysse
Atlanteren. Merk at en skipskurs utgjør en
[storsirkel](https://no.wikipedia.org/wiki/Storsirkel) på havoverflaten, noe som
ikke alltid utgjør en rett linje på mange kart. Fordelen med
[Mercator-projeksjon](https://en.wikipedia.org/wiki/Mercator_projection) er
at storsirkler her vises som rette linjer, men til gjengjeld blir avstander
forvrengte jo lenger man kommer mot polene. Dere må derfor bruke
[Haversines formel](https://www.w3tutorials.net/blog/calculate-distance-between-two-latitude-longitude-points-haversine-formula/)
for å beregne distansen mellom hvert veipunkt.

Siden vi forutsetter at det ikke er snakk om isbrytere må man også holde avstand
til polarisen. Her kan dere fx hente kart fra [Victoria](/kart/victoria) – bruk
kartlaget `Met_Norway_Ice_Chart`.

Hvis dere ønsker kan dere også korrigere farten vha strømprognose i
Oceanforecast, men det er ikke noe krav siden den ikke har historiske data.

### 2. Hente isfjellobservasjoner fra Iceberg

Copernicus tilbyr [nedlasting av
data](https://help.marine.copernicus.eu/en/articles/7949409-copernicus-marine-toolbox-introduction#h_9172b5c79a)
via kommandolinje, Python og browser, men krever registrering og har dessverre
ikke noe REST-API som kan brukes i apper.

Vi har derfor laget et midlertidig produkt på apiet kalt
[Iceberg](https://api.met.no/weatherapi/iceberg/0.1/documentation) som viser
posisjoner for isfjell i Arktis i løpet av en uke i GeoJSON-format. Data blir
oppdatert manuelt, så man skal normalt kunne finne data for forrige arbeidsdag.
Men om dere finner en annen kilde til isfjellposisjoner kan dere gjerne bruke
den istedet.

Isfjellene bør kunne plottes på kartet og gi varsel om de er innen en viss radius
fra skipets posisjon på samme tid.

### 3. Beregne drivbaner i Drifty

Hvis man finner et isfjell som ser ut til å utgjøre en fare for valgt kurs,
består oppgaven å kjøre en simulering for dette i Drifty.
Legg merke til at observasjonen kan være fra flere dager tilbake, så da må
korrekt starttidspunkt angis i input til Drifty. Så må dere sammenlikne
resultatet (som er et sett med simulerte baner) og finne ut hvor mange som er
i nærheten av skipets kurs, og ut fra dette beregne en prosentvis sjanse for
at de krysser. På samme måte kan man også kjøre simuleringen baklengs og finne
ut hvor et isfjell kommer fra.

Drifty krever lengde, bredde og dybde for isfjell i simuleringen, disse kan
beregnes ut fra flg variabler:

- `IA_BLN`: Maximum horizontal iceberg length in meters at waterline level
- `BRGARE`: Total iceberg area in square meters

## Datakilder

### Obligatoriske

- [Iceberg](https://api.met.no/weatherapi/iceberg/0.1/documentation) - satellittobservasjoner av isfjell
- [Drifty](/drifty/) openberg - drivbanesimuleringer
- [MetAlerts](https://api.met.no/weatherapi/metalerts/2.0/documentation) - maritime farevarsler

### Polaris kart

- [Victoria WMS](https://public-victoria.met.no/wms?service=WMS&version=1.3.0&request=GetCapabilities&format=image%2Fpng&transparent=true&group=in2000)

Bruk LAYERS=Met_Norway_Ice_Chart og STYLES=icechart ([eksempel](https://victoria.met.no/wms?REQUEST=GetMap&SERVICE=WMS&VERSION=1.3.0&FORMAT=image%2Fpng&STYLES=icechart&TRANSPARENT=TRUE&TIME=2026-02-16T00%3A00%3A00Z&LAYERS=Met_Norway_Ice_Chart&WIDTH=3452&HEIGHT=1504&CRS=EPSG%3A3857&BBOX=-25144310.51397454%2C1908272.9190080315%2C17583880.838383913%2C20524495.33903906))

### Andre APIer

- [Oceanforecast](https://staging.api.met.no/weatherapi/oceanforecast/2.0/documentation) - punktbasert vær- og havvarsel
- [BarentsWatch](https://www.barentswatch.no/) - kartdata for hav og kyst
- [AIS (Automatisk identifikasjonssystem)](https://www.kystverket.no/ais) - posisjonsdata for fartøyer (sanntid og historiske data)
- [Havvarsel API](https://api.havvarsel.no/apis/duapi/havvarsel/v2/swagger-ui.html)

## Kommentarer

### Beregning av dimensjoner på isfjell

> Ja, det er nok veldig vanskelig i praksis å måle høyde og dypgang på
> isfjell fra satellitt, og in-situ observasjoner finnes nok heller ikkje i
> nær sanntid. Men det er nok helt greit å bare anta en standard høyde (over
> vann) på feks 5 m, og tilsvarende dybde (under vann) på 50 m (typisk 10 ganger
> høyden). Evt at bruker kan overstyre dette manuelt i appen.
>
> Bredde kan man her beregne/estimere fra BRGARE / IA_BLN = 150598 / 679 = 222 m.
>
> Dimensjonene på isfjellet har ikkje veldig stor betydning på driften, men
> isfjell vil grunnstøte i modellen dersom havdyp er mindre enn isfjellets
> dybde.
>
> Drifty gir ikkje noen tydelig tilbakemelding om slik grunnstøting, og
> plottene vil bare vise at isfjellene stopper opp, men ikkje kva som er
> grunnen.
>
> Men i netCDF-fila som man kan laste ned vil man se at variabelen "moving"
> blir satt til 0 når isfjellene grunnstøter. Denne kan bli 1 igjen dersom
> tidevann hever isfjellet fra grunnen.
>
> — Knut Frode Dagestad

## Se også

- [ArcticInfo](https://www.barentswatch.no/arcticinfo/) - tjeneste for skipstrafikk
- [cryo.met.no](https://cryo.met.no/) - portal for arktis


{% comment %}

skalere opp staging <- ip alias in2000.drifty.met.no

brukernavn ?

geojson output ?

små filer

kontakt knut frode dagestad
- modelldata tilbake i tid? minst 2020
- hvem har laget isfjell?

icebox


- størrelse
- hele verden
- smelting?
- ma ti døgn frem i tid

default ridsskritt

4 dimensjoner

https://data.marine.copernicus.eu/product/SEAICE_ARC_SEAICE_L4_NRT_OBSERVATIONS_011_007/description

SAR Sea Ice Berg Concentration and Individual Icebergs Observed with Sentinel-1 & RCM | Copernicus Marine Service

omvendt oljedrift

{% endcomment %}
