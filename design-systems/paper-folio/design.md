---
version: 0.1
name: Paper Folio
description: A bound book of plates and notes. The Dream Journal becomes a heirloom object, not an app — each dream is a numbered folio, each interpretation a small essay set in serif. Two serifs (EB Garamond body + Cormorant Garamond italic display) with no sans-serif except for micro-labels ≤11px. The palette is hand-mixed earth pigments on warm cream paper — rust, ochre, dusty rose, sage. Surfaces always carry a 40%-opacity grain overlay. Frames, hairlines, ornaments (※ ❦ ✦), dashed rules, drop caps, and letterpress-style stamp chips. Illustrations are flat-color surrealist plates in the Magritte / de Chirico tradition — literal scenes containing one impossibility per plate.

colors:
  paper: "#ECE3D0"
  vellum: "#F0E6D2"
  ink: "#2A221B"
  ink-mark: "#1F1A16"
  ink-soft: "rgba(42, 34, 27, 0.68)"
  ink-faint: "rgba(42, 34, 27, 0.42)"
  rust: "#A64B2A"
  ochre: "#C08A3E"
  dusty-rose: "#C98A8A"
  sage: "#7A8A6A"
  rule: "rgba(42, 34, 27, 0.16)"

shadows:
  paper-lift: "4px 4px 0 rgba(42, 34, 27, 0.12)"
  stamp-press: "2px 2px 0 rgba(42, 34, 27, 0.18)"

textures:
  grain: "Procedural fractal-noise SVG overlay at ~40% opacity, mix-blend-mode: multiply. Required on every page surface — without it the system reads as a flat web page."

typography:
  display:
    fontFamily: "'Cormorant Garamond', serif"
    fontStyle: italic
    fontSize: 54px
    fontWeight: 400
    lineHeight: 0.92
    letterSpacing: "-1px"
  title:
    fontFamily: "'Cormorant Garamond', serif"
    fontStyle: italic
    fontSize: 24px
    fontWeight: 400
    lineHeight: 1.15
  body:
    fontFamily: "'EB Garamond', serif"
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.8
    letterSpacing: "+0.1px"
  drop-cap:
    fontFamily: "'Cormorant Garamond', serif"
    fontStyle: italic
    fontSize: 56px
    color: "{colors.rust}"
    lineHeight: 0.7
    float: left
  eyebrow:
    fontFamily: "'Inter', system-ui, sans-serif"
    fontSize: 10px
    fontWeight: 500
    letterSpacing: 0.4em
    textTransform: uppercase
    color: "{colors.rust}"
  running-head:
    fontFamily: "'JetBrains Mono', ui-monospace, monospace"
    fontSize: 12px
    fontWeight: 500
    letterSpacing: 0.2em
    textTransform: uppercase
  caption:
    fontFamily: "'EB Garamond', serif"
    fontStyle: italic
    fontSize: 13px
    fontWeight: 400
    lineHeight: 1.55
    color: "{colors.ink-soft}"

spacing:
  space-1: 4px
  space-2: 8px
  space-3: 12px
  space-4: 16px
  space-6: 24px
  space-8: 32px
  space-12: 48px
  page-margin-x: 28px
  page-margin-y: 36px
  column-gutter: 20px

radii:
  stamp: 2px
  circle: 50%
  none: 0

borders:
  frame: "1.5px solid {colors.ink-mark}"
  rule: "1px solid {colors.rule}"
  rule-dashed: "1px dashed {colors.rule}"
  hairline: "0.5px solid {colors.ink-soft}"

