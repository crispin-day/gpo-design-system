# Good People Only — Brand & Style Guide

**Design world: "A State of Play"** · v1.0 · July 2026
Source of truth: www.goodpeopleonly.com (repo `crispin-day/good-people-only`, branch `redesign/state-of-play`).
This document supersedes `GPO-BRAND-GUIDANCE.md` and `DESIGN_GUIDE.md`, which describe the retired identity.

How to use this: everything here is prescriptive. If you are generating visual material for GPO (web pages, decks, one-sheets, social assets), follow the tokens and rules exactly. The "Never" list at the end is as binding as the palette.

---

## 1. The idea

Good People Only is a boutique artist management company, record label, and brand partnership agency. The identity is called **A State of Play**: work approached with the seriousness of craft and the looseness of play. Visually it draws from warm-paper editorial print and Bauhaus geometric posters.

The register is **playful and intentional, never childish**. Play shows up as geometry in motion, a wink of red, a punchline in the copy. It never shows up as bounce physics, cartoon energy, or decoration for its own sake.

Three behaviors define the system:

1. **One motif, everywhere.** Concentric circle-to-squircle contours, grown from the circular logo. Alive on the homepage hero, traced as a static outline elsewhere. Do not invent second motifs.
2. **Red is punctuation, not paint.** Red appears on the smallest possible unit that carries the meaning: one word in a sentence, the period after the wordmark, an arrow, a 6px dot. Never backgrounds, never panels, never large fills.
3. **Quiet ground, deliberate marks.** Cream paper, warm ink, lots of air. Frames and boxes are avoided; spacing and 2px ink rules do the separating.

---

## 2. Logo

The mark is a solid ink disc with **GOOD** stacked as **GO / OD** knocked out of it, so the background shows through the letterforms. The knockout is the point: the logo has no white in it, ever. On cream, cream shows through; on ink, use the white-disc variant.

<img src="public/logo-knockout.png" width="130" alt="Knockout logo: ink disc with GOOD cut out"> &nbsp;&nbsp; <img src="public/logo-circle-black.png" width="130" alt="One-color black and white disc"> &nbsp;&nbsp; <img src="public/logo-circle-white.png" width="130" alt="White disc for ink and dark grounds">

*Left to right: knockout (default, on cream), one-color disc, white disc (for ink/dark grounds; shown here on a light page, so it reads faint by design).*

**Files** (in `public/` of the site repo):

| File | What it is | Use on |
|---|---|---|
| `logo-knockout.png` | Ink disc, letters knocked out (transparent) | Cream/paper grounds. Default. |
| `logo-circle-black.png` | Black-and-white disc | Favicon source, one-color contexts |
| `logo-circle-white.png` | White disc | Ink/dark grounds |
| `wordmark-good-black.png` / `-white.png` | GOOD wordmark alone | Rare, small lockups |

**Rules**

- Clear space: at least 25% of the disc's diameter on all sides.
- Minimum size: 24px diameter on screen.
- Never recolor the disc red or green. Never add a white plate behind it.
- Motion (interactive contexts): on hover the disc spins like a record at 100°/s; on exit it reverses and unwinds back to 0°. If you implement a hover spin, it must unwind, not snap.
- The full company name set in type ("GOOD PEOPLE ONLY.") always takes a red period. The period is red; the words are ink.

---

## 3. Color

Sampled from the reference print set. Nothing on the site is pure black or pure white.

| Token | Hex | Contrast on paper | Role |
|---|---|---|---|
| `--ink` | `#1A1A18` | 14.9:1 | Text, rules, the logo, recolored partner logos. Warm near-black. |
| `--paper` | `#EEE7D7` | — | The ground. Every surface is this cream. |
| `--paper-2` | `#E7DFCB` | — | Slightly deeper cream for subtle layering |
| `--red` | `#D0130F` | 4.51:1 | Punctuation only (see rules below). Large/bold text and marks only, never body text. |
| `--green` | `#00712C` | 5.02:1 | Reserve accent. Almost never used; do not introduce it without a reason. |
| `--dim` | `#5F5B50` | 5.50:1 | Secondary text. Body-safe. |
| `--border-1` | `#DBD3BE` | — | Hairline on cream (use sparingly; frameless is preferred) |
| `--border-2` | `#C6BCA2` | — | Stronger hairline on cream |

**Red usage rules (strict)**

Allowed: one emphasized word inside an ink sentence; the period after the wordmark; arrows (↗); small dots and separators; the animated contour field; the cursor; a focus outline.
Not allowed: backgrounds, buttons fills, panels, borders around sections, more than one red element competing in a viewport, body-size red text.

**Grey ramp caution:** the neutral greys (`#F7F7F5` … `#111111`) were designed for white grounds. On cream they can sit at near-1:1 contrast and disappear. For anything that must be visible on cream, use `--ink`, `--dim`, or the two cream-derived borders above.

---

## 4. Typography

