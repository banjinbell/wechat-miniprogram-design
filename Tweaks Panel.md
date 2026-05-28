---
name: tweaks-panel
description: Sub-skill of `WeChat Mini-Program Design`. Use when generating the in-prototype Tweaks panel — the small live-toggleable control surface that lets the user re-skin the design without going back to the chat. Covers control selection, persistence, UI density, conflict handling, and the ceiling/floor rules that separate a useful Tweaks panel from a settings menu.
---

# Tweaks Panel

A Tweaks panel is the user's hands on the design while it's still warm. It is not a settings page; it is not a Figma plugin; it is not a feature toggle UI. It is a small, opinionated panel of curated controls that let the user *experience* the design's variations live, and either commit to one or reject all of them.

This skill expands Phase 3 Step "Tweaks panel" of the master `WeChat Mini-Program Design` skill.

## Core Principles

1. **Curated, not free-form** — every Tweak is a hand-picked set of 2–6 options. Never offer a free color picker, a slider with 100 stops, or a font dropdown with 50 entries. The user trusts you to have already pruned the bad choices.
2. **Floor 3, ceiling 8** — fewer than 3 tweaks reads as gimmick; more than 8 reads as a settings page. Most prototypes ship with 4–5.
3. **One tweak = one design hypothesis** — each control answers one question the design is currently uncommitted on. "Should the brand color lean coral or terracotta?" "Should the type pair lean editorial or playful?" "Should density be airy or dense?"
4. **Persist by default** — every tweak writes to `localStorage` and rehydrates on load. Users refresh the prototype constantly; losing their settings is jarring.
5. **The panel hides when not needed** — Tweaks toggles on/off from the host. When off, the panel is fully hidden, not minimized. The design must look correct without the panel — never use the panel as compensation for an unfinished design.
6. **Tasteful defaults even when the user didn't ask** — even if the user didn't list any tweaks in Phase 1 Q7, add 2–3 of the safest curated tweaks (primary color · type pairing · density). Reactivity is a free polish move.

---

## Phase 1: Pick the Tweaks

For each candidate tweak, evaluate against three criteria before committing:

| Criterion | Pass | Fail |
| --- | --- | --- |
| **Hypothesis-bearing** | "Is the brand more pink or orange?" — a question the design is still answering | "Pick any color you like" — abdication of design responsibility |
| **Visible immediately** | Toggling causes visible change in the current viewport (or one tap away) | Toggling changes a screen the user has to navigate to find |
| **Reversible without confusion** | User can return to default in one click | Toggling cascades into other state the user can't see |

### The canonical tweak families

For mini-program design, ~90% of tweaks fall into 8 families. Curate within these:

| Family | Question it answers | Recommended control | Typical option count | Notes |
| --- | --- | --- | --- | --- |
| **Primary color** | "What's the brand's mood color?" | `TweakColor` (curated swatches, 3–4 options) | 3–4 | Never a free picker. Each swatch is a complete sub-palette, not just one hex. |
| **Type pairing** | "How serious is this product?" | `TweakRadio` or `TweakSelect` (2–4 named pairings) | 2–4 | Show pairings as named bundles ("Editorial · 思源宋体 + EB Garamond"), not as font names. |
| **Mood-system style** | "How are emotions rendered?" | `TweakRadio` (Emoji / Color bead / SVG face / Slider) | 2–4 | This is the highest-impact tweak for diary / wellness products. |
| **Density** | "Is the product airy or dense?" | `TweakRadio` (Airy / Standard / Dense) | 2–3 | Maps to spacing scale multipliers (0.85× / 1.0× / 1.15×). |
| **Card style** | "How modern is the chrome?" | `TweakRadio` (Sharp / Rounded / Pill) | 2–3 | Maps to radius token sets. |
| **Dark mode** | "Day or night use?" | `TweakToggle` | 2 | Wire to a `data-theme` attribute, swap CSS variables. |
| **Background texture** | "Plain or atmospheric?" | `TweakSelect` (None / Grain / Stars / Pattern) | 3–4 | One of the highest-value tweaks for atmospheric systems. |
| **CTA style** | "Loud or restrained?" | `TweakRadio` (Subtle / Standard / Loud) | 2–3 | Maps to shadow / size / animation intensity. |

### Tweaks to almost never offer

- **Free font picker** — the entire point of the design is the type pairing; outsourcing it abandons the hypothesis
- **Free color picker** — same reasoning; one bad hex destroys the palette's harmony
- **Spacing slider with infinite range** — your eye sets the spacing rhythm; the user's eye sees one cramped or empty result
- **Animation speed slider** — 99% of users won't touch it; the 1% who do produce a less-good result than your default
- **"Toggle everything"** master switch — defeats the per-tweak hypothesis
- **Layout swap that changes navigation** — breaks the user's mental model of the prototype

