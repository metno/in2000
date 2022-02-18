---
layout: page
title: Havvarsel-Frost
date: 2022-02-13
author:
---

## Eksempler på spørring mot Havvarsel-Frost-server

Disse spørringene er laget interaktivt ved å bruke Swagger-dokumentasjonen for
`/api/v1/obs/badevann/get`, som er tilgjengelig her:

- <https://havvarsel-frost.met.no/docs/apiref#/obs/badevann>

### Metadata

Returner alle bøyer som har tidsserier i perioden 2016–2020 (uten observasjoner, kun metadata/informasjon om bøyene)

- <https://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=false&buoyids=%2A&parameters=%2A>

eller med curl (for testing):

    curl -X GET "https://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2020-12-31T23%3A59%3A59Z&incobs=false&buoyids=%2A&parameters=%2A" -H "accept: application/json"

### Badetassen

Returner alle observasjoner gjort av bøye med ID 5 i perioden 2016–2020 fra badetassen.no

- <https://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2021-12-31T23%3A59%3A59Z&incobs=true&buoyids=5&sources=badetassen%2Eno&parameters=%2A>

eller med curl (for testing):

    curl -X GET "https://havvarsel-frost.met.no/api/v1/obs/badevann/get?time=2016-01-01T00%3A00%3A00Z%2F2021-12-31T23%3A59%3A59Z&incobs=true&buoyids=5&sources=badetassen%2Eno&parameters=%2A" -H "accept: application/json"
