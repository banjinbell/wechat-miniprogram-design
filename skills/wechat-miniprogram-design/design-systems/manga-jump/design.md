---
version: 0.1
name: Manga Jump
description: A weekly shōnen magazine for the user's own life. The diary becomes an issue of *DIARY MAG / 日記マガジン* — every entry is a numbered episode set in heavy ink, screentone, and jump-red. Two type voices — a heavy CJK gothic for headlines (Noto Sans SC 900) and a tall Latin display (Anton / Bebas Neue) for masthead, volume marks, and stat counters — over newsprint cream paper. Surfaces always carry a screentone dot field at ~8% opacity. Heavy 2–2.5px ink borders, 4px hard-offset shadows in ink or red, slanted red banners, speech bubbles, and zip-tone bursts. The generated comic is a real 4-panel black-and-white manga page with screentoned panels.

colors:
  newsprint: "#F4EFE3"
  paper: "#FAF7EE"
  ink: "#0B0B0B"
  ink-soft: "#5A5448"
  red: "#D8321F"
  yellow: "#F4CC2A"
  blue: "#2A4E8A"
  rule: "rgba(11,11,11, 0.18)"
  rule-faint: "rgba(11,11,11, 0.08)"

shadows:
  ink-offset: "4px 4px 0 #0B0B0B"
  ink-offset-sm: "2px 2px 0 #0B0B0B"
  red-offset: "4px 4px 0 #D8321F"
  red-offset-sm: "2px 2px 0 #D8321F"

textures:
  screentone: "Radial-dot pattern, 3–4px tile, ~16% black dots on cream. Applied at ~8% opacity behind every page surface as a flat-color zip-tone field. Required for the magazine feeling — without it the system reads as a flat web page."
  motion-lines: "Radial line bursts emanating from a point. Used inside dramatic comic panels (panel 03 of every comic) and behind emphasis stickers."

typography:
  display:
    fontFamily: "'Anton', 'Bebas Neue', 'Noto Sans SC', sans-serif"
    fontSize: 44px
    fontWeight: 400
    lineHeight: 0.85
    letterSpacing: "-1px"
    textTransform: uppercase
  headline:
    fontFamily: "'Noto Sans SC', 'PingFang SC', system-ui, sans-serif"
    fontSize: 22px
    fontWeight: 900
    lineHeight: 1.15
  body-serif:
    fontFamily: "'Noto Serif SC', serif"
    fontSize: 13px
    fontWeight: 400
    lineHeight: 1.7
  body-heavy:
    fontFamily: "'Noto Sans SC', 'PingFang SC', system-ui, sans-serif"
    fontSize: 14px
    fontWeight: 700
    lineHeight: 1.4
  eyebrow:
    fontFamily: "'Anton', 'Bebas Neue', sans-serif"
    fontSize: 11px
    fontWeight: 400
    letterSpacing: 0.15em
    textTransform: uppercase
  micro-label:
    fontFamily: "'Noto Sans SC', sans-serif"
    fontSize: 10px
    fontWeight: 900
    letterSpacing: 0.2em
  page-number:
    fontFamily: "'Anton', 'Bebas Neue', sans-serif"
    fontSize: 9px
    fontWeight: 400
    letterSpacing: 0.1em
    color: "{colors.ink-soft}"
  drop-cap:
    fontFamily: "'Anton', 'Bebas Neue', sans-serif"
    fontSize: 28px
    color: "{colors.red}"
    lineHeight: 0.8
    float: left

spacing:
  space-1: 4px
  space-2: 8px
  space-3: 12px
  space-4: 16px
  space-6: 24px
  space-8: 32px
  space-12: 48px
  page-margin-x: 18px
  page-margin-y: 20px
  comic-gutter: 6px

radii:
  square: 0
  inset-pill: 999px
  bubble: 18px

borders:
  frame: "2px solid #0B0B0B"
  frame-heavy: "2.5px solid #0B0B0B"
  rule: "1.5px solid #0B0B0B"
  rule-dashed: "1px dashed rgba(11,11,11, 0.18)"

