---
layout: page
title: Case 5. Åpent case
parent: Årets caser
#grand_parent: Tidligere års caser
date: 2026-02-26
author: Geir Aalberg
---

Her kan dere i prinsippe lage hva dere vil, men dere må bruke minst én av datakildene nedenfor.

## Vegvær og luftkvalitet

Utslipp og svevestøv fra vegtrafikken er en av hovedkildene til helseskader grunnet
forurensning i Norge, og etter høyt blodtrykk er den største risikofaktoren for
dødsfall globalt.

- [Airqualityforecast](https://api.met.no/weatherapi/airqualityforecast/0.1/documentation) - luftkvalitet prognoser

Været spiller en stor rolle for eksponering siden kulde gjør at forurenset luft
konsentreres langs bakken. Statens vegvesen har meteorologiske målestasjoner
langs riks- og fylkesveiene, se [kart](https://vegvar.atlas.vegvesen.no/#/kart).
Disse dataene kan hentes fra deres API (finnes også i [Frost](/frost/) hvis dere
heller vil bruke denne):

- [Værdata målinger](https://dataut.vegvesen.no/dataservice/vaerdata-malinger-api) - API fra Statens vegvesen (krever registrering)

Deres [datakatalog](https://www.vegvesen.no/fag/teknologi/apne-data/sok-i-dataportalen/)
har også trafikkstatistikk, miljødata m.m.

## MeteoGate

MET samarbeider med flere andre meteorologiske institutter med å levere data til
en felles portaltjeneste. Dette skal gjøre det mulig for brukere å finne alle
europeiske data på ett sentralt sted, uten å måtte lære seg 40 forskjellige
grensesnitt/APIer.

På sikt kan det kanskje også føre til at hvert land ikke lenger vil tilby egne
APIer, men i stedet henvise til portalen. Vi ønsker derfor å lære om brukernes
erfaringer med å bruke denne nye tjenesten. Merk at deler av tjenesten krever
registrering.

- [MeteoGate APIs](https://meteogate.eu/) - europeisk hub for meteorologiske data

## Radardata

Radarobservasjoner er den beste kilden for å varsle nedbør.
Bruk minst en av flg kilder:

- [Radar STAC API](https://radar-stacapi.met.no/) - radarmosaikk fra Meteorologisk institutt

Dette er en tjeneste som leverer data på [GeoTIFF](https://en.wikipedia.org/wiki/GeoTIFF) format.
Disse må dekodes før dataene kan plottes på kart.

- [OpenRadarData API](https://radar.meteogate.eu/api/docs) -  European weather radar observations from OPERA-EUMETNET

Begge bruker et [EDR](/edr/)-grensesnitt, som er i ferd med å bli en standard for
alle tjenster fra de europeiske meteorologiske instituttene.

## Felles datakatalog

DigDir har laget en katalogtjeneste for offentlige APIer og datasett, det samme
har Kartverket for geofaglige data.

- [data.norge.no](https://data.norge.no/data-services) - DigDir
- [GeoNorge](https://www.geonorge.no/) - Kartverket

Siden MET bruker mye tid på å publisere metadata om våre tjenester på disse
portalene, ønsker vi å vite mer om hvor godt kjent disse er og hvor lette de
er å bruke. Oppgaven blir å lete litt rundt i disse katalogene og finne noen data dere
synes er interessante (både fra oss og andre produsenter), og kombinere disse
med værdata fra MET i en app. Prosessen må dokumenteres, med en vurdering av
disse portalene.

## KI – MCP-server

Kunstig intelligens brukes nå overalt innen IT, og vi har fått mange ønsker om
en sentral MCP-tjeneste som kan brukes mot LLMer. MET har laget en prototype på
en [MCP-server](/ai/mcp) som er åpen for testing.

- [MET MCP-server](https://webapi.met.no/mcp-docs/) - se [presentasjon](/ai/MET_Norway_MCP_server.pdf)

Merk at denne ikke er satt opp for IN2000, men etter påtrykk fra brukere av
api.met.no. Det er foreløpig uvisst om IFI har LLM-ressurser som kan benytte
MCP, i så fall er det mulig å kjøre en lokal instans av [Ollama](https://ollama.com/)
med [gpt-oss](https://ollama.com/library/gpt-oss) på en server.

## THREDDS

Nesten alt av hva MET produserer av data lagres i [THREDDS](/thredds/), som også fungerer
som arkiv. Det er derfor den eneste kilden til mange av dataene vi leverer.
I 2022 var det flere team som rapporterte at det var vanskelig å lese data
fra thredds.met.no siden biblioteket NetCDF-Java feiler da Android mangler støtte
for en krypteringsalgoritme som kreves for HTTPS. Dette er naturligvis et stort
problem for MET, og vi ønsker å finne ut om dette problemet fortsatt er uløst
i 2026.

Eksempler på interessante data som mange etterlyser:

- [Skogbrannfareindeks](https://thredds.met.no/thredds/catalog/fwi/catalog.html) - datagrunnlag for [skogbrannfare.met.no](https://skogbrannfare.met.no/)
