# AIQIA 2027 — Conference Website

Website for the **First International Conference on Artificial Intelligence & Quantum: Innovations and Applications (AIQIA 2027)**,
24–25 September 2027, Symbiosis Institute of Technology (SIT), Hyderabad — a hybrid conference.

- **Scope / page structure** follows the previous conference website hosted by SIT Hyderabad.
- **Visual design:** Open Sans + Roboto, navy `#002855` / blue `#00629B` gradients, white sticky menu, pill buttons.

Plain static HTML/CSS/JS — no build step, no framework.

## Structure

```
.
├── index.html                   Home
├── committee.html               Organizing committee
├── call-for-papers.html         Scope + 8 technical tracks (accordion)
├── instructions-for-authors.html
├── review-manuscripts.html
├── camera-ready.html
├── important-dates.html         Timeline
├── programs.html                Workshops, tutorials, forums… (#anchors) + schedule
├── registration.html            Fee table
├── venue.html / hotels.html / places.html / visa.html / visa-request.html
├── sponsorship.html             Tiers + sponsor logos
├── contact-us.html
├── coming-soon.html / sitemap.html / 404.html
├── assets/
│   ├── css/style.css            All styles (design tokens at the top in :root)
│   ├── fonts/                   Self-hosted Roboto, Open Sans, Material Icons (no Google Fonts needed)
│   ├── js/config.js             ← Conference facts & links (dates, CMT link, email…)
│   ├── js/main.js               Header/nav/footer (defined once), countdown, accordion, animations
│   ├── img/logos/               AIQIA and Symbiosis logos
│   ├── img/favicon.png          Browser-tab icon (from the AIQIA logo)
│   ├── img/patterns/            Decorative SVG backgrounds
│   ├── img/hero|committee|sponsors|venue/   Photo folders
│   └── docs/                    CFP brochure PDF
├── .htaccess                    Clean URLs (/committee → committee.html), custom 404
└── .cpanel.yml                  cPanel deployment
```

## Editing

| To change… | Edit |
|---|---|
| Dates, venue, CMT/registration links, email, socials | `assets/js/config.js` |
| Menu items / footer | `NAV` and `footerHTML` in `assets/js/main.js` |
| Colours / fonts | `:root` variables in `assets/css/style.css` |
| Page content | the page's `.html` file |

Search the repo for `TODO` and `TBA` to find every placeholder that still needs real content.

### Adding images
- **Committee:** square photo in `assets/img/committee/`, replace the `<span class="material-icons">person</span>` inside `.pic` with an `<img>`.
- **Placeholders** (`<div class="ph …">`): replace the whole div with an `<img>`.
- **Hero photo:** add `assets/img/hero/hero.jpg` and uncomment the photo rule under `.hero` in `style.css`.

## Local preview

```bash
python -m http.server 5173
```

Then open http://localhost:5173. (Clean URLs like `/committee` only work on Apache via `.htaccess`; locally use `committee.html`.)
