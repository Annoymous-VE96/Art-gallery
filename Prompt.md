# [GALLERY NAME] — Website Build

## Fill these in before running
Replace every bracketed value below with real content. Where you don't have
real content yet, leave the bracket as-is — the agent should generate
tasteful placeholder copy/imagery and mark it clearly so it's easy to swap
later.

- `[GALLERY NAME]`
- `[CITY / NEIGHBOURHOOD]`
- `[GALLERY PHILOSOPHY — one or two sentences on what kind of art/artists it shows]`
- `[OPENING HOURS]`
- `[ADDRESS]`
- `[CONTACT EMAIL / PHONE]`
- `[CURRENT EXHIBITION NAME + ARTIST + DATES]` (if none exists yet, generate a
  plausible placeholder exhibition and mark it `<!-- PLACEHOLDER EXHIBITION -->`)

## Role
Build a new single-page website for `[GALLERY NAME]`, a contemporary art
gallery that represents and exhibits artists. This is **informational, not
e-commerce** — no cart, no checkout, no product pricing. The goal is to make
someone want to walk in the door or follow the gallery's program.

Use the **frontend-design** and **ui-ux-pro-max** skills for every decision
involving typography, color, layout, spacing, and motion. Don't default to
generic template patterns — this site needs a distinct point of view.

---

## Visual direction: Bold & maximalist
This is a deliberate departure from safe, minimal gallery-website tropes
(all-white, all-serif, tiny type). Go loud, but *intentional* — maximalism
that reads as curated chaos, not clutter.

- **Color**: pick one saturated, unexpected accent (not the default
  black/red art-world cliché — consider acid green, cobalt, magenta, or a
  clashing duotone) against a high-contrast base (near-black or near-white,
  your call). Use the accent aggressively — full-bleed color blocks, not
  just a link color.
- **Type**: oversized, expressive display type for headlines — mix a
  serif/display face with a utility grotesk for contrast. Type can break
  grid, overlap images, run at odd angles. Body copy stays legible and
  restrained — the loudness lives in headlines and section breaks, not
  paragraphs.
- **Layout**: asymmetric, broken-grid composition. Avoid centered,
  evenly-spaced "safe" sections — let elements bleed off-edge, overlap,
  vary in scale dramatically between sections.
- **Texture**: consider a subtle grain/noise overlay or halftone treatment
  to keep saturated color from feeling flat/digital.
- **Cursor & micro-interactions**: a custom cursor state on hover over
  artwork/links is appropriate for this mood — keep it lightweight and
  make sure it's disabled on touch devices.

Set this up as a token-based design system in `:root` (same approach as a
typical production site: color, type scale, spacing, radii, motion timing
all as CSS custom properties) so the whole system stays consistent and
editable — don't hardcode one-off values in components.

---

## Structure: single scrolling page
Build as one HTML file with the following sections, in order. Each section
should feel like a distinct "beat" — vary rhythm and scale between them
rather than repeating the same section template six times.

### 1. Header / nav
Fixed or sticky, minimal — gallery name/mark, a handful of in-page anchor
links (Exhibition, Artists, Visit, Contact), condenses on scroll.

### 2. Hero
Full-bleed, high-impact. Large expressive type stating what the gallery is
and does. Should feel like a poster, not a corporate banner. Generate a
striking placeholder visual here (see Imagery section below) if real
photography isn't available yet.

### 3. Current exhibition
The most important content block after the hero — treat it like a feature,
not a card. `[CURRENT EXHIBITION NAME + ARTIST + DATES]`. Include a short
curatorial blurb, dates, and a strong visual moment (large artwork image,
generous negative space around it).

### 4. Featured artists
A gallery/grid of represented artists — photo or artwork thumbnail, name,
one-line description. Grid should break the boring 3-column repeat pattern
— vary tile sizes for visual rhythm (masonry or explicit size variation).
On hover/tap, reveal a bit more (medium they work in, a signature piece).

### 5. About / philosophy
`[GALLERY PHILOSOPHY]`. Editorial layout — large pull-quote treatment
works well here given the bold direction. Keep this section calmer than
the surrounding ones as a rhythm break.

### 6. Past exhibitions / archive
A scrollable or filterable strip/grid of past shows — thumbnail + title +
year. Doesn't need full detail per item, this is a credibility/breadth
signal.

### 7. Visit
`[ADDRESS]`, `[OPENING HOURS]`, embedded map or map-style graphic, transit/
parking note if relevant.

### 8. Contact / mailing list
`[CONTACT EMAIL / PHONE]` plus a simple email signup for exhibition
announcements. No form-handling backend needed — front-end only, note it
as a TODO for backend wiring.

### 9. Footer
Gallery name/mark, quick links, social links, address repeat, copyright.

---

## Imagery & animation
- **Placeholder artwork**: since real photography likely isn't ready yet,
  use Antigravity's built-in image generation (Nano Banana) to produce
  abstract, gallery-appropriate placeholder artwork and hero imagery that
  matches the bold/maximalist palette — don't reach for generic stock
  photos, they'll undercut the "distinct gallery" feel. Comment every
  generated placeholder clearly (`<!-- PLACEHOLDER ARTWORK: replace with
  client photography -->`) so they're trivial to find and swap later.
- **Animation**: scroll-triggered reveals (stagger grid items in on
  entry), a hero moment that feels alive on load (not just a static fade),
  and confident hover states on artwork/artist tiles. Keep it
  performant — CSS transforms/opacity only, no layout-thrashing
  animations. Respect `prefers-reduced-motion`: every animation needs a
  static, still-complete fallback.
- **Image handling**: consistent aspect ratios within each grid (hero can
  break this, grids shouldn't), lazy-load anything below the fold,
  explicit width/height to prevent layout shift.

---

## Constraints (apply throughout)
- Single HTML file, vanilla CSS/JS — no framework unless you flag why one's
  needed and get sign-off first.
- Mobile-first responsive, even though the desktop composition is
  intentionally asymmetric — define how the broken-grid layouts collapse
  gracefully on narrow viewports rather than just shrinking everything.
- Accessibility is non-negotiable regardless of visual boldness:
  sufficient contrast on text over color/imagery, visible focus states,
  semantic HTML, alt text on every image (including generated
  placeholders — describe what the placeholder depicts), reduced-motion
  fallback for every animation.
- No copyrighted artist names, real gallery names, or real artwork —
  everything content-wise until I supply real assets should be clearly
  marked placeholder, original, or generated.

## Output
After building, give me a short summary of: the color/type system you
chose and why, where placeholder content/imagery was used (so I know what
to send you to swap in), and any accessibility or performance notes.