---
layout: page
title: Case 5. Åpent case - bruk av KI
parent: Årets caser
#grand_parent: Tidligere års caser
date: 2026-01-30
author: Geir Aalberg
---

![Vær-robot](ai_weather.jpg)

## Bakgrunn

***Alle snakker om været, nå også roboter.***

Kunstig intelligens har hatt en ekstrem fremgang de siste årene, også innen
værvarsling. MET bruker allerede KI for å produsere en del varsler, og i løpet
av året vil dette også bli tatt i bruk for værvarslene på Yr.
Vi er interesserte i å se hvilke andre muligheter som kan ligge innenfor dette feltet.

Dette caset passer best for de som er interesserte i å utforske hvilke
muligheter som finnes innen KI. Vi vet ikke svarene, og det er ingen fasit.

## Funksjonelle krav

Appen skal kunne snakke med METs MCP-server. Denne har allerede koblinger mot
Locationforecast og MetAlerts, og vi håper å få på plass kobling mot Frost ASAP.
Har dere ønsker om kobling mot flere datakilder hos MET tar vi gjerne mot forslag.


Talegjenkjenning?

Kom med ønsker om ønsket funksjonalitet

Åpenbare standardprompts?

## Datakilder

- [MET MCP-server](https://webapi.met.no/mcp-docs/) - **obligatorisk**

I tillegg kan dere gjerne bruke andre MCP-servere, her er noen eksempler:
- [weather-mcp](https://github.com/weather-mcp/weather-mcp) - værdata fra NOAA og Open-Meteo (kildekode)

Eventuelt kan dere også gjerne skrive deres egen MCP server hvis dere har lyst.

## Dokumentasjon

- [What is the Model Context Protocol (MCP)?](https://modelcontextprotocol.io/docs/getting-started/intro)
- [Eksempel på hvordan bygge klient i Kotlin](https://modelcontextprotocol.io/docs/develop/build-client) - (forutsetter Claude)
- [Connect to remote MCP Servers](https://modelcontextprotocol.io/docs/develop/connect-remote-servers)
- [Add an MCP server in Android Studio](https://developer.android.com/studio/gemini/add-mcp-server)

