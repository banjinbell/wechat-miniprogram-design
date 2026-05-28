---
version: 0.1
name: Liquid Iridescence
description: A loud, saturated, generationally-now system for the Dream Journal — dreams treated as creative material instead of sacred ritual. Engineered for screenshots and TikTok. A modern grotesk (Space Grotesk) carries the "current" voice; Instrument Serif Italic carries romantic display moments and gradient-text accents. The palette is a small set of saturated hues — pink, cyan, amber, violet — combined as blurred blobs, conic sweeps, and a signature 135° iris gradient. Surfaces are deep purple-black voids painted by 2–4 soft color blobs blurred at 50–80px. Containers are glass-fill (4% white + 10% stroke + 12px backdrop-blur). Depth comes from blur and glow only — never hard shadow.

colors:
  midnight: "linear-gradient(160deg, #1A0A3E 0%, #0D0820 60%, #1A0A3E 100%)"
  void: "#0D0820"
  pink: "#FF6BD6"
  cyan: "#5EEAD4"
  amber: "#FFB86B"
  violet: "#B794F6"
  iris: "linear-gradient(135deg, #FF6BD6 0%, #FFB86B 50%, #5EEAD4 100%)"
  ink: "#FEF5FF"
  ink-soft: "rgba(254, 245, 255, 0.7)"
  ink-faint: "rgba(254, 245, 255, 0.42)"
  glass-fill: "rgba(254, 245, 255, 0.04)"
  glass-stroke: "rgba(254, 245, 255, 0.1)"

blurs:
  blob: 60px
  card-backdrop: 12px
  hero-conic: 50px

typography:
  display:
    fontFamily: "'Instrument Serif', serif"
    fontStyle: italic
    fontSize: 56px
    fontWeight: 400
    lineHeight: 0.95
    letterSpacing: "-1px"
  title:
    fontFamily: "'Instrument Serif', serif"
    fontStyle: italic
    fontSize: 28px
    fontWeight: 400
    lineHeight: 1.05
  interp-lede:
    fontFamily: "'Instrument Serif', serif"
    fontStyle: italic
    fontSize: 22px
    fontWeight: 400
    lineHeight: 1.5
  body:
    fontFamily: "'Space Grotesk', sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.65
  body-emph:
    fontFamily: "'Space Grotesk', sans-serif"
    fontSize: 14px
    fontWeight: 500
    lineHeight: 1.65
  eyebrow:
    fontFamily: "'Space Grotesk', sans-serif"
    fontSize: 11px
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.3em
    textTransform: uppercase
  tag-chip:
    fontFamily: "'Space Grotesk', sans-serif"
    fontSize: 10px
    fontWeight: 600
    letterSpacing: 0.25em
    textTransform: uppercase

spacing:
  space-1: 4px
  space-2: 8px
  space-3: 12px
  space-4: 16px
  space-5: 20px
  space-6: 24px
  space-8: 32px
  space-12: 48px
  screen-padding-x: 20px
  screen-padding-y: 24px

radii:
  card: 24px
  card-large: 28px
  chip: 9999px
  button-round: 50%
  input: 16px

