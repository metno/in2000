---
layout: page
title: Case 5 - Oppdrettsanlegg
date: 2022-02-09
---

Lag en app som viser miljøforhold ved et oppdrettsanlegg for laks. Oppdrettsindustrien i Norge foregår for det meste som oppdrett av laks i åpne merder i sjøen. Fisken påvirkes av det omliggende miljøet på en direkte måte. Det fysiske miljøet ved en oppdrettslokalitet, det vil si vannets saltholdighet, temperatur og bevegelse (strøm), kan variere mye fra dag til dag. Det vil være av interesse for fiskeoppdrettere å kunne få en indikasjon på hvordan miljøforholdene på anlegget deres vil endre seg de neste dagene.

Havmodellen NorKyst-800 beregner daglig nødvendige parametere på et horisontalt rutenett med 800 m oppløsning for hele landet time for time og ca. to døgn fram i tid. Andre
sammensatte parametere som tykkelsen på blandingslaget eller statistiske forhold kan være
interessant å inkludere. Det samme gjelder muligheten for å beskrive forventet smittepress fra lakselus.

Miljøforhold ved oppdrettsanlegg er interessant både for havbruksnæringa og de som regulerer denne. Det er viktig å overvåke hvordan denne næringen påvirker miljøet, slik at drift kan skje på en bærekraftig måte.

## Noen ideer til inspirasjon
 * Kart med plassering av oppdrettsanlegg
 * Tidsserier av saltholdighet, temperatur og strøm fra lokaliteten
 * Tidsserier av beregnet blandingslagsdyp fra lokaliteten
 * Smittepress fra lakselus ved lokaliteten de siste ukene
 * Værvarsel ved lokaliteten

## Datakilder
Primære (obligatisk) - se [egen side for THREDDS](/thredds/):
 * Daglige verdier av resultater fra strømmodellen [NorKyst-800](https://thredds.met.no/thredds/catalog/fou-hi/norkyst800m-1h/catalog.html)
 * [Ukentlige verdier av beregnet smittepress fra lakselus](http://thredds.nodc.no:8080/thredds/catalog/smittepress_new2018/catalog.html) basert på NorKyst-800

Sekundære (valgfritt) – se [Generelle ressurser](/general):
 * Oceanforecast

### Avhengigheter
 * NetCDF Java <https://www.unidata.ucar.edu/downloads/netcdf-java/>
 * SLF4J <https://repo1.maven.org/maven2/org/slf4j/slf4j-jdk14/1.7.36/>

## Mest relevante interessenter
Havforskningsinstituttet, Eide Fjordbruk, SEARIS og andre oppdrettsselskaper.
