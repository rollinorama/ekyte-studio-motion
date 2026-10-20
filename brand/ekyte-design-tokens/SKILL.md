---
name: ekyte-design-tokens
description: >
  Use this skill whenever working on the ekyte Design System 2026 and needing to apply,
  recommend, or validate design tokens (Figma variables). Triggers include: designing
  components, reviewing Figma screens, writing CSS/code, creating new UI elements,
  or answering questions like "which token should I use for X?". This skill covers
  all three token collections: base, alias, and typography.
---

# ekyte Design System 2026 — Design Tokens Skill

## Architecture Overview

The ekyte design system uses a **three-layer token architecture**:

```
base (primitive values)
  └─ alias (semantic tokens) ← USE THESE IN COMPONENTS
       └─ components
```

**Rule #1**: Always use `alias` tokens in components. Never reference `base` tokens directly in UI elements.

There are 3 variable collections:
- **`base`** — 95 primitive variables (raw colors, scale numbers, type values)
- **`alias`** — 94 semantic variables (what and where to use)  
- **`typography`** — 10 font size variables

---

## Collection: `base`

### Colors — Neutrals
The neutral palette goes from lightest (100) to darkest (options). It is a blue-gray scale.

| Token | Hex | Note |
|-------|-----|------|
| `color/neutral/white` | #FFFFFF | Pure white |
| `color/neutral/100` | #F7F9FC | Near-white, very light blue-gray |
| `color/neutral/200` | #EDF1F7 | Light background |
| `color/neutral/300` | #F0F0F0 | Neutral gray (no blue tint) |
| `color/neutral/400` | #E5E8EB | Border-level gray |
| `color/neutral/500` | #C6CAD7 | Medium gray |
| `color/neutral/600` | #8F9BB3 | Medium-dark, blue-gray |
| `color/neutral/700` | #727594 | Purple-gray |
| `color/neutral/800` | #4F4F4F | Dark gray |
| `color/neutral/900` | #333333 | Very dark gray |
| `color/neutral/1000` | #404040 | Slightly lighter than 900 (use for max-contrast headings) |
| `color/neutral/options` | #222B45 | Deep navy — sidebar only |

### Colors — Brand & Semantic Palettes

Each palette has steps 100–900. The **500 step is always the primary/default**:

| Palette | 500 (primary) | Usage |
|---------|---------------|-------|
| **blue** | #1F74FF | Primary action, links, interactive |
| **green** | #06C131 | Success, positive states |
| **yellow** | #FFAA00 | Warning, attention |
| **red** | #FF0000 | Error, destructive, critical |
| **purple** | #5555F5 | Secondary brand accent |
| **magenta** | #CF26C4 | Special/tertiary accent |

### Scale (numeric base)
Values: 0, 1, 2, 4, 8, 10, 11, 12, 13, 14, 16, 20, 24, 28, 32, 40, 64, 80, 120, 160, 200

Used internally by alias tokens — not for direct use.

### Typography Base
| Token | Value |
|-------|-------|
| `type/font family/body` | nunito |
| `type/font family/heading` | nunito |
| `type/font weight/regular` | regular (400) |
| `type/font weight/semibold` | semibold (600) |
| `type/font weight/bold` | bold (700) |

---

## Collection: `alias` — Color Tokens

### Text Colors (`color/text/*`)

Use exclusively for coloring **text elements** (headings, paragraphs, labels, spans).

