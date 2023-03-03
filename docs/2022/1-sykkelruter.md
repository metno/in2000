---
layout: page
title: Case 1. Sykkelruter i Oslo
parent: 2022
grand_parent: Tidligere års caser
date: 2022-02-18
---

Lag en app som viser anbefalte sykkelruter i Oslo tatt i betraktning trafikk,
vær, luftkvalitet og andre mulige faktorer. Oslo Kommune har laget et API hvor
man kan laste ned koordinater for alle sykkelveier og vise på kart. MET tilbyr
både prognoser og faktiske målinger av svevestøv og NOx for storbyer som viser
hvor det er minst forurensning.

## Datakilder

Følgende datakilder er **obligatoriske**:

- minst ett værvarsel (Locationforecast eller Nowcast)
- minst en kilde til luftkvalitet (MET eller NILU)
- anbefalte sykkelruter (fx fra Oslo Kommune)

### MET:

Se [Generelle ressurser](/general)

- Locationforecast
- Nowcast
- Airqualityforecast - prognoser for luftkvalitet

### NILU:

- [NILU API](https://api.nilu.no/) - målinger av luftkvalitet (sanntid og historisk)


### Oslo Kommune:

- [Skiltede byruter for sykkel](https://developer.oslo.kommune.no/katalog/data/bym-byruter) - Nedlastbart datasett
- [Sykkelparkering](https://developer.oslo.kommune.no/katalog/data/bym-sykkelparkering) - Nedlastbart datasett
- [Sykkelkart](https://www.oslo.kommune.no/gate-transport-og-parkering/sykkel/sykkelkart/#toc-3) (Google Maps)

Kommunen holder på å utvikle en ny versjon av dette APIet. Vi regner med dagens versjon
vil fungere til sommeren, men de har lovet å gi oss beskjed dersom det komme
endringer her i løpet av semesteret.

### Eksempel

Løsning fra 2020:

![Eksempel fra 2020](/images/examples/sykkel2.png)
