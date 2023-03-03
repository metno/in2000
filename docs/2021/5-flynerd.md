---
layout: default
title: Case 5. Flynerd-app
parent: 2021
grand_parent: Tidligere års caser
date: 2021-02-19
author: Geir Aalberg
---

# Case 5. Flynerd-app

Lag en app for alle som er hekta på fly! Mulig eksempler på bruksområde:

- Vis fly i lufta over Norge. Live flight data kan hentes gratis fra fx OpenSky
- Vis værforhold på flyplasser (TafMetar dekker hele verden)
- Vis vertikalsnitt på enkelte flyruter (NLAroutes, Verticalprofile)

## Inspirasjonskilder:

- <https://www.flightradar24.com/>
- <https://www.ippc.no/>
- [Graphical Aviation Forecasts](https://gaf.met.no/#/) fra met.no


## Datakilder:

Minst ett av flg MET-apier (obligatorisk):

- Aviationforecast 1.6 - Textual aviation weather forecasts
- NLAroutes 1.0 - Vertical cross sections for flight routes
- Sigcharts 1.0 - Significant Weather Charts for aviation
- Spotwind 1.1 - Spotwind forecasts for airport landing systems
- Tafmetar 1.0 - Receive TAF/METAR from airports
- Turbulence 1.1 - Turbulence prognosis
- VerticalProfile 1.1 - Vertical weather profiles for aviation

Andre kilder:

- <https://opensky-network.org/apidoc/>
  - Eksempel: <https://opensky-network.org/api/states/all?lamin=60&lomin=8&lamax=75&lomax=15>
- <https://rapidapi.com/collection/flight-data-apis>
- <https://geekflare.com/flight-data-api/>
