---
version: 0.1
name: Glass Dusk
description: A diary that opens onto the sky at golden hour. The product surface is a four-stop sunset gradient (peach → dusty pink → lilac → dusk blue); every container is a backdrop-blurred glass plate floating on top of it. The mood system is "beads of light" — translucent gradient spheres rather than emoji or numeric scales. A DM Serif Display italic carries the emotional voice; Noto Sans SC carries function. Stars, a sun orb, and a lilac aura blob live behind every screen as atmospheric texture. Generated illustrations are watercolor dusk scenes inside frosted glass panels. The system is engineered for iOS 17+ liquid-glass aesthetics and reads as treat-yourself-after-work intimate.

colors:
  g1: "#FFB89A"
  g2: "#E89AB8"
  g3: "#A684D6"
  g4: "#5D6FBF"
  ink: "#221836"
  ink-soft: "rgba(34,24,54, 0.62)"
  ink-faint: "rgba(34,24,54, 0.38)"
  glass-fill: "rgba(255,255,255, 0.22)"
  glass-fill-strong: "rgba(255,255,255, 0.34)"
  glass-stroke: "rgba(255,255,255, 0.55)"
  gold: "#F5D682"
  mood-warm: "#FFD79A"
  mood-hot: "#FFA68A"
  mood-soft: "#E695C8"
  mood-dream: "#A68CDA"
  mood-quiet: "#7E9ADB"

gradients:
  dusk-sky: "linear-gradient(180deg, #FFB89A 0%, #E89AB8 32%, #A684D6 64%, #5D6FBF 100%)"
  sun-orb: "radial-gradient(circle at 35% 35%, #FFE2B0 0%, #FFA56F 50%, transparent 75%)"
  aura-blob: "radial-gradient(circle, #C58AE0 0%, transparent 70%)"
  cta-warm: "linear-gradient(135deg, #FFE2B0 0%, #FFB0C8 50%, #C595E0 100%)"
  spectrum: "linear-gradient(90deg, #FFE2B0 0%, #FFB0C8 30%, #E695C8 55%, #A68CDA 80%, #7E9ADB 100%)"

shadows:
  glass: "0 12px 30px rgba(34,24,54, 0.16), inset 0 1px 0 rgba(255,255,255, 0.55)"
  glass-strong: "0 8px 20px rgba(34,24,54, 0.18), inset 0 1px 0 rgba(255,255,255, 0.5)"
  cta-glow: "0 14px 36px rgba(255,168,160, 0.55), inset 0 1px 0 rgba(255,255,255, 0.6)"
  tab-float: "0 12px 36px rgba(34,24,54, 0.3)"
  text-on-sky: "0 1px 6px rgba(34,24,54, 0.2)"

textures:
  sun-orb: "200×200 radial-gradient sphere blurred 0.5px, fixed off-canvas top-right. Reads as the sun about to set. Present on every screen."
  aura-blob: "240×240 violet radial blur(20px) at 0.6 opacity, bottom-left. Atmospheric weight on the lower-left of every screen."
  stars: "5–8 sub-pixel 2px white dots with 6px white box-shadow, scattered above the sun line. Required for the dusk-to-night feeling."

typography:
  display:
    fontFamily: "'DM Serif Display', 'Noto Serif SC', serif"
    fontStyle: italic
    fontSize: 52px
    fontWeight: 400
    lineHeight: 1.0
    letterSpacing: "-1px"
  title:
    fontFamily: "'DM Serif Display', 'Noto Serif SC', serif"
    fontStyle: italic
    fontSize: 28px
    fontWeight: 400
    lineHeight: 1.15
  body:
    fontFamily: "'Noto Sans SC', -apple-system, system-ui, sans-serif"
    fontSize: 13px
    fontWeight: 400
    lineHeight: 1.85
  body-emphasis:
    fontFamily: "'DM Serif Display', 'Noto Serif SC', serif"
    fontStyle: italic
    fontSize: 22px
    fontWeight: 400
    lineHeight: 1.3
  eyebrow:
    fontFamily: "'Noto Sans SC', sans-serif"
    fontSize: 11px
    fontWeight: 400
    letterSpacing: 0.25em
  micro-label:
    fontFamily: "'Noto Sans SC', sans-serif"
    fontSize: 10px
    fontWeight: 400
    letterSpacing: 0.3em
  caption:
    fontFamily: "'Noto Sans SC', sans-serif"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.6
    color: "{colors.ink-soft}"