components:
  masthead:
    description: "Top-of-screen magazine masthead. A skewed red banner (`DIARY MAG / 日記マガジン`) on the left, then a 2.5px ink rule beneath. Below the rule: `VOL.07` set in 44px Anton, the month (`三月号`) in 18px Noto Sans 900, and an issue subtitle (`SPRING ISSUE · ¥0`) in 9px Anton. Always present on home and calendar."
  comic-panel:
    border: "{borders.frame-heavy}"
    description: "A 4-panel comic page lives inside a 2.5px ink container with 6px gutters between panels. Every panel is filled with paper-cream, then has a page-number (`01–04`) set in Anton 6px in the bottom-right corner. Use screentone (radial dots) for sky and ground; pure white for figures."
  speech-bubble:
    background: "#FFFFFF"
    border: "1.6px solid #0B0B0B"
    borderRadius: "{radii.bubble}"
    padding: "7px 12px"
    description: "Rounded 18px-radius white bubble with a 1.6px ink stroke and an SVG tail (5 directions: bl, br, tl, tr, c). Used inside comic panels and floating over comic-result hero. Inside type: Noto Sans 12/1.35."
  banner-red:
    background: "{colors.red}"
    color: "#FFFFFF"
    transform: "skewX(-8deg)"
    padding: "3px 9px"
    description: "Slanted red flag for the masthead and for major section labels (`TODAY`, `第 07 話`). Anton 11px uppercase with +0.15em tracking. The skew is required — a non-skewed red block reads as a button instead of a banner."
  callout-pill:
    background: "{colors.ink}"
    color: "#FFFFFF"
    padding: "4px 8px"
    description: "Black pill containing a tab label or category name. Noto Sans 11/900. Used in the bottom tab bar (active tab) and as section headers (`本周心情`)."
  cta-block:
    background: "{colors.ink}"
    color: "#FFFFFF"
    boxShadow: "{shadows.red-offset}"
    padding: "14px 0"
    description: "Primary CTA. Solid black block, full-width, with a 4px hard offset shadow in red. 16/900 Noto Sans label, +0.25em tracking. The red shadow is the system's loudest move — never use elsewhere."
  cta-block-secondary:
    background: "{colors.paper}"
    color: "{colors.ink}"
    border: "{borders.frame}"
    boxShadow: "{shadows.ink-offset-sm}"
    description: "Secondary CTA. 2px ink border, paper fill, small ink-offset shadow."
  mood-tile:
    border: "{borders.frame}"
    background: "{colors.paper}"
    description: "Square tile, 2px ink border, paper fill. Contains a 26px MangaMood face + a label. Active state swaps fill to `{colors.yellow}` and adds 3px ink-offset shadow."
  stat-card:
    border: "{borders.frame}"
    background: "{colors.paper}"
    boxShadow: "{shadows.ink-offset-sm}"
    description: "Numerical stat tile. Anton 28px number with a small Noto Sans micro-label beneath. Featured stat (middle of stat row) gets red-offset shadow instead of ink-offset."
  list-row:
    borderBottom: "{borders.rule-dashed}"
    description: "Past-issue rows. 36px square date column (Anton number + Noto micro day), 28px MangaMood face, title (Noto 14/700), tag (`#FOO` Anton 9 +0.1em), rotated `READ` label."
  floating-add:
    background: "{colors.red}"
    border: "2.5px solid #0B0B0B"
    boxShadow: "3px 3px 0 #0B0B0B"
    borderRadius: "50%"
    description: "56px circular floating + button suspended above the tab bar's centre. Anton 32px `＋` glyph. The only round element in the system."
  sticker-label:
    background: "{colors.yellow}"
    border: "{borders.frame}"
    boxShadow: "{shadows.ink-offset-sm}"
    transform: "rotate(4–8deg)"
    description: "Rotated yellow callout sticker (`NEW!`, `FIN.`) pinned to corners of cards and comics. Anton 10–11px +0.1em tracking."
  manga-mood-face:
    description: "32px circle with 1.6px ink border, paper fill, and five SVG eye/mouth combinations (calm / happy / sad / angry / tired). The system's emoji — never use Unicode emoji or third-party faces."
---

# Manga Jump

## When to reach for this system

Use Manga Jump when the diary should feel like the user is the protagonist of their own *Weekly Shōnen Jump*. The product becomes a magazine — masthead, episode numbers, volume marks, and a 4-panel comic generated from today's entry.