components:
  glass-card:
    background: "{colors.glass-fill}"
    border: "1px solid {colors.glass-stroke}"
    backdropFilter: "blur({blurs.card-backdrop})"
    borderRadius: "{radii.card}"
    padding: 20px
    description: "The default elevated container. Never solid. Sits on top of the gradient weather underneath."
  featured-card:
    background: "{colors.glass-fill}"
    border: "2px solid"
    borderImage: "{colors.iris} 1"
    borderRadius: "{radii.card-large}"
    description: "Exactly one card per screen gets the iris gradient as a 2px border. This is how the user's eye knows where to go."
  iris-text:
    background: "{colors.iris}"
    backgroundClip: text
    color: transparent
    fontFamily: "'Instrument Serif', serif"
    fontStyle: italic
    description: "Gradient text on one — and only one — word per display title (e.g. 'good MORNING dreamer'). Never use the iris as a large fill, only as text or as a thin border."
  color-blob:
    width: "60–80% of viewport"
    background: "{colors.pink} | {colors.cyan} | {colors.amber} | {colors.violet}"
    filter: "blur({blurs.blob})"
    opacity: "0.55–0.8"
    mixBlendMode: screen
    description: "Two to four large soft-blurred color blobs always live behind the UI, even on quiet screens. Blobs bleed off-screen; never contain them. Where two overlap, screen-blend brightens the intersection — that's the system's signature glow."
  conic-aurora:
    background: "conic-gradient(from 0deg, #FF6BD6, #FFB86B, #5EEAD4, #B794F6, #FF6BD6)"
    filter: "blur({blurs.hero-conic})"
    opacity: 0.7
    description: "Used on hero/cover surfaces. A conic sweep blurred into oblivion behind a radial vignette that darkens corners to {colors.void}."
  cta-floating:
    width: 68px
    height: 68px
    background: "{colors.iris}"
    borderRadius: "{radii.button-round}"
    boxShadow: "0 12px 32px rgba(255, 107, 214, 0.4), 0 0 60px rgba(94, 234, 212, 0.25)"
    description: "Primary action is a 68px round gradient button floating at the bottom-center. No persistent tab bar — secondary nav is in the header."
  pill-chip:
    background: "{colors.glass-fill}"
    border: "1px solid {colors.glass-stroke}"
    borderRadius: "{radii.chip}"
    padding: "6px 12px"
    fontFamily: "'Space Grotesk', sans-serif"
    fontSize: 11px
    description: "Default tag/chip. Glass-fill, uppercase 0.25em-tracked sans label. Active state swaps the border for an accent color (pink, cyan, amber)."
  gradient-bar:
    background: "{colors.iris}"
    borderRadius: 4px
    description: "Every data bar (REM duration, mood spectrum, count visualization) is rendered with a gradient — never a flat fill. Direction varies per chart."
  vignette:
    background: "radial-gradient(circle at 50% 50%, transparent 0%, rgba(13, 8, 32, 0.3) 80%, rgba(13, 8, 32, 0.85) 100%)"
    description: "Darkens corners on hero/cover surfaces so the conic-aurora reads as luminous from the center rather than uniformly bright."
---

# Liquid Iridescence

## When to reach for this system

Use Liquid Iridescence when the product wants to feel current, expressive, and shareable. The system is engineered for screenshots and TikTok.

**Best for** — Gen-Z and younger millennial audiences (18–35), social/share-heavy surfaces, lucid-dreaming and consciousness-exploration framings, paid premium tiers that need to feel premium. Closest neighbors: Linear's marketing site, Spotify Wrapped, Arc Browser, Bambu Labs, the "tech with feeling" wave.

**Avoid for** — serious therapeutic surfaces, audiences over 50, moments where the user is in distress, any surface where the product should disappear behind the content. The system has high visual ego — if the dream itself is meant to be the only thing in the room, this is the wrong system.

## Aesthetic direction

| | |
|---|---|
| **Visual references** | Y2K iridescence · Beeple early renders · holographic stickers · WebGL gradient generators · TikTok "core" aesthetic boards · soap bubbles in macro photography · oil-on-water |
| **Tactile qualities** | Wet, saturated, somewhere between liquid and gas. Color bleeds into adjacent color. Always blurred — never crisp. Type sits over color as if floating on a film. |
| **Three keywords** | *vibrant. liquid. now.* |

## Color

The palette is small (4 saturated hues + ink) and combined infinitely. Colors are **never used flat** — they always appear as gradients, conic sweeps, or blurred blobs.

### Tokens

```css
--li-surface       : linear-gradient(160deg, #1A0A3E, #0D0820 60%, #1A0A3E);
--li-void          : #0D0820;
--li-ink           : #FEF5FF;        /* pink-undertoned white */
--li-ink-soft      : rgba(254,245,255, 0.70);
--li-ink-faint     : rgba(254,245,255, 0.42);
--li-pink          : #FF6BD6;
--li-cyan          : #5EEAD4;
--li-amber         : #FFB86B;
--li-violet        : #B794F6;
--li-iris          : linear-gradient(135deg, #FF6BD6, #FFB86B 50%, #5EEAD4);
--li-glass-fill    : rgba(254,245,255, 0.04);
--li-glass-stroke  : rgba(254,245,255, 0.10);
```

### Role assignments

| Token | Role |
|---|---|
| `--li-surface` | Page background. Always a soft 160° diagonal gradient so highlights can sit on it. |
| `--li-iris` | The signature gradient. Brand mark, primary CTA, gradient text on key words, featured-card border. Never used as a large flat fill. |
| `--li-pink` | Recording state, "primary" highlighted word, hottest emotion. |
| `--li-cyan` | "Done" / system positive, lucid-dream tag, secondary highlighted word. |
| `--li-amber` | Warmth, sensory tag, action prompts. |
| `--li-violet` | Mystical tag, supporting blob in compositions. |
| `--li-ink` | Body text. Pink-undertoned white — never `#FFFFFF`. |
| `--li-glass-*` | Backdrop-blur cards and pills always sit on this stroke + 4% fill. |