components:
  running-head:
    description: "Top-of-screen folio identifier. Mono uppercase, e.g. 'VOL. III · NO. 047'. Always present. Sits 24px from the top edge, tracked +0.2em. Pairs with a hairline rule below it."
  framed-plate:
    border: "{borders.frame}"
    borderRadius: "{radii.stamp}"
    boxShadow: "{shadows.paper-lift}"
    description: "Every illustration sits inside a 1.5px hairline frame. A small 'Plate I' label tucks into the top edge of the frame, on the rule itself. The 4px hard offset shadow gives the impression of a book lying on a table."
  drop-cap:
    description: "Opens every interpretation. 56px italic Cormorant in {colors.rust}, line-height 0.7, floated left. The first 2–3 lines wrap around it. The drop-cap is the system's most romantic move — use it on every interpretation lede."
  ornament-break:
    description: "Section breaks use a centered ornament glyph (※, ❦, ✦, ✺) flanked by hairline rules. Pattern: ────  ✦  ────"
  rule-dashed:
    border: "{borders.rule-dashed}"
    description: "Between rows in lists and tables. Solid rules are reserved for chapter starts and bottom of frames."
  stamp-chip:
    border: "{borders.frame}"
    borderRadius: "{radii.stamp}"
    padding: "4px 10px"
    fontFamily: "'Inter', sans-serif"
    fontSize: 10px
    letterSpacing: 0.25em
    textTransform: uppercase
    transform: "rotate(-2deg)"
    description: "Tags rendered as letterpress stamps. 1.5px ink border, sans micro-label inside, slight -2 to -4° rotation. Stamps look pressed, not printed."
  cta-block:
    background: "{colors.ink-mark}"
    color: "{colors.paper}"
    borderRadius: "{radii.stamp}"
    padding: "14px 24px"
    boxShadow: "{shadows.paper-lift}"
    fontFamily: "'EB Garamond', serif"
    description: "Primary CTAs are square solid ink blocks with a 4px hard offset shadow — like a rubber stamp pressed onto paper. EB Garamond label, never sans."
  mood-chip:
    background: "transparent"
    border: "1px solid {colors.ink-soft}"
    borderRadius: "{radii.stamp}"
    padding: "4px 10px"
    fontFamily: "'EB Garamond', serif"
    fontStyle: italic
    fontSize: 13px
    description: "Italic serif word inside a 1px ink-soft border. Mood/feeling tags only; system tags use the stamp-chip pattern instead."
  ornament-glyphs:
    description: "Permitted symbols: ※ ❦ ✦ ✺ ✴ ─ ━ ──. No emoji ever. The hand-set typographic ornaments are the only decorative glyphs."
  paper-grain:
    description: "Procedural noise SVG (feTurbulence baseFrequency 0.65, 3 octaves) layered as ::after at ~40% opacity, mix-blend-mode multiply. Applied to every page-level surface. Skipping the grain is the most common mistake — the system reads as a flat web page without it."
---

# Paper Folio

## When to reach for this system

Use Paper Folio when the user is treating dream-keeping as a slow, literary practice. The product becomes an heirloom object — bound, numbered, archival — not an app.

**Best for** — users who keep physical journals, who read fiction, who buy hardcover books and stationery. Daytime use, slower interaction patterns, deeper retention per session. Premium pricing signals strongest of the three systems. Neighbors: Day One, Substack reader mode, the Penguin Classics app, MUBI, Are.na. Books, not apps.

**Avoid for** — rapid-tap interactions, gamification, social sharing, push-notification-heavy surfaces, anything that needs to feel instantaneous. The system is built on cream + serif + etched illustration; it cannot accommodate neon, gradient, or glassmorphism without breaking.

## Aesthetic direction

| | |
|---|---|
| **Visual references** | René Magritte · Giorgio de Chirico · Penguin Classics covers (Coralie Bickford-Smith) · old natural-history plates · letterpress chapbooks · pressed-flower notebooks · sepia photographs |
| **Tactile qualities** | Cream paper with soft grain. Ink slightly bleeding into fiber. Hand-set type. Hairline rules, dashed dividers, stamped seals. Nothing pristine — everything has been opened and closed. |
| **Three keywords** | *literary. archival. patient.* |

## Color

Earth pigments on warm cream paper. Every accent feels hand-mixed. Never a saturated digital color.

### Tokens

```css
--pf-paper      : #ECE3D0;             /* page background */
--pf-vellum     : #F0E6D2;             /* slight elevation */
--pf-ink        : #2A221B;             /* body text */
--pf-ink-mark   : #1F1A16;             /* marks, frames, CTAs */
--pf-ink-soft   : rgba(42,34,27, 0.68);
--pf-ink-faint  : rgba(42,34,27, 0.42);
--pf-rust       : #A64B2A;             /* primary accent */
--pf-ochre      : #C08A3E;             /* highlights */
--pf-rose       : #C98A8A;             /* tender emotion */
--pf-sage       : #7A8A6A;             /* calm emotion */
--pf-rule       : rgba(42,34,27, 0.16);
```

