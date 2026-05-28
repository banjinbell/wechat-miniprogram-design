# Design Systems Index

Two product lines, six systems. Pick the right one for the brief before opening a Figma file.

## Product line A · Dream Journal *(three systems)*

> Source HTML: `Dream Journal · Design Systems.html`

Three independent visual systems explored for the Dream Journal product. Each is self-contained, has a distinct emotional register, and is ready to be lifted into Figma libraries, code tokens, and copy guidelines.

| Slug | Name | One-liner | When to reach for it |
|---|---|---|---|
| `cosmic-nocturne` | Cosmic Nocturne | Sacred ritual on a dark cosmic ground | Nighttime reading, vulnerable first-person content, meditative tone |
| `liquid-iridescence` | Liquid Iridescence | Saturated gradient weather, screenshot-ready | Gen-Z / younger millennial, social-share moments, premium tier |
| `paper-folio` | Paper Folio | A bound book of plates and notes | Literary practice, daytime reading, heirloom pricing, print/PDF |

## Product line B · Diary Comic *(three systems)*

> Source HTML: `Diary Comic · Design Systems.html`

Three independent visual systems explored for the WeChat diary mini-program — a product where the user logs text + mood and the app generates a 4-panel comic. Each system gives the generated comic a different visual identity and a different relationship to the diary body.

| Slug | Name | One-liner | When to reach for it |
|---|---|---|---|
| `manga-jump` | Manga Jump | A weekly shōnen magazine for the user's own life | Comic-first products, manga-primed audiences, serialized/monthly-issue feel, collectible mini-programs |
| `glass-dusk` | Glass Dusk | Frosted glass plates on a sunset gradient sky | Evening/end-of-day diaries, iOS-native liquid-glass aesthetic, gentle self-care positioning |
| `y2k-bubble` | Y2K Bubble | A diary that thinks it's a 2002 MP3 player | Gen-Z and screenshot-shareable products, school/campus user bases, candy-loud secondary skins |

Each system has its own folder with two files:

```
design-systems/
├── README.md                         ← this file
│
│   ── Product line A · Dream Journal
├── cosmic-nocturne/
│   ├── design.md                     ← full spec: tokens, type, components, voice, CJK, do/don't, gaps
│   └── preview.md                    ← selection card: when to choose, signature moves
├── liquid-iridescence/
│   ├── design.md
│   └── preview.md
├── paper-folio/
│   ├── design.md
│   └── preview.md
│
│   ── Product line B · Diary Comic
├── manga-jump/
│   ├── design.md
│   └── preview.md
├── glass-dusk/
│   ├── design.md
│   └── preview.md
└── y2k-bubble/
    ├── design.md
    └── preview.md
```

**`preview.md`** is the short selection card — read it first to decide which system fits a brief.
**`design.md`** is the full spec — read it before doing any production design in that system.

## How to read these files

Every `design.md` has the same structure so you can compare across systems:

1. **YAML frontmatter** — colors, shadows, typography, spacing, radii, components as tokens. Copy-pasteable into CSS or design-token tooling.
2. **When to reach for this system** — best-for / avoid-for, audience age, closest neighbors.
3. **Aesthetic direction** — visual references, tactile qualities, three keywords.
4. **Color** — tokens + role assignments.
5. **Typography** — scale, signature treatments, voice rules.
6. **Layout** — screen-level composition principles.
7. **Depth** — what shadow/glow/grain language the system uses.
8. **Illustration direction** — prompt scaffold + composition rules.
9. **Voice & copy** — example slots with canonical phrasing.
10. **Do & Don't.**
11. **CJK & international.** — Chinese pairings, loading, adjustments, known gaps.
12. **Iteration checklist** — 6–7-item gut-check before shipping a new screen.
13. **Known gaps** — honest list of what hasn't been figured out yet.

## How to pick between them

### Dream Journal · A vs B vs C

| Axis | Cosmic Nocturne | Liquid Iridescence | Paper Folio |
|---|---|---|---|
| Audience age | 25–45 | 18–35 | 28–55 |
| Time of day | Night, just-woken | Any time, social | Day, slow reading |
| Interpretation tone | Mystical · Jungian | Poetic · curious | Literary · editorial |
| Shareability | Medium | **High** | Low |
| Build complexity | Medium (glow, blur) | **High** (gradients, blends) | Low (flat, hairlines) |
| Ad creative | Yes — atmospheric | **Yes** — eye-catching | No — too quiet |
| Premium signal | Strong | Strong | **Strongest** (heirloom) |

### Diary Comic · D vs E vs F

