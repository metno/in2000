---
title: Yr-maps
date: 2025-03-12
author: Geir Aalberg
layout: page
parent: Kart
grand_parent: Generelle ressurser
#nav_exclude: true
state: draft
tags:
    - guide
summary: >
    Kom igang med Yr-maps
---

![Screenshot av vindanimasjon](/2025/yr-wind.png)

I 2023 siden lanserte vi nye værkart på Yr, som blant annet inkluderte
animerte vindkart basert på algoritmer utviklet for visualisering av data fra
partikkelakselerator. De nye kartene, som erstatter vår gamle WMS-karttjeneste
er utviklet etter spesifikasjon fra NRK og bruker Mapbox-protokollen.

I motsetning til andre karttjenester er de dog ikke laget for å plottes direkte
på kartet, men i stedet behandles som rådata som må prosesseres i klienten for
optimal visning. For eksempel har de ikke transparens, og vi bruker rød- og
grønnkomponenten i bildet for å angi hhv x- og y-komponenten av vindvektorer.
For optimal ytelse bør man bruke en GPU til å prosessere karttilene om til
bilder som kan vises på skjerm, enten via en backend med bruk av OpenGL, eller
vha WebGL direkte i klienten.

{% comment %}
## Demo

<script src="https://unpkg.com/maplibre-gl/dist/maplibre-gl.js"></script>
<link href="https://unpkg.com/maplibre-gl/dist/maplibre-gl.css" rel="stylesheet" />

<div id='map' style="width: 100%; height: 800px;"></div>
<script>
    var map = new maplibregl.Map({
        container: 'map',
        style: 'https://osm.api.met.no/styles/basic-preview/style.json',
        center: [15, 65],
        zoom: 4
    });
</script>
{% endcomment %}

## Datakilder

- <https://beta.yr-maps.met.no/> - kart-API med dokumentasjon

Kartilene bruker WebMercator-projeksjon, som er default i de fleste kartklienter.

## Ressurser

### Yr-maps

- [Dokumentasjon fra NRK](https://nrkno.github.io/yr-map-docs/) på tile rendering med [kildekode](https://github.com/nrkno/yr-map-docs)
- [TileConvert](https://github.com/metno/tileconvert) - Go-kode for proxy server for produksjon av tiles som kan leses direkte inn i kartbibliotek
- [Yr-maps demo client](https://client.yr-maps.met.no/)

## Spørsmål?

Kontakt yr-maps@met.no for tekniske spørsmål angående kartene.