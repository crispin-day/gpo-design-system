# How the live site implements this

Read this when you are working inside the `crispin-day/good-people-only` repo, or
when you need to know why the code contains tokens the brand guide tells you not to
use. For work outside that repo, `assets/tokens.css` is the cleaner starting point.

Source of truth for the identity is the site itself: `crispin-day/good-people-only`,
design world "A State of Play", v1.0 July 2026. The guide document lives at the repo
root as `STATE-OF-PLAY-BRAND-GUIDE.md`, with an HTML rendering at
`docs/gpo-brand-guide.html`. Two earlier documents, `docs/archive/GPO-BRAND-GUIDANCE.md`
and `docs/archive/DESIGN_GUIDE.md`, describe the retired identity and are superseded.
Do not take styling direction from them.

That repo auto-deploys to production on push to `main`, so changes go through a branch
and a pull request.

## Font wiring

The site loads both faces through `next/font/google` in `app/layout.tsx` and exposes
them as CSS variables, which is why the font tokens indirect through `--font-geo` and
`--font-jetbrains` rather than naming the families directly:

```ts
import { Jost, JetBrains_Mono } from "next/font/google"

const jost = Jost({ variable: "--font-geo", ... })
const jetbrains = JetBrains_Mono({ variable: "--font-jetbrains", ... })
```

```css
--font-display: var(--font-geo), "Futura", "Avenir Next", "Century Gothic", system-ui, sans-serif;
--font-sans:    var(--font-geo), "Futura", ui-sans-serif, system-ui, sans-serif;
--font-mono:    var(--font-jetbrains), ui-monospace, "SF Mono", Menlo, monospace;
```

Outside Next.js, load Jost and JetBrains Mono from Google Fonts directly and name the
families in the stack, as `assets/tokens.css` does.

## Tokens that exist in code but should not be used

`app/globals.css` carries three groups of leftovers from the earlier white-ground
design. They are still defined because components elsewhere in the tree reference
them, not because they are sanctioned.

| In the code | Why to avoid it |
|---|---|
| `--gray-50` through `--gray-950` | Designed for white grounds. On cream several sit near 1:1 contrast and disappear entirely. This is what made the Inquiries frame and the roster rules invisible, which is why `--border-1` and `--border-2` were derived from the paper instead. |
| `--true-black: #000000`, `--true-white: #FFFFFF` | Pure black and pure white surfaces are Never item 8. |
| `--paper-cool: #FAFAF7` | Effectively an off-white ground. The system has one ground and it is `--paper`. |

The semantic aliases are safe and are what components should reference:
`--fg-1` (ink), `--fg-2` (`--gray-700`), `--fg-3` (`--dim`), `--bg-1` (paper),
`--border-strong` (ink), `--accent` (red).

Note `--fg-3` was deliberately moved off `--gray-500`, which only reached 3.6:1 on the
new paper, onto `--dim` at 5.5:1. If you are tempted to reach into the grey ramp for
secondary text, that migration is the reason not to.

One more small drift: `--text-7xl: 180px` exists in `globals.css` but never made it
into the guide's token appendix. It is in `assets/tokens.css` for parity.

## Where the pieces are

| Thing | Path in the site repo |
|---|---|
| Token definitions | `app/globals.css` |
| Font loading | `app/layout.tsx` |
| Logo and wordmark files | `public/` |
| Partner and client logos | `public/brands/` |
| Artist photography | `public/artists/` |

## A caution about existing pages

Not every page in the repo is a model of the system. The Good Kid pitch pages under
`app/good-kid/` use the GPO paper and ink tokens correctly, but they are GPO pitch
surfaces, not Good Kid brand surfaces. Good Kid has its own separate brand guide with
a completely different palette and typeface. Do not read those CSS modules as a
reference for either system.
