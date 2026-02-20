---
layout: page
title: Klimavariabler
parent: 2025
grand_parent: Tidligere års caser
date: 2025-02-27
author: Ketil Tunheim
---

## Finne riktige variabler

### cloud_area_fraction

Her er dataene for gjennomsnittlig skydekke:

<https://seklima.met.no/months/mean(cloud_area_fraction%20P1M)/all_years/SN18700/nb/>

<https://seklima.met.no/days/mean(cloud_area_fraction%20P1D)/custom_period/SN18700/nb/2024-01-01T00:00:00+01:00;2024-12-31T23:59:59+01:00>

### surface_downwelling_shortwave_flux_in_air

Blant timedata fins det blant annet skydekke i octas, solskinnstid i
minutter, og gjennomsnittlig globalstråling i W/m2:

<https://seklima.met.no/hours/cloud_area_fraction,sum(duration_of_sunshine%20PT1H),mean(surface_downwelling_shortwave_flux_in_air%20PT1H)/custom_period/SN18700/nb/2024-01-01T00:00:00+01:00;2024-02-01T23:59:59+01:00>

<https://seklima.met.no/hours/cloud_area_fraction,sum(duration_of_sunshine%20PT1H)/custom_period/SN18700/nb/2024-01-01T00:00:00+01:00;2024-02-01T23:59:59+01:00>

### boolean_clear_sky_weather

Klarvær er en ganske streng definisjon, på det meste målte Blindern 14
slike i 1963:

<https://seklima.met.no/months/sum(boolean_clear_sky_weather(cloud_area_fraction%20P1D)%20P1M)/all_years/SN18700/nb/>

Her er alle dagene i hele 2024:

<https://seklima.met.no/days/boolean_clear_sky_weather(cloud_area_fraction%20P1D)/custom_period/SN18700/nb/2024-01-01T00:00:00+01:00;2024-12-31T23:59:59+01:00>

Altså ikke en ideell indikator nei, den er nok lagd for helt andre formål.

## Hvordan lage Frost-kall

Det er ikke alltid opplagt hvordan konvertere kall fra SeKlima til Frost, bl.a.
fordi SeKlima viser "fornorsket" tittel på variabler som ikke er den samme som
brukes i URLen. Følgende metode kan være en nyttig workaround:

{: .note }
Før du bruker Frost må du opprette en bruker og få nøkkel. Etter å ha gjort et
Frost-kall og lagt inn nøkkelen som brukernavn i dialogboksen vil browseren huske
denne og sende med hvert kall inntil omstart.

Du får også alt du trenger fra seklima-URLen for å lage frostkall, nemlig
elementid, sourceid og referencetime. Her er et av frost-kallene bak
timedataene:

<https://frost.met.no/observations/v0.jsonld?elements=cloud_area_fraction&sources=SN18700&referencetime=2024-01-01T00:00:00Z/2024-02-01T23:59:59Z>

Det er også mulig å finne frost-kall fra Seklima:

1. Før du trykker Vis resultat, trykk F12 (Chrome) eller høyreklikk og velg
Inspect (Firefox). Åpne deretter fanen Network.
2. Trykk Vis resultat og dobbeltklikk på linjene som dukker opp under
Network
3. Frost-lenke står ved "currentLink" (for Firefox, høyreklikk og velg Copy Value > Copy URL).

Under er en av disse kallene for timedataene.
Den har et par ekstra innstillinger som ikke trengs, og komma
og mellomrom og slask er erstatta med koder, så den er litt verre å lese:

<https://frost.met.no/observations/v0.jsonld?elements=cloud_area_fraction&levels=default&qualities=0%2C1%2C2%2C3%2C4%2C5&referencetime=2024-01-01T00%3A00%3A00Z%2F2024-02-01T23%3A59%3A59Z&sources=SN18700&timeoffsets=default&timeresolutions=PT1H%2CPT3H%2CPT6H%2CPT12H>