| Axis | Manga Jump | Glass Dusk | Y2K Bubble |
|---|---|---|---|
| Audience age | 16–35 | 22–38 | 14–28 |
| Time of day | Any (collectible/serial) | Evening (golden hour) | Any (social/screenshot) |
| Comic style | Real B&W manga, screentone, speech bubbles | Watercolor dusk silhouettes, no faces, glass frames | Flat candy pop, big eyes, pink cheek dots |
| Voice | Bilingual JP/CN editorial — `第 07 話 / FIN.` | Soft texting at golden hour — `March 11,` italic | 19-yo group chat — `★ DIARY.EXE ★`, `(´；ω；\`)` |
| Shareability | Medium-high (collectible feel) | Low-medium (dark gradient kills screenshots) | **Highest** |
| Build complexity | Medium (heavy borders + offsets + screentone) | **High** (backdrop-blur on every container) | Medium (offset shadows + nested frames) |
| Iconography | `MangaMood` SVG faces | Gradient mood beads | `BubbleFace` SVG bubbles |
| Background | Newsprint + 8% screentone | 4-stop dusk gradient + sun + aura + stars | Pastel + pixel-heart/sparkle pattern + rainbow ribbon |
| Premium signal | Strong (collectible) | **Strongest** (iOS-native premium) | Low — built for loudness, not luxury |
| Tone-deafness risk | Low | Low | **High** (loud against grief/illness) |
| Mood granularity ceiling | 5 fixed faces | 5 beads × intensity slider (~20 states) | 5 fixed faces |

If you are picking one system to ship: use these axes.
If you are blending two: lift discrete pieces (one system's color, another's typography) — never mix the illustration treatments.

### Cross-line guidance

The two product lines are **not interchangeable**. A diary-comic system is built around a 4-panel generated illustration as the headline feature; a dream-journal system is built around a single dream image + long-form interpretation. The component vocabulary differs at the foundation:

- Diary Comic systems all ship a `comic-panel` primitive and a `mood-face` SVG kit. Dream Journal systems ship a single `dream-illustration` frame and a mood-chip cluster.
- Diary Comic typography assumes short body (1 entry = 1 day, ~150–300 chars). Dream Journal typography assumes long body (1 dream = paragraph-essay).
- Diary Comic systems are CJK-first (the product targets a WeChat mini-program). Dream Journal systems are bilingual.

If you need to mix lines — e.g. a dream journal that also generates a comic — pick one line as the foundation and lift only the discrete illustration treatment from the other, never the full system.

---

## Figma library — what to build

The markdown files above let designers *specify* and *reason about* the system. To actually design with it in Figma, you need a published library. Here's the recommended structure (one library per system; do not combine three systems into one library):

### 1 · Foundations (variables, not components)

Use **Figma Variables** with collections + modes. One mode per system if you publish a single shared library; one collection per system if separate.

