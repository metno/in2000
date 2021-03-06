---
layout: page
title: Public WMS Service
date: 2020-06-26
author: Geir Aalberg
---

The Public WMS service is a map service delivering tiles for use with WMS clients like OpenLayers,
Leaflet, OpenStreetMap and others.

## Capabilities

To see which data are available, use the `GetCapabilities` method:

<https://public-wms.met.no/verportal/verportal.map?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities>

<https://public-wms.met.no/verportal/radar_nowcast.map?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities>

## Layers

The following are currently supported (see Capabilites for an up-to-date list):

*Verportal:*

- precipitation_3h_global
- precipitation_6h_global
- surface_pressure_global
- wind_10m_global
- temperature_2m_global
- precipitation_1h_regional
- precipitation_3h_regional
- surface_pressure_regional
- wind_10m_regional
- temperature_2m_regional
- clouds_precipitation_regional
- radar_precipitation_intensity
- radar_precipitation_intensity_nordic
- radar_precipitation_intensity_reverse
- sea_current_regional
- sea_salinity_regional
- sea_temperature_regional
- sea_surface_height_regional
- sea_wave_height_direction_regional
- background
- base.LATLON
- coastlines
- h20.Nedbor_1t
- h20.Trykkfelt
- h20.vindfelt
- kart
- nordic.bottom

*radar_nowcast:*

- background
- coastlines
- diana (Radar Nowcast)
- radar_nowcast

## Projections

The following map projections are currently supported:

- EPSG:3857
- EPSG:900913
- EPSG:3575
- EPSG:4326
- EPSG:32633
- EPSG:32761
- EPSG:25833
