---
layout: page
title: Case 5. Åpent case - på havet
date: 2023-02-21
---

Her er det fritt valg hva slags app man vil lage, men det må være relatert
til havet og bruke de obligatoriske datakildene.
Forslaget krever godkjenning fra veileder/kursledelsen.
Vi anbefaler å sjekke tidligere års caser for inspirasjon og datakilder.

Kontaktperson ang dette caset er [Martin Sætra](mailto:martinls@met.no).

## Krav

Følgende tjenester fra api.met.no er obligatoriske for alle apper, siden
alle som har tilknytning til havet må forholde seg til naturkreftene:

- Oceanforecast [API](/general) - strøm, bølger, temperatur
- Locationforecast eller Nowcast [API](/general) - vær og vind
- MetAlerts [API](/general) (enten XML eller GeoJSON)

Andre datakilder som kan være nyttige:

- Gribfiles [API](/general) - værdata for nedlasting til navigasjonsapper
- Textforecast [API](/general) - tekstvarsler for kyst og fiskebanker
- Sunrise [API](/general) - ferdsel i mørke krever ekstra forhåndsregler
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

### Vannsport

**App for sportsdykkere, surfere og brettseilere for å finne tid/sted med fine forhold.**
Strøm, bølger og tildels temperatur er viktig for å planlegge sportsaktiviteter
til sjøs, og noe man naturligvis ikke gjør hvis det er utstedt maritime farevarsler.
Her har det tidligere år kommet inn flere kreative løsninger.

### Badetemperaturer langs kysten

**App som viser badetemperaturer langs Norskekysten.**
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

### Fiskeoppdrett

**App som viser miljøforhold ved et oppdrettsanlegg.** Utbredelse av lakselus
påvirkes bl.a. av vannets saltholdighet, temperatur og bevegelse (strøm), og er et
mye større problem i Sør-Norge enn i Nord-Norge. Informasjon om dette er nyttig
for miljøvernere, vetrinærer og ansatte i bransjen, og er også relevant for å finne
hvor det er mest bærekraftig å legge nye oppdrettsanlegg.

Det er mulig å laste ned [ukentlige verdier av beregnet smittepress fra
lakselus](http://thredds.nodc.no:8080/thredds/catalog/smittepress_new2018/catalog.html)
fra NODC vha OPeNDAP-protokollen, se [egen side for THREDDS](/thredds/).
Nedlasting fra thredds.met.no fungerer ikke så bra siden den krever kryptering,
noe som Java-biblioteket for Android mangler.

Farevarsler er relevante siden uvær gjerne fører til store skader og rømming
av oppdrettsfisk som påvirker villfiskbestanden negativt. Man trenger derfor
tid til å sikre merdene for å minimere skader.

### Eksempler på tidligere løsninger

![Eksempel fra 2020 (appen Fimafeng)](/images/examples/fimafeng.png)
