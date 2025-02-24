---
layout: page
title: Case 5. Åpent case
parent: 2024
grand_parent: Tidligere års caser
date: 2024-01-26
author: Geir Aalberg
---

Selv om vi får mange positive tilbakemeldinger på våre tjenester, er det også
noen klager. En av de tingene vi hører oftest er at de fleste tjenester ser ut
til å være laget av forskjellige folk som ikke snakker sammen (som ikke er helt
usant). Dette fører til at lærekurven for å bruke et nytt produkt blir
uforholdsmessig høy når man allerede har lært seg å bruke andre.

Mye av årsaken skyldes mangelen på etablerte standarder for API-grensesnitt.
Her har [OpenAPI](https://www.openapis.org/what-is-openapi) gjort mye for å gjøre
det enklere å lage klienter, men å forstå hvordan man søker og tolker data er
fortsatt like uoversiktlig.

## OGC API - Environmental Data Retrieval

En nye standard som holder på å etablere seg innen geofag er [EDR](/edr/) fra
[OGC](https://www.ogc.org/). I praksis vil det kun bety noe annerledes URLer, fx:

- <https://api.met.no/weatherapi/locationforecast/2.0/edr/collections/complete/position?coords=POINT(10+60)&z=123> †

i stedet for

- <https://api.met.no/weatherapi/locationforecast/2.0/complete?lon=10&lat=60&altitude=123>

† (Her er "+" URL-enkoding for mellomrom slik at linken ikke blir brutt opp.)

Selve [spesifikasjonen](https://www.ogc.org/standard/ogcapi-edr/) er ganske
tunglest, og det er ikke lett å lage å lage servere som leverer data på
EDR-format. Likevel mener mange at å konsumere EDR bør være ganske lett, siden
det bare er å navigere seg fram til passende URLer med Swagger/OpenAPI som
hjelp.

Oppgaven til dere blir derfor å finne ut om EDR er så lett å forstå at alle
utviklere kan bruke dette som standard søkegrensesnitt, eller om det kun er egnet
for eksperter innen geofag, og vi må lage enklere alternativer for "vanlige" utviklere.

Vi stiller derfor som krav at teamene må bruke EDR alle steder hvor det er
tilgjengelig, inkl produkter på api.met.no hvor dette er implementert. Dette skal
utgjøre hovedfunksjonaliteten i appen.

## Funksjonelle krav

Her kan man lage hva slags app man vil, men den skal primært hente data via
EDR-standarden. Dere kan bruke hvilke EDR-tjenester dere vil, de må ikke være fra MET.
**Løsningsforslaget krever godkjenning fra veileder/kursledelsen, hvor dere må
oppgi hvilke EDR-tjenester dere planlegger å bruke.**

## Eksempler på EDR-tjenester

### MET

- [Produkter med EDR-støtte på api.met.no](https://api.met.no/swagger2-ui/index.html) (under arbeid)
- [interpol](https://interpol-b.met.no/) - diverse værvarsler
- [trapp-api](https://trapp-test.met.no/) - varseltavle
- [SWiM](https://swim-dev.met.no/) - METAR for flytrafikk (kan kombineres med Case 2)

Dokumentasjon:

- [EDRisobaric](https://github.com/metno/edrisobaric) - kildekode for EDR-server for flyværdata (kan kombineres med Case 2)
- METs [EDR-profil](https://github.com/metno/edr-profile) for værvarsler

### Andre dataleverandører

- [UK Met Office](https://labs.metoffice.gov.uk/edr)
- [Finske Meteorologiske Institutt](https://opendata.fmi.fi/edr)
- [Det Kongelige Nederlandske Meteorologiske Institutt](https://developer.dataplatform.knmi.nl/apis)
- [IBL SWIM](https://swim.iblsoft.com/data/opmet/edr) - METAR for flytrafikk (kan kombineres med Case 2)
