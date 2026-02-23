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

- [Caseliste for årets kurs](./2026/)<br>
  Beskrivelse og ressurser spesifikt for hvert case

- [Tidligere års kurs](./old)<br>
  Caselister og annen info

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

All tekst på disse sidene kan lastes ned fra
[GitHub](https://github.com/metno/in2000/) og er lisensiert under Norsk lisens
for offentlige data (NLOD) og Creative Commons 4.0 BY International, se [Frie
meteorologiske data](https://www.met.no/frie-meteorologiske-data/lisensiering-og-kreditering).
Det samme gjelder illustrasjoner dersom ikke annet er angitt.

Innholdet er generert vha [Jekyll](https://jekyllrb.com/) og [Just the
Docs](https://github.com/just-the-docs/just-the-docs).