**Best for** — diaries with AI-generated comics as the headline feature; users who grew up on Naruto, One Piece, *Honey and Clover*, *Yotsuba&*; mini-programs that want to feel collectible and serialized (one issue per month). Strongest "this is a real product" signal for the comic-generation use case. Neighbors: 名作之壁, Mangadex covers, *Honey and Clover* tankōbon, Akira Toriyama's gag-page art direction.

**Avoid for** — meditation apps, calming/therapeutic surfaces, financial or productivity tools, audiences over 45 unprimed for manga, or surfaces where the comic is incidental rather than central. The system has high visual ego and a fixed aesthetic — if you remove the masthead and the comic, the product loses its identity.

## Aesthetic direction

| | |
|---|---|
| **Visual references** | *Weekly Shōnen Jump* covers · *Honey and Clover* tankōbon · Akira Toriyama splash pages · ChibiMaruko strip layouts · Risograph zines · Yusuke Murata's color rough work · old Animage editorial spreads |
| **Tactile qualities** | Cheap newsprint paper. Heavy ink that lifts a hair off the page. Screentone dots laid on by hand. Red spot-color in two places per page, never more. Speech bubbles drawn in 1.6px black. Everything sits at a slight angle. |
| **Three keywords** | *serialized. inked. loud.* |

## Color

Two-color print on newsprint. The palette is engineered to look like spot-color offset — black ink, one red, and one optional yellow flat. Everything else is paper white or screentone.

### Tokens

```css
--mj-newsprint  : #F4EFE3;           /* page background */
--mj-paper      : #FAF7EE;           /* card / panel fill */
--mj-ink        : #0B0B0B;           /* text, borders, frames */
--mj-ink-soft   : #5A5448;           /* secondary text */
--mj-red        : #D8321F;           /* jump red — banners, CTAs, featured shadow */
--mj-yellow     : #F4CC2A;           /* callout yellow — stickers, highlights */
--mj-blue       : #2A4E8A;           /* cover blue — rare, alternate seasonal accent */
--mj-rule       : rgba(11,11,11, 0.18);
--mj-rule-faint : rgba(11,11,11, 0.08);
```

### Role assignments

| Token | Role |
|---|---|
| `--mj-newsprint` | Page background. Always with screentone dot overlay at ~8% opacity. |
| `--mj-paper` | Card surfaces, comic panel fills, mood tiles, stat cards. Slightly warmer than the page. |
| `--mj-ink` | All body text, every border, every frame. Reads as warm black; not pure `#000000`. |
| `--mj-ink-soft` | Secondary metadata (`SPRING ISSUE · ¥0`, day labels, captions). |
| `--mj-red` | Banners, the floating add button, the primary-CTA drop shadow, drop caps, drama accents. Two appearances per screen max. |
| `--mj-yellow` | Sticker callouts (`NEW!`, `FIN.`), highlighted text spans inside body. One appearance per screen. |
| `--mj-blue` | Reserved for alternate covers (autumn issue, special editions). Not used in the default issue. |
| `--mj-rule` | Solid hairlines under masthead and inside list rows. |
| `--mj-rule-faint` | Dashed dividers between back-issue list rows. |

## Typography

**Three voices**: an Anton/Bebas Latin display for magazine chrome, a 900-weight CJK gothic for headlines, and Noto Serif SC for diary body. Italic does not exist in this system; emphasis comes from weight, color, and skew.

- **Anton / Bebas Neue** — the magazine's Latin voice. Used for `VOL.07`, `EP.07`, page numbers, eyebrows, and the masthead `DIARY MAG`. Always uppercase. Never lowercase.
- **Noto Sans SC 900** — the CJK headline weight. Used for `三月号`, entry titles, tab labels, big stat numbers when no Latin glyph exists. Carries the punch.
- **Noto Sans SC 700** — list row titles and CTA labels.
- **Noto Serif SC 400** — diary body, the only place a serif appears. Reads quieter than the rest of the page so the diary entry feels like reading, not headlines.

### Scale