---

## Phase 2: Wire the Panel

Use the project's `tweaks_panel.jsx` starter component. Do not hand-roll the host protocol, drag-to-move, or close-button — they're already there. Copy via:

```jsx
copy_starter_component({ kind: "tweaks_panel.jsx" })
```

Read the copied file's usage notes for the exact import order and control APIs.

### Standard composition

```jsx
const defaults = {
  primary: '#D8321F',          // brand red
  pairing: 'editorial',         // 'editorial' | 'playful' | 'classic'
  density: 'standard',          // 'airy' | 'standard' | 'dense'
  dark: false,
  texture: 'screentone',        // 'none' | 'grain' | 'screentone'
};

function PrototypeWithTweaks() {
  const [tweaks, setTweak] = useTweaks(defaults);

  return (
    <>
      <DesignCanvas ...>
        { /* artboards consume tweaks via context or props */ }
      </DesignCanvas>

      <TweaksPanel title="Tweaks">
        <TweakSection title="Brand">
          <TweakColor
            label="Primary"
            value={tweaks.primary}
            onChange={(v) => setTweak('primary', v)}
            options={['#D8321F', '#C04A28', '#A6502E', '#7A3522']}
          />
          <TweakRadio
            label="Type pairing"
            value={tweaks.pairing}
            onChange={(v) => setTweak('pairing', v)}
            options={[
              { value: 'editorial', label: '编辑' },
              { value: 'playful', label: '俏皮' },
              { value: 'classic', label: '经典' },
            ]}
          />
        </TweakSection>
        <TweakSection title="Layout">
          <TweakRadio label="Density" value={tweaks.density} ... />
          <TweakSelect label="Background" value={tweaks.texture} ... />
        </TweakSection>
        <TweakSection title="Mode">
          <TweakToggle label="Dark mode" value={tweaks.dark} ... />
        </TweakSection>
      </TweaksPanel>
    </>
  );
}
```

### Control selection guide

| Control | Use when |
| --- | --- |
| `TweakColor` (curated swatches) | Brand color or accent color, **always with `options=[]` array of 3–5 hexes or full palettes** |
| `TweakToggle` | Binary state (dark mode, capsule visible) |
| `TweakRadio` | 2–4 mutually exclusive choices with short labels (≤8 chars each) |
| `TweakSelect` | 5+ choices or long labels (textures, font pairings with long names) |
| `TweakSlider` | Genuinely continuous values (rare — usually density steps better as a 3-option radio) |
| `TweakNumber` | Power-user numerical input (rare in design tweaks) |
| `TweakText` | Brand string / product name only (rare) |
| `TweakButton` | Reset-to-defaults action |

**Default to `TweakRadio` for any 2–4 choice tweak.** Segmented controls are the most legible Tweaks UI; selects bury choices behind a tap.

### Threading tweaks into the design

Two patterns; pick by scope:

**Pattern A — CSS variables on root** (preferred for color / density / dark mode):

```jsx
useEffect(() => {
  const root = document.documentElement;
  root.style.setProperty('--brand-primary', tweaks.primary);
  root.setAttribute('data-theme', tweaks.dark ? 'dark' : 'light');
  root.setAttribute('data-density', tweaks.density);
}, [tweaks]);
```

Components read `var(--brand-primary)`. A single re-render flips the whole prototype.

**Pattern B — React context** (for tweaks that change component vocabulary like type pairing or mood system):

```jsx
const TweaksContext = React.createContext(defaults);
// wrap the canvas in <TweaksContext.Provider value={tweaks}>
// components read via useContext(TweaksContext)
```

Use this for tweaks where the change isn't a simple CSS variable — e.g. swapping a `MangaMood` SVG for a `BubbleFace` SVG, or swapping the `Noto Serif SC` font family for `LXGW WenKai`.

---

## Phase 3: Conflict & Edge Cases

Tweaks can collide. Plan for it.

### Conflict patterns

- **Dark mode + light brand color** — pure pink CTA on near-black looks wrong. Solution: when `dark` is on, look up the brand color in a `palette[primary].dark` variant instead of using the raw hex. Each brand swatch ships with a light and a dark pair.
- **Density "dense" + texture "pattern"** — the pattern reads as visual noise when the screen is also packed. Solution: auto-reduce pattern opacity from 12% to 6% when density is dense.
- **Pairing "playful" + dark mode** — Quicksand 800 on near-black with the same drop-shadow text reads cheap. Solution: tweak the shadow accent to a brighter candy hue in dark mode.
- **Card style "sharp" + mood system "BubbleFace"** — sharp ink corners under cute bubble faces is incoherent. Solution: lock card style to "rounded" when mood is BubbleFace, or surface a warning.

