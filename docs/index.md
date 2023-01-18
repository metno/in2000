---
layout: default
title: IN2000 kursressurser
date: 2023-02-17
author: Geir Aalberg
---

# Kursressurser for IN2000

Dette er en oversikt over ressurser (primært fra MET) som studentene kan
bruke på de forskjellige casene i kurset.

## Generelle APIer

- [Introduksjon til METs APIer](./intro)<br>
  Hvordan bruke api.met.no, Frost m.m.

- [Generelle API ressurser for alle caser](./general)<br>
  Produkter og tjenester som er relevante uansett case

- [Caseliste for årets kurs](./2023/)<br>
  Ressurser spesifikt for hvert case

## Kontaktinfo

For spørsmål vedr METs tjenester, send en epost til en **(og kun én)** av følgende adresser alt
etter hva dere lurer på:

- api.met.no: <weatherapi-adm@met.no>
- frost.met.no: <observasjon@met.no>
- havvarsel-frost.met.no: <martinls@met.no> (kun datainnhold, for teknisk hjelp bruk samme som Frost)
- thredds.met.no: <thredds@met.no>

Merk eposten med "IN2000" i subject-feltet så vi skjønner hva det er snakk om. Ikke send til flere adresser
samtidig, da ender vi opp med multiple saker i forskjellige systemer som genererer mye ekstraarbeid og rot.

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
