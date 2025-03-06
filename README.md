
# IN2000 kursdokumentasjon

# in2000.met.no

Kursmateriale for IN2000 (Software Engineering med Prosjektarbeid) ved UiO.

Dette repoet brukes for å generere siten <https://in2000.met.no/> som hostes
via GitHub Pages.

## Skrive dokumentasjon

Aller først må du laste ned repoet fra GitHub.
Dette krever at du har en bruker på GitHub (i utgangspunktet privat).

    $ git clone git@github.com:metno/in2000.git

For å skrive dokumentasjon må du bruke formatet [Markdown]().
Se dokumentasjonen for [GitHub Pages](https://docs.github.com/en/pages)
for mer informasjon.

Selve siten ligger i mappen `/docs`, og er organisert etter årstall.
Materiale for årets kurs ligger i mappen med inneværende år som navn med én fil
for hvert case.

## Kodebiblioteker o.l.

Alt som ikke skal vises på selve siten, men skal kunne lastes ned og integreres
i app-koden skal legges i mappen `/resources`. Dermed kan studentene laste ned
disse hva Git og få løpende oppdateringer.

## Testing

Før du commiter endringer bør du teste at siten fungerer på din lokale maskin.

1. Installer Jekyll etter [denne oppskriften](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll).

2. Installer gems og generer siten:

```
$ cd doc
$ bundle install
$ ./site run
```

Du vil da kunne se resultatet i din browser på følgende adresse:

- <http://localhost:4000/>

## Opplasting

Lag en pull request i GitHub, så vil vi reviewe endringene og merge inn i master.
