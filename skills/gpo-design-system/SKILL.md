---
name: gpo-design-system
description: >-
  The Good People Only (GPO) brand and style guide, "A State of Play". Use whenever
  producing or reviewing visual material for Good People Only, goodpeopleonly.com,
  Good People Record Co., GPO Brands, or GPO Management, including web pages, landing
  pages, decks, one-sheets, pitch documents, social assets, email signatures, and any
  HTML/CSS/React work in the good-people-only repo. Also use when asked whether
  something is "on brand" for GPO, when writing GPO copy, or when recoloring partner
  logos for GPO materials. Reach for this even when the request never says "brand" or
  "design system", because GPO's rules are prescriptive and deliberately unlike
  default modern styling, so anything built without them will be wrong in predictable
  ways.
---

# GPO Design System: A State of Play

Good People Only is a boutique artist management company, record label, and brand
partnership agency. Its identity is called **A State of Play**: work approached with
the seriousness of craft and the looseness of play. Visually it draws from warm-paper
editorial print and Bauhaus geometric posters.

The register is **playful and intentional, never childish**. Play shows up as geometry
in motion, a wink of red, a punchline in the copy. It never shows up as bounce
physics, cartoon energy, or decoration for its own sake.

This guide is prescriptive. The rules came from a founder who rejected specific things
by name, so the "Never" list is as binding as the palette.

## Before you build anything

1. Read the tokens in `assets/tokens.css` and paste them in rather than retyping hex
   values. Hand-typed colors drift, and this palette has no near-neighbours that pass
   contrast on cream.
2. For web work, start from `assets/starter.html`, which is a correct skeleton with
   the cursor, ground, and type already right.
3. Build.
4. Run the self-check at the bottom of this file before you deliver. Most failures
   here are not taste failures, they are the five or six specific things listed there.

If you need the full source document, it is `references/brand-guide.md`. Read it when
you are doing something the summary below does not cover: the contour motif in detail,
photography treatment, the logo motion spec, or the full copy voice. For how the live
site actually implements this, including tokens that exist in code but should not be
used, read `references/implementation.md`.

## The default failure mode

The most likely wrong output is a competent generic modern website: white background,
rounded cards with soft shadows, a blue or gradient accent, pill buttons, a sans-serif
system font, and em dashes in the copy. Every one of those is off-brand here.

GPO is cream paper, square corners, frameless sections, one geometric typeface, and
red used the way a printer would use a second ink: sparingly, because it costs extra.
Hold that image and most decisions follow.

## Color

Nothing is pure black or pure white. The ground is always cream.

| Token | Hex | Role |
|---|---|---|
| `--ink` | `#1A1A18` | Text, rules, the logo, recolored partner logos. Warm near-black. 14.9:1 on paper. |
| `--paper` | `#EEE7D7` | The ground. Every surface is this cream. |
| `--paper-2` | `#E7DFCB` | Slightly deeper cream for subtle layering. |
| `--red` | `#D0130F` | Punctuation only. 4.51:1, so large or bold text and marks only, never body text. |
| `--green` | `#00712C` | Reserve accent. Almost never used. Do not introduce it without a reason. |
| `--dim` | `#5F5B50` | Secondary text. Body-safe at 5.50:1. |
| `--border-1` | `#DBD3BE` | Hairline on cream, used sparingly. |
| `--border-2` | `#C6BCA2` | Stronger hairline on cream. |

**Red is punctuation, not paint.** It appears on the smallest unit that carries the
meaning: one word in a sentence, the period after the wordmark, an arrow, a 6px dot,
the cursor, a focus outline. The reason is contrast economy. Red at `#D0130F` only
clears 4.51:1 on cream, so it is legible as a mark and illegible as a wash, and one
red element per viewport is what makes that element read as the point.

Never use red for backgrounds, button fills, panels, section borders, or body text,
and never let two red elements compete in one viewport.

**Grey ramp caution.** A neutral grey ramp exists in the site's CSS, inherited from a
white-ground design. On cream those greys sit near 1:1 contrast and disappear. For
anything that must be visible, use `--ink`, `--dim`, or the two cream-derived borders.

## Typography

One family carries the identity: **Jost**, an open revival of Futura, the geometric
face of the reference material. Fallback stack:
`Jost, "Futura", "Avenir Next", "Century Gothic", system-ui, sans-serif`. Futura PT is
an acceptable paid substitute.

