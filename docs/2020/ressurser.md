---
layout: page
title: API-ressurser
parent: 2020
grand_parent: Tidligere års caser
date: 2021-02-19
author: Geir Aalberg
---



## 1. Bevegelser i havet

Aktuelle scenarios kan være ferdsel i Oslofjorden eller Nordishavet.

- [Oslofjord](/weatherapi/oslofjord/0.1/documentation) - Strømkart over Oslo- og Drammensfjorden
- [Oceanforecast](/weatherapi/oceanforecast/0.9/documentation) - havvarsel for punkt
- [Gribfiles](/weatherapi/gribfiles/1.1/documentation) - nedlasting av GRIB-filer
- [Textforecast](/weatherapi/textforecast/2.0/documentation) - tekstvarsler for områder
    - coast_no
    - sea_no
    - areas
- [Tidalwater](/weatherapi/tidalwater/1.1/documentation) - tidevann for havner
- [Icemap](/weatherapi/icemap/1.0/documentation) - Isvarslingstjenesten
  - ny versjon 2 under arbeid, kom gjerne med ønsker her

**NB: Verdier i Tidalwater er i meter, ikke cm (som tidligere angitt)!**

Andre kilder:

- [FjordOs](http://www.fjordos.no/live/?page_id=1250) - Dagens strømvarsel for Oslofjorden

## 2. Ras-, flomv- og flovarsling

- [Tidalwater](/weatherapi/tidalwater/1.1/documentation) - tidevann for havner
- [Oceanforecast](/weatherapi/oceanforecast/0.9/documentation) - havvarsel for punkt

Andre datakilder:

- [Kartverket](https://www.kartverket.no/sehavniva/) - se havnivå

## 3. Luftkvalitet i kommuner

Ved spørsmål, kontakt <a href="mailto:eivindgw@met.no">Eivind G. Wærsted</a> direkte.

- [https://airquality-expert-ifi.met.no/](https://airquality-expert-ifi.met.no/)
- [Presentasjon](https://drive.google.com/file/d/1ykXgoQ4dQ02NXADc4krMG0pUa0Kz3m-i/view?usp=sharing) - slides fra Eivinds foredrag

Brukes av [Miljødirektoratet](https://dev.miljodirektoratet.no/fagbruker-luftkvalitet).

- [Vetenskapens Värld](https://www.svtplay.se/video/25693852/vetenskapens-varld/vetenskapens-varld-sasong-32-giftet-i-luften) (geoblocking).

## 4. Prediksjon av klima

Datakilder hos MET:

- [Frost](https://in2000-frostproxy.ifi.uio.no/) - historiske klimadata
- [Presentasjon](https://docs.google.com/presentation/d/1pMblBHPuVYF6yBN2ejTJzwJOmkpKvQJ0vcwhxBYjrDI/edit?usp=sharing) - slides fra Louises foredrag
- [THREDDS](https://thredds.met.no/thredds/obs.html) - griddede observasjonsdata

Presentasjoner ved Ketil Isaksen fra MET:

- [Heavy MET talk - The Arctic climate transformation and the effects on the cryosphere](https://www.youtube.com/watch?v=A8S5e11h9MA)
- [Slow TV fra Svalbard](https://tv.nrk.no/serie/svalbard-minutt-for-minutt/2020/DVFJ30006219/avspiller)

Andre datakilder:

- [SeKlima](https://seklima.met.no/observations/) - grafiske framstillinger fra Frost
- [KlimaServiceSenter](https://klimaservicesenter.no/faces/desktop/scenarios.xhtml?climateIndex=precipitation_amount&period=Annual&scenario=RCP85&region=NO&mapInterval=2085) - klimafremskrivinger
- [MOSJ](http://www.mosj.no/no/klima/atmosfare/temperatur-nedbor.html) - visualisering Svalbard-observasjoner
- [Copernicus](https://cds.climate.copernicus.eu/cdsapp#!/search?type=dataset&keywords=%28%28+%22Product+type%3A+Climate+projections%22+%29%29) - klimafremskrivinger
- [Convection permitting climate simulations for Svalbard](https://cms.met.no/site/2/klimaservicesenteret/rapporter-og-publikasjoner/_attachment/15506?_ts=16edbb32a83) - Background-report for Climate in Svalbard 2100
- [THREDDS](https://thredds.met.no/thredds/catalog.html) - *veldig* god trening hvis man har planer om å bli forsker

## 5. Droner og luftrom

Mange begrensninger:

- vær og vind
- sikt (kun dagslys)
- høyde (ikke over 120 m)
- avstand på 150 m fra folk, bygninger og trafikk
- avstand på 150 m fra festivaler, sportsarrangementer og militære områder
- avstand på 5 km fra lufthavner (med mindre annet er avtalt)
- bruke av andre sensorer enn foto/video krever registrering hos NSM

Diverse lover og regler:

- [Luftfartstilsynet](https://luftfartstilsynet.no/droner/hobbydrone/dronelek/)
- [AviNor](https://avinor.no/konsern/pa-flyplassen/droner/generelt)
- [Datatilsynet](http://www.datatilsynet.no/regelverk-og-skjema/veiledere/droner---hva-er-lov)
- [Nasjonal Sikkerhetsmyndighet](https://nsmstat.maps.arcgis.com/apps/webappviewer/index.html)

Samt et aktuelt scenario for bønder:

- [Tilsyn av sauer](https://docplayer.me/62771004-Tilsyn-med-drone-rimelig-og-effektivt.html)

# Felles kilder

- [Hvordan bruke tjenesten](./guide)
- [Locationforecast](/weatherapi/locationforecast/1.9/documentation) - værvarsel for punkt
    - [2.0 beta](/weatherapi/locationforecast/2.0/documentation) - ny versjon med native JSON
- [Nowcast](/weatherapi/nowcast/0.9/documentation) - nåvarsel (nedbør basert på radar)
- [Sunrise](/weatherapi/sunrise/2.0/documentation) - solopp/nedgang
- [Textforecast](/weatherapi/textforecast/2.0/documentation) - tekstvarsler for områder
- [MetAlerts](/weatherapi/metalerts/1.1/documentation) - farevarsler
    - [CAP format](https://en.wikipedia.org/wiki/Common_Alerting_Protocol) - Common Alerting Protocol
    - [Yr Warning Icons](https://github.com/nrkno/yr-warning-icons) - PNG/SVG-ikoner som matcher eventType



Flere datakilder kan komme til etterhvert.
