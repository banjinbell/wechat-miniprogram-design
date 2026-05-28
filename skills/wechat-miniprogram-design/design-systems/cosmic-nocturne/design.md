---
version: 0.1
name: Cosmic Nocturne
description: A reverent nighttime system for a dream journal. The product reads as a small celestial event observed from a dark room — deep cosmic indigo grounds, warm gold moonlight, a soft violet nebula behind illustrations, and a romantic italic serif (Cormorant Garamond) carrying every emotional sentence. A second voice — system sans, uppercase, wide-tracked — carries dates, modes, and process labels. Borders are veils (rgba whites at low alpha), shadows are glows, and a faint star field lives behind every dark surface. The system is engineered for legibility against near-black backgrounds and breaks visually on white.

colors:
  cosmos: "radial-gradient(ellipse at 50% 0%, #2A1A5E 0%, #14102E 45%, #0A0B2E 100%)"
  void: "#0A0B2E"
  nebula: "#A78BFA"
  moon-gold-warm: "#FDE68A"
  moon-gold-deep: "#F59E0B"
  rose-aura: "#F9A8D4"
  ink: "#F5E9FF"
  ink-soft: "rgba(245, 233, 255, 0.62)"
  ink-faint: "rgba(245, 233, 255, 0.35)"
  stroke-veil: "rgba(245, 233, 255, 0.08)"

shadows:
  glow-moon: "0 0 60px rgba(253, 230, 138, 0.6)"
  glow-nebula-soft: "0 0 80px rgba(167, 139, 250, 0.35)"
  card-elevated: "0 12px 40px rgba(10, 11, 46, 0.6)"
  cta-warm: "0 8px 32px rgba(245, 158, 11, 0.35)"

typography:
  display:
    fontFamily: "'Cormorant Garamond', serif"
    fontSize: 56px
    fontWeight: 400
    lineHeight: 0.95
    letterSpacing: "-1px"
  title-l:
    fontFamily: "'Cormorant Garamond', serif"
    fontSize: 32px
    fontWeight: 400
    fontStyle: italic
    lineHeight: 1.1
    letterSpacing: "-0.3px"
  body-serif:
    fontFamily: "'Cormorant Garamond', serif"
    fontSize: 19px
    fontWeight: 400
    lineHeight: 1.7
    letterSpacing: "0.2px"
  body-serif-italic:
    fontFamily: "'Cormorant Garamond', serif"
    fontSize: 19px
    fontWeight: 400
    fontStyle: italic
    lineHeight: 1.7
  eyebrow:
    fontFamily: "'Inter', -apple-system, system-ui, sans-serif"
    fontSize: 11px
    fontWeight: 500
    lineHeight: 1.2
    letterSpacing: 0.3em
    textTransform: uppercase
  caption:
    fontFamily: "'Inter', -apple-system, system-ui, sans-serif"
    fontSize: 11px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: "0.5px"
  micro-label:
    fontFamily: "'JetBrains Mono', ui-monospace, monospace"
    fontSize: 11px
    fontWeight: 500
    letterSpacing: 0.15em
    textTransform: uppercase

spacing:
  space-1: 4px
  space-2: 8px
  space-3: 12px
  space-4: 16px
  space-6: 24px
  space-7: 28px
  space-8: 32px
  space-12: 48px
  screen-padding-x: 24px
  screen-padding-y: 28px
  text-column-gutter: 56px

radii:
  pill: 9999px
  card: 22px
  input: 14px
  chip: 14px

canvas:
  width: 100vw
  height: 100vh

