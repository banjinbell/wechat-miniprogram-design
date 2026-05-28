# WeChat-Native Component Vocabulary

> Reference for `WeChat Mini-Program Design` skill. Read this in Phase 3 when picking the component vocabulary for the chosen fidelity mode, and again in Phase 6C when writing the engineering handoff.

Three component libraries dominate mini-program engineering: **WeUI** (Tencent official, the WeChat default look), **Vant Weapp** (Youzan, the dominant consumer-product library), and **Taro UI** (JD, multi-platform). Most teams ship using one of these. As a designer, you must know what they offer so you can either:

- **Use their vocabulary** (in WeChat-native fidelity mode) — fast handoff, signal-correct.
- **Translate yours into theirs** (in Custom-skinned mode) — engineering can swap CSS variables on existing components instead of re-implementing from scratch.
- **Reject them entirely** (in Brand-immersive mode) — but explicitly, with a rationale.

The table below translates the three libraries' atomic components into our design-system language (`design-systems/<slug>/design.md` component recipes).

| Role | WeUI | Vant Weapp | Taro UI | Our system equivalent |
| --- | --- | --- | --- | --- |
| Page background | `body` (white default `#FFFFFF`) | `body` (`#F7F8FA` gray) | `body` (`#FAFBFC`) | `--surface` token; never default white if Custom-skinned. |
| List row | `weui-cell` (gray hairline divider, 16px h-padding) | `van-cell` (label · value pattern, right-chevron, 1px hairline) | `AtListItem` | `card-default` + dashed/hairline divider per system. Our list rows often wear color (mood face + title + tag chip), not just text. |
| Card | (no dedicated component; uses `weui-panel`) | `van-card` (product card: image left, title/price/tag right) | `AtCard` | `card-default` (white fill + 2.5px ink border + offset shadow) or system-specific (`glass-card`, `framed-plate`, etc.). |
| Primary button | `weui-btn weui-btn_primary` (#07C160 fill, 8px radius, full-width default) | `van-button type="primary"` (#1989FA fill, 999px radius) | `AtButton type="primary"` (#6190E8 fill) | `cta-block` / `cta-rainbow-chrome` / `cta-warm` — system-specific. Our CTAs are bigger, more committed, often double-framed. |
| Secondary button | `weui-btn weui-btn_default` (white fill, 1px gray border) | `van-button type="default"` | `AtButton size="normal"` | `cta-block-secondary` — usually paper-fill + ink border + small offset shadow. |
| Warn / destructive | `weui-btn weui-btn_warn` (#E64340 fill) | `van-button type="danger"` (#EE0A24) | `AtButton type="secondary"` styled red | System red token — applied to the same `cta-block` shape, not a different shape. |
| Tag / chip | `weui-tag` (1px border, small radius) | `van-tag` (filled, hollow, mark, plain variants) | `AtTag` (round, hollow, mark) | System-specific: `stamp-chip` (rotated letterpress) / `tag-label` (candy sticker) / `mood-chip` (italic serif). |
| Mood / emoji | — | — | — | **Always system-specific SVG** (`MangaMood`, `BubbleFace`, mood beads). Never reach for an off-shelf emoji picker. |
| Tab bar (bottom) | `weui-tabbar` (icon + label, white fill, 1px top border) | `van-tabbar` + `van-tabbar-item` (icon + label, badge support) | `AtTabBar` | System-specific (`DTab` / `ETab` / `FTab`) — ours often float, have rounded corners, or use a candy-color active state. |
| Top nav bar | `weui-navbar` (title + back arrow, 44px) | `van-nav-bar` (left/title/right slots) | `AtNavBar` | Usually replaced with a custom header that respects the capsule. Standard nav-bars feel generic. |
| Input field | `weui-input` (1px bottom border) | `van-field` (label + input + clear button) | `AtInput` (label · input · clear · error) | Custom — usually framed (our `border-frame`) or sitting inside a glass plate, never the default underline-only look. |
| Modal | `weui-dialog` (centered, title + body + 2 actions) | `van-dialog` (slots for header/body/footer) | `AtModal` | Custom — bottom sheet with system radius + system depth. The centered dialog reads as a v1 web modal. |
| Action sheet | `weui-actionsheet` (slide up from bottom) | `van-action-sheet` (description + cancel slot) | `AtActionSheet` | Bottom sheet with system styling. Respect 34px iOS safe-area inset. |
| Toast | `weui-toast` (centered black panel + checkmark) | `van-toast` (4 variants: text, loading, success, fail) | `AtToast` | Custom toast — usually system-tinted (paper + ink border) instead of generic black-panel. |
| Loading indicator | `weui-loadmore` (spinner + "正在加载") | `van-loading` (circular/spinner) | `AtActivityIndicator` | System-specific loading state — animated SVG, system color, often paired with a "the AI is drawing your comic" copy line. |
| Stepper / quantity | — | `van-stepper` | `AtInputNumber` | Usually system-tinted with ink borders + offset shadows. |
| Uploader | `weui-uploader` | `van-uploader` | (none) | Usually styled into an `image_slot` placeholder. |
| Empty state | `weui-msg` (icon + title + description + action) | `van-empty` (4 illustrations) | (manual) | **Always system-specific** — illustrated, branded, never the off-shelf "暂无数据 / no data" stock illustration. |

**Color palette reference** (use these only when in WeChat-native fidelity mode):

| Library | Primary | Secondary | Warn | Link |
| --- | --- | --- | --- | --- |
| WeUI | `#07C160` (WeChat green) | `#1AAD19` | `#FA5151` | `#576B95` |
| Vant Weapp | `#1989FA` (Vant blue) | `#07C160` | `#EE0A24` | `#1989FA` |
| Taro UI | `#6190E8` | `#78A4FA` | `#FF4949` | `#6190E8` |

If you find yourself reaching for these hex values outside WeChat-native mode, stop. You are about to ship something that looks like every other mini-program.

**Translation pattern for handoff**: when handing off a Custom-skinned design to a team using Vant Weapp, write the handoff as "use `van-button` with these CSS overrides…" instead of "build a new button from scratch." Engineering swaps tokens; they don't reinvent atoms.

## WXSS gotchas — native element behavior the design must accommodate

WXSS is not CSS-in-the-browser. Several native elements behave differently than their HTML counterparts. If your design assumes browser-CSS semantics, engineering will hit a wall.

| Element / pattern | Browser CSS behavior | WXSS behavior | What this means for design |
| --- | --- | --- | --- |
| `<image>` | Accepts `box-shadow` directly | **Ignores `box-shadow`** | Wrap every shadowed image in a `<view>` and shadow the wrapper. Plan for this in component recipes — every `comic-panel` / `card-with-photo` is image-inside-view, never bare image. |
| `<button>` | No default border | **Ships with a grey hairline border on top** | A global reset (`button::after { display: none; }`) is required. Mention in handoff; designers should not specify "native button" anywhere. Use `<view>` with `hover-class` instead for custom buttons. |
| `<input>` placeholder | `::placeholder` pseudo-element | **`placeholder-class` attribute**, no pseudo-element | Specify placeholder styling as a named class in component recipes (e.g. `"input-placeholder"`), not as `::placeholder { ... }`. |
| Press state | `:hover` / `:active` | **`hover-class` attribute** (~150ms hover trigger, press-state semantics) | Don't design web-style hover effects; they have no equivalent on mobile WeChat. Design tap-down / press states instead and document them as `hover-class` rules. |
| Bottom-fixed elements | `padding-bottom: 34px` | **Use `env(safe-area-inset-bottom)`** | Every bottom-fixed CTA, tab bar, sheet must read `padding-bottom: calc(16px + env(safe-area-inset-bottom));` in handoff CSS. Designers: assume 34px of safe-area at the bottom on iPhone X+, 0 on older devices. |
| Pull-down refresh | Custom required | **System-provided** (configured per page in `app.json`) | Don't design a custom pull-down indicator unless explicitly overriding in Brand-immersive. |

## Pattern law — feedback, errors, and toasts

WeChat has strong cultural conventions about feedback patterns. Breaking them makes the product feel un-WeChat-ish in a way users register as "amateur."

- **Toast is success or info only.** Auto-dismisses in 1.5s. Centered, with optional icon. Never use it for errors — errors must persist until the user resolves them.
- **Form errors live in two places**: a summary at the top of the form (`出错 · 请检查以下项`), and inline beneath the offending field (red text, ~12px, with a small icon if your system has one). Both, not either.
- **Loading is its own state, not a toast.** Use a full-screen loading view, an inline spinner, or a skeleton screen depending on context. A `weui-toast` with a spinner is acceptable for short (≤2s) blocking operations only.
- **Success confirmation after destructive action** uses a brief toast + an immediate UI update; not a modal. Modals interrupt; toasts inform.
- **Modals are for required decisions only.** "Confirm delete?" — yes. "Welcome to the app!" — no.
- **Action sheets slide up from bottom** and are dismissable by tapping outside or pulling down. Always include a separate cancel row at the very bottom (after a small visual gap from the action options) to match WeChat's native pattern.