#### Heading Text
| Token | Resolves to | Use when |
|-------|-------------|----------|
| `color/text/heading/1000` | neutral/1000 (#404040) | Maximum contrast headings in modals/alerts |
| `color/text/heading/900` | neutral/900 (#333333) | Primary page titles (h1, h2) |
| `color/text/heading/800` | neutral/800 (#4F4F4F) | Secondary headings, subtitles |
| `color/text/heading/700` | neutral/700 (#727594) | Tertiary heading, section labels |
| `color/text/heading/600` | neutral/600 (#8F9BB3) | Muted heading, inactive state |
| `color/text/heading/500` | neutral/500 (#C6CAD7) | Very muted / placeholder heading |
| `color/text/heading/400` | neutral/400 (#E5E8EB) | Heading on dark backgrounds |
| `color/text/heading/300` | neutral/300 (#F0F0F0) | Heading on very dark backgrounds |
| `color/text/heading/200` | neutral/200 (#EDF1F7) | Heading on dark backgrounds |
| `color/text/heading/100` | neutral/100 (#F7F9FC) | Near-white heading on dark bg |
| `color/text/heading/white` | neutral/white (#FFFFFF) | White heading on dark/colored bg |
| `color/text/heading/options` | neutral/options (#222B45) | Heading inside the sidebar/dark menus |

**Default heading**: use `color/text/heading/900` for most page headings.

#### Body Text
| Token | Resolves to | Use when |
|-------|-------------|----------|
| `color/text/body/1000` | neutral/1000 | High-emphasis bold body text |
| `color/text/body/900` | neutral/900 | Body in emphasis/bold contexts |
| `color/text/body/800` | neutral/800 | **Default body text** (paragraphs, descriptions) |
| `color/text/body/700` | neutral/700 | Secondary body, captions |
| `color/text/body/white` | white | Body text on dark surfaces |
| `color/text/body/options` | neutral/options | Body text inside sidebar |

**Default body text**: use `color/text/body/800`.

#### Link Text
| Token | Resolves to | Use when |
|-------|-------------|----------|
| `color/text/link/default` | blue/500 (#1F74FF) | Inline links in text |
| `color/text/link/hover` | blue/600 (#274BDB) | Link on hover/focus |
| `color/text/link/neutral` | neutral/700 (#727594) | Links without emphasis (breadcrumb, nav) |

#### Disabled Text
| Token | Resolves to | Use when |
|-------|-------------|----------|
| `color/text/disabled/100` | neutral/400 | Completely disabled text (lowest contrast) |
| `color/text/disabled/200` | neutral/500 | Disabled placeholder text |
| `color/text/disabled/300` | neutral/600 | Disabled label / field text |

#### Status Text (Semantic)
Each status has three variants — use them together as a set:

| Status | Token | Resolves to | Use for |
|--------|-------|-------------|---------|
| **Info** | `color/text/information/light` | blue/200 | Info banner background |
| **Info** | `color/text/information/default` | blue/500 | Info icon and main text |
| **Info** | `color/text/information/dark` | blue/700 | Info text on light background |
| **Success** | `color/text/success/light` | green/200 | Success badge background |
| **Success** | `color/text/success/default` | green/500 | Success icon and text |
| **Success** | `color/text/success/dark` | green/800 | Success text on light background |
| **Warning** | `color/text/warning/light` | yellow/200 | Warning banner background |
| **Warning** | `color/text/warning/default` | yellow/500 | Warning icon and text |
| **Warning** | `color/text/warning/dark` | yellow/800 | Warning text on light background |
| **Error** | `color/text/error/light` | red/200 | Error message background |
| **Error** | `color/text/error/default` | red/500 | Error icon and text |
| **Error** | `color/text/error/dark` | red/800 | Error text on light background |

**Pattern rule**: The `light` variant always goes on backgrounds/fills; `default` on icons and main text; `dark` on text when the background is already the `light` color.

---

### Surface Colors (`color/surface/*`)

Use for **backgrounds, fills, and borders** of containers, not for text.

#### Background Surfaces
| Token | Resolves to | Use when |
|-------|-------------|----------|
| `color/surface/background/default` | neutral/100 (#F7F9FC) | **Application body background** |
| `color/surface/background/white` | white (#FFFFFF) | Cards, modals, inputs, dropdowns |
| `color/surface/background/highlight` | neutral/200 (#EDF1F7) | Table row hover, highlighted sections |
| `color/surface/background/borders` | neutral/400 (#E5E8EB) | Dividers, card borders, separators |
| `color/surface/background/dark` | neutral/900 (#333333) | Tooltips (dark), overlays, dark badges |

#### Button Surfaces
| Token | Resolves to | Use when |
|-------|-------------|----------|
| `color/surface/buttons/button-on` | blue/500 (#1F74FF) | Primary button — default/active state |
| `color/surface/buttons/button-hover` | blue/600 (#274BDB) | Primary button — hover state |
| `color/surface/buttons/button-disabled` | neutral/700 (#727594) | Text/icon color in disabled button |
| `color/surface/buttons/button-disabled-background` | neutral/200 (#EDF1F7) | Fill of disabled button |
| `color/surface/buttons/white` | white (#FFFFFF) | Ghost/outline button text; text on dark buttons |

---

### Icon Colors (`color/icons/*`)

Use **exclusively on SVG icon elements**. These mirror the text/status tokens but are semantically separated to allow future independent changes.

#### Main Icons (neutral)
| Token | Resolves to | Use when |
|-------|-------------|----------|
| `color/icons/main/light` | neutral/500 (#C6CAD7) | Inactive/placeholder icon |
| `color/icons/main/default` | neutral/700 (#727594) | **Default icon color** in the UI |
| `color/icons/main/dark` | neutral/900 (#333333) | Icon in emphasis / selected state |

#### Disabled Icons
| Token | Resolves to | Use when |
|-------|-------------|----------|
| `color/icons/disabled/100` | neutral/400 | Fully disabled icon (lowest contrast) |
| `color/icons/disabled/200` | neutral/500 | Disabled icon, slightly more visible |
| `color/icons/disabled/300` | neutral/600 | Disabled icon in interactive element |

#### Status Icons
Same structure as text status, but for icons only:

| Status | Token suffix | Base color |
|--------|-------------|-----------|
| Information | `color/icons/information/light/default/dark` | blue/200, blue/500, blue/700 |
| Success | `color/icons/success/light/default/dark` | green/200, green/500, green/800 |
| Warning | `color/icons/warning/light/default/dark` | yellow/200, yellow/500, yellow/800 |
| Error | `color/icons/error/light/default/dark` | red/200, red/500, red/800 |

---

## Collection: `alias` — Size Tokens

### Spacing (`sizes/spacing/*`)

Base unit: 4px. Use only values from this scale — no ad-hoc values.

| Token | Value | Use when |
|-------|-------|----------|
| `sizes/spacing/none` | 0px | Explicitly removing spacing |
| `sizes/spacing/sp-4` | 4px | Gap between icon and label; internal chip padding |
| `sizes/spacing/sp-8` | 8px | Small button padding; gap between inline elements |
| `sizes/spacing/sp-10` | 10px | Vertical padding of inputs and selects |
| `sizes/spacing/sp-12` | 12px | Horizontal input padding; list item gap |
| `sizes/spacing/sp-16` | 16px | Card padding; dense grid column gap |
| `sizes/spacing/sp-24` | 24px | Section padding; form group gap |
| `sizes/spacing/sp-32` | 32px | Modal/drawer padding; between-section space |
| `sizes/spacing/sp-40` | 40px | Page-level container padding; large block margin |

**Top-level shortcuts** also exist (`sizes/sp-4` through `sizes/sp-40`) — these are equivalent to the `sizes/spacing/*` variants.

### Border Radius (`sizes/radius/*`)

| Token | Value | Recommended component |
|-------|-------|----------------------|
| `sizes/radius/none` | 0px | Tables, separators, full-bleed elements |
| `sizes/radius/rd-4` | 4px | Checkboxes, radios, small inputs |
| `sizes/radius/rd-8` | 8px | **Buttons, inputs, dropdowns, select fields** |
| `sizes/radius/rd-16` | 16px | **Cards, modals, panels, dialogs** |
| `sizes/radius/rd-24` | 24px | Banners, callouts, large info blocks |
| `sizes/radius/rd-32` | 32px | Wide chips, large tags |
| `sizes/radius/rd-40` | 40px | FAB buttons, avatars |
| `sizes/radius/rd-200` | 200px | Pills, badge-style chips, toggles |

### Border Width (`sizes/border/*`)

| Token | Value | Use when |
|-------|-------|----------|
| `sizes/border/none` | 0px | No border (explicit reset) |
| `sizes/border/br-1` | 1px | Default borders on inputs, cards, tables |
| `sizes/border/br-2` | 2px | Focus rings, selected states, emphasis borders |

---

## Collection: `typography`

The system uses **Nunito** exclusively for all text (both body and headings).

### Font Sizes

| Token | Value | Use when |
|-------|-------|----------|
| `fontsize/body/xs` | 10px | Counters, footnotes, timestamps in dense tables |
| `fontsize/body/sm-table` | 11px | Table cell content in dense layouts; axis labels in charts |
| `fontsize/body/sm` | 12px | Form labels, helper text, badges, chips |
| `fontsize/body/sm-text` | 13px | Secondary descriptions, sidebar items, metadata |
| `fontsize/body/xm` | 14px | Placeholder text, dropdown items, nav items |
| `fontsize/body/md` | 16px | **Primary body text, paragraphs, inputs** |
| `fontsize/body/lg` | 20px | Intro text of sections, KPI values, card hero text |
| `fontsize/headings/h1` | 12px | Category labels in uppercase (eyebrow text) |
| `fontsize/headings/h2` | 16px | Panel headers, form section labels, table headers |
| `fontsize/headings/h3` | 20px | Card subtitles, accordion headers, drawer titles |

**Note**: h1 at 12px is used for uppercase category labels (SECTION_LABEL style), not full-size headings. The heading scale is intentionally compact.

---

## Decision Guide: Which Token to Use?

### "I need to color a text element"
→ Use `color/text/*` tokens
- Title/heading → `color/text/heading/{weight}`
- Paragraph → `color/text/body/{weight}` (default: `/800`)
- Link → `color/text/link/default`
- Error text → `color/text/error/default` (on white) or `/dark` (on error/light bg)
- Disabled → `color/text/disabled/300`

### "I need to color an icon"
→ Use `color/icons/*` tokens (never `color/text/*`)
- Default icon → `color/icons/main/default`
- Inactive icon → `color/icons/main/light`
- Error icon → `color/icons/error/default`
- Disabled → `color/icons/disabled/100`

### "I need a background color"
→ Use `color/surface/background/*`
- App body → `/default`
- Card/modal → `/white`
- Row hover → `/highlight`
- Divider/border → `/borders`
- Dark tooltip → `/dark`

### "I need a button state color"
→ Use `color/surface/buttons/*`
- Button active → `button-on`
- Button hover → `button-hover`
- Button disabled (text) → `button-disabled`
- Button disabled (bg) → `button-disabled-background`

### "I need spacing"
→ Use `sizes/spacing/sp-{value}` — never hardcode px values outside the scale.

### "I need border-radius"
→ Inputs/buttons: `rd-8` | Cards/modals: `rd-16` | Pills: `rd-200`

---

## Common Mistakes to Avoid

| ❌ Wrong | ✅ Correct |
|----------|-----------|
| Using `color/neutral/800` directly on a text element | Use `color/text/body/800` |
| Using `color/text/error/default` to color an error icon | Use `color/icons/error/default` |
| Using `color/text/heading/white` on a white background | Only use `/white` tokens on dark/colored surfaces |
| Using `color/neutral/options` (#222B45) outside the sidebar | That deep navy is exclusively for the sidebar/dark-menu context |
| Using `warning/light` color for error/light context | Never mix status families — stay within one status type |
| Hardcoded `16px` padding | Use `sizes/spacing/sp-16` |
| Border-radius `50%` for pills | Use `sizes/radius/rd-200` (200px achieves the pill effect) |
| Any font family other than Nunito | The system has one font: `type/font family/body` = Nunito |
| `font-size: 15px` | Not in the scale — use 14px (xm) or 16px (md) |

---

## Token Quick-Reference by Component

| Component | Surface | Text | Icon | Radius | Border |
|-----------|---------|------|------|--------|--------|
| Page background | `surface/bg/default` | — | — | — | — |
| Card | `surface/bg/white` | `text/heading/900` | — | `rd-16` | `br-1` + `bg/borders` |
| Input (default) | `surface/bg/white` | `text/body/800` | `icons/main/default` | `rd-8` | `br-1` + `bg/borders` |
| Input (disabled) | `surface/bg/highlight` | `text/disabled/300` | `icons/disabled/300` | `rd-8` | `br-1` |
| Input (error) | `surface/bg/white` | `text/error/default` | `icons/error/default` | `rd-8` | `br-2` + `text/error/default` |
| Button primary | `surface/buttons/button-on` | `text/heading/white` | `icons/main/light` | `rd-8` | none |
| Button hover | `surface/buttons/button-hover` | `text/heading/white` | — | `rd-8` | none |
| Button disabled | `surface/buttons/button-disabled-background` | — | `icons/disabled/200` | `rd-8` | none |
| Alert — info | `text/information/light` | `text/information/dark` | `icons/information/default` | `rd-8` | `br-1` + `text/information/default` |
| Alert — success | `text/success/light` | `text/success/dark` | `icons/success/default` | `rd-8` | `br-1` |
| Alert — warning | `text/warning/light` | `text/warning/dark` | `icons/warning/default` | `rd-8` | `br-1` |
| Alert — error | `text/error/light` | `text/error/dark` | `icons/error/default` | `rd-8` | `br-1` |
| Table header row | `surface/bg/highlight` | `text/heading/700` | — | `rd-4` | `br-1` + `bg/borders` |
| Table row hover | `surface/bg/highlight` | — | — | — | — |
| Sidebar | `neutral/options` (direct) | `text/heading/white` | `icons/main/light` | none | — |
| Pill/Badge | status `light` | status `dark` | status `default` | `rd-200` | none |
| Tooltip dark | `surface/bg/dark` | `text/heading/white` | — | `rd-8` | none |
| Link inline | — | `text/link/default` | — | — | — |
