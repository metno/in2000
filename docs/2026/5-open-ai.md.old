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
værvarsling. MET bruker allerede KI for å produsere både tekstlige og numeriske
varsler, og mer er i kjømda. Nytt av året er at vi nå eksperimenterer med
egne grensesnitt for KI-baserte agenter.

## Funksjonelle krav

Appen skal kunne snakke med METs MCP-server. Denne har allerede koblinger mot
Locationforecast og MetAlerts, og vi håper å få på plass kobling mot Frost ASAP.
Har dere ønsker om kobling mot flere features tar vi gjerne mot forslag.

MCP-serveren skal i prinsippet fungere mot alle AI-modeller som støtter MCP (dvs
de fleste), men vi har bare testet den med Copilot og Claude. Det blir litt opp
til hvert team å finne ut hvilke LLM-er som fungerer best.

### Talegjenkjenning

De færreste ønsker vel å skrive inn lange tekster på telefonen, og vil heller
foretrekke å snakke. Vi er usikre på om Android Studio støtter talegjenkjenning,
men hvis dere får til å implementere dette ville det vært gode sjanser for å
vinne en av prisene.


## Presentasjon og demo

Siden det trolig er uklart for de fleste hvordan MCP fungerer og det vanskelig
kan forklares på ti minutter har vi arrangert for en egen digital demo uken
etter kick-off. Alle som har lyst kan joine foredraget på Google Meet og stille
spørsmål i chaten. Personvernet er beskyttet via METs databehandleravtale med
Google.

### KI-demo: MET MCP-server

Håvard Futsæter <havardf@met.no> holder eget digitalt foredrag tirsdag 3. mars
kl 10:30 – 11:30. Link til videomøte gis senere.

{% comment %}
- Tuesday 3 Mar 2026 10:30–11:30
- Video call link: <https://meet.google.com/ajo-jrvs-thk>
- Or dial: +47 21 40 03 69 PIN: 263 796 436#
- More phone numbers: <https://tel.meet/ajo-jrvs-thk?pin=4362624582662>
{% endcomment %}


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

