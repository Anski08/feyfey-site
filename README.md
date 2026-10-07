# FeyFey — public site

Four static pages. No build step, no dependencies, no JavaScript.

| File | Route | Purpose |
|---|---|---|
| `index.html` | `/` | Company page: the problem, how it works, where data lives, honest status |
| `developer.html` | `/developer.html` | Architecture: storage model, scheduler arithmetic, security model, trade-offs |
| `privacy.html` | `/privacy.html` | Field-by-field description of what is stored. **Draft** |
| `terms.html` | `/terms.html` | Terms of service. **Draft** |
| `assets/styles.css` | — | All design tokens and components |

## Running it

Open `index.html` in a browser. That is the whole workflow.

For a local server:

```powershell
python -m http.server 8080
```

Then visit `http://localhost:8080`.

## Deploying

Any static host works, with no configuration:

- **GitHub Pages** — Settings → Pages → deploy from `main`, root folder
- **Netlify** — drag the folder in, or connect the repo; no build command, publish directory `.`
- **Vercel** — import the repo; framework preset "Other", no build command

Links between pages are relative and include the `.html` extension, so the site
behaves identically on all three and when opened directly from disk.

## Before this goes to a real audience

1. Replace every `[BRACKETED]` placeholder in `privacy.html` and `terms.html` —
   entity name, address, contact email, jurisdiction, venue, age, refund policy.
2. Have both legal pages reviewed by a qualified professional, then remove the
   draft banners.
3. Re-check the "What works today / Not finished" lists on `index.html` against
   the app. They are maintained by hand.
4. Once the app rename ships, delete the "About the name" callout in
   `developer.html`.

## Conventions

- Read [`CONTEXT.md`](CONTEXT.md) before writing copy. Terms have fixed meanings —
  "item" is not "video file", and "teach-back" is a usage pattern, not a feature.
- Design decisions and their rationale are in [`DESIGN-NOTES.md`](DESIGN-NOTES.md).
- Every factual claim about the product must be traceable to the application
  source. This site's premise is transparency; an inaccurate sentence costs more
  here than a missing one.
