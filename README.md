# meteo

Statyczna strona z wyszukiwarką miast dla meteogramów. Wybierasz miasto, a strona
osadza odpowiedni meteogram `https://app.meteo.pl/meteogram/<lat>,<lon>` w ramce
iframe (z odnośnikiem zapasowym).

## Uruchomienie lokalne

`index.html` wczytuje `cities.min.json` przez `fetch`, więc strona musi być
serwowana przez HTTP (otwarcie pliku bezpośrednio nie zadziała):

```bash
python3 -m http.server 8000
```

Następnie otwórz http://localhost:8000.

## Pliki

- `index.html`: strona
- `cities.min.json`: nazwy miast i współrzędne używane przez stronę

## Źródło danych

Lista miast pochodzi z https://www.geoportal.gov.pl/.

## Hosting

W pełni statyczna: można ją wystawić przez GitHub Pages lub Cloudflare Pages.

---

# meteo (English)

Static city-search page for Polish meteograms. Pick a city and the page embeds
the matching `https://app.meteo.pl/meteogram/<lat>,<lon>` meteogram in an iframe
(with a link fallback).

## Run locally

`index.html` loads `cities.min.json` with `fetch`, so it must be served over HTTP
(opening the file directly won't work):

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Files

- `index.html`: the page
- `cities.min.json`: city names and coordinates used by the page

## Data source

The city list comes from https://www.geoportal.gov.pl/.

## Hosting

Fully static: serve it with GitHub Pages or Cloudflare Pages.
