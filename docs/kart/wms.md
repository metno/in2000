---
layout: page
title: WMS
parent: Kart
grand_parent: Generelle ressurser
nav_order: 26
date: 2026-03-05
author: Geir Aalberg
#tags:
#    - guide
summary: >
    Introduksjon til OGC Web Map Service protokoll
---

## WMS-standarden

Standarden er definert her: <https://www.ogc.org/standard/wms/>

Kort forklart bruker man typisk flg metodekall mot tjenesten:

- **GetCapabilities**: Returnerer en liste over lag med tilhørende styles som XML
- **GetMap**: Returnerer et bilde med angitt dimensjon og projeksjon for et gitt lag/style

For en introduksjon til WMS, se [tutorial fra
NOAA](https://sos.noaa.gov/support/sos/how-to/wms-tutorial/all/).

## WMS klientbiblioteker

- [MapLibre](https://maplibre.org/)
- [OpenLayers](https://openlayers.org/) - Javascript for web
- [Leaflet](https://leafletjs.com/examples/wms/wms.html) - Javascript for mobile

Fordelen med OpenLayers er at den kan lese GetCapabilities direkte og lage
layer- og styleselector automatisk. For de andre er man nødt til å skimme
gjennom XMLen og finne aktuelle lag/styles som må hardkodes i klienten.