| Token | Size | Family | Weight | Use |
|---|---|---|---|---|
| `--ty-display` | 44 / 0.85 / -1px / uppercase | Anton | 400 | `VOL.07` masthead numeral, big stat counters |
| `--ty-headline` | 22–26 / 1.15 | Noto Sans SC | 900 | Entry titles, dream titles in detail view |
| `--ty-body-serif` | 13 / 1.7 | Noto Serif SC | 400 | Diary body text, transcribed entries |
| `--ty-body-heavy` | 14 / 1.4 | Noto Sans SC | 700 | List row titles, CTA labels, caption rows |
| `--ty-eyebrow` | 11 / +0.15em / uppercase | Anton | 400 | `← BACK`, `SHARE ▸`, `CAPTIONS · ふきだし` |
| `--ty-micro-label` | 10 / +0.2em / 900 | Noto Sans SC | 900 | `标题 / TITLE`, `今日心情 / MOOD` field labels |
| `--ty-page-number` | 9 / +0.1em | Anton | 400 | Comic panel `01`–`04` corner numbers |
| `--ty-drop-cap` | 28 / 0.8 / float | Anton | 400 | First-character drop cap on diary body, always in red |

### Signature treatments

- **Anton + Noto Sans 900 are the system's heartbeat.** A `VOL.07` Anton sitting beside `三月号` in Noto 900 is the canonical type pairing. Use it on every screen that has a masthead.
- **Drop cap in `--mj-red`, set in Anton, opens diary body.** Not Noto Serif's first character — an Anton Latin or numeric drop cap that the body wraps around. This is what makes the body feel "set" rather than typed.
- **All eyebrows are bilingual.** Field labels read `标题 / TITLE`, section headers read `分镜 · ふきだし`, modes read `撰稿中 · DRAFTING`. The bilingual pattern is required.
- **No italic anywhere.** This system has no italic mode. Emphasis = weight (900), color (red), or skew (the red banner). If you need italic emphasis, you're in the wrong system.
- **Yellow highlight as marker pen.** Inside body text, important phrases get a `--mj-yellow` background span (no padding, no radius). It reads as a highlighter swipe.

## Layout

The product **looks like a magazine being read**.

1. **Every home/calendar screen has a masthead.** Skewed red banner (`DIARY MAG`) + 2.5px rule + Anton volume mark + Noto 900 month + Anton sub-issue. Without it the product reads as a generic note-taking app.
2. **Pages are framed in 2px ink.** Every card, mood tile, stat card, and comic panel sits inside a 2px (cards) or 2.5px (comics, CTAs) hard ink border. Hairline borders break the system.
3. **Hard offset shadows do all elevation work.** 2–4px `0 0` shadows in `--mj-ink` for default elevation; in `--mj-red` for the one featured element per screen. No blur, ever.
4. **Stickers and banners rotate.** `NEW!` yellow stickers rotate 4–8°, `FIN.` rotates 4°, the red `DIARY MAG` banner has an 8° skew. The 0°-square layout is broken by these in 2–3 places per screen.
5. **Comic page is the hero on every comic-result screen.** A 2.5px-ink-bordered 2×2 grid of cream panels with 6px gutters, fed by SVG scenes. The comic itself is the only piece of "content media" in the system — no photos, no illustrations elsewhere.

### Spacing & radii

```css
/* spacing — multiples of 4 */
--space-1: 4px;   --space-2: 8px;   --space-3: 12px;  --space-4: 16px;
--space-6: 24px;  --space-8: 32px;  --space-12: 48px;
--page-margin-x: 18px;
--page-margin-y: 20px;
--comic-gutter: 6px;       /* between panels of the comic grid */

/* radii — mostly square */
--radius-square    : 0;        /* the default for cards, panels, CTAs */
--radius-bubble    : 18px;     /* speech bubbles only */
--radius-circle    : 50%;      /* mood faces, floating + button */

/* borders — heavy ink */
--border-frame       : 2px solid #0B0B0B;
--border-frame-heavy : 2.5px solid #0B0B0B;
--border-rule        : 1.5px solid #0B0B0B;
--border-rule-dashed : 1px dashed rgba(11,11,11, 0.18);

/* shadows — hard offset only */
--shadow-ink         : 4px 4px 0 #0B0B0B;
--shadow-ink-sm      : 2px 2px 0 #0B0B0B;
--shadow-red         : 4px 4px 0 #D8321F;
--shadow-red-sm      : 2px 2px 0 #D8321F;
```

## Depth

The system has exactly **two depth tools**: hard offset shadow (no blur) and screentone overlay. No gradients, no glow, no backdrop-blur.

