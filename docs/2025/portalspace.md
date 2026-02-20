---
layout: page
title: Portalspace kravspesifikasjon
parent: 2025
grand_parent: Tidligere års caser
date: 2024-02-03
author: Håkon Offernes
---

![portalspace logo](/images/portalspace.png)

Det vi all hovedsak ser etter, er om det er forsvarlig å skyte opp i løpet de
neste timene. For å vite om dette er mulig er det flere kriterier som hukes av.

## Funksjonelle krav

|REQ-ID|Beskrivelse|Valgfri|
|-|-|-|
|REQ-1|Appen skal la bruker velge og lagre ett punkt som oppskytningssted .|Nei|
|REQ-2|Appen skal vise været på bakkenivå for de neste 4 timene. (se SREQ-2.1 til SREQ-2.8)|Nei|
|SREQ-2.1|Appen skal vise temperatur på bakkenivå for de neste 4 timene.|Nei|
|SREQ-2.2|Appen skal vise fuktighet på bakkenivå for de neste 4 timene.|Nei|
|SREQ-2.3|Appen skal vise gjennomsnittlig vindhastighet og hastighet i vindkast på bakkenivå for de neste 4 timene.|Nei|
|SREQ-2.4|Appen skal vise vindretning på bakkenivå for de neste 4 timene.|Nei|
|SREQ-2.5|Appen skal vise forventet nedbør for de neste 4 timene.|Nei|
|SREQ-2.6|Appen skal vise forventet sikt de neste 4 timene.|Nei|
|SREQ-2.7|Appen skal vise forventet duggpunktet de neste 4 timene.|Nei|
|SREQ-2.8|Appen skal vise forventet skydekke de neste 4 timene.|Ja|
|REQ-3|Appen skal vise vindretning og hastighet opp til 10 km høyde. |Nei|
|REQ-4|Appen skal vise retning og størrelse på Vindskjær mellom atmosfæriske lag opp til 10 km høyde. |Nei|
|REQ-5|Appen skal la bruker se på tilgjengelige relevante data minst 72 timer frem i tid. (Relevante data se SREQ-2.1 til SREQ-2.7) |Nei|
|REQ-6|Appen skal gi bruker en rapport om det er trygt å skyte opp den neste timen basert på verdier satt av bruker. |Nei|
|SREQ-6.1|Appen skal gi bruker en rapport om det er trygt å skyte opp på et valgt tidspunkt basert på verdier satt av bruker. |Ja|
|SREQ-6.2|Appen skal gi bruker en liste over gode oppskytningsvinduer minst 72 timer frem i tid. |Ja|
|SREQ-6.3|Appen skal la bruker sortere og filterer en liste over oppskytningsvinduer basert på værmelding for det tidsintervallet. |Ja|
|REQ-7|Appen skal vise faren for lyn de neste 4 timene og/eller avstand til nærmeste lyn-nedslag. |Ja|
|REQ-8|Appen skal fortelle bruker hva maksimal oppskytningshøyde (uten avtale med luftfartstilsynet) er på et punkt bruker velger.|Ja|
|REQ-9|Appen skal vise banen til en simulert oppskytning basert på data skrevet inn av bruker.|Ja|

## Forklaring

### Sikt (REQ-2)
Vi vil se raketten under oppskytning. Både for å kunne ivareta sikkerhet, men
også for å få opptak av oppskytningen. Derfor er det viktig å vite sikten man
kan forvente under oppskytningsvinduet. Lave skyer kan føre til at sikten blir
redusert, i tillegg til tåke.

### Nedbør (REQ-2)
Siden vi jobber med elektronikk og kryogeniske væsker så er det viktig å være
varsom med fukt og temperatur. Kryogeniske væsker gjør all fukt til is som er
problematisk hvis det skjer i ventiler eller inni raketten. Elektronikk liker
sjeldent vann og fukt, og derfor ønsker vi å skjerme rakett så mye som mulig.
Derfor er det viktig å vite om det er meldt nedbør innen oppskytningsvinduet
eller spesielt høy luftfuktighet den dagen.

### Vindhastighet ved forskjellige høyder (REQ-4)
Raketten er lett å påvirke når den beveger seg sakte. Derfor kan vind
uforutsigbart påvirke nedfallsområde på to kritiske stadier i den ballistiske
banen, oppskytning og ved fallskjermsfasen. Ved oppskytning vil raketten bevege
seg sakte og vil dermed ikke være like stabil som den når den har en høyere
hastighet. I fallskjermsfasen daler raketten sakte ned mot bakken etter at
fallskjermen er løst ut. Dette kan føre til at raketten beveger seg langt
horisontalt ved for sterk vind. Alt dette kan påvirke nedfallsområde som vi
ønsker å minimere av sikkerhetsmessige årsaker.

Vær spesielt oppmerksom på vindskjær (shear wind eller [wind
shear](https://en.wikipedia.org/wiki/Wind_shear)) som oppstår når vindretning
og/eller styrke endrer seg med høyden. Dette kan føre til rotasjon i objekter
som beveger seg mellom lagene. For å beregne dette må man bruke noen enkle
formler.

### Juridiske begrensninger (REQ-8)
Med tanke på at løsning skal være for et generelt use case så er det viktig at
oppskytning skjer på godkjent plass. Vi fokuserer ikke på grunneier eller
nødetater i denne løsningen ettersom det er individuelle avtaler. For
Luftfartstilsynets del så må de også kontaktes i god tid før oppskytning, men de
har klare retningslinjer. Blant annet er det ikke lov å skyte opp i kontrollert
luftrom. Dermed kan løsning inkludere om oppskytningsposisjon er innen
kontrollert luftrom.
Link til kart: [https://www.ippc.no/ippc/index.jsp](https://www.ippc.no/ippc/index.jsp)

## Ordliste

|Ord|forklaring|
|-|-|
|REQ|Requirement|
|SREQ|Sub-Requirement|