components:
  star-field:
    description: "25–50 sub-pixel white dots (2–3px) absolutely positioned across every dark surface. Each carries a 4px white box-shadow for halo. Never decorative — it is the texture that says 'this is night.' Without it the system falls flat."
  moon:
    width: 64px
    height: 64px
    background: "radial-gradient(circle at 35% 35%, {colors.moon-gold-warm} 0%, #FDE68A 40%, {colors.moon-gold-deep} 100%)"
    boxShadow: "{shadows.glow-moon}"
    description: "The system's signature focal point. Top-right or top-left quadrant of any illustration. Acts as the single light source for the screen."
  halo-blur:
    background: "radial-gradient(circle, rgba(167, 139, 250, 0.55) 0%, transparent 65%)"
    filter: "blur(28px)"
    description: "Soft violet/rose halo placed behind illustration subjects. 28–34px gaussian blur. Bleeds toward edges; never has a hard boundary."
  italic-accent:
    fontFamily: "'Cormorant Garamond', serif"
    fontStyle: italic
    color: "{colors.ink-soft}"
    description: "One or two italicized words inside an otherwise plain serif sentence. The system's typographic heartbeat — never use bold for emphasis."
  micro-label-chip:
    background: transparent
    color: "{colors.ink}"
    padding: "0"
    fontFamily: "'Inter', sans-serif"
    fontSize: 11px
    letterSpacing: 0.3em
    textTransform: uppercase
    description: "Standalone uppercase eyebrow used above titles. Sets the system as 'precise' while serif sets it as 'felt'. Often joined to a Chinese date with a center dot (TONIGHT · 三月十二)."
  veil-card:
    background: "rgba(245, 233, 255, 0.04)"
    border: "1px solid {colors.stroke-veil}"
    borderRadius: "{radii.card}"
    padding: 24px
    description: "All elevated containers. Glass-like — never opaque. Pair with screen-level blur if the card sits over a busy illustration."
  cta-primary:
    background: "radial-gradient(circle at 35% 35%, {colors.moon-gold-warm}, {colors.moon-gold-deep})"
    color: "{colors.void}"
    padding: "14px 28px"
    borderRadius: "{radii.pill}"
    boxShadow: "{shadows.cta-warm}"
    description: "Pill-shaped warm-gold radial button. Reads as a small captured moon. Only one CTA-primary per screen."
  mood-chip:
    background: "rgba(245, 233, 255, 0.06)"
    border: "1px solid {colors.stroke-veil}"
    color: "{colors.ink}"
    padding: "6px 14px"
    borderRadius: "{radii.pill}"
    fontFamily: "'Cormorant Garamond', serif"
    fontStyle: italic
    fontSize: 14px
    description: "Italic serif chip carrying single emotional words (untethered, tender, threshold). Never uppercase, never sans."
  divider-veil:
    height: 1px
    background: "{colors.stroke-veil}"
    description: "All horizontal rules. Never opaque gray — the rule should suggest containment without enforcing it."
  illustration-frame:
    description: "Illustrations break the screen gutter and bleed to the device edge. Pair every full-bleed illustration with a narrow text column (56px gutter) so book-column reading and cinematic image sit side by side."
---

## Overview

Cosmic Nocturne is a **nighttime, reverent system** for a dream journal — built for the moment between waking and reaching for the phone in the dark. The product becomes a quiet ritual, not an app.

The structural premise is **light against dark**. Every surface assumes a near-black cosmic background (`{colors.cosmos}` radial, never flat), and every accent emits a little light. The four accents — moon-gold, nebula violet, rose aura, ink-violet white — are treated as luminous, not painted. Hard edges are rare. The bright type sits over a halo; the CTA looks like a small captured moon; even body text carries a violet undertone so it harmonizes with the violet darkness behind it.

The type stack is **two voices working in opposition**. **Cormorant Garamond** carries every emotional sentence — page titles, dream titles, interpretation paragraphs, mood chips, italicized accent words. **Inter / SF Pro** carries everything functional — dates, modes, system labels, progress states. The serif is felt; the sans is precise. Italic, not bold, is the serif's emphasis tool; uppercase + 0.3em tracking is the sans's discipline.

Illustrations follow a strict aesthetic: one recognizable subject (animal, doorway, figure) silhouetted in warm glow against violet/indigo, no hard linework, always emitting its own light. Compositions break the screen gutter to feel cinematic, then a narrow text column (56px gutter) returns the eye to the rhythm of a printed book.

**Density philosophy: spacious, atmospheric, one focal point per screen.** Vertical gaps between blocks run 28–48px. Empty space is the system's primary tool for inducing reverence. Every screen contains exactly one element that emits light — a moon, a halo, a glowing CTA. Two focal points compete and break the spell.