spacing:
  space-1: 4px
  space-2: 8px
  space-3: 12px
  space-4: 16px
  space-6: 24px
  space-8: 32px
  space-12: 48px
  page-margin-x: 20px
  page-margin-y: 24px
  card-padding: 16px

radii:
  glass: 24
  glass-strong: 22
  pill: 999
  bead: "50%"
  tab: 32
  control: 22

borders:
  glass: "1px solid rgba(255,255,255, 0.55)"
  glass-strong: "1px solid rgba(255,255,255, 0.55)"
  divider: "1px solid rgba(34,24,54, 0.18)"

components:
  glass-card:
    background: "{colors.glass-fill}"
    backdropFilter: "blur(24px) saturate(140%)"
    border: "{borders.glass}"
    borderRadius: 24px
    padding: 16px
    boxShadow: "{shadows.glass}"
    description: "Default container — 22% white fill, 24px backdrop-blur, 1px white stroke at 55%, 24px radius, ambient drop shadow + inset highlight. Inside dark dusk background it reads as frosted glass."
  glass-card-strong:
    background: "{colors.glass-fill-strong}"
    backdropFilter: "blur(24px) saturate(140%)"
    border: "{borders.glass}"
    borderRadius: 22px
    description: "Featured glass plate. 34% white fill for higher opacity, slightly tighter 22px radius, used for the today/hero card on each screen."
  mood-bead:
    background: "radial-gradient(circle at 35% 30%, {color} 0%, {color}88 60%, transparent)"
    border: "1.5px solid rgba(255,255,255, 0.9)"
    borderRadius: 50%
    boxShadow: "0 0 18px {color}, inset 0 1px 4px rgba(255,255,255, 0.6)"
    description: "The mood system's atom. A translucent gradient sphere with a soft glow halo. Five fixed beads: warm/hot/soft/dream/quiet — each with its own color. Active state adds a brighter glow + 1.5px white stroke."
  comic-panel:
    background: "{colors.glass-fill}"
    backdropFilter: "blur(20px)"
    border: "{borders.glass}"
    borderRadius: 16px
    boxShadow: "{shadows.glass-strong}"
    description: "Comic panels are also glass plates — 4 panels in a 2×2 grid, 8px gutter, each with backdrop-blur and inset highlight. The watercolor scene paints inside the glass."
  cta-warm:
    background: "{gradients.cta-warm}"
    borderRadius: 28
    padding: "18px 0"
    boxShadow: "{shadows.cta-glow}"
    border: "1px solid rgba(255,255,255, 0.5)"
    description: "Primary CTA — soft warm 3-stop gradient (peach → pink → lilac), 28px radius, ambient warm glow shadow, 1px white stroke. Sits over the dusk gradient and feels lit from the inside."
  tab-bar-floating:
    background: "rgba(34,24,54, 0.4)"
    backdropFilter: "blur(30px) saturate(140%)"
    border: "1px solid rgba(255,255,255, 0.25)"
    borderRadius: 32
    boxShadow: "{shadows.tab-float}"
    description: "Floating tab bar with dark glass (40% ink fill, 30px blur). Active tab is a white pill at 85% opacity; inactive tabs are white at 85% alpha labels. Anchored 16px from the bottom + sides."
  bead-mood-picker:
    description: "Horizontal row of 5 beads (warm/hot/soft/dream/quiet). Inactive bead = 36px. Active bead = 44px + brighter glow + label weight 600. A label sits beneath each (`暖`, `热`, `柔`, `梦`, `静`)."
  intensity-slider:
    description: "Companion to mood-bead picker. A 6px-tall translucent track with the cta-warm gradient filling left → current value. Thumb is a 16px white circle with `0 2px 6px rgba(34,24,54, 0.25)` shadow. Right-side label is DM Serif italic (`暖暖`, `热烈`)."
  spectrum-bar:
    background: "{gradients.spectrum}"
    borderRadius: 18
    boxShadow: "inset 0 1px 0 rgba(255,255,255, 0.5)"
    description: "Monthly mood spectrum — a 36px-tall horizontal bar with the full spectrum gradient and overlaid white dots marking days. Used on calendar view."
  on-sky-type:
    color: "#FFFFFF"
    textShadow: "{shadows.text-on-sky}"
    description: "All text that sits directly on the dusk-sky background uses white (#FFF) with a faint 1px violet text-shadow. White on top quadrant (peach), white on bottom (dusk-blue) — both pass. Never use ink color directly on sky."
