---
version: 0.1
name: Y2K Bubble
description: A diary that thinks it's a 2002 MP3 player. Chrome silver gradients, candy primaries (bubblegum pink, baby blue, lemon, lime, lavender), pixel hearts and sparkles, bubble fonts, and a rainbow ribbon along the top of every screen. Every container is a 2.5px-ink-bordered rounded card with a 3–5px hard offset shadow. The signature move is the "rainbow gradient wrapper" — a 3-stop chromatic border around primary CTAs and featured cards. Mood is rendered as 5 hand-built `BubbleFace` SVG bubbles (yellow / pink / blue / lavender / green) with cartoon eyes and a glass-highlight. The system is built for screenshot-shareable, Gen-Z-friendly diary mini-programs and is engineered to look loud in friends' WeChat moments.

colors:
  bg-blue: "#D4E9FF"
  bg-pink: "#FFE3F1"
  ink: "#1B1059"
  ink-soft: "#5949A8"
  pink: "#FF6FB5"
  blue: "#5BCEFF"
  yellow: "#FFE066"
  green: "#A6F068"
  lavender: "#C8B0FF"
  paper: "#FFFFFF"

gradients:
  chrome: "linear-gradient(180deg, #FFF 0%, #E8F0FF 30%, #C0D0E8 55%, #FFFFFF 100%)"
  rainbow: "linear-gradient(90deg, #FF6FB5 0%, #FFD56A 25%, #A6F068 50%, #5BCEFF 75%, #C8B0FF 100%)"
  gold-pill: "linear-gradient(180deg, #FFF, #FFE066, #FFA600, #FFF)"
  ribbon: "linear-gradient(90deg, #FF6FB5, #FFD56A, #A6F068, #5BCEFF, #C8B0FF)"

shadows:
  ink-offset: "3px 4px 0 #1B1059"
  ink-offset-sm: "1.5px 2px 0 #1B1059"
  ink-offset-card: "2.5px 3px 0 #1B1059"
  ink-offset-deep: "4px 5px 0 #1B1059"

textures:
  pattern-pixel-hearts: "8–10 pixel heart sprites at 14px, rotated random angles, ~12–15% opacity, scattered across page background. Subtle texture — required for the system to feel populated."
  pattern-sparkles: "5–8 pixel star/sparkle SVGs at 14–18px, scattered, ~12% opacity. Adds shimmer. Used on writing/comic screens where pixel hearts would feel too cute."
  ribbon-top: "6px-tall rainbow gradient strip at the very top of every screen, just below the WeChat capsule. The system's flag."

typography:
  display:
    fontFamily: "'Quicksand', 'Noto Sans SC', sans-serif"
    fontSize: 38px
    fontWeight: 800
    lineHeight: 1.0
    textShadow: "2px 2px 0 #FFF, 4px 4px 0 #FF6FB5"
  headline:
    fontFamily: "'Quicksand', 'Noto Sans SC', sans-serif"
    fontSize: 22px
    fontWeight: 800
    lineHeight: 1.15
  body:
    fontFamily: "'Quicksand', 'Noto Sans SC', sans-serif"
    fontSize: 13.5px
    fontWeight: 400
    lineHeight: 1.75
  body-bold:
    fontFamily: "'Quicksand', 'Noto Sans SC', sans-serif"
    fontSize: 14px
    fontWeight: 700
    lineHeight: 1.4
  eyebrow:
    fontFamily: "'Quicksand', sans-serif"
    fontSize: 11px
    fontWeight: 800
    letterSpacing: 0.2em
  pixel-meta:
    fontFamily: "'VT323', 'Noto Sans Mono SC', monospace"
    fontSize: 13px
    fontWeight: 400
    letterSpacing: 0.05em
  tag-label:
    fontFamily: "'Quicksand', sans-serif"
    fontSize: 9px
    fontWeight: 800

spacing:
  space-1: 4px
  space-2: 8px
  space-3: 12px
  space-4: 16px
  space-6: 24px
  space-8: 32px
  space-12: 48px
  page-margin-x: 18px
  page-margin-y: 18px
  card-padding: 14px

