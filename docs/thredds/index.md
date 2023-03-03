---
layout: page
title: THREDDS
parent: Generelle ressurser
date: 2022-02-09
author: Martin L. Sætra
---

# THREDDS

## Spørring mot THREDDS-server hos MET

For å jobbe mot data som ligger i gitter/grid på THREDDS-servere så bruker vi
protokollen OPeNDAP. Denne kan aksesseres via HTTP, men det er vanligst å bruke
et eget bibliotek for dette, som f.eks. [FIMEX](https://wiki.met.no/fimex/start)
(C) eller [NetCDF-Java](https://www.unidata.ucar.edu/downloads/netcdf-java/) (Java).
Sistnevnte kan også brukes direkte i Kotlin. **Det er imidlertid problemer med å
bruke dette under Android.** Som ett av teamene i 2022 forklarer:

> Problemet med Netcdf i Android Studio ligger i hvordan Netcdf utfører
> HTTPS-forespørsler. I filen `EasySSLProtocolSocketFactory.java` prøves det å
> lage en instans av klassen `KeyManagerFactory` med en hardkodet algoritme
> "SunX509". Denne algoritmen er ikke tilgjengelig i Android sin kjøretid, så
> det kastes en `NoSuchAlgorithmException`. Her er en enkel reproduksjon av
> problemet (med stacktrace i README-filen):
>
> <https://github.com/filiphorvei/NetcdfError>
>
> Vi prøvde oss frem med litt forskjellige versjoner av Netcdf, inkludert
> netCdfAll-5.5.2 som det er lenket til i kursdokumentasjonen, og
> "edu.ucar:netcdf:4.3.22" fra Maven. Vi endte til slutt opp med å bruke 4.3.22
> i appen, så vidt jeg husker fordi den versjonen fungerte helt fint på
> HTTP-lenker (smittepress), imens 5.5.2 ikke fungerte på noe som helst.
>
> Her er en åpen GitHub-issue med noen som hadde samme feil som oss på
> netCdfAll-5.5.2, ikke med Netcdf men likevel:
>
> <https://github.com/rubenlagus/TelegramBots/issues/1012>
>
> Så det er noe som fungerer i et vanlig Java-miljø, men ikke når man kjører på
> Android.

### Eksempelkode

- [example.java](./example.java) - minimalt eksempel på bruk av NetCDF Java

Dette eksempelet bruker litt eldre funksjonalitet, og det er naturligvis flere
måter å gjøre dette på.

Avhengigheter:

 * NetCDF Java <https://www.unidata.ucar.edu/downloads/netcdf-java/>
 * SLF4J <https://repo1.maven.org/maven2/org/slf4j/slf4j-jdk14/1.7.36/>

## Dokumentasjon

Brukerdokumentasjon finnes her:

- [NetCDF-Java](https://docs.unidata.ucar.edu/netcdf-java/current/userguide/index.html)
- [Javadoc](http://javadox.com/edu.ucar/netcdf/4.2/overview-summary.html) som også dekker pakken `ucar.nc2.dt` som brukes i Java-eksempelet over

## THREDDS Data Server, OPeNDAP og NetCDF – hvordan forstå, og bruke, data

Hvis en tar en titt på siste varsel (filen med "fc" – altså forecast – i navnet) i https://thredds.met.no/thredds/catalog/fou-hi/norkyst800m-1h/catalog.html, og går inn på "Godiva2" under "Viewers" i bunnen, så kan de ulike variablene som ligger i filen visualiseres. Ved å velge for eksempel sea_water_salinity så kan en bla nedover i dypet, og antall dybdemeter vil vises i dropdown-menyen "height". Oppløsningen i dypet ikke er uniform. Grunnen til at at avstanden mellom lagene øker med dypet er at det skjer mindre i dypet. Vannmassene er mer homogene.

NetCDF-formatet, som dataene ligger på, er også selvdokumenterende. Hvis vi går inn på "OPENDAP" under "Access" (fra kataloglenken ovenfor) så vil vi se at for eksempel salinity har dimensjonene "time", "depth", "Y" og "X". Hvis vi så hadde listet innholdet i dimensjonsvariabelen depth, så ville vi kunne se alle dybdenivåene i meter.

Y og X vs. lat og lon: Det som gjør det litt vanskelig å direkte indeksere i horisontal utstrekning er at en må gå "via" Y og X for å finne geografiske koordinater lat og lon. Grunnen til dette er at alle variablene er lagret med en projeksjon, som gjør at det er forskjellig avstand mellom to gitter-punkter/verdier langt sør og lang nord. Så lenge en kun forholder seg til punkter så betyr imidlertid ikke dette med projeksjonen noe, det blir først viktig i det en vil tegne et felt (altså noe med en 2D-utstrekning).