---

# Glass Dusk

## When to reach for this system

Use Glass Dusk when the diary should feel like opening a window at golden hour. The product wants warmth, modernity, and the iOS 17+ liquid-glass language without slipping into Y2K. It's the system for end-of-day, alone-with-a-tea diary writing.

**Best for** — diaries used in the evening; users 22–38 who appreciate Apple's design language; products positioning as gentle, self-care-adjacent, never therapeutic; surfaces where the comic is treated as an emotional artifact, not a comic-strip. Neighbors: Apple Journal, Stoic, Moodnotes, Reflectly's calmer screens, the typography of Substack reader mode. Premium feel without ostentation.

**Avoid for** — daytime productivity, social-share moments (the dark gradient kills bright-light screenshots), gamified streaks, audiences over 50, anything that needs to feel snappy or transactional. The system is slow and atmospheric — high backdrop-blur usage means performance budget on older phones is real.

## Aesthetic direction

| | |
|---|---|
| **Visual references** | Apple Journal (the dusk wallpapers) · iOS 17 Control Centre · *Spirited Away* sky frames · James Turrell's twilight rooms · Korean drama golden-hour cinematography · Calm app's "Daily Calm" hero · Telegram's Stars purchase screen blur |
| **Tactile qualities** | Warm sky behind cold glass. Light passing through frosted plastic. Edges that catch a hairline highlight. No edges are sharp — everything is rounded 16–28px. Atmospheric, soft-focus, slightly out-of-reach. |
| **Three keywords** | *atmospheric. intimate. iOS-native.* |

## Color

The system has **two color regions**: the sunset gradient sky behind, and the cool-violet-ink glass plates on top. Accents come from the 5 mood-bead colors — each one has its own micro-palette.

### Tokens

```css
/* sky stops — used left to right, top to bottom of the dusk gradient */
--gd-g1            : #FFB89A;            /* peach */
--gd-g2            : #E89AB8;            /* dusty pink */
--gd-g3            : #A684D6;            /* lilac */
--gd-g4            : #5D6FBF;            /* dusk blue */

/* ink — only used on glass, never directly on sky */
--gd-ink           : #221836;            /* deep plum */
--gd-ink-soft      : rgba(34,24,54, 0.62);
--gd-ink-faint     : rgba(34,24,54, 0.38);

/* glass */
--gd-glass-fill          : rgba(255,255,255, 0.22);
--gd-glass-fill-strong   : rgba(255,255,255, 0.34);
--gd-glass-stroke        : rgba(255,255,255, 0.55);

/* mood beads — each its own micro-palette */
--gd-warm  : #FFD79A;     /* calm */
--gd-hot   : #FFA68A;     /* happy / heated */
--gd-soft  : #E695C8;     /* tender */
--gd-dream : #A68CDA;     /* dreamy / nostalgic */
--gd-quiet : #7E9ADB;     /* quiet / sad */

/* misc */
--gd-gold  : #F5D682;     /* sun orb, rare hero accent */
```

### Role assignments

| Token | Role |
|---|---|
| `--gd-g1..g4` | The sunset gradient sky behind every screen. Always used as a 4-stop vertical linear. Never partial. |
| `--gd-ink` | Text on glass plates only. Pure on the lightest glass, soft on inactive states. |
| `--gd-ink-soft / faint` | Secondary labels and inactive states on glass. |
| `--gd-glass-fill` | Default glass plate fill (22% white). |
| `--gd-glass-fill-strong` | Featured glass plate fill (34% white) — one per screen, the hero card. |
| `--gd-glass-stroke` | 1px white stroke on every glass surface — essential for the "edge of frosted glass" look. |
| `--gd-warm..quiet` | The 5 mood-bead colors, each used as its own radial gradient. |
| `--gd-gold` | Sun orb, rare hero metallic accents. Used at most once per screen. |

## Typography

**Two voices**: a romantic Italian-display italic serif for emotional moments, a clean CJK sans for everything functional. The serif italic is the system's emotional anchor — used liberally for diary titles, date displays, and emphasis.

