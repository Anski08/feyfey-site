# Design notes

## Where the design language came from

The visual system is derived from a measured study of a well-known study-app
interface, captured via computed styles, stylesheet text and hover-state diffs.
The source kit described itself as *"inspiration, not a brand clone"* and
explicitly instructed: **swap the primary hue and logo for your own product**, and
do not ship its logo, illustrations, copy or licensed typeface.

That instruction was followed:

| Token | Source kit | FeyFey | Why |
|---|---|---|---|
| Primary hue | `#4255FF` | **`#2848d8`** | FeyFey's existing app accent. Deeper, less recognisable as the source. |
| Typeface | Hurme Geometric Sans No.2 (commercial) | **Figtree** | Free, on Google Fonts, closest open match to the measured face. |
| Illustrations | Licensed product art | **Original inline SVG** | Nothing was copied. All diagrams are drawn from scratch. |
| Copy | — | **Original** | No source text was reused. |

What *was* adopted is structure and behaviour, which is not protectable and is what
makes the system worth using: the type scale, the 8px spacing grid, the radius
ladder, the motion timings, and the component rules.

## Rules carried over

- **One saturated colour in the chrome.** Teal, lime and amber appear only inside
  illustration tiles and callouts. Never on a control.
- **Ink, not black.** Body text is `#282e3e`. Only the hero headline uses the near-black
  `#0b1020`. Shadows are tinted with ink, never black.
- **Pills for every button.** `200px` radius. `8px` for inputs and cards, `24px` for
  large feature tiles.
- **Hover changes colour only.** `120ms`, no translate, no scale, no lift.
- **Bounce is for entrances.** The overshoot curve is used on tiles appearing
  (`popIn`), never on hover.
- **600 weight for anything clickable.** 400 body, 700 headings. Three weights total.
- **`prefers-reduced-motion` is honoured globally**, collapsing all animation and
  transition to `1ms`.

## Deliberate departures

**Light mode only.** The source kit has no dark palette. Inventing one would mean
guessing at fifteen tokens with nothing to verify against. The FeyFey application
has its own dark theme; this marketing site does not need to match it.

**No Tailwind.** The kit shipped a Tailwind v4 `@theme` block, which requires a build
step. Four static pages do not justify a toolchain, and the token names carry the
system just as well as plain custom properties. `var(--color-primary)` is as
expressive as `bg-primary` at this scale.

**No JavaScript.** Nothing on this site needs it. Not loading any is both the fastest
option and the most consistent with a privacy page claiming no tracking.

## If the app is restyled later

The application already uses CSS custom properties throughout its stylesheet, so
adopting these tokens there is largely a `:root{}` substitution rather than a
rewrite. The dark palette would need extending to cover any new token names.
