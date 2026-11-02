[README.md](https://github.com/user-attachments/files/34289593/README.md)
# ATC - Air Traffic Control Simulation

Seven free air traffic control simulators that run in the browser, with nothing to install. Choose an airport and a position, then control the traffic.

[Français](#français)

## Simulators

| Airport | Tower | Approach |
|---|---|---|
| Lyon Saint-Exupéry (LFLL) | Yes | Yes |
| Lisbon Humberto Delgado (LPPT) | Yes | Yes |
| New York Kennedy (KJFK) | Yes | Yes |
| Paris Charles de Gaulle (LFPG) | No | Yes |

- **Tower:** handle ground, takeoff and landing clearances.
- **Approach:** sequence arrivals onto the ILS and climb departures, keeping 3 NM or 1000 ft of separation.

The simulators are for fun and personal practice only. Do not use them for real-world navigation or air traffic control.

## Using the site

- The site is available in English and French. Use the FR / EN switch at the top of any page, or add `?lang=en` or `?lang=fr` to the address.
- The simulators themselves are in English.
- They are designed for a computer, and need a screen at least 1000 pixels wide.
- Click once inside a simulator to turn on the voices.

## Files

```text
index.html          Home page with the radar and flight strips
jouer.html          Page that runs a simulator
404.html            Page not found
sims/               The seven simulators
assets/sims.js      Simulator list and descriptions
assets/i18n.js      English and French site text
assets/radar.js     Home page radar
assets/style.css    Site styles
assets/previews/    Simulator screenshots
```

## Running it locally

The site has no build step. From this folder, start any static web server:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Publishing

Upload this folder to any static host, such as Netlify, GitHub Pages or Cloudflare Pages. `index.html` must stay at the root of the site.

On Netlify, drag the folder or a zip of its contents onto <https://app.netlify.com/drop>. Sign in so the site isn't kept behind a temporary password.

## Adding a simulator

1. Put the HTML file in `sims/`, for example `sims/egll-tour.html`.
2. Add a 640 × 360 screenshot to `assets/previews/` with the same name, for example `egll-tour.webp`.
3. Add an entry to `assets/sims.js`:

```js
{ id: 'egll-tour', code: 'EGLL', airport: 'Londres Heathrow', airportEn: 'London Heathrow',
  position: 'Tour', runways: '09L/27R, 09R/27L',
  job: 'Description en français.',
  jobEn: 'Description in English.' }
```

`id` must match the file names. `position` must be `'Tour'` or `'Approche'` in both languages. The site translates it automatically.

---

## Français

Sept simulateurs de contrôle aérien gratuits, à lancer dans le navigateur, sans rien installer. Choisissez un aéroport et un poste, puis contrôlez le trafic.

- **Tour :** Lyon, Lisbonne et New York.
- **Approche :** Lyon, Paris, Lisbonne et New York.
- **Langue :** le site est en français et en anglais, avec le bouton FR / EN ou `?lang=fr` dans l'adresse. Les simulateurs sont en anglais.
- **Écran :** ils sont conçus pour un ordinateur, avec au moins 1000 pixels de large.
- **Voix :** cliquez une fois dans le simulateur pour les activer.

Simulation de loisir et d'entraînement personnel, à ne pas utiliser pour la navigation ou le contrôle réels.

Pour tester le site sur votre ordinateur, lancez `python3 -m http.server 8000` dans ce dossier, puis ouvrez <http://localhost:8000>.

Pour le publier, envoyez ce dossier sur un hébergeur statique comme Netlify, GitHub Pages ou Cloudflare Pages, en gardant `index.html` à la racine.

Pour ajouter un simulateur, suivez les étapes de la section [Adding a simulator](#adding-a-simulator).