radii:
  card: 16
  card-soft: 14
  comic-panel: 18
  cta: 28
  pill: 999
  tab: 22

borders:
  card: "2.5px solid #1B1059"
  card-soft: "2px solid #1B1059"
  hairline: "1.2px solid rgba(27,16,89, 0.1)"

components:
  rainbow-ribbon:
    background: "{gradients.ribbon}"
    description: "6px-tall horizontal rainbow gradient strip at the very top of every screen, immediately under the WeChat top capsule. Always at 85% opacity. The system's flag — without it, the system collapses to a normal pastel app."
  chrome-pill:
    background: "{gradients.chrome}"
    border: "2px solid #1B1059"
    borderRadius: 999
    boxShadow: "{shadows.ink-offset-sm}"
    description: "Top-bar action button — 4-stop chrome gradient + 2px ink border + 999px pill radius + inset white highlight + inset bottom shadow. Used for `←`, `←返回`, calendar prev/next."
  bubble-face:
    background: "radial-gradient(circle at 32% 28%, #FFF 0%, {color} 35%, {color} 100%)"
    border: "2.5px solid #1B1059"
    boxShadow: "{shadows.ink-offset-sm}, inset -3px -3px 0 rgba(0,0,0, 0.08)"
    borderRadius: "50%"
    description: "Mood atom — circular bubble with a top-left highlight + cartoon-eye SVG + 2.5px ink border + offset shadow. 5 expressions × 5 colors (yellow/pink/blue/lavender/green). Never use Unicode emoji in this system; BubbleFace IS the emoji system."
  pixel-heart:
    description: "8-bit pixel heart drawn as a 10×9 SVG with crisp-rendering and 1px subpixel coordinates. Used in inline metadata, scattered backgrounds, the streak banner. Color matches context (pink default, blue for streak, ink for background pattern)."
  sparkle:
    description: "4-point star SVG (~10×10), used inline beside CTAs and headlines, and scattered in backgrounds. Comes in pink / blue / yellow / lavender — pick by surrounding color."
  card-default:
    background: "#FFFFFF"
    border: "{borders.card}"
    borderRadius: 16
    boxShadow: "{shadows.ink-offset-card}"
    description: "White-fill card with 2.5px ink border, 16px radius, 2.5px hard offset shadow. The system's default container — used for list rows and quiet cards."
  card-featured-rainbow:
    description: "Featured card. A 2px-padding outer wrapper filled with the rainbow gradient — the inner white card sits inside with 22px radius. Boxed in 4px ink offset shadow. Used for the today/hero card on home, the title block on write/comic screens."
  cta-rainbow-chrome:
    description: "Primary CTA. 3px outer rainbow-gradient frame + 26px inner chrome pill with 2px ink stroke + bold uppercase label flanked by sparkle SVGs. 4px ink offset shadow. The biggest moment in the system."
  card-color-fill:
    background: "{color}"
    border: "{borders.card}"
    borderRadius: 16
    boxShadow: "{shadows.ink-offset-card}"
    description: "Solid candy-color filled card (yellow/pink/blue/green/lavender). Used for stat tiles on calendar, mood legend chips, and select/highlighted states."
  tab-bar-rounded:
    background: "#FFFFFF"
    border: "{borders.card}"
    borderRadius: 28
    boxShadow: "{shadows.ink-offset-deep}"
    description: "Floating tab bar — white-fill rounded rectangle with 2.5px ink border + 4px ink offset shadow. Each tab is a separate child; active tab gets a candy-color fill + 2px ink border + smaller offset shadow + translate(-1px,-1px)."
  sticker-corner:
    background: "{colors.yellow}"
    border: "2px solid #1B1059"
    borderRadius: 8
    transform: "rotate(8–10deg)"
    boxShadow: "{shadows.ink-offset-sm}"
    description: "Rotated yellow sticker (`NEW!!`, `★ FRESH ★`) pinned at top-right of cards/comics. Quicksand 800 / 11px."
  comic-panel:
    background: "#FFFFFF"
    border: "{borders.card}"
    borderRadius: 18
    boxShadow: "{shadows.ink-offset-card}"
    description: "Single comic panel — white fill, 2.5px ink border, 18px radius, hard offset shadow. Has a numbered badge (color-coded circle: pink/blue/yellow/lavender for panels 1/2/3/4) at top-left, 2px-ink-bordered + offset shadow."
  pixel-counter:
    fontFamily: "VT323, monospace"
    description: "VT323 pixel font for all numerals (`14/31`, `2024.03.11`, `182 / ∞ chars`, calendar day numbers, `EP.07`). Pixel font is the system's metadata voice."
  mood-tile:
    description: "Square tile with 2.5px ink border + 14px radius + ink offset shadow + a BubbleFace + a label. Active state: candy-color fill + larger 4px ink offset + slight translate(-1px,-2px) for press-up effect."
  drop-shadow-text:
    description: "All display headlines use double drop-shadow text: `2px 2px 0 #FFF, 4px 4px 0 #FF6FB5` (or candy alt). The shadow color shifts by page (pink on home, blue on calendar). This is what gives titles their bubble-letter feeling."
