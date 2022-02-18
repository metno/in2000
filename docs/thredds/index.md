---
layout: page
title: THREDDS
date: 2022-02-09
author: Martin L. Sætra
---

## Spørring mot THREDDS-server hos MET

For å jobbe mot data som ligger i gitter/grid på THREDDS-servere så bruker vi
protokollen OPeNDAP. Denne kan aksesseres via HTTP, men det er vanligst å bruke
et eget bibliotek for dette, som f.eks. [FIMEX](https://wiki.met.no/fimex/start)
(C) eller [NetCDF-Java](https://www.unidata.ucar.edu/downloads/netcdf-java/) (Java).
Sistnevnte kan også brukes direkte i Kotlin.

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
