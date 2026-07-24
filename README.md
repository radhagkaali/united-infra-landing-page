# United Infra — Landing Page

A one-page marketing site for United Infra, a heavy civil / infrastructure
contractor (roadways, bridges, water & utilities, energy infra). Built as
plain HTML/CSS/JS — no build step required.

## Structure

```
United-Infra-Landing-Page/
├── index.html        Page markup (hero, services, process, projects, contact)
├── style.css          All styling — design tokens live at the top as CSS variables
├── script.js          Mobile nav toggle, scroll-reveal, contact form handling
├── assets/
│   ├── images/         Drop project/site photography here
│   └── icons/          Drop a favicon or extra icon assets here
└── README.md
```

All icons currently used on the page (logo mark, service icons, scroll cue)
are inline SVG in `index.html`, so the site renders with zero external
image dependencies. The `assets/` folders are there for real photography —
drop project photos into `assets/images/` and reference them from
`index.html` (e.g. in `.project-media`) or `style.css`.

## Design system

Defined as CSS custom properties at the top of `style.css`:

- **Color** — blueprint navy (`--ink`), cyanotype blue linework (`--blueline`),
  paper/concrete (`--paper`), steel grey (`--steel`), a single safety-amber
  accent (`--amber`) reserved for calls to action.
- **Type** — Oswald (display/headings), IBM Plex Sans (body), IBM Plex Mono
  (labels, sheet numbers, form status — anything meant to read like a
  drawing annotation).
- **Motif** — the page borrows the visual language of civil engineering
  drawing sheets: corner crop marks, a blueprint grid in the hero, a
  drawing "title block" (DWG NO. / SCALE / REV), and sheet numbers on the
  services and project cards.

## Running it locally

No dependencies or build step — open `index.html` directly in a browser,
or serve the folder with any static server, e.g.:

```
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Notes

- The contact form (`#contact-form`) is client-side only right now — it
  validates and shows a confirmation message but doesn't send anywhere.
  Wire the `submit` handler in `script.js` up to your backend or a form
  service (Formspree, Netlify Forms, etc.) when ready.
- Layout is responsive down to small mobile widths; the nav collapses to a
  toggle menu under ~860px.
- Respects `prefers-reduced-motion`.