- **Color variables** — every token from the `colors:` frontmatter, named in `system/category/role` form (e.g. `cosmic/accent/moon-gold-warm`, `liquid/glass/stroke`). Bind text and shape fills to variables only — never raw hex in component instances.
- **Typography styles** — every entry in the `typography:` frontmatter as a Figma Text Style. Name them by token (`display`, `title-l`, `body-serif`, `eyebrow`, `caption`, `micro-label`). Include the italic variants as separate styles, not as a property toggle.
- **Spacing variables** — the 4-multiple scale (`space-1` … `space-12`) as number variables. Use them in auto-layout gap/padding, not raw pixels.
- **Radius variables** — `radius-pill`, `radius-card`, `radius-input`, `radius-stamp` per system.
- **Effect styles** — every shadow/glow in the `shadows:` block (Cosmic's glow-moon, Liquid's CTA double-glow, Paper's paper-lift). Effect styles, not component instances — they should attach to any frame.
- **Grid styles** — page margins (24×28 phone), book-column gutter (56px), text-column max-width (480–560).

### 2 · Primitives (atoms)

Small atomic components. Each one should be a single layer or auto-layout frame with variant properties.

- **Icon** — line icons matching the system. Cosmic: thin (1.25px) outline icons with rounded caps. Liquid: filled or gradient-stroked icons. Paper: hand-drawn-feeling 1.5px hairline icons, slight imperfection.
- **Divider** — solid hairline / dashed / ornament-break (Paper only).
- **Badge / count pill** — small numerical chip per system.
- **Avatar / placeholder image** — system-styled placeholder frame.
- **Star / blob / grain background fill** — Cosmic's star field as a fill; Liquid's color blob as a frame with the right blur + blend; Paper's grain overlay as a tileable fill.

### 3 · Chips, tags, buttons

These are the highest-traffic components — invest the most in variants here.

- **Tag chip** — with variants for: state (default, active, disabled), color (per accent), shape (Paper's rotated stamp vs Liquid's pill vs Cosmic's veil).
- **Mood chip** — italic-serif single-word chip (Cosmic + Paper) / sans pill chip (Liquid).
- **Button** — variants for size (sm/md/lg), emphasis (primary/secondary/ghost), state (default/hover/pressed/disabled). Cosmic primary is the moon-gold radial pill; Liquid primary is the floating round iris CTA; Paper primary is the square stamp block.
- **Floating action button** — Liquid system only.

### 4 · Cards & containers

- **Veil card** (Cosmic) / **Glass card** (Liquid) / **Framed plate** (Paper) — three variants for the system-default elevated container.
- **Featured card** — Cosmic's gold-rimmed card / Liquid's iris-gradient-border card / Paper's vellum-elevated card.
- **Modal / sheet** — bottom sheet, centered modal, full-screen takeover.
- **List row** — dream item in folio listing, with title + subtitle + date + status.
- **Interpretation block** — long-form text block with optional drop cap (Paper) or pull quote (Cosmic) or gradient lede (Liquid).

### 5 · Composite UI

These are the next tier — pre-assembled patterns that appear on multiple screens.

- **Top bar / running head** — Cosmic's eyebrow line; Liquid's mode + count; Paper's `VOL. III · NO. 0XX` running head.
- **Tab bar / nav** — Cosmic and Paper have tab bars; Liquid uses a floating CTA + header tabs instead.
- **Process indicator** — `READING · 03 / 07` style progress for the AI interpretation generation. Critical for every system.
- **Mood / emotion picker** — chip cluster for tagging dreams. High traffic.
- **Audio recorder pill** — recording state with waveform.
- **Dream illustration frame** — image placeholder with system-appropriate framing (halo blur / 1.5px ink frame / no frame for Liquid).
- **Empty state** — first-run, no-dreams-yet, no-search-results.
- **Toast / inline notification** — system-appropriate alert treatment.

### 6 · Screens (templates)

Half a dozen full-screen frames per system, set up as page templates with proper page layouts and grids attached:

- **Home / today** — the just-woken first screen.
- **Recording** — active capture state.
- **Detail / interpretation** — single-dream long-form view.
- **Library / folio listing** — multi-dream browse.
- **Onboarding / first run** — three to five sequential frames.
- **Settings** — minimal, system-styled.
- **Year-in-review / wrapped** — Liquid system only; the share-driven moment.

### 7 · Documentation pages

Inside the Figma file:

- **Cover page** — system name, slug, three keywords, link to `design.md`.
- **Color page** — every swatch with name, hex, role, and usage notes.
- **Type page** — every text style at sample size + meta strip.
- **Component index** — every component published from this library, with usage notes.
- **Do/Don't gallery** — paired examples lifted from `design.md`.
- **Changelog** — when variables/components change, who and why.

### Conventions across all three libraries

- **Naming**: `system/category/component/variant` — e.g. `cosmic/card/veil-card/elevated`. Forced taxonomy reads better in the assets panel.
- **Variant properties**: use boolean toggles for `has-icon`, `has-drop-cap`, `is-featured`. Avoid 10-variant matrices — most properties should be booleans.
- **Auto-layout everywhere**: every component is auto-layout-resizable. No "fixed-size" components in the published library.
- **Annotate edge cases**: components attach to a hidden frame with "fails when…" notes for next time.
- **One designer owns variables; everyone can publish components.** Variables are the dependency root — they should change rarely and on purpose.

### What *not* to put in Figma

- Star fields, color blobs, and grain overlays at high count — these break Figma's rendering performance. Provide them as exported PNG/SVG assets to be dragged in, not as component instances.
- Live illustration prompts — keep prompt scaffolds in `design.md` and link out from a Figma documentation page. Don't paste them into image fills.
- Hard-coded copy — every component places text as variables / Figma variables (string) where it makes sense. Don't bake `"good morning, dreamer"` into a component master.

---

## Workflow for a designer joining the project

1. **Read this README** for orientation.
2. **Read all three `preview.md` files** to understand which system fits which moment.
3. **Pick one system** and read its `design.md` end to end (15–25 min per system).
4. **Open the Figma library for that system** and check the cover page + changelog.
5. **Pull from the variables and components**, never from raw hex or pasted layers.
6. **Reference the source HTML** (`Dream Journal · Design Systems.html`) when prose isn't enough — it shows the system in motion against itself.

## What's missing / open questions

- These docs are a **starting point**, not a finished spec. Each system has a `Known gaps` section listing what hasn't been figured out yet — read those before assuming completeness.
- The Figma libraries described above are **recommended**, not yet built. Building them is its own week of work per system.
- The illustration prompt scaffolds produce 70%-quality results out of AI image gen — a curated human-illustrated set of 20–30 archetypal plates per system is needed for production.
- Accessibility audits have not been run on any of the three systems. Cosmic's violet-on-violet body and Liquid's gradient text both need contrast verification.

---

*Drafted as a translation of `Dream Journal · Design Systems.html` — refine in collaboration with the team.*
