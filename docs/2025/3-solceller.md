---
layout: page
title: Case 3. Installasjon av solcellepaneler
parent: Årets caser
date: 2025-01-30
author: Geir Aalberg
---


![Tegning av takflater](https://datalandsbyen.norge.no/assets/uploads/files/1645011766071-otovo_ditt_tilbud_takflater_2022-02-08-11_20_58.png)


## Bakgrunn

Strømprisene har gått opp mye de siste årene, og selv om politikerne overbyr
hverandre i å love støtteordninger hver gang det er valg er fremtiden usikker.
Ved å produsere sin egen strøm vil man kunne ha forutsigbare kostnader og på
sikt trolig spare penger.

Selv om man skulle tro at solcellepaneler fungerer dårligere i våre nordlige
strøk enn i syden stemmer ikke dette. Solceller fungerer optimalt i minus 5°, og
dårlig ved temperaturer over 25°. Så lenge det ikke er snø kan solceller produsere
mer energi i Sør-Norge enn i Afrika.

Kostnadene for å montere solceller kan dog være høye, og effekten variere.
Derfor bør man på forhånd å lage estimater på utgifter og innsparing før man bestemmer seg.
Oppgaven blir å lage en app som kan hjelpe til med dette, og som minimum kan
beregne forventet effekt i kilowattimer (kWh).

Solceller finnes i mange effekt- og prisklasser, her bør dere sjekke markedet og finne
typiske eksempler.
Man kan søke om Enova-støtte på opptil 32.500 (tidligere 47.500) kroner hvis
man produserer strøm som kan tilbakeføres strømnettet uansett kilde (sol, vind, vann).
Det er også mulig å få støtte til fritidsboliger.

## Funksjonelle krav

Det forventes at brukeren selv oppgir gateadresse, og manuelt legger inn
areal/vinkel/retning for aktuelle takflater.

Må kunne:

- slå opp adresser for å finne kartkoordinater
- finne snittverdier for temperatur, snø og skydekke for området fra Frost
- beregne gjennomsnittlig forventet innkommende solenergi basert på influx, posisjon, skydekke og snø
- beregne forventet strømproduksjon (kWh) ut fra virkningsgrad og temperatur


Bør kunne:

- vise eiendommen i kart
- anslå forventet besparelse i strømregning ut fra HvaKosterStrømmen, Enova-støtte og [regjeringens strømtiltak](https://www.regjeringen.no/no/tema/energi/regjeringens-stromtiltak/id2900232/)
- forklare hva man kan drive med forventet produksjon på hytte ikke tilkoblet strømnettet
- beregne lønnsomhet ved installasjon av solcellepaneler gitt typiske priseksempler

Gjerne også:

- la bruker tegne inn polygon i kart for takflate og beregne areal/innfallsvinkel
- beregne lønnsomhet for andre [private strømkilder](https://www.enova.no/privat/alle-energitiltak/solenergi/solcelleanlegg/) (vindkraft, vannkraft, [kjernekraft](https://allthatsinteresting.com/david-hahn))

## Datakilder

- Klimadata fra [Frost](https://frost-beta.met.no/) **(obligatorisk)**
- [Photovoltaic Geographical Information System (PVGIS)](https://joint-research-centre.ec.europa.eu/photovoltaic-geographical-information-system-pvgis_en) - historisk innkommende solstråling
- [HvaKosterStrømmen?](https://www.hvakosterstrommen.no/strompris-api) - strømpriser nå og tidligere
- [Elhub API](https://tadata.no/providers/c6a9cb66-8b97-4b46-91c2-8225895f514b) - samler inn måledata fra alle Norges strømmålere

## Dokumentasjon

- [Solcellepanel effekt - hva er virkningsgrad?](https://www.otovo.no/blog/solcellepanel-solceller/solceller-norge-virkningsgrad/)
- Priseksempler for installasjon: [her](https://www.fjordkraft.no/solcellepanel/solcellepanel-pris/), [her](https://prisnorge.no/2025/01/11/solcellepanel-8-prisguider-for-installasjon/), [her](https://www.solsmart.no/pris/solcellepanel), [her](https://www.boligsmart.no/pris/solcellepanel-tak) og [her](https://solceller.no/panel-pris)
- [Regjeringens strømtiltak](https://www.regjeringen.no/no/tema/energi/regjeringens-stromtiltak/id2900232/)
- [Enova-støtte](https://www.enova.no/privat/alle-energitiltak/solenergi/solcelleanlegg/)

## Inspirasjon

- [Tilbud om solceller ved hjelp av bygningsdata - Otovo](https://datalandsbyen.norge.no/topic/150/tilbud-om-solceller-ved-hjelp-av-bygningsdata-otovo)
- [Solcellepanel: 8 Prisguider for Installasjon](https://prisnorge.no/2025/01/11/solcellepanel-8-prisguider-for-installasjon/)

## Spørsmål?

Kontakt <a href="mailto:observasjon@met.no">observasjon@met.no</a> for spørsmål ang Frost.