---

# Y2K Bubble

## When to reach for this system

Use Y2K Bubble when the diary should feel like a 2002 MP3 player skin built by a 19-year-old with a glitter pen. The product is loud, candy-colored, and engineered to look fun in friends' screenshots.

**Best for** — diaries targeting Gen Z and early millennial nostalgia; social-share-heavy products; surfaces where the comic is celebratory and the screenshot is the point; campus / school-aged user bases; mini-programs that compete with Pinkoi / Moo日记 / 一禅小和尚; secondary "cute" alternates inside a multi-skin product. Strongest shareability of the three systems. Neighbors: 2002 iPod skins, MSN Messenger themes, Tamagotchi, Sanrio, early Sanrio digital products, Powerpuff Girls UI, Tao Bao / Ling Show youthful skins, Honkai's lighter UI moments.

**Avoid for** — adult/serious/therapeutic surfaces, finance, productivity, audiences over 35, B2B contexts. The system has the highest visual ego of the three. If the user is sad or stressed, this system feels tone-deaf — pair it with a `glass-dusk` or `manga-jump` alternate.

## Aesthetic direction

| | |
|---|---|
| **Visual references** | 2002 iPod skins · MSN Messenger · Tamagotchi · Powerpuff Girls UI · Sanrio · The Sims 2 · Lisa Frank stationery · early MySpace profiles · Bonbon chocolates packaging · y2kaestheticinstitute.tumblr.com · Pinkoi homepage · 5252 by O!Oi |
| **Tactile qualities** | Hard candy. Bubblegum. Plastic with a glossy highlight. Chrome silver borders. Pixel-art at chunky scale. Stickers stuck on stickers. Nothing is matte; everything has a highlight. Hand-drawn rather than precise — let the corners breathe. |
| **Three keywords** | *candy. chrome. screenshot-able.* |

## Color

A bright pastel base + five candy primaries + chrome silver + ink night-blue. Every accent comes from the same 5 candy hues — no off-palette colors.

### Tokens

```css
/* surfaces — soft pastels */
--y2k-bg-blue  : #D4E9FF;            /* default page bg */
--y2k-bg-pink  : #FFE3F1;            /* alternate page bg (write screen) */
--y2k-paper    : #FFFFFF;            /* card fill */

/* ink — deep night blue, never black */
--y2k-ink       : #1B1059;
--y2k-ink-soft  : #5949A8;

/* candy primaries — 5 hues, all used at 100% saturation */
--y2k-pink     : #FF6FB5;
--y2k-blue     : #5BCEFF;
--y2k-yellow   : #FFE066;
--y2k-green    : #A6F068;
--y2k-lavender : #C8B0FF;

/* chrome — engineered to look like 2002 brushed metal */
--y2k-chrome   : linear-gradient(180deg, #FFF 0%, #E8F0FF 30%, #C0D0E8 55%, #FFFFFF 100%);

/* rainbow — the signature flag */
--y2k-rainbow  : linear-gradient(90deg, #FF6FB5 0%, #FFD56A 25%, #A6F068 50%, #5BCEFF 75%, #C8B0FF 100%);
```