The principle: **two tweaks are only orthogonal if they truly are.** If they aren't, the panel makes the design worse for the user. Audit your 4–5 tweaks in pairs and either fix the conflicts or remove one of the tweaks.

### Reset & defaults

Always include a **Reset to defaults** button at the bottom of the panel:

```jsx
<TweakButton onClick={() => Object.entries(defaults).forEach(([k, v]) => setTweak(k, v))}>
  Reset
</TweakButton>
```

This is the user's escape hatch when they've explored their way into a worse design than they started with — common, expected, never punish.

### Persistence behavior

- Persist all tweaks to `localStorage` under a single key per prototype (`tweaks:<product-slug>`).
- Rehydrate on mount, before first render — don't paint defaults then flicker to user state.
- Versioning: add a `version` field to the persisted state. If the prototype's `defaults` object changes shape (new tweaks added, options renamed), the loader detects version mismatch and falls back to fresh defaults rather than crashing on an unknown option.

```js
const STORAGE_KEY = 'tweaks:diary-comic';
const STORAGE_VERSION = 2;

function loadTweaks(defaults) {
  try {
    const raw = JSON.parse(localStorage.getItem(STORAGE_KEY));
    if (raw?.version !== STORAGE_VERSION) return defaults;
    return { ...defaults, ...raw.state };
  } catch { return defaults; }
}
```

---

## Phase 4: Designing the Panel Itself

The panel is also UI. It deserves the same care as the design it controls.

- **Width 280–320px** — narrow enough to leave the design visible alongside; wide enough for labels.
- **Section labels** — group tweaks into 2–4 sections (Brand / Layout / Mode / Atmosphere). Sectionless panels feel disorganized.
- **Heading per panel** — "Tweaks" or a product-specific name ("Tune your diary"). Avoid generic ("Settings", "Customize").
- **Live preview thumbnails** — for color and font tweaks, show what each option produces visually inside the swatch, not just a hex code or font name.
- **Densely typeset** — 13px labels, 12px option text, 8px vertical gaps. The panel is functional, not luxurious; don't waste vertical space.
- **Closeable + draggable** — the starter handles this. Don't disable it.
- **Initial state**: panel **open** by default on first load (so the user discovers it), **closed** on subsequent loads if the user closed it (persist the open/closed state).
- **Match the design's aesthetic on the panel chrome.** A panel in default flat-gray on a Glass Dusk prototype reads as foreign. Tint the panel chrome with the design's ink color and matching surface fill.

---

## Phase 5: Verification

Before delivery, run through:

1. **3-5 tweaks present, each hypothesis-bearing.** Not 1; not 12.
2. **Every tweak produces visible change in the current viewport** within 1 tap of navigation.
3. **Reset button restores defaults exactly.** No partial state.
4. **localStorage persists across refresh.** Open, change, refresh — verify state survives.
5. **Conflict pairs audited.** Dark mode + each brand color combination produces a defensible result.
6. **Panel hides cleanly when toggled off** — no leftover space, no leaked styles.
7. **Panel chrome matches the design's aesthetic.** Not default flat-gray on a styled prototype.
8. **Defaults are the design's strongest opinion** — the user should be able to leave every tweak alone and ship.

---

## What "Outstanding" Looks Like

A junior designer's Tweaks panel is a settings menu — every property of the design exposed, no opinion. A master designer's Tweaks panel is a sharp question the design is still answering. The differences:

- **The defaults are committed.** Tweaks let the user explore *around* a strong default; they don't ask the user to assemble the design from atoms.
- **Each tweak is a hypothesis.** "Is the brand red or terracotta?" — not "Pick a brand color from any hex."
- **The panel chrome matches the design.** A flat-gray panel on a Glass Dusk prototype tells the user the designer stopped caring.
- **Conflicts are designed-around, not exposed.** Dark mode + each color produces a coherent result, not a "well, that's broken" result.
- **No more than 5 tweaks.** Six is rare; eight is the absolute ceiling. The discipline of pruning is the work.
- **Persistence works.** Refresh doesn't punish exploration.
- **The user can close the panel and the design still feels finished.** The panel adds reactivity; it doesn't compensate for an undecided design.

A Tweaks panel is not where you let the user finish your design. It's where you let the user *test* your design's range. Ship the strongest default. Curate the exploration. Hide everything that isn't a hypothesis.