## Typography

Two faces, opposite voices, used in tight proportions.

- **Space Grotesk** — the "current" voice. Body, system labels, tag chips, timestamps, data values. Weight 400 for body, 500 for emphasis, 600 for uppercase labels.
- **Instrument Serif Italic** — the romantic accent. Display titles, dream titles, interpretation ledes, pull quotes. Used in shorter passages where the italic feels luxurious; never for long body runs.

### Scale

| Token | Size | Family | Weight | Use |
|---|---|---|---|---|
| `--ty-display` | 56 / 0.95 / -1px | Instrument Serif italic | 400 | Home greeting, mode-entry headlines. Always one word gradient-treated. |
| `--ty-title` | 28 / 1.05 | Instrument Serif italic | 400 | Dream titles, card titles, modal headers. |
| `--ty-interp-lede` | 22 / 1.5 | Instrument Serif italic | 400 | Interpretation opening sentence — often with gradient highlight on one word. |
| `--ty-body` | 14 / 1.65 | Space Grotesk | 400 | Supporting body, descriptions, secondary text under titles. |
| `--ty-eyebrow` | 11 / +0.3em / uppercase | Space Grotesk | 600 | System labels (`RENDERING · 04:17 AM`), section eyebrows. |
| `--ty-tag` | 10 / +0.25em / uppercase | Space Grotesk | 600 | Tag chips, timestamps, count badges. |

### Signature treatments

- **One gradient word per display title, never two.** The iris gradient on a single word ("good *morning* dreamer", "*lucid* recall") is the system's brand signature. Two gradient words on one screen reads as broken.
- **Every Space Grotesk label ≤14px is uppercase with ≥0.25em tracking.** Sentence-case Space Grotesk only at body size.
- **Italic Instrument Serif carries every emotional sentence.** No upright treatment exists for the serif in this system — if it's serif, it's italic.
- **Mix Latin grotesk and Chinese italic-serif in the same line freely.** `good morning, dreamer · 镜中的另一个我` is a canonical pattern.

## Layout

The system stacks **glass cards over weather**.

1. **Background is never empty.** Two to four large soft-blurred color blobs always live behind the UI, even on quiet screens. Without them the dark background reads as cheap.
2. **Glass-fill containers everywhere.** 4% white fill + 10% stroke + 12px backdrop-blur. Never solid panels. The UI should feel like a layer of glass floating over the gradient weather.
3. **Exactly one featured card per screen.** It gets the iris gradient as a 2px border. This is how the user's eye knows where to go.
4. **Data viz is welcome — as vibe, not chart.** Unlike Cosmic Nocturne, this system shows numbers (REM duration, mood spectrum, counts). Render every bar with a gradient — never a flat fill.
5. **Floating round CTA, no persistent tab bar.** Primary action lives in a 68px round iris-gradient button at bottom-center. Secondary nav is in the header.

### Spacing & radii

```css
/* spacing — multiples of 4 */
--space-1: 4px;  --space-2: 8px;   --space-3: 12px;  --space-4: 16px;
--space-5: 20px; --space-6: 24px;  --space-8: 32px;  --space-12: 48px;

/* radii — gently rounded; no square corners */
--radius-card        : 24px;
--radius-card-large  : 28px;
--radius-chip        : 9999px;
--radius-button-round: 50%;
--radius-input       : 16px;
```

## Depth

All depth comes from **blur and glow**. Hard shadows do not exist in the system.

- **Color blobs** at 50–80px gaussian blur, screen-blend, 55–80% opacity, bleeding off-screen.
- **Backdrop-blur** at 12px on every floating glass container.
- **Drop-glow** under floating CTAs: `0 12px 32px rgba(255,107,214,0.4), 0 0 60px rgba(94,234,212,0.25)` — two layered glows, never a single drop.
- **Vignette** on hero surfaces: a radial gradient darkening the corners to `--li-void` so the centered conic-aurora reads luminous.

## Illustration direction

Illustrations are **pure color and geometry** — no figures, no representational objects. Three blurred color blobs + (optionally) one thin white fine-line glyph (sine wave, concentric circles) on top.