### Role assignments

| Token | Role |
|---|---|
| `--y2k-bg-blue` | Home, comic-result, calendar background. The default. |
| `--y2k-bg-pink` | Write screen background. The "active" alternate. Switches by screen, not by mode. |
| `--y2k-paper` | All card fills, comic panel fills, mood tile inactive states. |
| `--y2k-ink` | Every border, every text color. Never use `#000000`. |
| `--y2k-ink-soft` | Secondary text, inactive labels. |
| `--y2k-pink..lavender` | Mood-bubble fills, tab active fill, sticker fill, drop-shadow text accent, list-row tag chips. Each tab/mood/tag gets a fixed color assignment so the user learns the mapping. |
| `--y2k-chrome` | Top-bar pills, chrome buttons, CTA inner fill. The "interactive" surface. |
| `--y2k-rainbow` | Top ribbon, featured-card outer frame, CTA outer frame. Exactly three places per screen. |

## Typography

**One sans + one pixel monospace.** The system is single-voiced — Quicksand carries everything — with VT323 dropping in for numerals and metadata only.

- **Quicksand 800** — the system's bubble-letter voice. Used for display, headlines, CTA labels, eyebrows, tags. Always 800 weight or higher for these slots.
- **Quicksand 400–700** — body, soft labels.
- **VT323** — pixel-font monospace. Used for all numerals (dates, counts, char-count, calendar days, `EP.07`) and for "system-y" metadata. This pixel-on-bubble pairing is the system's signature.
- **Noto Sans SC** — CJK fallback. Quicksand has no CJK glyphs, so all Chinese characters render in Noto Sans SC at the same weight.

### Scale

| Token | Size | Family | Weight | Use |
|---|---|---|---|---|
| `--ty-display` | 38 / 1.0 / shadow | Quicksand | 800 | Big bubble-letter page titles — always with double drop-shadow text |
| `--ty-headline` | 22 / 1.15 | Quicksand | 800 | Diary entry titles, comic title |
| `--ty-body-bold` | 14 / 1.4 | Quicksand | 700 | List row titles, CTA labels |
| `--ty-body` | 13.5 / 1.75 | Quicksand | 400 | Diary body text |
| `--ty-eyebrow` | 11 / +0.2em / 800 | Quicksand | 800 | `★ DIARY.EXE ★`, section labels (`✦ TODAY ✦`) |
| `--ty-pixel-meta` | 13 / mono | VT323 | 400 | Dates (`03.11.24`), char counts (`182 / ∞`), `EP.07`, calendar numbers |
| `--ty-tag-label` | 9 / 800 | Quicksand | 800 | Tiny tag chips (`#daily`, `#night`) |

### Signature treatments

- **Display titles always carry double drop-shadow text.** `text-shadow: 2px 2px 0 #FFF, 4px 4px 0 var(--accent);` — the accent shifts per page (pink on home, blue on calendar). This is what makes the title feel like a sticker/bubble letter.
- **VT323 pixel font for every numeral.** Dates, char counts, `EP.07`, calendar day numbers, `Day 14/31`. The pairing of bubble Quicksand text + pixel VT323 numbers is the system's bilingual identity.
- **Bracketed star ornaments.** Eyebrows are flanked by `★` or `✦` (`★ DIARY.EXE ★`, `✦ TODAY ✦`). This is a wrapping pattern, not a single-side decoration.
- **Tags wear color.** Every list-row tag chip gets a candy fill (pink/blue/lavender/green/yellow), a 1.2px ink border, a 6px radius. Tags are little stickers, not pills.

## Layout

The product is **a sticker album with a chrome MP3 menu on top**.

