---
layout: default
#title: IN2000
date: 2021-02-19
author: Geir Aalberg
---

# Caser 2019

For bruk av APIene, se [veiledning](./guide).

Casebeskrivelsene kan [lastes ned som PDF](./case.pdf).

## Case 1. Været til sjøs

api.met.no:

- [Locationforecast](/weatherapi/locationforecast/1.9/documentation) - værvarsel for punkt
- [Oceanforecast](/weatherapi/oceanforecast/0.9/documentation) - havvarsel for punkt
- [Gribfiles](/weatherapi/gribfiles/1.1/documentation) - nedlasting av GRIB-filer
- [Epsogram](/weatherapi/epsogram/1.1/documentation) - grafer for flyplasser (sperret?)
- [Nowcast](/weatherapi/nowcast/0.9/documentation) - nåvarsel (nedbør basert på radar)
- [Textforecast](/weatherapi/textforecast/2.0/documentation) - tekstvarsler for områder
    - coast
    - seabank
    - seahigh
    - areas
- [MetAlerts](/weatherapi/metalerts/1.1/documentation) - farevarsler
- [Tidalwater](/weatherapi/tidalwater/1.1/documentation) - tidevann for havner
- [Icemap](/weatherapi/icemap/1.0/documentation) - Isvarslingstjenesten
- [Sunrise](/weatherapi/sunrise/2.0/documentation) - solopp/nedgang

Se også Yr:

- [Hav og Kyst](https://www.yr.no/hav_og_kyst/)
- [Tekstvarsel for kystområdene](https://www.yr.no/hav_og_kyst/tekstvarsel/)

## Case 2. Lynvarsling

Forkunnskap: UALF (Universal ASCII Lightning Format), a.k.a. LLPS/CGLSS

api.met.no:

- [Lightning](/weatherapi/lightning/1.0/documentation) - lynobservasjoner hvert 5. minutt i UALF
- [Radarlightning](/weatherapi/radarlightning/1.1/documentation) - lynradarkart

Frost:

- [lightning](https://frost.met.no/api.html#!/lightning/getLightning) - historiske lynobservasjoner

lyn.met.no:

- [lyn.met.no](https://lyn.met.no/) - sanntids lynkart

## Case 3. Flyværvarsler

Forkunnskap: ICAO koder

api.met.no:

- [MetAlerts](/weatherapi/metalerts/1.1/documentation) - farevarsler
    - [CAP format](https://en.wikipedia.org/wiki/Common_Alerting_Protocol)
- [Tafmetar](/weatherapi/tafmetar/1.0/documentation) - generelle varsler
- [Sigmets](/weatherapi/sigmets/1.0/documentation) - ekstraordinære varsler
- [Textforecast/1.6](/weatherapi/textforecast/1.6/documentation)
    - aw_* - ekstraordinære varsler for flyplasser
    - iga_* - varsler for områder
- [Turbulence](/weatherapi/turbulence/1.1/documentation) - turbulenskart for flyplasser
- [Spotwind](/weatherapi/spotwind/1.0/documentation) - sidevindvarsler for flyplasser
- [Upperwindweather](/weatherapi/upperwindweather/1.1/documentation) - kart for høyere luftlag
- [Verticalprofile](/weatherapi/verticalprofile/1.1/documentation) - vertikalsnitt
- [Routeforecast](/weatherapi/routeforecast/1.0/documentation) - diverse kart og grafer
- [NLAroutes](/weatherapi/nlaroutes/1.0/documentation) - grafer for Norsk Luftambulanse
- [Locationforecast](/weatherapi/locationforecast/1.9/documentation) - værvarsel for punkt
- [Nowcast](/weatherapi/nowcast/0.9/documentation) - nåvarsel (nedbør basert på radar)
- [Geosatellite](/weatherapi/geosatellite/1.4/documentation) - satellittbilder (kommer snart)
- [Polarsatellite](/weatherapi/polarsatellite/1.1/documentation) - mere satellittbilder

## Case 4. Luftkvalitet i storbyer

- [Airqualityforecast](/weatherapi/airqualityforecast/0.1/documentation) - luftkvalitet API
- [uemep-wms.met.no](http://uemep-wms.met.no/) - WMS-klient + WMTS-tjener

WMS-klienten kan brukes som veiledning, og den må brukes sammen med
https://api.met.no/weatherapi/airqualityforecast/0.1/reftimes

Jeg tror oppgaven er ikke altfor vanskelig å gjennomføre så lenge man
har et greit WMS-klient-bibliotek (f.e. leaflet)

Det bør hete: Forventet luftkvalitet i de kommende dagene gitt
luftkvalitetsvarsel. Jeg tror ikke at noe annet enn 'airqualityforecast'
er relevant - oppgaven er jo mer eller mindre å bygge
[luftkvalitet.miljostatus.no](https://luftkvalitet.miljostatus.no/) som en app.

## Case 5. Klimastatistikk

- [Frost](https://frost.met.no/api.html) - historiske klimadata
- [THREDDS](http://thredds.met.no/thredds/obs.html) - griddede observasjonsdata

