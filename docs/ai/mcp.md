---
layout: page
title: MCP server
parent: Generelle ressurser
date: 2026-03-02
author: Geir Aalberg
---

![Vær-robot](/images/ai_weather.jpg)

## Bakgrunn

***Alle snakker om været, nå også roboter.***

Kunstig intelligens har hatt en ekstrem fremgang de siste årene, også innen
værvarsling. MET bruker allerede KI for å produsere både tekstlige og numeriske
varsler, og mer er i kjømda.

En av tingene vi jobber med er en MCP-server, som er et eget grensesnitt for
KI-baserte agenter. Denne har allerede koblinger mot Locationforecast og
MetAlerts, flere integrasjoner kommer kanskje etterhvert. Vi tar gjerne imot
forslag om nye tjenester og features som kan integreres.

MCP-serveren skal i prinsippet fungere mot alle AI-modeller som støtter MCP (dvs
de fleste), men vi har bare testet den med Copilot og Claude. Det er usikkert om
UiO har noen LLM med API som fungerer med MCP, dette er noe teamene må undersøke
før de velger å bruke serveren.

## Datakilder

- [MET MCP-server](https://webapi.met.no/mcp-docs/)
- [weather-mcp](https://github.com/weather-mcp/weather-mcp) - værdata fra NOAA og Open-Meteo (kildekode)

## Dokumentasjon

- [Presentasjon](/ai/MET_Norway_MCP_server.pdf) fra MET 3. mars
- [What is the Model Context Protocol (MCP)?](https://modelcontextprotocol.io/docs/getting-started/intro)
- [Eksempel på hvordan bygge klient i Kotlin](https://modelcontextprotocol.io/docs/develop/build-client) - (forutsetter Claude)
- [Connect to remote MCP Servers](https://modelcontextprotocol.io/docs/develop/connect-remote-servers)
- [Add an MCP server in Android Studio](https://developer.android.com/studio/gemini/add-mcp-server)
- [Ollama](https://ollama.com/) med [gpt-oss](https://ollama.com/library/gpt-oss)

## Kontakt

Ved spørsmål, send epost til <mcp-server@met.no>.