- **DM Serif Display Italic** — display, dream titles, dates rendered as "March 11," intensity labels, drop-quotes. The system's voice. Always italic; the upright form does not exist here.
- **Noto Sans SC 400** — body, eyebrows, labels, captions, tab labels. Every functional surface.
- **Noto Sans SC 500–600** — active states (mood label, selected tab text), increased weight conveying selection rather than color.

### Scale

| Token | Size | Family | Weight | Use |
|---|---|---|---|---|
| `--ty-display` | 52 / 1.0 / -1px / italic | DM Serif Display | 400 | "March 11," dates, screen-anchoring date hero on write screen |
| `--ty-title` | 28 / 1.15 / italic | DM Serif Display | 400 | Diary entry titles, comic result title |
| `--ty-body-emphasis` | 22 / 1.3 / italic | DM Serif Display | 400 | Quote pull within glass card, intensity readout (`暖暖`, `热烈`) |
| `--ty-body` | 13 / 1.85 | Noto Sans SC | 400 | Diary body text on glass plate, secondary descriptions |
| `--ty-eyebrow` | 11 / +0.25em | Noto Sans SC | 400 | `今晚`, `本周心情` over heroes |
| `--ty-micro-label` | 10 / +0.3em | Noto Sans SC | 400 | Inside glass cards: `今日 · TODAY`, `MOOD INDEX`, section markers |
| `--ty-caption` | 12 / 1.6 | Noto Sans SC | 400 | Comic captions, supporting metadata inside glass |

### Signature treatments

- **DM Serif italic is the emotional voice; it has no upright counterpart in this system.** Every italic moment is `DM Serif Display`. Never use Noto Sans italic for emphasis — DM Serif is the only emphasis tool.
- **Dates rendered as `March 11,` are the system's recurring motif.** Capital month, day, terminal comma. This appears on the write screen and the calendar header.
- **White text on sky carries a 1px violet text-shadow.** `0 1px 6px rgba(34,24,54, 0.2)`. Without it the white reads as pure-print white against a warm gradient and loses depth.
- **Ink only on glass; white only on sky.** This is the single non-negotiable type rule. Crossing them breaks the system: ink on sky = unreadable; white on glass = fluorescent.
- **Eyebrows use wide tracking (+0.25–0.3em).** This makes them recede into the glass surface, like an etched label.

## Layout

The system is **glass plates floating over weather**.

1. **The sky is always 4 stops, full bleed, never partial.** The dusk gradient occupies the entire viewport behind the UI. Cutting it short or using a flat-color region breaks the system.
2. **Every container is a glass plate.** 22% white fill, 24px backdrop-blur, 1px white stroke, 24px radius, ambient drop shadow + inset highlight. Never a solid panel.
3. **One "strong" glass per screen.** The hero/today card uses the strong variant (34% white fill, slightly tighter 22px radius). This is how the user's eye finds the focal point.
4. **Three atmospheric textures always present**: sun orb (top-right), aura blob (bottom-left), 5–8 sub-pixel stars (above sun line). Without them the sky reads as a cheap gradient.
5. **The tab bar floats**, 16px from each edge, dark glass (40% ink fill, 30px blur). Active tab is a white pill. The bar never spans full-width — it's a free-floating control.

### Spacing & radii

```css
/* spacing — multiples of 4, slightly looser than functional UI */
--space-1: 4px;   --space-2: 8px;   --space-3: 12px;  --space-4: 16px;
--space-6: 24px;  --space-8: 32px;  --space-12: 48px;
--page-margin-x: 20px;
--page-margin-y: 24px;
--card-padding: 16px;

/* radii — generous, iOS-native */
--radius-glass         : 24px;     /* default glass card */
--radius-glass-strong  : 22px;     /* featured/hero glass card */
--radius-tab           : 32px;     /* floating tab bar */
--radius-cta           : 28px;     /* primary warm CTA */
--radius-control       : 22px;     /* secondary buttons inside glass */
--radius-pill          : 999px;
--radius-bead          : 50%;      /* mood beads */

/* shadows */
--shadow-glass         : 0 12px 30px rgba(34,24,54,0.16), inset 0 1px 0 rgba(255,255,255,0.55);
--shadow-glass-strong  : 0 8px 20px rgba(34,24,54,0.18), inset 0 1px 0 rgba(255,255,255,0.5);
--shadow-cta-glow      : 0 14px 36px rgba(255,168,160,0.55), inset 0 1px 0 rgba(255,255,255,0.6);
--shadow-tab-float     : 0 12px 36px rgba(34,24,54,0.3);
```

