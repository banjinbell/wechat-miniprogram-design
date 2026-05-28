# WeChat Mini-Program Design

A coding-agent skill for designing **production-grade WeChat mini-program UI** — multi-screen interactive React prototypes inside a real iOS frame with the WeChat top capsule. Packaged as a Claude Code plugin; the core `SKILL.md` can also be read by other coding agents with filesystem access.

## What This Does

Helps non-designers design WeChat mini-programs by showing them **side-by-side device-frame previews** instead of asking them to describe aesthetics in words. The deliverable is a clickable HTML prototype + a `handoff.md` your dev team can implement against — including AI feature wiring with the CloudBase preflight checklist.

### Key Features

- **Real iPhone Frame** — Every screen lives inside an iOS bezel with the WeChat top capsule rendered correctly. No naked mockups.
- **Flows, Not Screens** — Default deliverable is a 4–6 screen flow on a pan/zoom canvas. The user reads transitions, not hero shots.
- **Visual Style Discovery** — 3 distinct home-screen previews side-by-side; pick the direction you like (or mix elements).
- **Anti-AI-Slop** — Avoids the "white card + system 苹方 + blue link + pink-purple gradient CTA" trap. 6 curated design systems with committed visual theses.
- **CJK-First Typography** — Real Chinese content, real product nouns, real dates. Latin display fonts pair *to* the CJK weight, not the other way.
- **CloudBase-Ready Handoff** — Generated `handoff.md` includes `wx.cloud.extend.AI` call shapes, the 5-step preflight checklist (envId, 成长计划, Token Credits, model group), and default model picks (`deepseek-v3.2` / `hunyuan-image-v2`).

## Installation

### Via Claude Code Plugin Marketplace

Two commands as **two separate Claude Code messages** (don't paste both at once):

```text
/plugin marketplace add https://github.com/banjinbell/wechat-miniprogram-design
```

After that finishes:

```text
/plugin install wechat-miniprogram-design@banjinbell
```

Then trigger with `/wechat-miniprogram-design:wechat-miniprogram-design` or just say *"帮我设计一个日记小程序"* — it auto-triggers.

Use the HTTPS URL. The shorter `banjinbell/wechat-miniprogram-design` form may make Claude Code try SSH, which can fail if GitHub isn't in your `known_hosts`.

### Claude Code Manual Installation

```bash
git clone https://github.com/banjinbell/wechat-miniprogram-design.git
cp -r wechat-miniprogram-design/skills/wechat-miniprogram-design ~/.claude/skills/
```

Triggers as `/wechat-miniprogram-design` (no plugin namespace).

### Other Coding Agents

Cursor, Cline, Aider, Codex, Gemini CLI, OpenCode — point the agent at this repo and ask it to use the skill:

```text
https://github.com/banjinbell/wechat-miniprogram-design
```

The agent should start from `skills/wechat-miniprogram-design/SKILL.md` and load referenced support files on demand. The skill body uses capability-name language (e.g. *"materialize a starter component"*) and defers shell-specific mechanisms to its built-in *Runtime Adapter* table, so it doesn't depend on Claude-Code-only tools.

## Usage

### Design a new mini-program

```text
> "帮我设计一个日记小程序，五个屏幕：首页 / 写日记 / 加载中 / 漫画结果 / 分享卡"
```

The skill will:

1. Ask 6 structured questions in one shot (product, user moment, flows, fidelity, brand, references)
2. Generate 3 distinct home-screen previews in iOS frames
3. Let you pick the direction (or mix elements across previews)
4. Expand the chosen direction into all the screens you listed, on a single pan/zoom canvas
5. Wire 2–4 live tweaks (color, type pairing, density, dark mode) so you can re-skin in-place
6. Open the prototype in your browser + auto-generate `handoff.md` and a 2× PNG set

### Refine an existing prototype

```text
> "Phase 3 这版 hover state 太重了，能改细一点吗？还有把成长版的 mood face 换成更可爱的"
```

The skill detects Mode C (enhancement), reads every existing screen first, then applies modifications under explicit rules (no breaking capsule clearance, no breaking 44px tap targets, no overflow).

### Recreate an existing mini-program

```text
> "我想把这个小程序的设计抄一遍：https://github.com/some-team/their-miniprogram"
```

The skill switches to Mode B (reskin), imports tokens from the source repo, identifies the component library in use, and recreates the design at your canvas — pixel-faithful via lifted hex values rather than eyeballed screenshots.

## Included Design Systems

Six pre-built, hand-tuned visual systems. The skill consults `design-systems/README.md` first, shortlists 2–3 candidates whose `audience / mood / time-of-day / shareability / build complexity` axes match your brief, then renders them as Phase 2 previews.

### Dream Journal line

- **Cosmic Nocturne** — Late-night, navy & gold, serif-led, contemplative
- **Liquid Iridescence** — Soft, dreamy, oil-on-water gradients, modern editorial
- **Paper Folio** — Tactile paper texture, hand-bound book aesthetic, warm neutrals

### Diary Comic line

- **Manga Jump** — 90s 日漫 spot color, screentone, kinetic, drop-shadow signatures
- **Glass Dusk** — Frosted glass plates, magic-hour gradients, premium consumer
- **Y2K Bubble** — Candy colors, chrome highlights, playful, share-first

Each system has a lightweight `preview.md` (~5KB, read during shortlisting) and a full `design.md` (~25KB, read only after the user picks the direction). Don't fit any of these? The skill will design a new system *in the same shape* and capture it for next time.

## File Structure

```
wechat-miniprogram-design/                       ← single-plugin marketplace
├── .claude-plugin/
│   ├── marketplace.json                         ← Claude Code marketplace catalog
│   └── plugin.json                              ← plugin manifest (rolling release)
├── skills/wechat-miniprogram-design/            ← the skill itself
│   ├── SKILL.md                                 ← entry point
│   ├── Tweaks Panel.md                          ← sub-skill
│   ├── design-systems/                          ← 6 design systems (selection index + previews + full specs)
│   ├── starters/                                ← ios-frame, design-canvas, tweaks-panel, image-slot
│   └── references/                              ← component-vocab, performance-budget, handoff-template
├── README.md
└── LICENSE                                      ← MIT
```

## License

MIT — see [LICENSE](LICENSE). Use it, fork it, embed it into your own skill library; attribution welcome but not required.

## Contributing

Issues and PRs welcome. The skill is opinionated by design — see *What "Outstanding" Looks Like* at the bottom of `skills/wechat-miniprogram-design/SKILL.md` for the bar it tries to clear.
