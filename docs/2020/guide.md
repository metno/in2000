---
layout: default
title: IN2000 guide 2020
date: 2021-02-19
author: Geir Aalberg
---

# Hvordan bruke api.met.no

Les [vilkår for bruk](TermsOfService) og [lisens](License).

Spørsmål om api.met.no og Frost kan sendes til <a href="mailto:in2000-help@met.no">in2000-help@met.no</a>.

## Proxy

Bruk IFI-proxyer der hvor mulig:

- [https://in2000-apiproxy.ifi.uio.no/](https://in2000-apiproxy.ifi.uio.no/)
- [https://in2000-frostproxy.ifi.uio.no/](https://in2000-frostproxy.ifi.uio.no/)

## Requester

Kun HTTPS støttes, HTTP vil bli redirected.

Sjekk alltid statuskoder:

- 200: OK
- 203: OK, men vil slutte å virke snart
- 403: Banhammer!
- 429: Throttling, slakk av trafikken umiddelbart

Sjekk levetid og ikke kall før utløpt:

    Expires: Tue, 12 Mar 2019 09:33:57 GMT

Ikke send unødige kall, og ikke når appen ikke er i bruk.

Bruk unik User-Agent header for å unngå throttling:

    `$ curl --user-agent 'gruppenavn'`

## Formater:

GPS-koordinater trunkeres til 3 desimaler. Ikke send request for hver meter!

Alle tidspunkter i GMT på ISO-format: 2019-01-15T12:00:00Z.

For XML, bruk en parser og XPath for å plukke ut data. Noen steder funker også
[konverting til JSON](/weatherapi/locationforecast/1.9/.json?lat=60.10&lon=9.58).

Navn på variabler og parametre er forsøkt holdt seg innenfor CF-standarden hvis mulig.
Denne er ganske omfattende, dere kan finne forklaringer på termene på
[cfconventions.org](http://cfconventions.org/Data/cf-standard-names/70/build/cf-standard-name-table.html).
