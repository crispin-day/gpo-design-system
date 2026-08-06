# GPO Design System

The Good People Only brand and style guide, **A State of Play**, packaged as a Claude
Code plugin so any Claude environment can load it on demand.

It is self-contained. A machine with this plugin installed needs neither the GPO HQ
repo nor the website checked out to produce correct GPO material.

## Install

```bash
claude plugin marketplace add crispin-day/gpo-design-system
```

```bash
claude plugin install gpo-design-system@gpo
```

Then it loads itself whenever a task involves GPO visual material: web pages, decks,
one-sheets, pitch documents, social assets, email signatures, or work in the
`good-people-only` repo.

To pick up later changes:

```bash
claude plugin marketplace update gpo
```

## Without the plugin system

Any environment that reads skills from a directory can use this directly. Copy
`skills/gpo-design-system/` into `~/.claude/skills/` (user scope) or `.claude/skills/`
(project scope).

## What's inside

| Path | What it is |
|---|---|
| `skills/gpo-design-system/SKILL.md` | The operative rules: color, type, logo, motif, layout, motion, cursor, copy, and the Never list |
| `references/brand-guide.md` | The full source guide, verbatim |
| `references/implementation.md` | How the live site wires it up, and which tokens in the code are leftovers not to use |
| `assets/tokens.css` | Paste-ready `:root` block, cursor and type rules included |
| `assets/starter.html` | Correct page skeleton to build from |
| `assets/logos/` | Logo and wordmark files |

## Source of truth

The canonical document is `STATE-OF-PLAY-BRAND-GUIDE.md` in the `good-people-only`
repo, which is the site itself. `references/brand-guide.md` here is a copy. If the
canonical guide changes, re-copy it and bump the version in
`.claude-plugin/plugin.json`.

## Use

Published so Claude environments can reach it without credentials. The brand,
the logo files, and the guide remain the property of Good People Only, and are not
offered under an open source licence. Use them for GPO work.
