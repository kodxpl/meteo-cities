# meteo

Statyczna strona z wyszukiwarką miast i własnymi wykresami prognozy pogody.
Wybierasz miasto, a strona pobiera prognozę dla jego współrzędnych i rysuje
cztery wykresy (SVG, bez bibliotek):

1. temperatura powietrza i gruntu,
2. opad i wilgotność,
3. prędkość wiatru i porywy,
4. zachmurzenie i mgła.

Obok wyszukiwarki jest odnośnik do oryginalnego meteogramu
`https://app.meteo.pl/meteogram/<lat>,<lon>`.

## Uruchomienie lokalne

`index.html` wczytuje `cities.min.json` przez `fetch`, więc strona musi być
serwowana przez HTTP (otwarcie pliku bezpośrednio nie zadziała):

```bash
python3 -m http.server 8000
```

Następnie otwórz http://localhost:8000.

## Pliki

- `index.html`: strona (wyszukiwarka i wykresy)
- `cities.min.json`: nazwy miast i współrzędne używane przez stronę

## Źródło danych

Lista miast pochodzi z https://www.geoportal.gov.pl/.

Prognoza (model UM 4 km, ok. 60 godzin) jest pobierana w przeglądarce z
`https://devmgramapi.meteo.pl`, czyli wewnętrznego API aplikacji app.meteo.pl.
Nie jest ono udokumentowane i może się zmienić; strona jest przeznaczona do
użytku domowego.

## Hosting

W pełni statyczna: można ją wystawić przez GitHub Pages lub Cloudflare Pages.

---

# meteo (English)

Static city-search page with its own weather forecast charts. Pick a city and
the page fetches the forecast for its coordinates and draws four charts
(plain SVG, no libraries):

1. air and ground temperature,
2. precipitation and humidity,
3. wind speed and gusts,
4. cloud cover and fog.

Next to the search box there is a link to the original meteogram,
`https://app.meteo.pl/meteogram/<lat>,<lon>`.

## Run locally

`index.html` loads `cities.min.json` with `fetch`, so it must be served over HTTP
(opening the file directly won't work):

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Files

- `index.html`: the page (search and charts)
- `cities.min.json`: city names and coordinates used by the page

## Data source

The city list comes from https://www.geoportal.gov.pl/.

The forecast (UM 4 km model, about 60 hours) is fetched in the browser from
`https://devmgramapi.meteo.pl`, the internal API of the app.meteo.pl app.
It is undocumented and may change; the page is meant for home use.

## Hosting

Fully static: serve it with GitHub Pages or Cloudflare Pages.
