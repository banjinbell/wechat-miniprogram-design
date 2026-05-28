# handoff.md template

> Reference for `WeChat Mini-Program Design` skill. The skeleton below is what Phase 5 writes by default into `handoff.md` alongside the prototype. Copy the structure, fill in the project-specific values from the chosen design system and the AI preflight results, and keep prose to a minimum — engineering wants token names, call shapes, and checklists, not narrative.

Engineering opens 微信开发者工具 with this doc and the prototype's CSS variables next to each other. The dev team or a downstream agent shell (see `ai-model-wechat`, `miniprogram-development`, `cloudbase` companion skills) reads it to implement the design.

---

## Template

````markdown
# <Product> · Handoff

## Tokens (paste into app.wxss)
:root { --primary: #D8321F; --ink: #0B0B0B; ... }

## Type scale (rpx for WXSS)
Display   — 88rpx / 0.85 line-height / Anton uppercase
Headline  — 44rpx / 1.15 / Noto Sans SC 900
Body      — 26rpx / 1.7 / Noto Serif SC 400
...

## Component recipes
### card-default
fill: --paper · border: 4rpx solid --ink · radius: 0 · shadow: 8rpx 8rpx 0 --ink

### cta-block (featured)
fill: --ink · color: --paper · border: 0 · radius: 0
shadow: 8rpx 8rpx 0 --red    ← the system's signature, one per screen
...

## rpx conversion
Design canvas: 393×852. Multiplier: 1px @ 393 design ≈ 1.91rpx.
All values above already converted.

## AI features

### Preflight checklist (complete BEFORE writing any wx.cloud.extend.AI code)
- [ ] EnvId bound: `wx.cloud.init({ env: '<envId>' })` configured in app.js
- [ ] 成长计划 enrollment for this envId checked (query AttendRecords). Two outcomes:
      - Enrolled → `hunyuan-exp` group is free, use it
      - Not enrolled → only paid groups work; default to `cloudbase`
- [ ] Token Credits resource pack non-zero (e.g. pkg_token_free_10w LeftValue > 0)
- [ ] Chosen model group Status=1 (active in this env)
- [ ] Picked group + model (see defaults below)

### Default group + model picks (override only with reason)
- Text: provider=`cloudbase`, model=`deepseek-v3.2`
- Image: provider=`hunyuan-image`, model=`hunyuan-image-v2`

### Per-feature wiring (one block per AI surface in the design)
**<Feature name, e.g. "Comic narrative from a diary entry">**
- Prompt template: <fill in — include user-input slots as `{{slot}}`>
- Provider/model: `cloudbase` / `deepseek-v3.2`
- Call:
  ```js
  const model = wx.cloud.extend.AI.createModel({ provider: 'cloudbase', model: 'deepseek-v3.2' });
  const res = await model.generateText({ messages: [{ role: 'user', content: filledPrompt }] });
  ```
- "AI unavailable" UI state: <screen name from prototype — the artboard that renders when the call fails / Token Credits exhausted / 成长计划 dropped>

**<Image-gen feature, if applicable>**
- Provider/model: `hunyuan-image` / `hunyuan-image-v2`
- Call:
  ```js
  const imageModel = wx.cloud.extend.AI.createImageModel({ provider: 'hunyuan-image', model: 'hunyuan-image-v2' });
  const { url } = await imageModel.generateImage({ prompt: filledPrompt });
  ```
- "AI unavailable" UI state: <artboard name>

Full call-shape details (streamText callbacks, error envelope, retry behavior) — see `ai-model-wechat` skill.
````

---

## Notes for the writer

- Keep the doc terse. Engineering doesn't want prose; they want token names and recipes.
- The AI section is **mandatory** if the design has any AI surface. The preflight checklist is not optional — without it, `wx.cloud.extend.AI.createModel(...)` fails opaquely at runtime.
- Include the "AI unavailable" artboard name for every feature. If the design doesn't have one yet, go back to Phase 3 and add it — production calls fail and the UI must degrade gracefully.
- For non-text modalities (audio/video gen), follow the same per-feature block pattern; swap `hunyuan-image` for the relevant provider group.
- If both 成长计划 and Token Credits are available, prefer `hunyuan-exp` group (free) for cost control, but **only after preflight confirms enrollment** — otherwise calls fail.
