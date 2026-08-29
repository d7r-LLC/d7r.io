# d7r Open Source — Design System v1

The official base UX for every d7r open source GitHub Pages site. Derived from the d7r
v2 design contract (Concept C "terminal prompt", `d7r/docs/ux/DESIGN-SYSTEM.md`) and
adapted for public documentation surfaces: polished, glossy glass, soft glows, dark-first
with a light theme, restrained motion.

**The stylesheet is the system.** `site/assets/d7r-os.css` carries every token and
component below. To apply the brand to another spec site, copy the stylesheet, use the
markup patterns in `site/index.html`, and change only content.

## Brand rules (binding, inherited from v2)

1. **Logo is the terminal prompt** `~/d7r.io` with a blinking block cursor. JetBrains
   Mono bold; `~/`, `7`, `.io`, and the cursor take the emerald accent; `d`, `r` take
   ink. Spec sites render their own prompt the same way (e.g. `~/derp-spec.dev`).
2. **Emerald contrast rule (hard).** `#10b981` is a dark-surface color and fails
   contrast on white. Light surfaces use emerald-700 `#047857`. The stylesheet encodes
   this in the theme tokens; never bypass them.
3. **Primary buttons are terminal chips.** Ink `#0d1117` background, emerald mono
   label; hover inverts to emerald background with ink text, plus a soft glow.
   Button labels may use command style (`browse --specs`).
4. **Eyebrows are mono and auto-prefixed `~/`** via CSS. Write the word; the prompt
   comes free.
5. **Icons are inline SVG** (Lucide-style, 24x24 viewBox, `stroke="currentColor"`,
   stroke-width 2). Never emoji.
6. **Voice:** confident, evidence-first, technical-credible, never hypey. The draft
   status flag stays visible on every spec site.

## Themes

Dark is the design source; light adapts. `<html data-theme="dark|light">` overrides;
with no attribute, `prefers-color-scheme` decides. The toggle persists to
`localStorage['d7r-theme']`. A no-flash boot script in `<head>` applies the stored theme
before first paint.

| Token | Dark | Light |
|---|---|---|
| `--bg` | `#0d1117` | `#f8fafc` |
| `--ink` | `#e6edf3` | `#0d1117` |
| `--accent` | `#10b981` | `#047857` |
| `--glass` | `rgba(22,27,34,.66)` | `rgba(255,255,255,.82)` |

Contrast: body text and accents meet 4.5:1 in both themes. Glass surfaces keep >= 0.8
opacity in light mode so cards stay visible.

## Signature surfaces

- **Aurora**: two fixed, blurred emerald/teal radial glows drifting on 26s/32s
  alternating loops. Ambience, never information.
- **Glass cards**: `backdrop-filter: blur(14px)` over `--glass`, 1px `--glass-line`
  border, a top-left shine gradient, soft shadow. Hover adds an emerald border and glow;
  no scale transforms, no layout shift.
- **Terminal cards** (`.termcard`): ink window with traffic lights and mono content, for
  code and registry specimens. Always ink, in both themes.
- **Dot gridfield**: faint masked dot grid behind the hero.
- **Numbered editorial cards**: mono `01`-style index, thin rule, big title, role chip.

## Typography

- **Plus Jakarta Sans** 400/500/600/700/800: body and headings. Headings 800,
  `letter-spacing: -0.02em`.
- **JetBrains Mono** 400-700: logo, eyebrows, numbers, chips, metadata, terminal cards.
- Body 17px/1.65. Hero clamps to `4.1rem` max.

## Motion

Soft and purposeful; nothing fast, nothing bouncy.

- Reveal-on-scroll: opacity + 18px rise, 550ms `cubic-bezier(0.22,1,0.36,1)`, once.
- Micro-interactions: 200ms color/border/shadow transitions.
- Logo cursor blinks at 1.15s steps.
- `prefers-reduced-motion` disables all of it, including the cursor.

## Accessibility checklist (per page)

- 4.5:1 text contrast in both themes; focus-visible rings; 44px touch targets;
- semantic landmarks, `aria-label` on the theme toggle and icon-only links;
- keyboard order matches visual order; color never the only signal.

## Rollout to spec sites

Each spec site keeps its own content and IA but adopts: the stylesheet, the prompt logo
with its own domain, the masthead, theme toggle, status flag, glass cards, and colophon.
Per-site accent stays emerald; specs are distinguished by content and role chips, not by
color forks.