## Depth

The system uses **backdrop-blur + ambient shadow + inset highlight** in a strict layered formula.

- **Backdrop blur 24px saturate 140%** on every glass plate. The saturation boost is what makes the glass plates feel warm rather than overcast.
- **Ambient drop shadow** `0 12px 30px rgba(34,24,54, 0.16)`. Soft, ink-violet, never pure black.
- **Inset top highlight** `inset 0 1px 0 rgba(255,255,255, 0.55)`. This single hairline at the top of every glass surface is what reads as "edge of frosted glass" rather than "translucent rectangle."
- **CTA glow shadow** `0 14px 36px rgba(255,168,160, 0.55)`. A warm peach glow under the primary CTA, suggesting it emits warmth onto the surface beneath.
- **No hard offset shadows.** No 0-blur shadows anywhere. The system is entirely soft, atmospheric depth.

## Illustration direction

The 4-panel comic is rendered inside **glass plates** — each panel is a backdrop-blurred frosted plate containing a watercolor dusk scene. The watercolor sits behind the glass blur, not in front.

### Prompt scaffold (for AI comic generation)

```
4-panel diary comic, watercolor and digital painting,
soft warm dusk lighting, peach/pink/lilac/dusk-blue palette
matching the sunset gradient #FFB89A → #E89AB8 → #A684D6 → #5D6FBF,
no hard line work, painterly edges, atmospheric haze,
silhouetted figures (no facial detail), back-lit,
panel 1: sunset establishing shot — figure at the window / station
panel 2: warm object close-up (cup, latte heart) at golden hour
panel 3: two figures meeting, soft aura between them
panel 4: night — moon, bed, soft "zzz", cool dusk-blue tones
each panel 4:5 aspect, square corners (the glass frame is added in CSS)
```

### Composition rules