One family carries the identity: **Jost** (Google Fonts, variable weight + italic). It is an open revival of Futura, the geometric face of the reference material. Fallback stack: `Jost, "Futura", "Avenir Next", "Century Gothic", system-ui, sans-serif`. True Futura PT is an acceptable paid substitute.

**JetBrains Mono** (400/500) exists for data-like fragments only (timestamps, catalogue numbers). Never for navigation, labels, or headings.

**The four voices**

| Voice | Spec | Example use |
|---|---|---|
| Display | Jost 700, UPPERCASE, letter-spacing -0.025em, line-height 0.92–1.0, sizes clamp large (36–96px) | Page titles: "WHERE BRANDS MEET CULTURE." |
| Tracked caps label | Jost 400–500, UPPERCASE, 12px, letter-spacing 0.22em, color `--dim` | Kickers, eyebrows, section labels: "WHO WE'VE WORKED WITH" |
| Body | Jost 400, 16–18px, line-height 1.55, color `--dim` or `#404040` | Paragraphs, card copy |
| Company voice (quote) | Jost 600 *italic*, large (30–56px), letter-spacing -0.015em, ink; the one emphasized word set **upright and red** inside the italic | "The most powerful marketing isn't advertising. It's **culture**." |

**Rules**

- Uppercase display type is the headline voice; sentence-case display is not used.
- The setup/punchline pattern is a house move: a quiet tracked-caps line hands off to the wordmark or the payoff line ("Surround yourself with" → "GOOD PEOPLE ONLY.").
- Headings get `text-wrap: balance`; body max-width ~62–68ch.
- **No em dashes anywhere in copy.** Use commas, colons, or periods. This is absolute.

---

## 5. The contour motif

The system's single graphic device: **~20 nested contours that morph from circle (center) to squircle (edge)**, drawn in red at ~0.44% of the field size stroke weight, grown outward from the logo disc at center. It reads as a record's grooves and a playing field at once.

- **Hero (homepage only):** the field is alive on canvas. It breathes slowly, winds under the pointer, and a click drops a "needle drop" pulse that rolls outward through the rings. Motion is calm; interaction has the payoff.
- **Everywhere else:** the motif appears as a single static **ink** contour trace, e.g. the rounded-superellipse outline that draws itself around roster photo tiles on hover (stroke ink, width 5, corner radius 7%/5.6% matching the tile).
- In print or static layouts: a single red contour ring set, low density, may anchor a cover or divider. Do not fill it, do not add drop shadows, do not render it in green.

One field per surface, maximum. The motif is an identity mark, not a texture.

---

## 6. Layout & composition

- Max content width 1440px; page padding `clamp(16px, 3vw, 40px)`; reading measure 680px.
- **Frameless by default.** Sections separate by whitespace and typography, not boxes. GPO explicitly removed card frames from its inquiry sections; do not add boxes, panels, or cards with borders unless information genuinely needs containment.
- Major structural breaks use a **2px solid ink rule** (page header bottom, CTA top). That is the only heavy rule in the system.
- Hairlines (`--border-1/2`) are for row separation inside lists only.
- Spacing scale: 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128 / 192px. Section padding is fluid: `clamp(48px, 7vw, 88px)` territory.
- Corners are square (`0px`) except the photo-tile superellipse (7% / 5.6%) and circles. No `border-radius: 8px` card aesthetics.
- Numbered list rows (01, 02, …) are used where order or countability is real (a capability list), set in tracked caps with a hover state that dims siblings.

---

## 7. Motion

Motion is the "play" in the system, and it is rationed.

- **One payoff per surface.** The homepage's payoff is the needle-drop field. A subpage's payoff is the ink trace drawing around a photo. Do not stack effects.
- Easing tokens: `--ease-out: cubic-bezier(0.2, 0.8, 0.4, 1)` for most transitions; durations 160ms (fast), 240ms (base), 480ms (slow). Hover states use base.
- Entrances: simple 16px fade-up, 600ms, small stagger (60ms steps). Nothing flies, bounces, or rotates in.
- Link hover: 1px underline grows left-to-right (`transform: scaleX`), 240ms.
- Continuous motion is only allowed where it is content: the hero field, and the client-logo strip on /brands (60s linear loop, pauses on hover, edge-fade mask, static wrapped list under `prefers-reduced-motion`).
- All motion must be time-based (per-ms), not frame-based, and must respect `prefers-reduced-motion` (the site globally collapses animation durations to 0.01ms).

---

## 8. Cursor system (web)

The visitor's presence is the system's atom: a small red disc.

- One cursor everywhere: a 10px red dot (inline SVG data-URI cursor, hotspot centered). It never changes over clickable elements; hover states on the elements themselves carry the affordance.
- Text fields: normal caret. Touch devices: unaffected.
- Inside the hero field: no OS cursor; the canvas draws its own small contour form that fades near the edges.
- Never mix in the hand/pointer cursor or size-changing cursors. If you add clickable elements, verify no component stylesheet reintroduces `cursor: pointer`.