### Role assignments

| Token | Role |
|---|---|
| `--pf-paper` | Page background. Always with grain overlay at 40% multiply. |
| `--pf-vellum` | Modal surfaces, the face of a framed plate, the clock dial on illustrations. |
| `--pf-ink` | All body text. Reads as warm near-black; never pure `#000000`. |
| `--pf-ink-mark` | Frame borders, drop shadow color, CTA fills. Slightly darker than body ink. |
| `--pf-rust` | Primary accent. Stamps, moon/sun in illustrations, highlighted italic words, drop caps, eyebrow labels. |
| `--pf-ochre` | Secondary stamps, marker-pen-style highlights under important phrases. |
| `--pf-rose` | Tender emotions only — "want to cry", "tender", "soft". Mood chips. |
| `--pf-sage` | Calm emotions, memory tags, distant elements in illustrations (clouds, mountains). |
| `--pf-rule` | All dividers (solid 1px or dashed 1px). |

## Typography

**Two serifs and one micro-sans.** This is the only system in the pack that refuses sans-serif at body and display sizes.

- **EB Garamond** — body, captions, transcribed dreams. Weight 400 at 16px / 1.8 line-height. Reads at the rhythm of a paperback novel.
- **Cormorant Garamond Italic** — display, dream titles, drop caps, accented italic words. The romantic serif. Never used upright in this system; if it's Cormorant, it's italic.
- **Inter** (≤11px only) — system labels and uppercase eyebrows. The only sans usage allowed. Acts as a printed stamp / page header.
- **JetBrains Mono** — running heads (VOL. III · NO. 047), folio numbers. Acts as the book's gutter type.

### Scale

| Token | Size | Family | Weight | Use |
|---|---|---|---|---|
| `--ty-display` | 54 / 0.92 / -1px | Cormorant Garamond italic | 400 | Cover headlines on home and detail screens |
| `--ty-title` | 22–26 / 1.15 | Cormorant Garamond italic | 400 | Dream titles in folio listing. Pair with a roman EB Garamond subtitle. |
| `--ty-body` | 16 / 1.8 / +0.1px | EB Garamond | 400 | Interpretation paragraphs, transcribed dreams |
| `--ty-drop-cap` | 56 / 0.7 / float | Cormorant italic | 400 | Opens every interpretation. Always in rust. |
| `--ty-eyebrow` | 9–10 / +0.4em / uppercase | Inter | 500 | Stamped eyebrows: `━━ 三月十一 · FOLIO 047` |
| `--ty-running-head` | 12 / +0.2em / uppercase | JetBrains Mono | 500 | Top-of-screen folio identifier |
| `--ty-caption` | 13 / 1.55 italic | EB Garamond italic | 400 | Plate captions, footnotes, editorial sign-offs |

### Signature treatments

- **Drop cap opens every interpretation.** 56px italic Cormorant in `--pf-rust`, floated left, the first 2–3 lines wrap around it. Without the drop cap the interpretation reads as a paragraph instead of an essay opening.
- **Cormorant is always italic in this system.** No upright treatment exists for the display serif. If you need an upright serif moment, use EB Garamond instead.
- **Every screen has a running head and a signature line.** Top: `VOL. III · NO. 047`. Bottom: a page indicator or editorial sign-off (`—— 三月十一夜，梦的图册编者 谨录`).
- **Sans-serif appears only at ≤11px and only uppercase, ≥0.25em tracked.** Sentence-case Inter does not exist in this system.
- **Italic Cormorant accents inside EB Garamond runs.** One italicized phrase per paragraph, in rust, marks the emotional center of the sentence.

## Layout

The product is **literally pretending to be a book**.

1. **Every screen is a page.** Top: running head (`VOL. III · NO. 047`). Bottom: signature line or page indicator. Both always present.
2. **Illustrations are framed plates.** Every dream illustration sits inside a 1.5px ink frame with a small "Plate I" label tucked into the top edge. Plates carry a 4px hard offset shadow — like a book lying on a table.
3. **Dashed rules and ornaments structure content.** Section breaks: centered ornament (※, ❦, ✦) flanked by hairline rules. Between list rows: dashed rules. Solid rules: chapter starts and bottom-of-frame only.
4. **Stamps, not buttons.** Tags and chips are letterpress stamps — 1.5px ink border, slight -2 to -4° rotation, all caps, sans micro-label. Primary CTAs are square solid ink blocks with a 4px hard offset shadow.
5. **Paper grain always on.** A procedural noise overlay at ~40% opacity multiplied over every page. Without it the system collapses into a flat web design.

