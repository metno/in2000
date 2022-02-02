---
layout: default
#title: IN2000: Case 2. Farevarsler
date: 2021-02-19
author: Geir Aalberg
---


# 4. Vektorkart

Vær med å teste ny kartløsning for Yr! MET holder på å lage en prototype for vektorkart,
og dere skal lage en klient for denne. Det finnes har mange mulige datakilder, for eksempel:

- temperatur, vind og nedbør i timesoppløsning for Norden
- temperatur, vind og nedbør i 6-timesoppløsning for hele verden
- nedbørsskyer i tilnærmet sanntid (nåvarsel)

## Mulige ideer

- Nedbørskart à la Yr med animerte regnbyger
- Vis temperaturkart for hele verden for å planlegge hvor man bør dra på sommerferie (post-Corona)
- Sykkelkart for Oslo med sykkelstier og fare for regn

## Datakilder

Primær (obligatorisk):

- [Testserver](https://test.openmaps.met.no/in2000/map/services) for IN2000
  - <https://test.openmaps.met.no/in2000/map/> (prototype på webklient)
  - <https://test.openmaps.met.no/in2000/map/services> (API)
  - <https://gitlab.met.no/yr-maps/maps-frontend-2020/> (intern kodebase)

Sekundære (valgfritt):

- Locationforecast
- Nedbørskart
- MetAlerts
- Sykkelstier med koordinater fra Oslo Kommune

## Dokumentasjon

Mapbox protokoll og biblioteker:

 - Vector tile specification: <https://github.com/mapbox/vector-tile-spec/>
 - Native bibliotek for Android og andre OS (iOS/MacOS): <https://github.com/mapbox/mapbox-gl-native>
 - Javascript biblioteker:
   - Mapbox GL <https://github.com/mapbox/mapbox-gl-js>
   - Openlayers <https://openlayers.org/>
   - Leaflet <https://leafletjs.com/>
 - Projeksjoner: <https://www.maptiler.com/google-maps-coordinates-tile-bounds-projection/>
 - Tile grids: <https://docs.microsoft.com/en-us/azure/azure-maps/zoom-levels-and-tile-grid?tabs=csharp>

## Teknisk info

Kartserveren leverer vektordata på mapbox format (protobuf) samt JSON metadata.
Klienten kan bruke Javascript eller native Android Mapbox-bibliotek
([Android-versjon](https://github.com/mapbox/mapbox-gl-native-android/) som
funker med Kotlin). Teamene kan selv velge bakgrunnskart (vi anbefaler
OpenStreetMap) og må rendre datalagene oppå dette.

Dette kreves at man setter seg litt inn i forskjellige kartprojeksjoner og
forskjellen på inner/outer polygon (hvilken vei de roterer), se dokumentasjon.

Et problem med de fleste GEO standarder er at de oftest bare støtter tre
dimensjoner lengde, bredde og høyde over havet. Dette gjelder også mapbox
formatene. I meteorologi trenger vi minst en dimensjon til, nemlig *tid*.
For øyeblikket er dette løst ved at vi har egne vektor-tiles for hvert tidsskritt.

På [testserveren](https://test.openmaps.met.no/in2000/map/services) finner dere
URLer på formen `parameter_navn/referansetid/tidsskritt`.

- Parameternavn, eks `air_temperature_2m`
- Referansetid, format `YYYYMMDDThhmmss` (UTC), eks 20210223T060000.
- Tidsskritt, på formen `NNN`, eks 001 (vurderer å bruke YYYYYMMDDThhmmss som format)

Man kan få mer metadata for hver enkelt endpunkt, i json, ved å bruke urlene der
får fra [services](https://test.openmaps.met.no/in2000/map/services). For øyeblikket så
støttes bare projeksjonen *web-mercator*.

En vektor-tile hentes med `parameter_navn/referansetid/tidsskritt/tiles/z/x/y.pbf`.
Dette vil returnere en vectortile hvor z/x/y er tile-koordinater:

- `z` zoom-nivå
- `x` lengde
- `y` bredde

Zoom-nivå og posisjon håndteres ofte av biblioteket dere bruker, feks mapbox-gl-native.

Kontakt: [Børge Moe](mailto:borgem@met.no)