---

## 9. Photography & imagery

- Artist/people photos: **4:5 portrait tiles**, corner radius 7%/5.6% (superellipse feel), with a cream multiply veil at 12% opacity so photos sit *in* the paper world rather than on top of it.
- Hover: the ink contour trace draws itself around the tile (stroke 5, centered on the boundary so it straddles the edge).
- No blurred-image backgrounds, no duotones, no circle/porthole crops of photos.
- Illustration/3D is off-brand. The system's only graphic is the contour motif.

**Partner/client logos** are always normalized into the system: all fills recolored to ink `#1A1A18`, knockout/negative areas to paper `#EEE7D7`, displayed at 72% opacity rising to 100% on hover. Never show third-party logos in their brand colors inside GPO materials. Sourced files live in `public/brands/`.

---

## 10. Voice & copy

- Short declaratives. Concrete nouns. The confidence of understatement: "The roster is small on purpose."
- The setup/punchline structure is the house rhythm: a quiet line that pays off in the name or the point.
- Emphasis is one red word, chosen because it is the word that matters ("love", "culture"), not for decoration.
- **No em dashes.** Ever. Use commas, colons, periods.
- No AI-inflected filler: avoid "elevate", "seamless", "unlock", "delve", stacked hype adjectives, and rhetorical throat-clearing. If a sentence could open any company's site, cut it.
- Approved phrases in circulation: "Working in a State of Play" (eyebrow), "Surround yourself with GOOD PEOPLE ONLY.", "Where brands meet culture.", "Campaigns that don't just reach audiences, they mobilize them.", "Separate companies, shared standards."
- Locations line: "Toronto · Los Angeles" (interpunct separator).
- Email: contact@goodpeopleonly.com. CTAs are direct: "Get in Touch ↗", "Tell us what you're building."

---

## 11. Never (rejected by the founder; do not reintroduce)

1. Bouncing/physics ball animations of any kind.
2. Circle or porthole crops on photos or cards.
3. Blurred image backgrounds.
4. Monospace type in navigation or headings.
5. Scrolling marquees of text or artist names (the /brands client-logo strip is the single sanctioned carousel).
6. "Pause motion" UI buttons.
7. Visible frames/borders around content sections (frameless preferred).
8. Pure white `#FFFFFF` or pure black `#000000` surfaces.
9. Red as a background, panel, or button fill.
10. Em dashes in any copy.
11. Childish or forced playfulness; if an idea needs the word "fun" to justify it, cut it.
12. Second decorative motifs, textures, gradients, or drop shadows (one soft hover shadow token exists; that is the ceiling).

---

## 12. Token appendix (CSS)

```css
:root {
  --ink: #1A1A18;          --paper: #EEE7D7;      --paper-2: #E7DFCB;
  --red: #D0130F;          --green: #00712C;      --dim: #5F5B50;
  --border-1: #DBD3BE;     --border-2: #C6BCA2;   --accent: var(--red);

  --font-display: "Jost", "Futura", "Avenir Next", "Century Gothic", system-ui, sans-serif;
  --font-sans:    "Jost", "Futura", ui-sans-serif, system-ui, sans-serif;
  --font-mono:    "JetBrains Mono", ui-monospace, "SF Mono", Menlo, monospace;
  --fw-display: 700;

  --text-xs: 12px; --text-sm: 14px; --text-base: 16px; --text-md: 18px;
  --text-lg: 22px; --text-xl: 28px; --text-2xl: 36px;  --text-3xl: 48px;
  --text-4xl: 64px; --text-5xl: 88px; --text-6xl: 128px;

  --lh-tight: 0.95; --lh-snug: 1.08; --lh-normal: 1.35; --lh-relaxed: 1.55;
  --tr-tight: -0.02em; --tr-wide: 0.04em; --tr-wider: 0.12em; --tr-widest: 0.22em;

  --ease-out: cubic-bezier(0.2, 0.8, 0.4, 1);
  --ease-snap: cubic-bezier(0.2, 0.9, 0.2, 1);
  --dur-fast: 160ms; --dur-base: 240ms; --dur-slow: 480ms;

  --max-w: 1440px; --max-w-read: 680px;
  --page-pad-x: clamp(16px, 3vw, 40px);
}

/* Cursor system: one dot, everywhere. Clickable elements signal through
   their own hover states, never through a cursor change. */
body {
  cursor: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="12" height="12"><circle cx="6" cy="6" r="5" fill="%23D0130F"/></svg>') 6 6, auto;
}
a, button, [role='button'], summary, label, select {
  cursor: inherit; /* the UA stylesheet's hand on links would beat the dot */
}
```

**Structure facts** for resource pages: divisions are Management, Good People Record Co. (label), Brands, and Affiliates (Stay Level Records, Stay Level Distribution, The Cabin Recording, Good Merch Only). GPO does not run in-house label services; distribution runs through Stay Level. Nav order: Management, Label, Brands, Affiliates, About, Contact.