1. **Rainbow ribbon (6px, 85% opacity) sits at the top of every screen** just under the WeChat capsule. It is the system's flag — without it the system reads as a pastel notes app.
2. **Background carries the texture pattern** — scattered pixel hearts (home/calendar) or pixel sparkles (write/comic) at ~12% opacity. The page must not be flat-pastel; the texture is what gives it character.
3. **Every container has the 2.5px ink border + 3–5px hard offset shadow stack.** Cards, tab bars, mood tiles, stickers — all share this border/shadow language. The shadow color is `--y2k-ink` (never black, never gradient).
4. **The "rainbow wrapper" is the system's hero move.** A featured card gets a 2px-wide rainbow outer frame; a primary CTA gets a 3px rainbow outer frame. Use **at most two** rainbow wrappers per screen.
5. **Bottom tab bar floats and translates on press.** The active tab has a candy fill, its own 2px ink border, a 1.5px inner offset shadow, and a `translate(-1px,-1px)` to feel pressed-up. Other tabs are flat.

### Spacing & radii

```css
/* spacing — multiples of 4 */
--space-1: 4px;  --space-2: 8px;   --space-3: 12px;  --space-4: 16px;
--space-6: 24px; --space-8: 32px;  --space-12: 48px;
--page-margin-x: 18px;
--page-margin-y: 18px;
--card-padding: 14px;

/* radii — soft but not infinite */
--radius-card        : 16px;
--radius-card-soft   : 14px;
--radius-comic-panel : 18px;
--radius-cta         : 28px;
--radius-pill        : 999px;
--radius-tab-item    : 22px;

/* borders — heavy ink */
--border-card        : 2.5px solid #1B1059;
--border-card-soft   : 2px solid #1B1059;
--border-hairline    : 1.2px solid rgba(27,16,89, 0.1);

/* shadows — hard offset, ink only */
--shadow-card        : 2.5px 3px 0 #1B1059;
--shadow-card-deep   : 4px 5px 0 #1B1059;
--shadow-small       : 1.5px 2px 0 #1B1059;
--shadow-offset      : 3px 4px 0 #1B1059;
```

## Depth

The system has **two depth tools**: hard offset shadow (ink, no blur) and texture pattern. No backdrop-blur, no soft shadows.

- **Ink offset shadow** at three intensities — `1.5×2px` (small, sticker), `2.5×3px` (default card), `4×5px` (deep, tab bar / hero). Always `--y2k-ink` (`#1B1059`), never pure black.
- **Texture pattern** behind every screen (pixel hearts or sparkles, ~12% opacity).
- **Inset bottom shadow on chrome pills** (`inset 0 -2px 0 rgba(0,0,0, 0.1)`) gives them a pressable-button quality.
- **No gradients except** the chrome (180° linear) and the rainbow (90° linear). No radial gradients except in the BubbleFace mood atoms.
- **No backdrop-blur anywhere.** The system is solid color and crisp ink edge.

## Illustration direction

The 4-panel comic is rendered in a **flat candy / pop-art style** — bright fills, 1.5–2px ink linework, big eyes, pink cheek dots, chunky compositions. Every panel has a candy-colored numbered badge in its top-left corner.

### Prompt scaffold (for AI comic generation)

```
4-panel cute pop diary comic, Y2K kawaii aesthetic,
flat candy colors (#FF6FB5 #FFE066 #5BCEFF #A6F068 #C8B0FF),
deep night-blue ink linework (#1B1059), 1.5–2px line weight,
big anime eyes, pink circle cheek dots, chunky proportions,
no gradients inside panels (flat color fills only),
glossy highlights on bubble shapes (latte mug, moon, eyes),
each panel rendered separately at 1:1.05 aspect,
panel 1: morning scene with cute big-eye protagonist
panel 2: coffee / object close-up with sparkles
panel 3: meeting friend, pixel heart between them
panel 4: bedtime with pillow + glossy moon + "Zzz" pixel font
```

### Composition rules

- **Every panel = candy color fill, 1.5–2px ink lines, no gradients.** Gradients break the candy-flat language.
- **Cute big eyes + pink cheek circles.** This is the system's character DNA. Without them, faces read as generic.
- **Always 4 panels, 2×2 grid, 10px gutter.** Slightly larger gutter than Manga Jump because the colored badges spill outside the panels.
- **Numbered badges in candy colors** (panel 1=pink / 2=blue / 3=yellow / 4=lavender), pinned at top-left, 24px circle, 2px ink border, with `1.5px 2px 0` ink shadow.
- **One pixel-art element per panel** — pixel heart, pixel sparkle, pixel "Zzz", pixel-style sun. The pixel motif threads the comic together.
- **A rotated yellow sticker (`★ FRESH ★`, `NEW!!`) is allowed on the comic frame**, never inside a panel.