- **Ink offset shadow** — `4px 4px 0 #0B0B0B`. Default elevation for cards, comic frames, primary buttons.
- **Red offset shadow** — `4px 4px 0 #D8321F`. Reserved for **one** element per screen — the "feature" of the page. Most often the primary CTA, sometimes a featured stat tile, sometimes the comic frame on the result screen.
- **Screentone field** — radial-dot pattern at 3–4px tile, ~8% opacity, behind the page background. Required for the magazine feeling.
- **Motion lines** — radial line bursts behind dramatic panels (e.g. panel 03 of the generated comic). Generated as SVG inside the comic, not as a CSS layer.

## Illustration direction

The illustration **is** the 4-panel comic. There are no illustrations elsewhere in the system — no decorative spots, no hero images.

### Prompt scaffold (for AI comic generation)

```
4-panel manga page, 2x2 grid layout, weekly Shōnen Jump aesthetic,
heavy 2.5px ink borders, 6px gutters,
black and white with screentone (radial dot) shading,
cream paper (#FAF7EE) panel backgrounds, ink (#0B0B0B) linework,
small page numbers (01–04) in Anton font at bottom-right of each panel,
optional red spot color (#D8321F) on hearts/exclamation marks only,
panel 1: scene setting (place + time of day),
panel 2: detail / close-up of one object from the diary entry,
panel 3: emotional climax — motion lines, speech bubble, biggest face,
panel 4: night / resolution — moon, bed, "Zzz" sound effect.
```

### Composition rules

- **Always 2×2, four panels, never more or fewer.** A 6-panel comic breaks the masthead's `VOL.XX · 4 格漫画` promise.
- **Each panel = one moment from one sentence of the diary.** Panels are not "stages of a feeling" — they are concrete scenes.
- **Screentone on sky and ground, pure white on figures.** This is the visual rhythm of jump manga.
- **One speech bubble per page, max two.** Bubbles fight the diary body for the reader's attention.
- **Red spot color only on hearts, exclamations, the moon (rare), or the cover banner.** Never as a panel fill.
- **The comic is captioned in plain text below.** Each panel gets a numbered Noto Sans caption row (`1 · 站台 · 拿铁握在手里还烫`). The caption is the bridge between diary body and comic.

## Voice & copy

Write like a **manga editor writing the splash page**. Headlines are short, two-line, emotionally direct. The diary body itself is the user's voice (don't rewrite it). Everything around it is editorial — `第 07 話`, `今日 · TODAY`, `撰稿中 · DRAFTING`, `本期 · 全 4 話`, `FIN.`.

| Slot | Example |
|---|---|
| Masthead | `DIARY MAG / 日記マガジン  ·  VOL.07  ·  三月号  ·  SPRING ISSUE` |
| Episode marker | `第 07 話` (red banner) + `2024 · 03 · 11` (Anton subtitle) |
| Entry headline | **初春的拿铁<br/>与电车窗** (Noto Sans 900, 22px, 2-line) |
| Body opener | **三**月的早晨像被人轻轻摇醒。 *(red Anton drop-cap on 三 — the first character set in Latin display)* |
| Field label | `标题 / TITLE`, `正文 / BODY`, `今日心情 / MOOD` |
| Mode eyebrow | `撰稿中 · DRAFTING`, `漫画稿 · FEATURE` |
| CTA | `生成 4 格漫画` (Noto Sans 16/900, +0.25em tracking, with NEW! sticker) |
| Sign-off | `FIN.` (yellow sticker, rotated 4°) |
| Tab labels | `日記 / 今日 · 過去 / 本棚 · 月暦 / 月历 · 作者 / me` |

## Do & Don't

### Do

- Open every home/calendar with the masthead. Without it, the product is a generic notes app.
- Pair `VOL.07` Anton with `三月号` Noto 900 — the canonical type pairing.
- Use the red drop-shadow on **one** element per screen, the most important action.
- Render mood as `MangaMood` SVG faces (5 fixed expressions). Never Unicode emoji.
- Place a `01–04` page number in the bottom-right of every comic panel — even when small.
- Rotate stickers and the red banner. A perfectly upright system reads as a notes app.
- Pair Chinese and Latin freely (`第 07 話`, `撰稿中 · DRAFTING`). The bilingual pattern is the magazine's voice.
- Yellow-highlight one phrase per body paragraph — the marker-pen swipe.

