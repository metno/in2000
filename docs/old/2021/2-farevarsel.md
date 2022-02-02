---
layout: default
#title: IN2000: Case 2. Farevarsler
date: 2021-02-19
author: Geir Aalberg
---

# Case 2. Farevarsler

Hent CAP-varsler fra MetAlerts og vis farenivå samt geografisk omfang.
CAP-filene og RSS-feeden er i XML-format, bruk en XML-parser og evt XSLT for å
vise som tekst.

CAP-filene inneholder lat/lon-polygoner som er laget for å kunne plottes i kartløsninger.
Kombiner gjerne med simulert GPS-posisjon for å finne farevarsel på nåværende
sted.

Historiske varsler er tilgjengelige per måned fom januar 2019. Bruk disse for å
vise sesongvariable varsler som er relevante for appen.

# Mulige ideer til app:

- Varsel om skogbrannfare (sommer)
- Varsel om dårlig vær og snøskredfare for turgåere (vinter)
- Varsel om fare for flo og storm langs kysten (aktuelt for båteiere og forsikringsselskaper, gjerne kombinert med værvarsel for båtførere)

# Datakilder:

Primær (obligatorisk):

- [MetAlerts](https://api.met.no/weatherapi/metalerts/1.1/documentation):
  [RSS-feed](https://api.met.no/weatherapi/metalerts/1.1/) med linker til
  CAP-varsler

Sekundære (valgfritt):

- Locationforecast
- Nowcast
- Textforecast (spesielt aktuelt for kysten og fiskebankene)
- Oceanforecast (ny versjon under arbeid)
- [Forestfireindex](https://api.met.no/weatherapi/forestfireindex/1.1/documentation) (under utfasing, men skal ikke slås av før tidligst juli)
- [CAP-varsler fra NVE](http://api.nve.no/doc/) (samme format som MetAlerts, burde kunne parses med samme kode). Eksempler:
  - Flom
  - Jordskred
  - Snøskred



