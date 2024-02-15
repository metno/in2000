---
layout: page
title: Sunrise
parent: Generelle ressurser
date: 2023-02-26
author: Håkon Tansem
email: haakont@met.no
---

Sunrise 3.0 er en tjeneste som leverer data om sol og måne. Backenden er skrevet
i Python, og kildekoden er tilgjengelig på
[GitHub](https://github.com/metno/celestial) med fri lisens.

Tjenesten leverer henholdsvis opp- og nedgangstider, samt når det to legemene
krysser meridian og antimeridian. Nedenfor følger en beskrivelse av disse
fenomenene.

## Oppgang/Nedgang for Solen

Oppgang for sola er det tidspunktet der det øverste punktet på soldisken krysser
horisonten.

Tilsvarende for nedgang har vi tidspunktet der det øverste punktet soldisken
igjen krysser horisonten på vei ned. Den astronomiske horisonten er et imaginært
plan som står 90° på den aksen som peker rett opp fra observatøren, også
kalt zenith.

Den visuelle solradien når den befinner seg ved horisonten er omtrent
0.266°. Ideelt sett kunne man da sagt at soloppgang inntreffer når
senteret til solskiven er 0.266° under horisonten. En svært viktig faktor
for når soloppgang visuelt intreffer er refraksjon grunnet Jordas atmosfære.
Grunnet jordas atmosfære vil lys fra objekter i verdensrommet avbøyes og deres
visuelle posisjon vil avvike fra deres faktiske posisjon. Nedenfor vises en
illustrasjon av fenomenet.

![Atmosfærisk refraksjon](/images/examples/atmosphere_refrac.png)

<em>Kilde: https://upload.wikimedia.org/wikipedia/commons/3/39/Atmospheric_refraction_-_sunset_and_sunrise.png</em>

Selv om lysavbøyning grunnet atmosfærens refraksjon ikke har en konstant verdi,
men varierer grunnet forhold som blant varierende temperatur, har man kommet
frem til en gjennomsnittsverdi på omtrent 0.566°. Legger man til den
visuelle Solradien og atmosfærens refraksjon, har man har da kommet frem til en
definisjon der soloppgang inntreffer når Solen er 0.833° under
horisonten. For videre lesning, der vi har basert mye av vår informasjon,
anbefales United States Naval Observatory sine nettsider:

<https://aa.usno.navy.mil/faq/RST_defs>

For månen har vi en tilsvarende definisjon. Siden Månen er nærmere enn Solen så
vil dens visuelle størrelse variere i større grad der den beveger seg i sin
elliptiske bane rundt jorden. Vi har likevel valgt å bruke en gjennomsnittsverdi
på 0.266° for månens visuelle radius. Tatt i betrakting verdien for
atmosfærens refraksjon har da månen og sola har samme definisjon på opp- og
nedgang i Sunrise 3.0.

## Krysning av Meridian/Antimeridian

Meridian er den linjen som går mellom Nord- og Sydpolen ved en gitt lengdegrad.

I grove trekk er det tidspunktet der et himmellegeme krysser denne linjen, sett
fra en observatør, også det tidspunktet der det gitte legemet står høyest på
himmelen. Tilsvarende står det lavest på himmelen når det krysser antimeridianen
(motsatt side av jordkloden). For beregninger av meridiankrysninger operer vi
med når senteret av henholdsvis månen og sola krysser meridianen. Vi har ikke
tatt hensyns til refraksjon på denne kalkulasjonen.

Merk at for månen kan det være dager krysning av meridian og antimeridian ikke
forekommer. Dette er ikke en feil, men er et resultat av at månen, som går i
bane rundt jorden som roterer, bruker mer enn 24 timer før den igjen krysser
samme longitude koordinat.

## Definisjon av døgn i Sunrise 3.0

Til vanlig forholder vi oss til et døgn som tiden fra kl 00:00 til kl 24:00
inenfor en gitt tidssone. Et problem med dette hva gjelder våre kalkulasjoner er
politisk definerte tidssoner som i realiteten brer seg utover større områder.
For eksempel har Kina kun èn tidssone (Beijing tid) selv om landet i realiten
strekker seg over fem tidssoner. For å sentrere kalkulasjonene rundt opplevd
døgn for observatøren har vi valgt å basere tidssintervallet for selve
kalkulasjonen på longitude koordinaten det spørres om.

Offset fra UTC tid i kalkulasjonene beregnes utifra å dele longitude koordinaten
med 15. Siden vi har 24 tidssoner og jorden roterer 360°, får vi offset
i antall timer fra lokal soltid ved å dividere longitude koordinat på 360/24=15.
Merk at longitude koordinatet kan ha verdier fra -180° til 180, der
Greenwich observatory i London befinner seg på longitude koordinat 0°.
Slik definerer vi offset i antall timer fra UTC tid i tidsintervallet
for våre beregninger. Svaret som finnes i responsen er regnet om til offset man
har definert i den gitte URL man har brukt for å utføre spørringen. I tillegg
kan hendelser for soloppgang og solnedgang komme en tid etter midnatt. For å
være sikker på at vi har definert et tidsintervall som fanger alle hendelser så
utvider vi tidssintervallet noe. Dette gjøre ved å ta utgangspunkt tidspunktet
for solens meridiankrysning og deretter legge til tolv timer i hver ende. Dette
fører til at om meridiankrysning ikke forekommer nøyaktig kl 12:00, så vil
tidsintervallet være noen minutter lenger en 24 timer. På denne måten har vi
definert et tidsintervall der vi kan fange opp solnedganger som inntreffer etter
midnatt.

I Sunrise 3.0 har vi tatt som utgangspunkt å rapportere hendelser for Solen på
en måte der man alltid vil få soloppgang først og deretter solnedgang. Selv om
solnedgang skulle forekomme etter midnatt og strengt tatt er en hendelse som
tilhørere dagen etter den man har spurt om. Dersom man spør et annet API kan man
finne at man kan få solnedgang først og så soloppgang da dette reelt sett er de
hendelsene som forekommer innenfor det etterspurte tidsintervallet.

For månen har vi kun tatt utgangspunkt i longitude koordinaten for å definere
tidsintervall for døgnet. Der rapporterer Sunrise 3.0 kun de hendelser som
forekommer innenfor forespurt tidsintervall i den rekkefølgen de forekommer.
