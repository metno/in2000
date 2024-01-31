---
layout: page
title: Case 1. Rakettoppskytning
parent: Årets caser
date: 2024-01-26
author: Geir Aalberg
---

![](/images/portalspace.png)

Lag en app for planlegging av rakettoppskytninger!

## Bakgrunn

Vi er i kontakt med rakettbyggegruppen på UiO som ønsker værdata, og ser på
muligheten til å sette opp en egen tjeneste for dette. Her kan da studentene
bygge en app for dette formålet og kanskje også se en oppskytning live mens de
bruker appen?

Ved en rakettoppskytning så er det mange faktorer som skal stemme, og en faktor
som vi ikke kan kontrollere er været. Derfor trenger vi kontinuerlig oppdatert
data på hvordan været kommet til å utvikle seg gjennom oppskytningsvinduet vårt.
Dette ville vanligvis vært jobben til en dedikert værstasjon, men vi ønsker å
undersøke om vi kan bruke åpen værdata til å gjøre et estimat.

## Krav

Det vi all hovedsak ser etter, er om det er forsvarlig å skyte opp i løpet de
neste timene. For å vite om dette er mulig er det flere kriterier som hukes av.

### Sikt

Vi vil se raketten under oppskytning. Både for å kunne ivareta sikkerhet, men
også for å få opptak av oppskytningen. Derfor er det viktig å vite sikten man
kan forvente under oppkskytningsvinduet. Lave skyer kan føre til at sikten blir
reduset, i tillegg til tåke.

### Nedbør

Siden vi jobber med elektronikk og kryogeniske væsker så er det viktig å være
varsom med fukt og temperatur. Kryogeniske væsker gjør all fukt til is som er
problematisk hvis det skjer i ventiler eller inni raketten. Elektronikk liker
sjeldent vann og fukt, og derfor ønsker vi å skjerme rakett så mye som mulig.
Derfor er det viktig å vite om det er meldt nedbør innen oppskytningsvinduet
eller spesielt høy luftfuktighet den dagen.

### Vindhastighet ved forskjellige høyder

Raketten er lett å påvirke når den beveger seg sakte. Derfor kan vind
uforsigbart påvirke nedfallområde på to kritiske stadier i den ballistiske
banen, oppskytning og ved fallskjermsfasen. Ved oppskytning vil raketten bevege
seg sakte og vil dermed ikke være like stabil som den når den har en høyere
hastighet. I fallskjermsfasen daler raketten sakte ned mot bakken etter at
fallskjermen er løst ut. Dette kan føre til at raketten beveger seg langt
horisontalt ved for sterk vind. Alt dette kan påvirke nedfallsområde som vi
ønsker å minimere av sikkerhetsmessige årsaker.

### Juridiske begrensninger

Med tanke på at løsning skal være for et generelt use case så er det viktig at
oppskytning skjer på godkjent plass. Vi fokuserer ikke på grunneier eller
nødetater i denne løsningen ettersom det er individuelle avtaler. For
Luftfarttilsynets del så må de også kontaktes i god tid før oppskytning, men de
har klare retningslinjer. Blant annet er det ikke lov å skyte opp i kontrollert
luftrom. Dermed kan løsning inkludere om oppskytningsposisjon er innen
kontrollert luftrom.

## Datakilder

### [Locationforcast](https://api.met.no/weatherapi/locationforecast/2.0/documentation)

Denne gir mye relevant data på flere av punkter under kravet, men inneholder
ikke informasjon om vindstyrke på høyder > 10 m over bakken. Til dette trenger vi et annet
API.

### [Isobarcgrib](https://api.met.no/weatherapi/isobaricgrib/1.0/documentation) (GRIB2 for southern_norway)

Her kan man laste ned filer i GRIB2-format som gir informasjon om trykk på
forskjellige nivåer. Dette kan vi bruke til å finne vind på forskjellige høyder.
I filene angis ikke høyde i meter men i trykkflater (isobarer), siden flyenes
høydemåler baserer seg på trykk.

For å regne ut høyde over havet kan man bruke [den hydrostatiske ligningen](https://en.wikipedia.org/wiki/Barometric_formula).
Da må man vite flg:

- trykk i høyden (GRIB)
- temperatur i høyden (GRIB)
- lufttrykk ved havnivå (locationforecast)
- (geopotensialet?)

NB: IsobaricGRIB leverer filer på ca 1.3 MB. Dette er kanskje uegnet å parse i
en mobilapp? I såfall er det mulig å bruke et Python-basert API som laster
ned GRIB fra apiet og leverer en vertikalprofil som CoverageJSON for et gitt punkt.

<https://github.com/metno/edrisobaric>

### [THREDDS (MEPS)](https://thredds.met.no/thredds/metno.html)

Det er også mulig å laste ned modelldata direkte fra thredds.met.no, men filene er
kjempestore (5 GB) og biblioteket for å hente data (NetCDF-Java) lar seg ikke kompilere
på Android pga manglende støtte for kryptering.

## Kontaktinformasjon / andre ressurser

- [Portal Space nettside](https://www.portalspace.no/)
- Håkon Offernes, Chief Electrical Officer, <haakono@portalspace.no>, +47 466 14 464