**JetBrains Mono** exists for data-like fragments only: timestamps, catalogue numbers.
Never for navigation, labels, or headings.

| Voice | Spec | Used for |
|---|---|---|
| Display | Jost 700, UPPERCASE, tracking -0.025em, line-height 0.92 to 1.0, clamp 36 to 96px | Page titles: "WHERE BRANDS MEET CULTURE." |
| Tracked caps label | Jost 400 to 500, UPPERCASE, 12px, tracking 0.22em, `--dim` | Kickers, eyebrows, section labels |
| Body | Jost 400, 16 to 18px, line-height 1.55, `--dim` | Paragraphs, card copy |
| Company voice | Jost 600 italic, 30 to 56px, tracking -0.015em, ink, with the one emphasized word set upright and red inside the italic | Pull quotes |

Display type is uppercase. Sentence-case display is not used. Headings get
`text-wrap: balance`, body measure runs 62 to 68ch.

The house rhythm is setup and punchline: a quiet tracked-caps line hands off to the
wordmark or the payoff. "Surround yourself with" resolves into "GOOD PEOPLE ONLY."

## Logo

The mark is a solid ink disc with **GOOD** stacked as **GO / OD** knocked out of it,
so the background shows through the letterforms. The knockout is the point: the logo
contains no white, ever. On cream, cream shows through. On ink, use the white disc.

Files are in `assets/logos/`:

| File | Use on |
|---|---|
| `logo-knockout.png` | Cream and paper grounds. The default. |
| `logo-circle-black.png` | Favicon source, one-color contexts. |
| `logo-circle-white.png` | Ink and dark grounds. |
| `wordmark-good-black.png` / `-white.png` | Rare, small lockups. |

Clear space is at least 25% of the disc diameter on all sides. Minimum size 24px.
Never recolor the disc red or green, and never put a white plate behind it. In
interactive contexts the disc may spin on hover at 100 degrees per second, and on exit
it must unwind back to zero rather than snap.

The company name set in type always takes a red period: the words are ink, the period
is red. "GOOD PEOPLE ONLY."

## The contour motif

The system has exactly one graphic device: roughly 20 nested contours that morph from
circle at the center to squircle at the edge, drawn in red at about 0.44% of field
size stroke weight, grown outward from the logo disc. It reads as a record's grooves
and a playing field at once.

On the homepage hero it is alive on canvas: it breathes slowly, winds under the
pointer, and a click drops a needle-drop pulse that rolls outward. Everywhere else it
is a single static ink contour trace, such as the outline that draws itself around
roster photo tiles on hover. In print or static layouts a single low-density red
contour ring set may anchor a cover or divider.

One field per surface, maximum. Do not fill it, do not shadow it, do not render it in
green, and do not invent a second motif. It is an identity mark, not a texture.

## Layout

- Max content width 1440px. Page padding `clamp(16px, 3vw, 40px)`. Reading measure 680px.
- **Frameless by default.** Sections separate by whitespace and typography, not boxes.
  Card frames were explicitly removed from the site's inquiry sections. Do not add
  boxes, panels, or bordered cards unless information genuinely needs containment.
- Major structural breaks use a 2px solid ink rule, at the page header bottom and the
  CTA top. That is the only heavy rule in the system.
- Hairlines are for row separation inside lists only.
- Spacing scale: 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128 / 192px. Section
  padding lives around `clamp(48px, 7vw, 88px)`.
- Corners are square. The exceptions are the photo-tile superellipse at 7% / 5.6% and
  actual circles. No 8px-radius card aesthetics.

## Motion

Motion is the play in the system, and it is rationed.

- **One payoff per surface.** The homepage's payoff is the needle-drop field. A
  subpage's payoff is the ink trace drawing around a photo. Do not stack effects.
- Easing `cubic-bezier(0.2, 0.8, 0.4, 1)`, durations 160ms fast, 240ms base, 480ms slow.
- Entrances are a 16px fade-up over 600ms with a 60ms stagger. Nothing flies, bounces,
  or rotates in.
- Link hover grows a 1px underline left to right via `transform: scaleX`, 240ms.
- Continuous motion is allowed only where it is content: the hero field, and the
  client-logo strip on /brands as a 60s linear loop that pauses on hover, carries an
  edge-fade mask, and falls back to a static wrapped list under reduced motion.
