---
layout: page
title: Case 1. Sol og måne
date: 2023-02-21
---

MET har laget en ny versjon av sin [Sunrise-tjeneste](/general) som er nettopp
lagt ut som beta. Denne er skrevet i Python og vil snart bli lagt ut som åpen
kildekode. Før vi startet arbeidet var det noen som spurte om vi faktisk trengte
en slik tjeneste. "Kan ikke folk regne ut dette selv?" var det noen som sa.

Det er et godt spørsmål. Vi vet at mesteparten av dagens trafikk kommer fra
mobilapper og statiske skjermløsninger ved skysstasjoner o.l. Hvorvidt disse har
nok regnekapasitet og lagringsplass for å lagre efmeridetabeller og kalkulere
tidspunkter med minuttpresisjon er et åpent spørsmål. Vi vil derfor utfordre
studentene til å lage en **app for å beregne soloppgang, solnedgang og når solen
står høyest (krysser meridianen)**.

For å kvalitetssikre at beregningene deres er korrekt skal appen sammenlikne
resultatet med følgende datakilder og vise forskjellen i en tabell:

- Sunrise 2.0 [API](/general) (XML) [(dokumentasjon)](https://docs.api.met.no/doc/sunrise/astro)
- Sunrise 2.1 [API](/general) (XML, samme som over men med noen bugfikser)
- Sunrise 3.0 [API](/general) (GeoJSON) [(dokumentasjon)](https://docs.api.met.no/doc/sunrise/celestial)

Dersom deres konklusjon er at det ikke er praktisk gjennomførbart å gjøre slike
beregninger med dagens mobilteknoligi, er dette også et fullt ut godkjent resultat.
I så fall er det ikke selve appen som vil vektlegges, men rapporten hvor dere forklarer
de tekniske begrensningene.

Hjelpemidler og referanser:

- [Astronomy Engine](https://github.com/cosinekitty/astronomy/tree/master/source/kotlin) - astronomisk Kotlin-bibliotek
- [Definisjoner på soloppgang og solnedgang](https://aa.usno.navy.mil/faq/RST_defs) fra US Naval Observatory
- [TimeandDate](https://www.timeanddate.no/astronomi/) - nyttig norskutviklet nettsted for alt som har med tid å gjøre

![Beregning av zenith](/images/examples/zenith.png)