### Spacing & radii

```css
/* spacing — multiples of 4, slightly larger than the other systems for book breathing */
--space-1: 4px;  --space-2: 8px;   --space-3: 12px;  --space-4: 16px;
--space-6: 24px; --space-8: 32px;  --space-12: 48px;
--page-margin-x: 28px;
--page-margin-y: 36px;

/* radii — sharp, paper-like */
--radius-stamp  : 2px;   /* all buttons, chips, frames */
--radius-circle : 50%;   /* ornaments only */
/* every other corner is square */

/* borders */
--border-frame  : 1.5px solid #1F1A16;
--border-rule   : 1px solid rgba(42,34,27,0.16);
--border-dashed : 1px dashed rgba(42,34,27,0.16);
--shadow-paper  : 4px 4px 0 rgba(42,34,27, 0.12);
--shadow-stamp  : 2px 2px 0 rgba(42,34,27, 0.18);
```

## Depth

The system uses **hard offset shadow** (no blur) and **paper grain** as its depth language. No gradients, no glow.

- **Paper-lift shadow** — `4px 4px 0 rgba(42,34,27,0.12)`. Used under framed plates and CTA blocks. The hard offset gives the feel of an object resting on paper.
- **Stamp-press shadow** — `2px 2px 0 rgba(42,34,27,0.18)`. Smaller offset for stamp chips and small buttons.
- **Grain texture** — the most important depth cue in the system. Procedural noise at 40% opacity multiplied over every page. Reads as paper fiber, not as a CSS layer.

## Illustration direction

Illustrations are **flat-color surrealist scenes** with hand-drawn line accents. Compositions are literal but the contents are impossible: a red moon resting on a windowsill, a train passing through a wall, a fish with wings.

### Prompt scaffold

```
[impossible scene] in the style of René Magritte,
warm cream paper, muted earth tones,
hand-drawn line accents, flat color illustration,
slight paper grain, vintage natural-history plate,
palette: #ECE3D0 #A64B2A #C08A3E #7A8A6A #1F1A16
```

### Composition rules

- The scene is always a place (a window, a wall, a horizon line) — not a floating object.
- One impossibility per plate (moon on sill, train through wall, fish with wings).
- Color is limited to 4–5 earth pigments per illustration.
- Add procedural grain on top at ~40% opacity, multiply mode.
- **No glow, no blur, no luminosity** — paper does not emit light.
- Every plate is framed (1.5px ink hairline) and labeled (`Plate I`, `Plate II`).

## Voice & copy

Write like an **editor of an old anthology**. Copy is formal, slightly archaic, with publisher's flourishes (`Vol. III · No. 047`, 附, 谨录). Interpretation reads like a footnote from a critical edition — careful, attributive, never assertive.

| Slot | Example |
|---|---|
| Running head | `VOL. III · NO. 047` |
| Cover headline | *昨夜，世界又翻了一页。* |
| Dream title + subtitle | *停在窗台的红色月亮* — *—— 附 · 一扇悬空的门* |
| Interpretation opener | **红**色的月亮是一种返乡的信号。 *(rust drop-cap on 红, then EB Garamond body)* |
| Editorial sign-off | *—— 三月十一夜，梦的图册编者 谨录* |
| Plate caption | *Plate I · 红月与窗* |

## Do & Don't

### Do

- Number everything (Folio 047, Plate I, Volume III). The book metaphor must be visible.
- Use drop caps to open every interpretation. The drop cap is the system's most romantic move.
- Render tags as letterpress stamps with -2 to -4° rotation.
- Overlay paper grain noise at ~40% multiply on every page.
- Reserve sans-serif for micro-labels only (≤11px, uppercase, tracked ≥0.25em).
- Use ornament glyphs (※, ❦, ✦) for section breaks. Hand-set, not emoji.
- Pair italic Cormorant titles with roman EB Garamond subtitles.