**Key Characteristics:**
- Two-voice type: Cormorant Garamond (everything emotional) and Inter / SF Pro (everything functional). Never cross-mix.
- Background is always a vignetted radial (`{colors.cosmos}`), never flat. The radial collapses to `{colors.void}` only on small elevated cards.
- Star field of 25–50 sub-pixel dots lives behind every dark surface as texture, never decoration.
- All borders are `{colors.stroke-veil}` — opaque grays do not exist in the system.
- Italic — not bold — is the serif's only emphasis tool. Bold collapses the elegance.
- Moon-gold is the brand mark and the only "warm" accent — used as radial fills, never as flat color.
- Every screen has exactly one focal point that emits light.
- Illustrations bleed to the device edge; text stays inside a 56px gutter (book-column inside a cinematic frame).

## Colors

### Palette

- **Cosmos** (`{colors.cosmos}`): The default page background. Always a vignetted radial — `#2A1A5E` at top-center, fading through `#14102E` to `#0A0B2E` at the corners. Never flat. The radial does the work of pulling the eye toward the top of the screen where the moon or focal point lives.
- **Void** (`{colors.void}` — `#0A0B2E`): The solid fallback. Use for elevated cards under 380px tall where the radial gradient would collapse to garbage. Reads as black-with-blue-bias.
- **Nebula** (`{colors.nebula}` — `#A78BFA`): The secondary glow. Halo behind illustrations, outline borders at 35% alpha, the "thinking" state of process indicators.
- **Moon-gold** (`{colors.moon-gold-warm}` `#FDE68A` → `{colors.moon-gold-deep}` `#F59E0B`): The primary brand accent. Always rendered as a radial, never as a flat fill — the gradient is what makes it feel like a real light source. Used for the brand mark, italic accent words inside titles, and the single CTA on each screen.
- **Rose Aura** (`{colors.rose-aura}` — `#F9A8D4`): Emotional highlights. The phrase the user should feel ("母亲的注视"). Used sparingly — overuse turns the system saccharine.
- **Ink** (`{colors.ink}` — `#F5E9FF`): All body text on dark. Never pure white — the violet undertone keeps it sitting inside the palette rather than fighting it. Plain `#FFFFFF` reads as a defect.
- **Ink-Soft** (`{colors.ink-soft}` — `rgba(245, 233, 255, 0.62)`): Secondary text, captions, italic body. Anything that should recede.
- **Ink-Faint** (`{colors.ink-faint}` — `rgba(245, 233, 255, 0.35)`): Tertiary chrome, disabled states, hairline labels.
- **Stroke-Veil** (`{colors.stroke-veil}` — `rgba(245, 233, 255, 0.08)`): All dividers, card outlines, mood-chip borders. The system never uses an opaque gray.

### Defaults

