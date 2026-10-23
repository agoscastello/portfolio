# Agostina Castello — Portfolio & CV

Static HTML/CSS portfolio. No build tools required — open any `.html` file in a browser.

## File structure

```
prueba/
├── index.html              ← Portfolio home (hero, work grid, about, contact)
├── cv.html                 ← Full CV (print-ready)
├── cannect.html            ← Case study: Cannect biotech traceability platform
├── mi-estudio.html         ← Case study: Mi Estudio B2B accounting platform
├── tlscontact.html         ← Case study: TLScontact enterprise console redesign
├── web-institucional.html  ← Case study: IT Patagonia institutional redesign
├── styles.css              ← Design system — all tokens, components, layout
└── README.md
```

## Adding images

Every case study has placeholder `<div>` elements with clear comments like:
```html
<!-- REPLACE: export from Cannect.fig and reference here -->
```

To add a screenshot:
1. Export from Figma (File → Export) as PNG or JPG
2. Save to `/images/` folder (create it if needed)
3. Replace the placeholder div with: `<img src="images/filename.jpg" alt="Description of the screenshot">`

Recommended export sizes:
- **Cover images** (hero): 1440 × 504px
- **Full-width content images**: 720px wide minimum
- **Side-by-side**: 680px each

## Customising colours

All colours are CSS custom properties in `styles.css` under `:root`:

```css
--bg:             #F9F8F5;   /* page background */
--text:           #161613;   /* primary text */
--text-secondary: #6B6A65;   /* body text, descriptions */
--text-tertiary:  #9E9D98;   /* labels, captions, metadata */
--border:         #E0DED8;   /* all dividers and borders */
--tag-bg:         #E8E7E2;   /* tag/chip backgrounds */
```

## Customising typography

Fonts are loaded from Google Fonts in `styles.css`:
- **Inter** — used for all body text, labels, UI
- **Fraunces** — used for display headings (hero, case study titles)

To change fonts: update the `@import` line at the top of `styles.css` and update `--font-sans` and `--font-serif`.

## Updating contact information

Update in three places:
1. `index.html` — hero section and contact section
2. `cv.html` — CV header address block
3. `styles.css` — no contact info here, only tokens

## Adding a new case study

1. Copy `cannect.html` as a starting template
2. Update the meta title, description, tags, heading, and all content
3. Add a card in `index.html` inside `.work-grid`
4. Add navigation links in `case-nav` sections of adjacent case studies

## Print / PDF export of CV

Open `cv.html` in Chrome → File → Print → Save as PDF.
Print styles are included in `styles.css` — the nav and footer hide automatically.

## Deploying

This is a static site — deploy to any static host:
- **Netlify**: drag the folder to netlify.com/drop
- **Vercel**: `vercel --prod` from this directory
- **GitHub Pages**: push to a repo and enable Pages in settings
- **Custom domain**: point your DNS to whichever host you use
