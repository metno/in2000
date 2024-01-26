---
layout: page
title: Case 1. Sol og måne
parent: 2023
grand_parent: Tidligere års caser
date: 2023-02-21
author: Geir Aalberg
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

For å kvalitetssikre at beregningene deres er korrekte skal appen sammenlikne
resultatet med følgende datakilder og vise forskjellen i en tabell:

- Sunrise 2.0 [API](/general) (XML) [(dokumentasjon)](https://docs.api.met.no/doc/sunrise/astro)
- Sunrise 2.1 [API](/general) (XML, samme som over men med noen bugfikser)
- Sunrise 3.0 [API](/general) (GeoJSON) [(dokumentasjon)](https://docs.api.met.no/doc/sunrise/celestial)

Dersom deres konklusjon er at det ikke er praktisk gjennomførbart å gjøre slike
beregninger med dagens mobilteknologi, er dette også et fullt ut godkjent resultat.
I så fall er det ikke selve appen som vil vektlegges, men rapporten hvor dere forklarer
de tekniske begrensningene.

{: .note }
[Yr.no](https://www.yr.no/) har nå gått over fra Sunrise til å bruke et internt
C#-bibliotek. Ta gjerne stikkprøver derfra med i sammenlikningen, fortrinnsvis i
perioden nærme midnattsol for å sjekke om solnedgang skjer etter midnatt.

## Hjelpemidler og referanser:

### Kode

- [Astronomy Engine](https://github.com/cosinekitty/astronomy/tree/master/source/kotlin) - astronomisk Kotlin-bibliotek
- [Kildekode for Sunrise/3.0](https://github.com/metno/celestial) - Python, **nå på GitHub**

### Data og dokumentasjon

- [Almanakk for Norge](https://www.mn.uio.no/astro/tjenester/publikum/almanakken/) - den autorative kilden, med ekstramateriale fra Institutt for teoretisk astrofysikk
- [Definisjoner på soloppgang og solnedgang](https://aa.usno.navy.mil/faq/RST_defs) fra US Naval Observatory
- [Kalkulator](https://aa.usno.navy.mil/data/RS_OneDay) fra samme sted
- [TimeandDate](https://www.timeanddate.no/astronomi/) - nyttig norskutviklet nettsted for alt som har med tid å gjøre

![Beregning av zenith](/images/examples/zenith.png)