- **Default surface background**: `{colors.cosmos}` radial. Apply to `<body>` and to every full-screen container.
- **Default headline color**: `{colors.ink}` — with one italicized word in `{colors.ink-soft}` for emphasis (the system's signature contrast).
- **Default body color**: `{colors.ink}` for long-form reading; `{colors.ink-soft}` for secondary paragraphs and captions.
- **Default brand-mark color**: `{colors.moon-gold-warm}`/`{colors.moon-gold-deep}` radial — never flat gold.
- **Default chip border**: `{colors.stroke-veil}`.
- **Default illustration palette**: void → nebula → moon-gold → rose-aura → ink, in that order from background to foreground.

When a moment needs warmth, swap the italic accent color from `{colors.ink-soft}` to `{colors.moon-gold-warm}`. The single accent word then reads as illuminated rather than recessed.

## Typography

### Font Family

The system runs two faces, each locked to its role.

**Cormorant Garamond** (display, body, accents) is the serif voice — a high-contrast Garaldine with a particularly expressive italic. Used for every page title, dream title, interpretation paragraph, mood chip, and italicized accent word inside an otherwise plain sentence. Weight 400 is default; italic is the system's signature. Never reach for bold — italic carries every emphasis the system needs.

**Inter / SF Pro Text** (functional chrome) is the sans voice — used exclusively for dates, system labels, section eyebrows, tab labels, progress states, and process indicators. Weight 400–500. Tracking increases as size decreases — micro labels at 9–11px get 0.25–0.3em letter-spacing and `text-transform: uppercase`. Sentence-case sans does not exist in this system.

Never use Cormorant for system chrome (dates, modes, progress). Never use Inter for emotional content. The two-role separation is the typographic structure.

### Typography Scale

| Token | Size | Family | Weight | Use |
|---|---|---|---|---|
| `{typography.display}` | 56 / 0.95 / -1px | Cormorant Garamond | 400 | Home greeting, dream titles in detail view, the question at the heart of each screen |
| `{typography.title-l}` | 32 / 1.1 / -0.3px | Cormorant Garamond italic | 400 | Dream titles in list, screen titles, section headers |
| `{typography.body-serif}` | 19 / 1.7 / +0.2px | Cormorant Garamond | 400 | Interpretation paragraphs, transcribed dreams — long-form reading |
| `{typography.body-serif-italic}` | 19 / 1.7 | Cormorant Garamond italic | 400 | Pull quotes, lyrical inset paragraphs, action prompts |
| `{typography.eyebrow}` | 11 / 1.2 / +0.3em / uppercase | Inter | 500 | Mode/date eyebrows above titles |
| `{typography.caption}` | 11 / 1.5 / +0.5px | Inter | 400 | Progress indicators, system feedback, secondary captions |
| `{typography.micro-label}` | 11 / mono / +0.15em / uppercase | JetBrains Mono | 500 | Record IDs (`RECORD · 048`), folio numbers, dev-style readouts |

### Defaults

- **Default for a hero greeting or screen title**: `{typography.display}` — Cormorant 400 at 56px with -1px tracking. Italicize one or two words inside it for the signature contrast.
- **Default for a dream-list title**: `{typography.title-l}` — Cormorant italic at 32px.
- **Default for body / interpretation**: `{typography.body-serif}` — Cormorant 400 at 19px / 1.7 line-height.
- **Default for any system label, mode, or date**: `{typography.eyebrow}` — Inter 500 at 11px, uppercase, 0.3em tracked.
- **Default for an italic emphasis word**: `{typography.body-serif-italic}` — never bold the underlying weight.

### Signature Treatments

- **Every display headline contains at least one italicized word.** Cormorant's italic carrying one or two words inside an otherwise upright sentence is the system's signature. A purely upright display headline reads as untreated.
- **Every Inter label is uppercase with ≥0.18em tracking.** Sentence-case Inter does not exist; it would break the precise/felt opposition.
- **Every body block uses line-height ≥1.7.** The serif's vertical stress needs the room.
- **Eyebrow labels combine Latin and Chinese with a center dot.** `TONIGHT · 三月十二` is the system's canonical eyebrow pattern. Mixing scripts here is intentional — both belong in this system.
- **Italic carries emphasis, always.** Bold is forbidden in serif runs. Even product names italicize.

### Typography Principles

The voice contrast is **felt serif ↔ precise sans**. Switching either side flattens the system. Cormorant should always feel **calm and slightly lyrical** — never centered for long runs, never letter-spaced, never bolded. Inter should always feel **distant and procedural** — uppercase, wide-tracked, used only for chrome. Long-form body text is always left-aligned and ragged-right; centering body breaks the book-column rhythm.

## Layout

### Canvas System

The system targets phone-first vertical canvases (`100vw × 100vh` per screen). Default screen padding is `24px` horizontal × `28px` vertical. Vertical gaps between content blocks run `28–48px` — generous breathing is non-negotiable. The 24px horizontal padding can break at illustration boundaries: illustrations bleed full-width to the device edge, then text columns return to a 56px inner gutter for book-column reading.

### Pixel Unit

Spacing snaps to a **4px grid**. Hairlines are 1px (dividers) or 1.5px (frames). Border-radius follows a small set: `22px` for cards, `14px` for inputs/chips, `9999px` for pills. Square corners are reserved for the rare "stamp" treatment — most chrome is gently rounded.

### Persistent Chrome

Three elements appear on most screens:
- **Eyebrow line** — Inter 11px uppercase tracked label paired with a Chinese date (`TONIGHT · 三月十二`). Top-left of the content area.
- **One focal point** — moon, halo, or glowing CTA. Exactly one per screen.
- **Star field** — 25–50 absolute-positioned 2–3px white dots scattered behind the surface. Twinkle animation is optional but tasteful.

### Atmospheric Overlay Stack

Each dark surface carries (z-order, bottom to top):
1. The `{colors.cosmos}` radial as ground.
2. The star field, at low z (behind illustration).
3. Halo-blur layer behind any illustration subject (`{components.halo-blur}`).
4. The illustration (or block of glass cards).
5. Text column inside the 56px gutter, on top.

Skipping the star field is the most common mistake. It is texture, not decoration.

## Depth and Elevation

### Glow as Depth

Cosmic Nocturne uses **emission, not drop shadow**, as the depth language. Elevated elements emit a soft radial glow into their surroundings:

- **Moon glow** (`{shadows.glow-moon}`) — 60px warm-amber glow. Used on the moon, on the primary CTA, on small "lit" stamps.
- **Nebula glow** (`{shadows.glow-nebula-soft}`) — 80px soft violet glow at 35% alpha. Used behind illustration subjects and behind elevated cards on long scrolls.
- **CTA warmth** (`{shadows.cta-warm}`) — 32px amber drop-glow under primary CTAs.
- **Card elevation** (`{shadows.card-elevated}`) — the only "hard" shadow in the system, used for modal-style cards that need to read as separate from the page. Even this is soft: 40px blur at 60% navy alpha.

### Veil Borders

Cards, chips, and dividers use `{colors.stroke-veil}` (1px white at 8% alpha) instead of opaque rules. The veil suggests containment without enforcing it — appropriate for a system that wants to feel like a room lit by candle, not a UI grid.

### Star Field as Spatial Cue

The star field provides ambient depth without requiring shadow on individual elements. It is part of the surface itself.

## Shapes and Treatment

### Border Radius

- `22px` (cards) — book-page round.
- `14px` (inputs, chips, mood chips, modals).
- `9999px` (pills, brand mark, CTAs).
- Square corners only on the rare letterpress-style "stamp" elements.

### Border Weights

- **1px** for all dividers and veil borders. Solid `{colors.stroke-veil}`.
- **1.5px** for illustration frames and stamp chips.
- **2px** only on focused inputs (nebula at 35% alpha).

### Decorative Element Types

**Moon** — Radial-gradient 64–90px disk in moon-gold with a 60px gold glow. The system's signature mark. Tucked into the top-right or top-left quadrant of illustrations and the brand wordmark.

**Halo-blur** — 28–34px gaussian-blurred radial behind illustration subjects. Soft violet, rose, or amber. Never has a hard boundary.

**Veil card** — 4% white fill, 8% white stroke, 22px radius. The default elevated container.

**Mood chip** — Italic serif word inside a 6×14px-padded pill with veil border. Never uppercase.

**Eyebrow line** — Uppercase Inter 11px paired with a Chinese date and a center dot.

**Star field** — 25–50 absolute 2–3px white dots with 4px white box-shadow halo and optional 3s twinkle keyframe.

**Primary CTA** — Pill in moon-gold radial fill with `{colors.void}` text. Always uppercase Inter label or italic Cormorant phrase, never sentence-case sans.

**Drop cap (optional)** — On the longest interpretation passages, a 56px italic Cormorant character in moon-gold floats at the paragraph opening.

## Do's and Don'ts

### Do

- Use italic Cormorant for one or two words inside a plain serif sentence — the contrast is the system's heartbeat.
- Let illustrations bleed full-width to the device edge; pair them with narrow 56px-gutter text columns underneath.
- Use moon-gold sparingly — it should always feel like a real light source, never an accent color.
- Use Inter uppercase tracking for dates, modes, and system labels — never for emotional content.
- Mix Chinese and English/Latin numerals freely — both belong here.
- Scatter 25–50 sub-pixel stars behind every dark surface. Without them the system reads as flat.
- Keep one and only one focal point per screen — moon, halo, or glowing CTA.
- Use radial gradients for every gold and every dark background. Flat fills break the luminous feel.

### Don't

- Don't use pure white (`#FFFFFF`). Always `{colors.ink}` or warmer — pure white breaks the violet harmony.
- Don't use the system on light or cream backgrounds. It requires near-black to breathe.
- Don't add emoji. The moon glyphs (✦, ✧) are permitted very sparingly; nothing else.
- Don't use bold serif. Italic carries emphasis; bold collapses the elegance.
- Don't combine moon-gold with bright red, green, or pure cyan. The palette is a closed system.
- Don't draw opaque gray dividers. All borders are `{colors.stroke-veil}`.
- Don't have two focal points compete on a single screen.
- Don't use Cormorant for system chrome or Inter for emotional content. Cross-mixing voices flattens the system.

## CJK & International Content

Cormorant Garamond does not cover CJK glyphs. For Chinese (or other CJK) content, pair it with **思源宋体 / Noto Serif SC** at weights 400–500.

### Recommended Chinese Pairing

| Role | Latin (default) | Chinese counterpart |
|---|---|---|
| Display / titles / italic accents | Cormorant Garamond 400 + italic | Noto Serif SC 500 (no italic — see Known CJK Gap) |
| Body / interpretation | Cormorant Garamond 400 | Noto Serif SC 400 |
| System labels / dates / eyebrows | Inter 500 uppercase tracked | Inter 500 uppercase tracked (kept Latin — for Chinese dates use full-width 三月十二) |

### Loading

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;1,400;1,500&family=Inter:wght@400;500&family=Noto+Serif+SC:wght@400;500&display=swap" rel="stylesheet">
```

### Universal CJK Adjustments

- **Line-height**: increase Chinese body to 1.85–1.95 (up from the Latin 1.7). Noto Serif SC characters are square and visually full.
- **Letter-spacing**: set to 0 on every CJK run. The system's mood-chip serif italic looks elegant on Latin but compressed on CJK.
- **No italic on Noto Serif SC**: there is no credible italic Chinese serif on Google Fonts. Substitute the italic-accent treatment with one of: (a) color change to `{colors.moon-gold-warm}`, (b) faux-italic at 6–8° (acceptable when the run is ≤4 characters), or (c) one character set in a contrasting weight (700 inside a 400 sentence).
- **Text-transform: uppercase on Inter labels**: keep as-is for Latin. For Chinese dates, use the canonical full-width form (`三月十二`, `二〇二五年三月`).
- **Eyebrow pattern**: `TONIGHT · 三月十二` mixes Latin and Chinese on purpose — keep both. Pure-Chinese eyebrows feel heavier; pure-Latin loses cultural grounding.
- **Punctuation**: full-width Chinese punctuation （，。：；！？「」（）） in body; half-width permitted in mixed Latin/Chinese lines.
- **Space between CJK and Latin (盘古之白)**: insert an ASCII space between every Chinese character and adjacent Latin character or digit. `读取潜意识 03 / 07`, not `读取潜意识03/07`.

### Aesthetic Notes for This System

The system's voice contrast — felt italic serif vs. precise sans — partially collapses in a CJK build because there is no italic Chinese serif. Compensate by leaning on the **non-typographic** signature elements: the moon, the halo-blur, the star field, the moon-gold radial. These carry the emotional voice when italic alone can't. Use color-swap (`{colors.moon-gold-warm}`) or weight-swap to mark accented words instead of italic.

### Known CJK Gap

- **No CDN-loadable italic Chinese serif.** The italic Cormorant treatment is the system's signature; in CJK the closest substitutes are color, weight, or faux-italic. None replicate the elegance of true italic.
- **No CDN Chinese counterpart for Inter Mono labels.** The micro-label treatment (mono uppercase tracked) is Latin-only. For Chinese readout text use Noto Serif SC 500 at smaller size with no transform — it reads as "system" without trying to be mono.

## Responsive Behavior

The system is built phone-first (375–430px viewport). Tablet and desktop expand horizontally by holding the text column at 480–560px and centering it; illustrations continue to bleed full-bleed to the viewport edge. No breakpoints adjust type scale — display remains 56px on every size, since the system assumes the user is reading at arm's length on a phone.

### Animation Triggers

- The star field carries a 3–4s twinkle keyframe at low amplitude (opacity 0.4 → 0.8). Reduce or disable under `prefers-reduced-motion`.
- The moon glow has a slow 6s pulse (opacity 0.85 → 1.0).
- Transitions between screens cross-fade at 400–600ms with a subtle vertical drift (8px). No hard slide transitions.

### Print Behavior

The system is not built for print. Cream-paper printing of dark-cosmic surfaces produces unreadable output. Use System C (Paper Folio) instead for any print or export-to-PDF surface.

## Iteration Guide

1. Any new screen gets the `{colors.cosmos}` radial and 25–50 stars. Don't skip the star field.
2. Any new headline contains at least one italicized Cormorant word. The italic contrast is non-negotiable.
3. Any new system chrome uses Inter uppercase ≥0.18em tracked. Sentence-case Inter does not exist here.
4. Any new card uses `{components.veil-card}` — 4% white fill, 8% white stroke. Opaque cards break the spell.
5. Any new color accent is moon-gold (warm focal), nebula (cool atmospheric), or rose aura (emotional). Don't introduce green, cyan, or pure red.
6. Any new illustration is silhouette-on-glow — one subject, backlit, never frontlit. Full-bleed to the device edge.
7. Animated elements respect `prefers-reduced-motion`. The star field and moon pulse are atmospheric, not informational.

## Known Gaps

- **No documented dark-light theme switch.** The system assumes near-black ground. A light-mode variant has not been designed and likely cannot exist without breaking the aesthetic.
- **Star field is JS-generated**. Positions and twinkle delays are randomized at mount. Static export to image (for marketing screenshots) requires snapshotting after JS runs.
- **Illustrations are AI-generated** following the prompt scaffold in this doc. A hand-illustrated alternative for the brand mark and the top 10 dream archetypes is recommended but not yet produced.
- **No specified loading or skeleton state.** Interpretation generation can take 5–15s; the system needs a dedicated "reading the unconscious · 03 / 07" progress treatment that has not yet been spec'd as a component.
- **Accessibility note**: the violet-on-violet body text (ink on cosmos) sits at WCAG AA at body size but fails large-text AAA. Test specific layouts; the system may require a high-contrast variant for accessibility settings.

## Illustration Direction

### Prompt Scaffold

```
[subject] floating in deep cosmic indigo,
soft violet nebula behind, warm gold moonlight rim,
misty, glowing, painterly, dreamlike,
no hard outlines, atmospheric blur, 4:3,
color palette: #0A0B2E #A78BFA #FDE68A #F9A8D4
```

### Composition Rules

- One subject, centered or slightly off-center, never two.
- Subject is always backlit, never frontlit — silhouette over glow.
- Vignette darkens to `{colors.void}` at the four corners for clean bleed integration with the screen background.
- Reserve the top-right or top-left quadrant for a moon or light source.
- No hard linework anywhere. If a reference uses ink lines, soften them to atmospheric edges.

## Voice & Copy Tone

Write like **a tarot reader who has read Jung**. Copy is short, declarative, and emotionally direct. It names archetypes (mother, water, threshold, animal) without explaining them. Never explanatory, never therapeutic — the reader is treated as an adult capable of sitting with mystery.

### Canonical Examples

- **Greeting**: 你昨夜，*梦见了什么？*
- **Interpretation opener**: 鲸是深海中的远古之物，它的眼睛承载着你最古老的安全感——母亲的注视。
- **Pull quote**: *"梦中被困住的月光，是你白日里没说出口的那句话。"*
- **Action prompt (gentle)**: *给母亲打一通电话 — 今日*
