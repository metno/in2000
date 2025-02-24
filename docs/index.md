---
layout: home
title: Hovedside
nav_order: 1
date: 2023-02-17
author: Geir Aalberg
---

![UiO](/images/03_uio_full_logo_no_pos.png) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ![MET](/images/Met_RGB_Horisontal.jpg)

# Kursressurser for IN2000

Dette er en oversikt over ressurser (primært fra MET) som studentene kan
bruke på de forskjellige casene i kurset.

## APIer

- [Generelle API-ressurser for alle caser](./general)<br>
  Produkter og tjenester som er relevante uansett case

- [Caseliste for årets kurs](./2025/)<br>
  Beskrivelse og ressurser spesifikt for hvert case

- [Tidligere års kurs](./old)<br>
  Caselister og annen info

## Kontaktinfo

For spørsmål vedr METs tjenester, send en epost til en **(og kun én)** av følgende adresser alt
etter hva dere lurer på:

- api.met.no: <weatherapi-adm@met.no>
- frost.met.no: <observasjon@met.no>
- Yr.kart: <yr-maps@met.no>
- havvarsel-frost.met.no: <martinls@met.no> (kun datainnhold, for teknisk hjelp bruk samme som Frost)
- thredds.met.no: <thredds@met.no>
- PortalSpace: <haakono@portalspace.no>

Merk eposten med "IN2000" i subject-feltet så vi skjønner hva det er snakk om.
Ikke send til flere adresser samtidig, da ender vi opp med multiple saker i
forskjellige ticketsystemer, noe som genererer mye ekstraarbeid og rot.

{% comment %}

## Nyheter

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a><br/>
      <span class="post-meta">{{ post.date | date: "%-d %b %Y" }}</span>
    </li>
  {% endfor %}
</ul>

<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>

{% endcomment %}

## Lisensiering og kreditering

Alt innhold på disse sidene kan lastes ned fra
[GitHub](https://github.com/metno/in2000/) og er lisensiert under Norsk lisens
for offentlige data (NLOD) og Creative Commons 4.0 BY International, se [Frie
meteorologiske data](https://www.met.no/frie-meteorologiske-data/lisensiering-og-kreditering).

Innholdet er generert vha [Jekyll](https://jekyllrb.com/) og [Just the
Docs](https://github.com/just-the-docs/just-the-docs).