### Prompt scaffold

```
abstract iridescent blobs in deep purple void,
color blobs of hot pink #FF6BD6, mint cyan #5EEAD4,
warm amber #FFB86B, heavy gaussian blur,
wet liquid mercury, soft film grain, 4:3,
no figures, no objects, pure color
```

### Composition rules

- Always 3 blobs minimum, always different hues, always overlapping.
- `mix-blend-mode: screen` — colors brighten where they overlap.
- Add ~18% film grain on top, multiply mode, to keep the image from feeling sterile.
- Optional: one thin white iridescent SVG line (sine wave, ring) sitting on the surface.

## Voice & copy

Write like a **friend who studied semiotics**. Bilingual fluently: English carries system labels and brand voice; Chinese carries emotional content. Curious, slightly poetic, never clinical, never mystical.

| Slot | Example |
|---|---|
| Greeting | *good morning, dreamer.* |
| Data callout | 昨夜你在 REM 中停留了 1 小时 47 分钟。有 3 个画面等待显影。 |
| Interpretation lede | *镜子在梦中从来不是镜子 —— 它是你不敢承认的那部分自己。* |
| System label | `RENDERING · please stay still` |

## Do & Don't

### Do

- Use gradient text on **one** word per title — never more.
- Let color blobs bleed off-screen — never contain them.
- Mix Chinese serif italic and Latin grotesk in the same line.
- Treat every chart bar as a gradient — never a flat fill.
- Apply 12px backdrop-blur on every floating container.
- Reserve a single featured card per screen for the iris gradient border.

### Don't

- Don't use the iris gradient as a fill across large areas — only as border, text, or small marks.
- Don't use sharp shadows. All depth is blur and glow.
- Don't substitute Inter or Roboto for Space Grotesk — the geometric quirks (the open `a`, slanted `g`) matter.
- Don't add stock illustrations or photographs. Color blobs only.
- Don't stack more than two gradient elements per viewport — visual noise.
- Don't use pure white. Always `--li-ink` (`#FEF5FF`).

## CJK & International

Space Grotesk has limited CJK coverage; Instrument Serif has none. For Chinese content:

| Role | Latin | Chinese counterpart |
|---|---|---|
| Display / titles | Instrument Serif italic | Noto Serif SC 500 (no italic — see note) |
| Body / labels | Space Grotesk 400–600 | Noto Sans SC 400–600 |

**Loading**:
```html
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Space+Grotesk:wght@400;500;600;700&family=Noto+Serif+SC:wght@400;500&family=Noto+Sans+SC:wght@400;500;600&display=swap" rel="stylesheet">
```

**Adjustments for CJK runs**:
- Letter-spacing 0 on every CJK run; loosen line-height to 1.8 (up from 1.65) for body.
- No `text-transform: uppercase` on Chinese text — CJK has no case.
- For Chinese tag labels, drop the uppercase + 0.25em tracking pattern and instead use Noto Sans SC 600 at 11–12px with no transform.
- Gradient-text treatment works on Noto Serif SC weight 500 — verify the gradient stops still read as multi-colored at the smaller character widths.
- Insert ASCII space between adjacent CJK and Latin (盘古之白).

**Known CJK gap**: no italic Chinese serif on Google Fonts. Substitute italic with gradient-text on that word, or use a weight contrast (700 inside 500).

## Iteration checklist

1. Background carries 2–4 blurred color blobs (50–80px blur, screen-blend, bleeding off-screen).
2. Every elevated container is glass-fill (4% white + 10% stroke + 12px backdrop-blur).
3. Exactly one featured card per screen has the iris gradient as a 2px border.
4. Display title contains exactly one gradient-text word.
5. All chart bars are gradients, never flat.
6. Primary action is a 68px round iris button floating at bottom-center.
7. No hard shadows — depth is blur and glow only.

## Known gaps

- **Performance**: backdrop-blur + multiple large blobs is GPU-heavy. Budget ≤4 blurred blobs and ≤6 backdrop-blur surfaces per screen, especially on Android mid-tier.
- **Screenshot fidelity**: gradient-text on Instagram/TikTok compression sometimes posterizes. Test the brand gradient at Instagram Story bitrate.
- **Light-mode variant**: not designed. The blobs and iris read as muddy on a light surface; a light variant would require a different palette.
- **Accessibility**: gradient text on dark fails AA at small sizes (<16px). Reserve gradient-text for display only — never for body or labels.