### Don't

- Don't use pure white (`#FFFFFF`). Always cream-tinted (`--pf-paper`).
- Don't use pure black (`#000000`). Always warm near-black (`--pf-ink-mark`).
- Don't add gradients, glow, or backdrop-blur. The system is matte, paper-flat.
- Don't use saturated digital colors. Earth pigments only.
- Don't use the system for time-sensitive notifications — it is too slow-feeling to convey urgency.
- Don't substitute emoji for the ornament glyphs.
- Don't render Cormorant upright. If you need upright serif, use EB Garamond.
- Don't skip the grain overlay. The system collapses without it.

## CJK & International

EB Garamond and Cormorant cover Latin only. For Chinese content, pair with **思源宋体 / Noto Serif SC** at weights 400–500.

| Role | Latin | Chinese counterpart |
|---|---|---|
| Display / italic titles / drop cap | Cormorant Garamond italic | Noto Serif SC 500 |
| Body / interpretation | EB Garamond 400 | Noto Serif SC 400 |
| Eyebrow / stamp labels | Inter 500 uppercase tracked | Inter 500 (Latin-only stamps), or Noto Sans SC 600 (Chinese stamps, no transform) |
| Running head | JetBrains Mono uppercase | Noto Sans Mono CJK SC 500 or keep mono Latin paired with Chinese date (`VOL. III · 三月十一`) |

**Loading**:
```html
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@1,400;1,500&family=EB+Garamond:ital,wght@0,400;1,400&family=Inter:wght@500&family=JetBrains+Mono:wght@500&family=Noto+Serif+SC:wght@400;500&display=swap" rel="stylesheet">
```

**Adjustments for CJK runs**:
- Line-height 1.9–2.0 for Chinese body (up from 1.8). Noto Serif SC is square and visually full.
- Letter-spacing 0 on every CJK run; `+0.1px` Latin tracking does not apply.
- **No italic Chinese serif exists.** For the italic-accent treatment inside body, substitute one of: (a) color swap to `--pf-rust`, (b) weight contrast (500 inside 400), (c) underline with `text-decoration-color: --pf-ochre`.
- Drop cap works on Chinese — pick a meaningful opening character and render in `--pf-rust` at 56px.
- Mood chips: substitute italic Cormorant with Noto Serif SC 500 at the same size.
- Stamp chips with Chinese characters drop the uppercase + tracking pattern; use Noto Sans SC 600 at 11–12px instead.
- Full-width Chinese punctuation （，。：；！？「」） in body.
- Insert ASCII space between adjacent CJK and Latin (盘古之白).

**Known CJK gap**: no italic Chinese serif on Google Fonts. The italic-display contrast partially collapses; lean on the **drop cap, framed plates, grain texture, and stamp chips** to carry the system identity when italic alone can't.

## Iteration checklist

1. Every screen has a running head (`VOL. III · NO. 047`) and a signature line.
2. Every interpretation opens with a rust drop cap, italic Cormorant, 56px.
3. Every illustration sits in a 1.5px ink frame with a "Plate I" label and a 4px paper-lift shadow.
4. Every tag is a stamp chip (1.5px border, sans micro-label, -2 to -4° rotation).
5. Every page has a 40% multiply grain overlay.
6. Every divider is hairline 1px — solid for chapter starts, dashed between rows.
7. No gradients, no glow, no backdrop-blur anywhere.

## Known gaps

- **Grain performance**: SVG noise overlays can be heavy on long-scrolling pages. Use a tiled noise PNG instead of fresh `feTurbulence` per surface if you hit FPS issues.
- **No dark-mode variant.** The system depends on cream paper as ground. A dark version would require a different palette and break the book metaphor.
- **Search and dense data UIs are awkward**. Spreadsheet-like surfaces don't fit the book metaphor. Either avoid them or render them as table-of-contents pages (numbered, paginated).
- **Illustration cost**: every dream needs a Magritte-style plate. AI-generation works for archetypes (moon, door, fish) but breaks on specific dream content. Plan for a curated library of ~30 plates with fallbacks.
- **Notifications and urgent surfaces don't fit.** The system has no "urgent" treatment. For modal alerts, break out of the system and use a plain modal in `--pf-vellum` with a stamp-chip CTA.
