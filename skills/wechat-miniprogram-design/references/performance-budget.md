# Performance Budget

> Reference for `WeChat Mini-Program Design` skill. Read this **before generating** in Phase 3 — the budget below determines which visual effects are even available to you. Brand-immersive fidelity is where most of these constraints bite hardest.

Mini-programs run inside WeChat's WebView. On iOS this is WKWebView (Safari-equivalent, fast). On Android it is the **X5 kernel based on an older Chromium** — markedly slower on backdrop-blur, large gradients, complex shadows, and long lists. Treat Android low-end (Redmi Note / Vivo Y-series / OPPO A-series, ~50% of the Chinese installed base as of 2024) as the design floor.

The budget is a contract between design and engineering. Break it and the product feels broken to half your users.

## Silent-failure CSS — features that don't error, just don't render

This is the single most important section. The following CSS features are unreliable in WeChat's WebView (especially X5 on Android). They don't throw an error; they simply render as if the property weren't there. A design that depends on them for its identity ships broken to a large slice of users without anyone noticing in QA.

| Feature | Behavior on X5 / older WebViews | What gets shown instead | Mitigation |
| --- | --- | --- | --- |
| `backdrop-filter` | Often ignored; sometimes renders as opaque white | Solid white or transparent; "glass" reads as a flat panel | `@supports not (backdrop-filter: blur(0))` fallback to opaque `rgba(255,255,255,0.5)` fill. See pattern below. |
| `filter: blur()` / `drop-shadow()` | Unreliable; performance cliff even when supported | Un-blurred / un-shadowed element | Use static blurred PNG / pre-rendered shadow assets. Never depend on `filter` for iconic identity. |
| `clip-path` (polygon / path) | Spotty support; complex paths fail | Original square / un-clipped element | Use SVG masks via `mask-image` (more reliable), or pre-render the clipped shape as an image. Never use `clip-path` for an iconic shape (a star CTA, a tilted card). |
| Scroll-driven animations (`animation-timeline: scroll(...)`) | Not supported | No animation; element static | Use IntersectionObserver + add/remove classes in JS. Don't design parallax for production unless engineering owns the JS implementation. |
| `view-transition-name` / View Transitions API | Not supported in mini-program WebView | Page swap with no transition | Implement custom transitions via CSS keyframes + JS state. View Transitions are still bleeding-edge web tech and have no mini-program equivalent. |
| CSS Container Queries | Spotty | Element renders at default size | Use media queries on viewport; don't design responsiveness that depends on container size. |
| CSS `:has()` selector | Spotty | Selector silently doesn't match | Avoid in production WXSS. If used in HTML prototype, document the intent so engineering can re-implement as React/JS conditional. |

The pattern is consistent: **bleeding-edge CSS features fail silently in mini-program WebViews.** Treat anything younger than ~2020 in the CSS spec as not-portable until proven otherwise. The HTML prototype the skill produces can use them freely (Chrome dev simulator); the handoff doc must flag them.

## Package & asset budgets

| Asset | Floor | Ceiling | Notes |
| --- | --- | --- | --- |
| Main package size | — | **2 MB** | Hard limit before WeChat refuses to publish. Subpackages can extend to 20 MB total. |
| First-screen JS | — | **500 KB** | First-render budget. Past this, T1 (time-to-first-paint) on Android drops below 1s. |
| Hero image (full-bleed) | — | **200 KB** | Compress to WebP if user base is on WeChat ≥7.0 (covers ~98% in 2024). |
| Card / list thumbnail | — | **30 KB** | At 2× scale. WebP preferred. |
| Logo | — | **20 KB** | SVG preferred; falls back to PNG @1×/2×/3×. |
| Inline SVG illustration | — | **15 KB per** | Past this, parse cost dominates render. Split into images and reuse. |
| Custom font file (WOFF2) | — | **150 KB per weight** | Each additional weight costs another 80–150 KB. **Two weights max** for the whole product (one CJK + one Latin). Subset CJK fonts; do not ship the full 16,000-glyph file. |
| Total custom font weight | — | **300 KB** | The aggregate ceiling. Cuts T1 on Android by ~300ms vs unbounded. |

## Render-cost budget (per screen, per frame target)

| Effect | Cost on Android low-end | Verdict | Mitigation |
| --- | --- | --- | --- |
| `transform` / `opacity` animation | 1× (GPU-composited) | **Free** — always prefer | — |
| `box-shadow` blur ≤ 8px | 1× | **OK** | — |
| `box-shadow` blur 8–16px | 2× | **OK for ≤ 3 elements per screen** | Beyond 3, switch to a static drop-shadow image asset. |
| `box-shadow` blur > 16px | 4–6× | **Avoid** in scrollable content; OK on static hero only | Use a layered radial-gradient PNG instead. |
| Linear gradient (no blur) | 1× | **Free** | GPU-composited. |
| `backdrop-filter: blur(20px)` | **10–20×** on X5 kernel | **Catastrophic for >2 layers per screen.** Often renders as opaque white on low-end Android (silently broken). | Limit to ≤ 2 concurrent glass plates on Android. Provide a fallback `rgba(255,255,255,0.4)` opaque fill when `@supports not (backdrop-filter: blur(0))`. |
| Procedural noise SVG (`feTurbulence`) | 3–5× per surface | **Avoid generating live**; use a pre-rendered tileable PNG | Same visual, 1× cost. |
| Long list ≥ 30 items, no recycling | Cumulative — scrolling drops to 20fps after item 50 | **Always use `recycle-view` / `lazy-load`** | The Vant Weapp `van-list` and WeUI `weui-virtual-list` handle this. |
| Custom font with full CJK glyph set | First paint blocked 400–800ms | **Always subset** | Use `font-display: swap` and a system-font fallback. |
| Multiple Google Font weights | +200ms per weight | **2 weights max** | See font budget above. |

## Concrete rules of thumb

- **Glass Dusk-style designs** (backdrop-blur everywhere) need a hard fallback policy for Android. The system's `design.md` should call this out — if it doesn't, **add it before generating**. The fallback is a higher-opacity solid fill without blur, ambient shadow retained.
- **Long-form lists** (calendar grids, archive views, dream library): paginate or virtualize past 30 items. The user will not scroll past 30 anyway; you're paying render cost for an audience of zero.
- **Animations** on scroll-bound elements (parallax, fade-in-on-scroll) are deadly on Android. Restrict scroll-bound motion to one element per screen, max.
- **Image weight audit**: before delivery, screenshot every screen, compute its total asset weight, and flag any screen >500 KB. The screens users open most (home, today, write) should be the lightest.
- **Frame budget**: 60fps = 16ms per frame. WeChat's WebView reliably hits 30fps (33ms budget). Design for 30fps; anything that requires 60fps on low-end is broken.
- **Subset CJK fonts aggressively.** The full Noto Sans SC ships ~10 MB. Subsetted to the ~3,000 glyphs your product actually uses, ~400 KB. The skill's `CJK & International` checklist in every `design.md` should specify which glyph subset.

## Detection & fallback pattern

```css
/* Default — assume backdrop-blur works */
.glass-card {
  background: rgba(255,255,255, 0.22);
  backdrop-filter: blur(24px) saturate(140%);
}

/* Fallback for Android X5 / older browsers */
@supports not (backdrop-filter: blur(0)) {
  .glass-card {
    background: rgba(255,255,255, 0.55);
    /* keep the inset highlight; drop the blur */
  }
}
```

Test in WeChat developer tools' "真机调试" (real-device debug) on at least one Redmi/Vivo low-end before declaring a design ready for Brand-immersive fidelity. The desktop simulator lies.
