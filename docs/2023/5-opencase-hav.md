---
layout: page
title: Case 5. Åpent case - på havet
parent: Årets caser
date: 2023-02-21
author: Geir Aalberg og Martin Sætra
---

Her er det fritt valg hva slags app man vil lage, men det må være relatert
til havet og bruke de obligatoriske datakildene.
Forslaget krever godkjenning fra veileder/kursledelsen.
Vi anbefaler å sjekke tidligere års caser for inspirasjon og datakilder.

Kontaktperson ang dette caset er [Martin Sætra](mailto:martinls@met.no).

## Krav

Alle som har tilknytning til havet må forholde seg til naturkreftene, det
være seg for ferdsel på sjøen, havbruk eller lyn og torden om sommeren.
**Det er derfor er obligatorisk å bruke *alle* følgende tjenester fra api.met.no:**

- Oceanforecast [API](/general) - strøm, bølger, temperatur
- Locationforecast eller Nowcast [API](/general) - vær og vind
- MetAlerts [API](/general) (enten XML eller GeoJSON)

Andre datakilder som kan være nyttige:

**MET APIer**:

- [Havvarsel-Frost](/havvarsel/) - nesten-live observasjoner av temperatur lange norskekysten
- Gribfiles [API](/general) - værdata for nedlasting til navigasjonsapper
- Textforecast [API](/general) - tekstvarsler for kyst og fiskebanker
- [Tidalwater](/weatherapi/tidalwater/1.1/documentation) - tidevann for havner
- Sunrise [API](/general) - ferdsel i mørke krever ekstra forhåndsregler

**Andre dataleverandører:**

- [Se havnivå](http://xn--sehavniv-h0a.no) - tidevann- og vannstandsdata langs norskekysten fra Kartverket
- [OpenSeaMap](http://www.openseamap.org/index.php?id=openseamap&L=1) - frie sjøkart i WMS-format
- [Kartlag med værdata](/wms/) i WMS-format (foreløpig noe ustabile i drift)
- [Oslo Kommunes API for badeplasser](https://www.oslo.kommune.no/natur-kultur-og-fritid/tur-og-friluftsliv/badeplasser-og-temperaturer/)

## Eksempler

Noen forslag basert på tidligere løsninger:

### Ferdsel til havs

**App for småbåtførere og seilere som viser vind og strøm langs kysten.**
De fleste båtførere har i dag navigasjonssystemer som viser sjøkart med
dybdeforhold og skipsleier, men disse inkluderer vanligvis ikke været.
Det er mulig å lage en app som viser vind- og strømforhold på sjøkart, gjerne
også kombinert med å regne ut effektiv fart og beregnet tid per distanse.
Noen har også tidligere laget spesialiserte apper for redningsmannskap, som
har vist seg å bli godt mottatt og hatt kommersielt potensiale.

![Eksempel fra 2020 (appen Fimafeng)](/images/examples/fimafeng.png)

### Vannsport

**App for sportsdykkere, surfere og brettseilere for å finne tid/sted med fine forhold.**
Strøm, bølger og tildels temperatur er viktig for å planlegge sportsaktiviteter
til sjøs, og noe man naturligvis ikke gjør hvis det er utstedt maritime farevarsler.
Her har det tidligere år kommet inn flere kreative løsninger.

![Eksempel fra 2022 (appen Surfespot)](/images/examples/surfespot.png)

Prisen for mest kreativ bruk av METs data gikk i fjor til et team som hadde
kjørt en regresjonsanalyse av data fra Oceanforecast og laget en formel som
beregnet de beste surfestedene i Norge:
![Prisvinnende formel](/images/examples/regresjonsmodell_surfespot.png)

### Badetemperaturer langs kysten

**App som viser temperaturer langs Norskekysten.**
Det samles inn “live” observasjoner fra bøyer plassert ved populære badesteder
rundt omkring i hele landet. Flere aktører står for innsamlingen, men alle
observasjonene kan hentes ut fra en egen Frost-server hos Meteorologisk
institutt, som vi kaller [Havvarsel-Frost](/havvarsel/).

Oslo Kommune har også et API for badetemperaturer, men de begynner typisk ikke å
samle inn målinger før 1. juni.

I tillegg er det mange som har observert at prognosene fra [Oceanforecast](/general)
stemmer ganske bra overens med målingene (max 1° differanse). Denne dekker også
hele kysten, ikke bare offentlige badeplasser og er derfor mer praktisk hvis man
fx er ute og ferdes i båt.

Uansett hvor man bader er det viktig å få med seg værvarslet, siden de færreste
synes det er stas å bade når det regner eller blåser. Farevarsler er det ikke så
mange av i badesesongen, men det vil etterhvert på våren komme farevarsler om lyn, noe
som ikke er så kjekt når man er i nærheten av vann.

Noen ideer til inspirasjon:
 * Kart med “live” badetemperaturer plottet inn på kjente badesteder.
 * Rangering av strender etter vanntemperatur, lufttemperatur, minste forskjell i vanntemperatur og lufttemperatur osv.
 * Hvilken tid på døgnet er det mest behagelig å bade?
 * Legge til flere parametre, som for eksempel soloppgang og solnedgang, eller flo og fjære.
 * Hvor gode er varslene/prognosene fra api.met.no til å predikere badetemperaturer? Sammenligning av Oceanforecast-varsler og observasjoner.
 * Kombinere observasjoner og varsler - inkludert “nowcasting”?
 * Offshore operasjoner - mulighetsvinduer for vedlikehold osv.

![Badetemperaturer](/images/examples/badetemp.jpeg)