### Don't

- Don't use pure `#000000` — always `--mj-ink` (`#0B0B0B`).
- Don't use rounded corners on cards. Square is default. Only speech bubbles and circles are round.
- Don't introduce a third spot color. Red and yellow are the system; blue is reserved for special editions only.
- Don't use blur, glow, backdrop-blur, or gradient fills. All depth = hard offset shadow.
- Don't use serif (Noto Serif SC) for anything except diary body. It breaks the magazine voice.
- Don't put more than two speech bubbles inside one comic page.
- Don't add a third "featured" element — only **one** red-shadow piece per screen.
- Don't use italic. There is no italic mode.

## CJK & International

The system is **CJK-first by design** (the magazine voice is Japanese-Chinese hybrid: `日記マガジン`, `三月号`, `第 07 話`). Latin is used as chrome and counterpoint.

| Role | CJK | Latin counterpart |
|---|---|---|
| Display volume mark | Noto Sans SC 900 | Anton 44 uppercase |
| Headline | Noto Sans SC 900 | Anton 22 uppercase |
| Body | Noto Serif SC 400 | (no Latin body voice — the system rarely reads in Latin runs of >5 words) |
| Eyebrow / chrome | Noto Sans SC 900 (chinese-only chrome) | Anton +0.15em uppercase |
| Page number | — | Anton |

**Loading**:
```html
<link href="https://fonts.googleapis.com/css2?family=Anton&family=Bebas+Neue&family=Noto+Serif+SC:wght@400;500;700;900&family=Noto+Sans+SC:wght@400;500;700;900&display=swap" rel="stylesheet">
```

**Adjustments for CJK runs**:
- Line-height 1.7 for body, 1.15 for headlines.
- Letter-spacing 0 on CJK runs; +0.15em tracking is Latin-only.
- **The drop cap can be Chinese or Latin** — in this system, Anton-set Latin or numeric drop caps (the `三` in body opener) are preferred because they pair with the masthead voice.
- Speech-bubble type is Noto Sans 900 12px — never serif.
- Use Japanese characters as ornament (`日記マガジン`, `ふきだし`, `第 X 話`) even when the surrounding language is Chinese — this is the magazine's editorial voice.
- Full-width Chinese punctuation (，。：；！？「」) inside body. Half-width inside Latin eyebrows.

**Known CJK gap**: when Anton/Bebas Neue is unavailable, the Latin display falls back to a system geometric sans and the masthead loses its weight. Always preload Anton.

## Iteration checklist

1. Every home/calendar page has the masthead (red banner + VOL + month + sub-issue).
2. Every card and CTA has a 2–2.5px ink border. No hairlines.
3. **Exactly one** element per screen uses the red drop-shadow.
4. Every screen has at least one rotated element (sticker, red banner, mood-tile-active).
5. Every comic page has 4 panels, 2×2, 6px gutters, page numbers 01–04 in Anton.
6. Mood is rendered as MangaMood SVG faces. No Unicode emoji.
7. The body opener has a red Anton drop-cap.
8. Background carries the screentone overlay (~8% radial dots).

## Known gaps

- **Comic generation cost & coherence**: the system depends on the AI comic looking like real manga. Off-style output (anime-illustration, cartoon, line-only without screentone) breaks the page. Budget for a tightly-prompted generation pipeline and 1–2 retries before showing the user.
- **Mood expressivity ceiling**: 5 fixed `MangaMood` faces are sufficient for daily logging but break on extreme states (panic, ecstasy). Add 2–3 alternate faces before scaling to a wider user base.
- **No dark mode.** The system is a printed magazine; dark mode would require a different ink/paper inversion and the red would have to shift. Plan a "midnight issue" alternate palette instead of a flat invert.
- **Accessibility on red CTA**: red drop-shadow on a black block is a high-contrast pairing but the brand red against pure cream needs WCAG verification. Yellow-on-cream is borderline — keep yellow to fills, never to text.
- **Animation / hover states are not specified.** The system reads as a print artifact; if used for web, a 2–4px shadow shift on hover ("page lift") is the canonical interaction. Tap-down: shadow collapses to 0.
