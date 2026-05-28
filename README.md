# WeChat Mini-Program Design

A skill for designing **production-grade WeChat mini-program UI** — multi-screen interactive React prototypes that live inside a real iOS frame with the WeChat top capsule. Helps non-designers discover their aesthetic through side-by-side device-frame previews rather than abstract style words.

> **What you get:** a clickable HTML prototype + a `handoff.md` your dev team can implement against — including AI feature wiring with the CloudBase preflight checklist.

---

## Who this is for

- **Designers / PMs / founders** designing a WeChat mini-program from scratch
- **Engineers** prototyping the UI before writing WXML/WXSS/JS
- **Non-designers** who want to discover what aesthetic they like by reacting to side-by-side phones rather than guessing style words

The skill assumes you are designing for the **WeChat mini-program medium** (not generic web UI). The capsule, the safe-area, the 44px hit target, the WeChat tab bar, the `rpx` unit — these are the medium's signature edges, and this skill designs *with* them.

---

## What's required

### To run the skill (mandatory)

- An **agent shell with filesystem access**. Verified to work with:
  - Claude Code (terminal, IDE, or claude.ai)
  - Cursor
  - Cline
  - Aider
  - Codex CLI
  - Any custom MCP-based coding agent
- A **modern browser** to view the deliverable (Chrome, Edge, Safari, Firefox).

That's it. No MCP servers, no API keys, no cloud accounts to *run the skill itself*.

### To take the design to production (optional, for the dev team afterwards)

The skill generates a `handoff.md` that names the companion skills/resources the dev team uses to implement the design. These are **not** runtime dependencies of this skill — they're reading material for whoever picks up the handoff:

- [`miniprogram-development`](https://docs.cloudbase.net/) — project scaffold, WeChat Developer Tools workflow, `miniprogram-ci` preview / upload / release
- [`cloudbase`](https://docs.cloudbase.net/) — environment binding, NoSQL/MySQL, 云函数, 云存储, the AI extension overview
- [`ai-model-wechat`](https://docs.cloudbase.net/ai/) — exact `wx.cloud.extend.AI` call shape, model groups, mandatory 2-step preflight
- [`auth-wechat`](https://docs.cloudbase.net/) — native mini-program login (`wx.login` → OPENID/UNIONID)
- A WeChat mini-program AppID + a CloudBase EnvId
- (For AI features) Token Credits resource pack or 成长计划 enrollment

If you're only doing design review, none of these matter. The prototype runs in your browser.

---

## Installation

### Claude Code

```bash
cp -r "WeChat Mini-Program Design" ~/.claude/skills/
```

Then in a new session, the skill auto-triggers on prompts like *"帮我设计一个日记小程序"* or *"design a fitness tracking mini-program"*.

### Cursor / Cline / Aider / generic agents

Place the folder anywhere your agent's skill loader scans. For Cursor and most MCP-based shells, reading `SKILL.md` at session start (via the agent's rules / system-prompt convention) is enough — the body is self-contained.

### Manual / one-off use

You don't have to "install" anything. Just point your agent at `SKILL.md` and start the conversation:

> "Read `/path/to/WeChat Mini-Program Design/SKILL.md` and follow it. I want to design a mini-program for tracking gym workouts."

---

## Quick start

In your agent, after the skill is loaded:

```
你好，帮我设计一个日记小程序，五个屏幕：首页 / 写日记 / 加载中 / 漫画结果 / 分享卡
```

The skill responds by:

1. **Phase 1 — Content discovery.** Asks 6 structured questions in one shot (product, user moment, flows, fidelity level, brand assets, tone/references). You answer once.
2. **Phase 2 — Style discovery.** Generates **3 distinct home-screen previews** in real iOS device frames with the WeChat capsule rendered. You pick the direction you like (or "mix elements").
3. **Phase 3 — Full prototype.** Expands the picked direction into all the screens you listed, on a pan/zoom design canvas. Wires in 2–4 tasteful tweaks (color, type pairing, density, dark mode) so you can re-skin live. Wires the AI feature through an `aiComplete` hook with real LLM calls in claude.ai or a realistic mock everywhere else.
4. **Phase 4 — Delivery.** Opens the prototype in your browser and summarizes how to navigate it.
5. **Phase 5 — Share & Export.** Auto-generates a 2× PNG set + a `handoff.md` with color tokens, type scale, component recipes, rpx conversion, and the AI features section with the CloudBase preflight checklist.

---

## File structure

```
WeChat Mini-Program Design/
├── SKILL.md                  ← entry point (~530 lines)
├── Tweaks Panel.md           ← sub-skill for the in-prototype Tweaks panel
├── README.md                 ← you are here
│
├── design-systems/           ← 6 pre-built named visual systems
│   ├── README.md             ← selection index with comparison axes
│   ├── cosmic-nocturne/      ┐
│   ├── liquid-iridescence/   │  Dream Journal line (~25KB design.md each)
│   ├── paper-folio/          ┘
│   ├── manga-jump/           ┐
│   ├── glass-dusk/           │  Diary Comic line
│   └── y2k-bubble/           ┘
│
├── starters/                 ← copy-paste JSX building blocks
│   ├── ios-frame.jsx         ← iOS device bezel + WeChat capsule
│   ├── design-canvas.jsx     ← pan/zoom multi-artboard canvas
│   ├── tweaks-panel.jsx      ← live-toggleable controls
│   └── image-slot.js         ← user-fillable image placeholders
│
└── references/               ← progressive disclosure docs (read only when needed)
    ├── component-vocab.md    ← WeUI / Vant Weapp / Taro UI translation
    ├── performance-budget.md ← X5 silent-failure CSS, asset weight ceilings
    └── handoff-template.md   ← handoff.md skeleton with AI preflight section
```

---

## Key design choices

- **The prototype is NOT the mini-program.** It's an HTML React design in Chrome — use modern CSS freely (`clip-path`, `backdrop-filter`, `:has()`). Production-side portability is documented in `handoff.md`, not pre-degraded into the design.
- **Show flows, not screens.** A mini-program is judged on transitions and reactivity. The default deliverable is a 4–6 screen flow on a single canvas, not isolated hero shots.
- **CJK-first typography.** Real Chinese content, real product nouns, real dates. Latin display fonts get paired *to* the CJK weight, not the other way.
- **Distinctive over "WeChat default".** White rounded-corner cards + system 苹方 + blue links is "AI slop" of this medium. The skill picks committed visual theses from the pre-built design-systems library.
- **Production AI uses `wx.cloud.extend.AI` directly** — no cloud function proxy. The skill writes the call shapes and preflight checklist into `handoff.md` for the dev team.

---

## Portability across agent shells

Different shells expose different tools. This skill uses **capability-name language** in the body ("materialize a starter component", "render to PDF", "open the deliverable") and defers each concrete mechanism to a *Runtime Adapter* table inside `SKILL.md`. The table has columns for:

- Claude.ai shell (artifact viewer) — uses `copy_starter_component`, `window.claude.complete`, `done` signal
- Claude Code (terminal / IDE) — uses Read + Write, mock with `setTimeout`, write file + tell user the path
- Generic fallback — covers Cursor, Cline, Aider, vanilla Claude Code, Codex CLI, custom MCP agents

The Generic fallback is intentionally lowest-common-denominator: filesystem + browser + shell. If your shell isn't listed, add a column.

---

## License

(See repository root.)

---

## Contributing / feedback

Issues and PRs welcome. The skill is opinionated by design — see *What "Outstanding" Looks Like* at the bottom of `SKILL.md` for the bar it tries to clear.