## Voice & copy

Write like an **excited 19-year-old texting their group chat**. Short sentences. Emoticons-as-syntax (`(´；ω；`)`, `(*´﹀`*)`). Bracketed star wrappings (`★ MY COMIC ★`). Mixed CN/EN/JP. The body is the user's voice; everything else is enthusiastic editorial.

| Slot | Example |
|---|---|
| Brand wordmark | `★ DIARY.EXE ★` |
| Page title (display) | **三月日记** (with `2px 2px 0 #FFF, 4px 4px 0 #FF6FB5` shadow) |
| Streak banner | `已经记录 14 天 · 连续 5 天 ★` |
| Section eyebrow | `✦ TODAY ✦`, `✦ 标题 ✦`, `✦ 今天的事 ✦`, `✦ MOOD LEGEND ✦` |
| Episode marker | `EP.07` (VT323 pixel font) |
| Body sample | `傍晚去了那家咖啡店！！\n小M说她终于离职了 (´；ω；\`)\n我们干杯——为不再勉强的人生 ☆` |
| Char count | `184 / ∞ chars` (VT323) |
| Mood labels | `平静 · 开心 · 想哭 · 生气 · 累` |
| CTA primary | `✦ 生成 4 格漫画 ✦` (flanked by sparkle SVGs, inside chrome pill, inside rainbow frame) |
| Sticker | `NEW!!`, `★ FRESH ★` |
| Tab labels | `今日 / 过往 / 月历 / 我` (each its own candy color when active) |

## Do & Don't

### Do

- Run the rainbow ribbon (6px, 85% opacity) along the top of every screen. Without it the system collapses.
- Use VT323 pixel font for every numeral. Pixel + bubble is the system's bilingual identity.
- Wrap titles in star ornaments (`★ DIARY.EXE ★`, `✦ TODAY ✦`).
- Wear color on tags — each tag is a candy sticker, not a neutral pill.
- Use double drop-shadow text on display titles (`2px 2px 0 #FFF, 4px 4px 0 <accent>`).
- Render mood as `BubbleFace` SVGs (5 hand-drawn faces × 5 candy colors).
- Render the primary CTA inside two nested frames: rainbow outer + chrome inner. Flank label with sparkles.
- Rotate stickers (`NEW!!`, `★ FRESH ★`) 8–10°.
- Translate active tab bar items by `(-1px, -1px)` for a "pressed-up" feel.
- Mix CN / EN / JP freely (`三月日记`, `DIARY.EXE`, `★ FRESH ★`, `Zzz`).

### Don't

- Don't use pure `#000000`. Always `--y2k-ink` (`#1B1059`).
- Don't use Unicode emoji except `★ ✦ ✧ ♡ ☆`. The BubbleFace SVGs are the mood-emoji system.
- Don't use backdrop-blur, glass effects, or soft shadows. Everything is hard offset shadow.
- Don't use thin (1px) borders. Minimum 1.2px for hairlines, 2px for cards.
- Don't use serif anywhere. Quicksand + VT323 only.
- Don't introduce non-palette colors. The 5 candy primaries + chrome + ink + 2 pastel bgs are the entire system.
- Don't use the rainbow gradient as a fill across large areas — only as a 2–3px wrapper border or the 6px top ribbon.
- Don't apply the system to vulnerable / serious diary entries — the loudness feels tone-deaf.
- Don't go below 12% texture pattern opacity — the system looks empty.

## CJK & International

Quicksand lacks CJK. Pair with **Noto Sans SC at the same weight** (400 for body, 700–900 for headlines). VT323 lacks CJK too; for Chinese metadata, fall back to **Noto Sans Mono SC**.

