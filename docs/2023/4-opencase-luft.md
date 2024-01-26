---
layout: page
title: Case 4. Åpent case - i lufta
parent: 2023
grand_parent: Tidligere års caser
date: 2023-02-21
author: Geir Aalberg
---

Her er det fritt valg hva slags app man vil lage, men det må være relatert
til atmosfæren og bruke de obligatoriske datakildene.
Forslaget krever godkjenning fra veileder/kursledelsen.
Vi anbefaler å sjekke tidligere års caser for inspirasjon og datakilder.

- **For apper relatert til luftfart er det obligatorisk å bruke minst to flyværprodukter.**
- **For andre apper må man bruke minst to værprodukter, inkludert MetAlerts dersom
det er relevant for situasjonen.**

## Eksempler

Noen forslag basert på tidligere løsninger:

### Flyveplanlegger

Norske piloter bruker i stor grad Avinors IPPC-tjeneste (Internet Pilot Planning
Centre) for å hente informasjon om flyplasser og atmosfæriske forhold. Denne er
imidlertid ikke optimal for bruk på mobiltelefon, særlig når man befinner seg i
lufta uten dekning! **Lag en app-versjon av IPPC som cacher data lokalt og kan
vise nedlastede data uten å være tilkoblet nett.**

De fleste dataene under "MET - Meteo" ligger under "Aviation" på api.met.no. Ligning Maps og Wave Maps
(brukes hovedsaklig av offshore helikoptertrafikk) hentes i dag via FTP, men kommer
på apiet om kort tid. Det samme gjelder nye turbulenskart.

![IPPC](/images/examples/ippc.png)

### "Live" flight radar

**Lag en app som viser alle fly som er i lufta over Norge akkurat nå.**
Dere kan også vise planlagte avganger og ankomster, og sjekke været på
flyplassene for å gi en indikasjon på om det blir forsinkelser.

Det finnes mange tjenester som tilbyr data som kan være interessante:

- **TafMetar** og **Sigmets**  [API](/general) - værvarsler for flyplasser i "flyspråk" (ikke forsøk å oversette disse)
- [OpenSky](https://opensky-network.org/apidoc/) - live flight data [(eksempel)](https://opensky-network.org/api/states/all?lamin=60&lomin=8&lamax=75&lomax=15)
- [Andre flight data apier](https://rapidapi.com/collection/flight-data-apis)
- [Enda flere apier](https://geekflare.com/flight-data-api/)
- [Web-basert løsning](https://www.flightradar24.com/)

![FlightRadar](/images/examples/flightradar.png)

### Trafikklys for flyplasser

Etter ønsker fra flygeledere lagde noen OsloMET-studenter i 2022 en prototype
kalt [Aerodrome Warning Traffic Light System](https://awtl.met.no/). Her kan
flygelederne justere terskelverdier for været og få vite når det er trygt å
opererere flyplassen. Piloter kan også bruke den for å sjekke forholdene for
en flyrute. Denne tjenesten vil nok kunne optimalises mye for mobil ved å lage
som en app.

![AWTL](/images/examples/awtl.png)

### Droner og luftrom

Det er mange begrensninger som droneflyvere må forholde seg til. I tillegg til
vær og sikt finnes det mange regler som gjør det ulovlig å fly mer enn 150 m fra
tettbebyggelse, festivaler, sportsarrangementer, fengsler, militære områder mm.
Er man i nærheten av flyplasser er reglene enda strengere. Fom. 2021 må i tillegg
alle droneflyvere registrere seg, noe mange ikke er klar over. **Lag en app som
viser om det er trygt å sende opp drone på en gitt lokasjon, i forhold til vær,
sollys og regler.**

Aktuelle datakilder:

- Locationforecast og Nowcast [API](/general) - værforhold
- Sunrise [API](/general) - når er det lyst?

Diverse lover og regler:

- [Luftfartstilsynet](https://luftfartstilsynet.no/droner/)
- [AviNor](https://avinor.no/konsern/pa-flyplassen/droner/generelt)
- [Datatilsynet](http://www.datatilsynet.no/regelverk-og-skjema/veiledere/droner---hva-er-lov)
- [Nasjonal Sikkerhetsmyndighet](https://nsmstat.maps.arcgis.com/apps/webappviewer/index.html)
- [SafeToFly](https://www.safetofly.no/)

Samt et aktuelt scenario for bønder:

- [Tilsyn av sauer](https://docplayer.me/62771004-Tilsyn-med-drone-rimelig-og-effektivt.html)

![SafeToFly](/images/examples/safetofly.png)