- All motion is time-based per millisecond, never frame-based, and must respect
  `prefers-reduced-motion`.

## Cursor, on web

The visitor's presence is the system's atom: a small red disc. One cursor everywhere,
a 10px red dot as an inline SVG data-URI with the hotspot centered. It does not change
over clickable elements, because the elements carry their own hover affordance.

Text fields keep a normal caret. Touch is unaffected. Inside the hero field the OS
cursor is hidden and the canvas draws its own small contour form.

Never reintroduce the hand pointer or size-changing cursors. If you add clickable
elements, check that no component stylesheet brings back `cursor: pointer`.

## Photography and partner logos

Artist and people photos are 4:5 portrait tiles with 7% / 5.6% corner radius and a
cream multiply veil at 12% opacity, so photos sit *in* the paper world rather than on
top of it. On hover the ink contour trace draws itself around the tile.

No blurred image backgrounds, no duotones, no circle or porthole crops.
Illustration and 3D are off-brand. The contour is the only graphic.

Partner and client logos are always normalized into the system: all fills recolored to
ink `#1A1A18`, knockout areas to paper `#EEE7D7`, displayed at 72% opacity rising to
100% on hover. Third-party logos never appear in their own brand colors inside GPO
materials.

## Voice and copy

Short declaratives. Concrete nouns. The confidence of understatement: "The roster is
small on purpose." Setup and punchline is the rhythm. Emphasis is one red word, chosen
because it is the word that matters, not for decoration.

**No em dashes or en dashes, ever.** Use commas, colons, or periods. This is absolute
and it applies to every piece of GPO copy.

Avoid AI-inflected filler: "elevate", "seamless", "unlock", "delve", stacked hype
adjectives, rhetorical throat-clearing. If a sentence could open any company's
website, cut it.

Phrases in circulation: "Working in a State of Play", "Surround yourself with GOOD
PEOPLE ONLY.", "Where brands meet culture.", "Campaigns that don't just reach
audiences, they mobilize them.", "Separate companies, shared standards."

Locations line is "Toronto · Los Angeles" with an interpunct. Email is
contact@goodpeopleonly.com. CTAs are direct: "Get in Touch ↗".

## Structure facts

Divisions are Management, Good People Record Co. (label), Brands, and Affiliates
(Stay Level Records, Stay Level Distribution, The Cabin Recording, Good Merch Only).
GPO does not run in-house label services; distribution runs through Stay Level.
Nav order: Management, Label, Brands, Affiliates, About, Contact.

## Never

These were rejected by the founder by name. Do not reintroduce them, and if a request
seems to call for one, say so and propose the in-system alternative instead.

1. Bouncing or physics ball animations of any kind.
2. Circle or porthole crops on photos or cards.
3. Blurred image backgrounds.
4. Monospace type in navigation or headings.
5. Scrolling marquees of text or artist names. The /brands client-logo strip is the
   single sanctioned carousel.
6. "Pause motion" UI buttons.
7. Visible frames or borders around content sections.
8. Pure white `#FFFFFF` or pure black `#000000` surfaces.
9. Red as a background, panel, or button fill.
10. Em dashes in any copy.
11. Childish or forced playfulness. If an idea needs the word "fun" to justify it, cut it.
12. Second decorative motifs, textures, gradients, or drop shadows. One soft hover
    shadow token exists and that is the ceiling.

## Self-check before delivering

Run through this. It catches nearly every real failure.

- Is the ground `#EEE7D7` rather than white, and is there no `#FFFFFF` or `#000000`
  surface anywhere?
- Is every red instance a mark, a word, a dot, or an arrow, with no red fills, and no
  more than one red element competing per viewport?
- Are corners square, apart from circles and the 7% / 5.6% photo tiles?
- Are sections separated by space and typography rather than boxes or borders?
- Is all display type uppercase Jost, with mono confined to data fragments?
- Is there exactly one motion payoff on the surface, and does it respect
  `prefers-reduced-motion`?
- On web, is the red dot cursor present, and has no stylesheet reintroduced
  `cursor: pointer`?
- Are partner logos recolored to ink rather than shown in brand colors?
- Does the copy contain zero em dashes, and does the wordmark carry a red period?
- Read the Never list once more against what you built.