| Role | Latin | Chinese counterpart |
|---|---|---|
| Display | Quicksand 800 + drop-shadow | Noto Sans SC 900 + same drop-shadow |
| Headline / CTA | Quicksand 800 | Noto Sans SC 900 |
| Body | Quicksand 400 | Noto Sans SC 400 |
| Pixel numerals | VT323 | Noto Sans Mono SC 500 (less playful but renders CJK; for char counts and dates, accept VT323's lack of CJK and keep them Latin-only) |
| Eyebrow | Quicksand 800 +0.2em | Noto Sans SC 800 +0.1em (CJK tracking <0.15em) |

**Loading**:
```html
<link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500;600;700;800&family=VT323&family=Noto+Sans+SC:wght@300;400;500;700;900&family=Noto+Sans+Mono+SC:wght@500&display=swap" rel="stylesheet">
```

**Adjustments for CJK runs**:
- Line-height 1.75 for body, 1.15 for titles. The CJK is denser; don't tighten further.
- Letter-spacing 0 on CJK body; tighten eyebrow tracking from Latin's +0.2em to +0.1em.
- **Drop-shadow on titles works equally for CJK and Latin** — Noto Sans SC 900 holds the shadow as well as Quicksand 800.
- VT323 + Chinese coexist by keeping numerals Latin (`14/31`, `03.11.24`) and Chinese surrounding. The pixel-mono / CJK split is part of the look.
- BubbleFace labels (`平静`, `开心`, `想哭`, `生气`, `累`) are 1–2 CJK characters — pair perfectly with the candy bubbles.
- Use `(´；ω；\`)` emoticons in body — they are the period millennial CJK style and reinforce the y2k era.
- Full-width Chinese punctuation in body; half-width in eyebrows/CTA.

**Known CJK gap**: there is no Chinese bubble-font equivalent of Quicksand 800. The system relies heavily on the Latin chrome (`DIARY.EXE`, `EP.07`, `★ FRESH ★`, `NEW!!`) to carry the y2k voice. All-Chinese deployments lose some of the loudness; compensate by leaning harder on candy color and sticker chrome.

## Iteration checklist

1. Rainbow ribbon (6px, 85% opacity) at the very top of every screen.
2. Background texture pattern (pixel hearts on home/calendar, sparkles on write/comic) at ~12% opacity.
3. Every container has 2.5px ink border + hard ink offset shadow. No hairlines for cards.
4. Display titles carry the double drop-shadow text (`2px 2px 0 #FFF, 4px 4px 0 <candy>`).
5. Every numeral is VT323 pixel font.
6. Mood is BubbleFace SVGs (5 expressions × 5 candy colors). No Unicode emoji.
7. Star-wrapping ornaments on eyebrows (`★ FOO ★`, `✦ BAR ✦`).
8. At most two rainbow wrappers per screen (featured card + CTA, typically).
9. Active tab bar items are translated `(-1px, -1px)` and candy-filled.

## Known gaps

- **Accessibility risk on candy chips**: pink-on-white at 9px tag size approaches WCAG contrast floor. Bump tag labels to 800-weight to compensate; verify contrast for each candy color individually.
- **No dark mode.** The system is built on light pastels and chrome. A dark version would require inverting chrome (impossible) or replacing it with neon. Plan a separate "neon" alternate skin instead.
- **The "rainbow wrapper" is expensive to lay out.** A 2–3px outer gradient frame around a featured card requires an extra wrapper div. Make this a primitive component, not a one-off pattern.
- **Comic generation off-style risk**: cute pop-art with cheek dots and big eyes is not the default style of most diffusion models. Plan a small LoRA or curated style anchor before scaling generation.
- **Mood expressivity ceiling**: 5 BubbleFace expressions cover the daily-log space but break on rare states (panic, ecstasy, dissociation). Don't try to scale to 20+ — instead, layer a free-text mood note beneath the bubble.
- **The pixel-font numeric voice doesn't print well.** For PDF export, VT323 at small sizes pixelates ugly on dpi <150. Provide a Noto Sans Mono fallback for print/share-card exports.
- **Tone-deafness risk**: applying this system to a vulnerable entry (illness, grief, burnout) reads as mocking. If the product has emotional-content detection, swap to a `glass-dusk` alternate skin on flagged entries.
