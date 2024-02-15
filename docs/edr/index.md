---
layout: page
title: OGC API - EDR
parent: Generelle ressurser
nav_order: 90
date: 2024-02-15
author: Geir Aalberg
---

En nye standard som holder på å etablere seg innen geofag er **Environmental
Data Retrieval** fra [OGC](https://www.ogc.org/). Dette er en del av et sett av
tilhørende standarder kalt [OGC API](https://ogcapi.ogc.org/), hvorav EDR er
spesielt beregnet for søk i geodata. Som offentlig institutt er vi derfor pålagt
å implementere denne på bakgrunn av EUs
[INSPIRE-direktiv](https://knowledge-base.inspire.ec.europa.eu/legislation/inspire-directive_en).

## Standarder

- [Innføring i EDR](https://opengeospatial.github.io/e-learning/ogcapi-edr/text/basic-main.html)
- [EDR spesifikasjon](https://www.ogc.org/standard/ogcapi-edr/)



## Struktur

```mermaid
graph TB
    landingpage --> landingpage
    landingpage --> openapi
    landingpage --> conformance
    landingpage --> collections

    collections --> collection/1
    collections --> collection/2
    collections --> collection/3

    collection/2 --> position
    collection/2 --> area
    collection/2 --> locations
    collection/2 --> items

    collection/3 --> instances
    instances --> instance/1
    instances --> instance/2
    instances --> instance/3

    instance/2 --> position'
    instance/2 --> area'
    instance/2 --> locations'
    instance/2 --> items'

```

## Testverktøy

- UK Met Office sin [kartklient](https://labs.metoffice.gov.uk/edr/static/html/query.html)
