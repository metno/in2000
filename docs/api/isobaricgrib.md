---
layout: page
title: IsobaricGRIB
parent: Generelle ressurser
nav_order: 2
date: 2024-02-15
author: Geir Aalberg
---

GRIB er et format for å laste ned rasterdata, som er mye brukt innen meteorologi.
APIet leverer GRIB-filer både for luftfart og for ferdsel til sjøs.

- [Isobarcgrib](https://api.met.no/weatherapi/isobaricgrib/1.0/documentation)

Her kan man laste ned filer i GRIB1- (Europa) og GRIB2-format (Sør-Norge), som
gir informasjon om vind og temperatur på forskjellige nivåer i atmosføren.
Det er hovedsaklig GRIB2 som er av interesse siden GRIB1-filene har svært lav oppløsning.

## Innhold

Filene er delt opp i flere lag med data. Hvert lag angir en trykkflate
fra 850 hPa (ca 1.5 km.o.h.) til 100 hPa. Hvert lag inneholder flg dataverdier:

- u (vind øst/vest)
- v (vind nord/sør)
- t (temperatur)

u og v følger her vanlig kartesisk koordinatsystem, dvs at positiv u blåser fra vest mot øst,
og positiv v fra sør til nord.

For å regne ut vindustyrke og -retning må man bruke vektorregning. Flg formler kan brukes:

    vindstyrke = sqrt(u^2 + v^2)
    retning = atan2(u, v)

Se [denne veiledningen](http://colaweb.gmu.edu/dev/clim301/lectures/wind/wind-uv) for detaljer.

Mer informasjon om vektorer kan finnes i [hefte for
MAT1110](https://www.uio.no/studier/emner/matnat/math/MAT1110/v06/Vektorhefte.pdf).

## Parsing av data

Det finnes en rekke [GRIB-parsere for Java](https://github.com/search?q=grib2+language%3AJava&type=repositories&l=Java)
som potensielt burde kunne brukes til å parse GRIB2. Dog leverer IsobaricGRIB
filer på ca 1.3 MB, som kanskje er tungvint å lese inn i i en mobilapp. I såfall
er det mulig å bruke en backend-server for lesing/parsing som leverer data til appen.

MET har laget et open source Python-basert API som laster ned IsobaricGRIB-filer
fra apiet og leverer en vertikalprofil som CoverageJSON for et gitt punkt.
Koden kan være nyttig å lese for å finne ut hvordan man skal tolke dataene.
Dersom dere bruker denne får dere også litt trening i å bruke [EDR](/edr):

- <https://github.com/metno/edrisobaric> - kildekode i Python

For å sjekke innhold i GRIB-filer anbefaler vi å bruke
[ecCodes](https://confluence.ecmwf.int/display/ECC/ecCodes+Home).
Denne har flere nyttige kommandolinjeverktøy man kan bruke:

- `grib_ls` - vis lag og datapunkter
- `grib_get_data` - lister data for hvert punkt (*mye* output)
- `grib_count` - sjekk antall datalag

Eksempel på JSON-output fra `grib_ls`:

    $ grib_ls -j /medusa/modpro/isobaricgrib/T_YTNB85_C_ENMI_20240314060000.bin 
    { "messages" : [ 
      {
        "edition": 2,
        "centre": "enmi",
        "date": 20240314,
        "dataType": "fc",
        "gridType": "regular_ll",
        "stepRange": 3,
        "typeOfLevel": "isobaricInhPa",
        "level": 850,
        "shortName": "v",
        "packingType": "grid_jpeg"
      },
      ...


## Beregning av høyde

I filene angis ikke høyde i meter men i trykkflater (isobarer), siden flyenes
høydemåler baserer seg på trykk og man flyr langs trykkflater i stedet for
på fast høyde over havet. Trykket angis i hPa (hektopascal).

For å [regne ut](https://physics.stackexchange.com/questions/333475/how-to-calculate-altitude-from-current-temperature-and-pressure)
høyde over havet kan man bruke [den hydrostatiske
ligningen](https://en.wikipedia.org/wiki/Barometric_formula)
ut fra flg kjente variabler:

- trykk i høyden (GRIB)
- temperatur i høyden (GRIB)
- lufttrykk ved havnivå (locationforecast)
- (geopotensialet? kan ignoreres under 10 000 m.o.h.)