- **Silhouettes, never faces.** Figures are dark plum (#3D2D5A) silhouettes against warm backgrounds. The viewer projects the protagonist onto the silhouette.
- **Always 4 panels, 2×2 grid, 8px gutter.** Comics are wrapped in glass — the watercolor sits behind a backdrop-blurred frosted frame.
- **Each panel = one warm or cool moment.** Panels 1–3 are warm; panel 4 is cool (the dusk → night transition). This temperature arc is the system's narrative spine.
- **No speech bubbles, no text inside panels.** Captions live in a separate glass plate below the comic — DM Serif italic numerals (`1`, `2`, `3`, `4`) + Noto Sans 13 caption per panel.
- **Warm-glow halo around emotional elements.** A 22% radial light haloes the central object/figure of each panel.

## Voice & copy

Write like **a friend texting you at golden hour**. Short, soft, sensory. Quietly observational. No second-person directives, no "you should…", no therapy-speak.

| Slot | Example |
|---|---|
| Greeting (eyebrow + display) | `晚上好` + *今晚的天空，是暮光紫。* |
| Date display | *March 11,* (italic, with terminal comma) |
| Entry title | *拿铁里漂着一颗小小的心* |
| Body opener | 傍晚的咖啡店，落地窗里映出整片天空。 |
| Pull quote in body | *"为不再勉强的人生。"* (italic, leading em-dash framing) |
| Mood prompt | `今天的心情是哪种光` |
| Intensity readout | *暖暖* (italic DM Serif, paired with slider) |
| CTA | `✦ 让 AI 把今晚画成漫画` |
| Section eyebrow | `今晚 ✦ TONIGHT`, `MOOD INDEX`, `本月光谱` |

## Do & Don't

### Do

- Run the dusk gradient full bleed on every screen. Always 4 stops, top → bottom.
- Wrap every container in glass (22% fill, 24px backdrop-blur, 1px white stroke, ambient shadow + inset highlight).
- Use exactly one strong-glass plate per screen as the hero.
- Always render the sun orb (top-right), aura blob (bottom-left), and 5–8 stars (above sun line) — even on writing screens.
- Use DM Serif italic for every emotional moment; use Noto Sans for everything else.
- Render dates as `March 11,` italic.
- Render mood as gradient beads (warm/hot/soft/dream/quiet). Each bead is its own micro-palette.
- White text on sky always carries the 1px violet text-shadow.

### Don't

- Don't use ink on sky or white on glass. Cross-rule.
- Don't use hard offset shadows. All shadows are soft, ambient, blurred ≥20px.
- Don't introduce a third type voice. DM Serif italic and Noto Sans only.
- Don't use the system on light/cream backgrounds. The dusk gradient is required.
- Don't use Unicode emoji except `✦`, `✧`, `♡` (rare). The mood beads are the emoji system.
- Don't use a flat-color region anywhere in the viewport — it breaks the atmospheric premise.
- Don't go below 22% glass fill — the cards become invisible against the gradient.

## CJK & International

DM Serif Display lacks CJK glyphs. Pair with **Noto Serif SC 500** for italic-display Chinese moments — but accept that "italic Chinese serif" is a faux concept; lean on weight and color instead.

| Role | Latin | Chinese counterpart |
|---|---|---|
| Display italic | DM Serif Display italic | Noto Serif SC 500 (no italic) |
| Body | Noto Sans SC 400 | Noto Sans SC 400 |
| Eyebrow / micro | Noto Sans SC 400 +0.25–0.3em | Noto Sans SC 400 +0.15em (CJK doesn't tolerate +0.25em as gracefully) |

**Loading**:
```html
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Noto+Serif+SC:wght@400;500;700&family=Noto+Sans+SC:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

**Adjustments for CJK runs**:
- Line-height 1.85 (body), 1.3 (title). The display italic loosens to 1.15 on Latin but 1.25 on CJK.
- Letter-spacing 0 on body CJK; +0.15em on CJK eyebrows (down from +0.25em on Latin).
- **No italic Chinese serif exists on Google Fonts.** For the italic-emphasis treatment inside body, substitute one of: (a) DM Serif Display Latin numeral or English fragment (e.g. *"March 11"*); (b) weight contrast (Noto Serif SC 500 inside Noto Sans 400); (c) color shift to `--gd-soft`.
- Mood-bead labels (`暖`, `热`, `柔`, `梦`, `静`) are single CJK characters — pair beautifully with DM Serif italic.
- Insert ASCII space between adjacent CJK and Latin runs (盘古之白).
- White-on-sky text shadow same for Latin and CJK — Chinese characters are visually denser so the shadow is needed equally.

**Known CJK gap**: the date motif `March 11,` is Latin-only. For all-Chinese deployments, render as `三月十一日` in Noto Serif SC 500 — accept the loss of italic motion and trust the gradient + glass to carry the warmth.

## Iteration checklist

1. Dusk gradient (4 stops) covers the full viewport on every screen.
2. Sun orb (top-right), aura blob (bottom-left), and 5–8 stars are present even on dense screens.
3. Every container is glass — 22% fill / 24px blur / 1px white stroke / ambient shadow + inset highlight.
4. **Exactly one** strong-glass plate per screen (34% fill, hero card).
5. White text on sky has the 1px violet text-shadow; ink text only on glass.
6. DM Serif italic for every emotional/title moment; Noto Sans for everything functional.
7. Mood is rendered as gradient beads (5 colors). Selected bead is brighter + 1.5px white stroke.
8. Tab bar floats, dark-glass, 16px from each edge.

## Known gaps

- **Performance budget on backdrop-blur**: every glass card is `backdrop-filter: blur(24px) saturate(140%)`. On older Android devices and below iOS 15 this is expensive. Provide a "reduced motion / reduced transparency" fallback: solid `rgba(255,255,255, 0.4)` fills without blur, ambient shadow retained.
- **Contrast verification on white-over-sky**: white text over the peach top of the gradient passes WCAG AA at large sizes only; small (12px) white captions on the lightest part of the sky may fail. Always check against the `--gd-g1` stop.
- **The watercolor comic generation is unproven.** Silhouetted figures + warm/cool temperature arc + 4 panels in a single prompt is a heavy ask for current AI models. Plan a curated set of dusk-scene templates as fallback.
- **No "loud" state.** The system has no urgent / alert / error treatment that matches the aesthetic. For destructive confirmations, break out into a vanilla iOS sheet rather than try to invent an angry-glass variant.
- **Date motif is Latin-only.** `March 11,` italic is the system's most distinctive type move; CJK deployments lose it. Plan an `三月十一日` Noto Serif 500 alternate that doesn't try to imitate italic.
- **Mood granularity ceiling**: 5 beads (+ intensity slider) gives ~20 perceived states. Above that, the bead system collapses. Don't try to scale to 20+ discrete moods.
