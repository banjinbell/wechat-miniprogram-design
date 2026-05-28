# Y2K Bubble — Preview Card

Use this small file for title-screen previews and template selection only. For final product design, read the full design doc listed below.

## Files

- Full design doc: `design-systems/y2k-bubble/design.md`
- Preview card: `design-systems/y2k-bubble/preview.md`

## Selection Metadata

- Slug: `y2k-bubble`
- Tagline: A diary that thinks it's a 2002 MP3 player. Chrome silver, candy primaries, pixel hearts, bubble fonts, and a rainbow ribbon along the top.
- Mood: candy, chrome, screenshot-able, loud, nostalgic-Y2K
- Tone: an excited 19-year-old texting their group chat — bracketed star wrappings, mixed CN/EN/JP, emoticons-as-syntax (`(´；ω；\`)`)
- Formality: low
- Density: medium-dense (stickers stacked on stickers)
- Scheme: light pastel (baby blue + bubblegum pink alternate)
- Audience: 14–28, Gen-Z and early-millennial nostalgia, social-share-heavy users, campus/school cohort
- Best for: comic-diary mini-programs targeting Pinkoi / Moo日记 / Sanrio-style audiences, screenshot-driven products, secondary "cute" skin inside a multi-skin product. Strongest shareability of the three systems. Neighbors: 2002 iPod skins, MSN Messenger, Tamagotchi, Powerpuff Girls UI, Sanrio, The Sims 2, Lisa Frank stationery.
- Avoid for: adult/serious/therapeutic surfaces, finance, productivity, audiences over 35, B2B contexts. The system is tone-deaf for vulnerable entries — pair with a `glass-dusk` alternate skin if the product handles grief/illness.

## Visual Snapshot

A baby-blue page (or bubblegum pink on the write screen) with a 6px rainbow gradient strip running along the top, just under the WeChat capsule. Scattered behind the UI: 8–10 pixel hearts (home/calendar) or pixel sparkles (write/comic) at ~12% opacity. Every container is a 2.5px-ink-bordered rounded card with a 2.5–4px hard offset shadow in deep night blue (#1B1059, never black). The system's hero move is the "rainbow wrapper" — a 2–3px outer gradient frame around the featured today card and the primary CTA. The primary CTA is two nested frames: rainbow outside, chrome silver inside (a 4-stop 180° linear gradient that looks like 2002 brushed metal), with a bold uppercase Quicksand label flanked by sparkle SVGs. Display titles use double drop-shadow text (`2px 2px 0 #FFF, 4px 4px 0 #FF6FB5` on home, `…0 #5BCEFF` on calendar) for a bubble-letter feeling. Mood is rendered as 5 hand-built `BubbleFace` SVG bubbles (yellow / pink / blue / lavender / green), each with cartoon eyes, glass top-highlight, and pink cheek circles — never Unicode emoji. Every numeral (dates, char counts, calendar days, `EP.07`) is set in VT323 pixel font. Eyebrows are wrapped in star ornaments (`★ DIARY.EXE ★`, `✦ TODAY ✦`). Tags are candy-color stickers, each with its own fixed color (#daily=yellow, #night=lavender, #rant=pink). The floating tab bar is white-fill with active tabs translated `(-1px, -1px)` for a press-up feel.

## Preview Ingredients

- Surfaces: bg-blue #D4E9FF (default) · bg-pink #FFE3F1 (write screen alt) · paper #FFFFFF
- Ink: #1B1059 (deep night blue, never black) + #5949A8 soft
- Candy primaries: pink #FF6FB5 · blue #5BCEFF · yellow #FFE066 · green #A6F068 · lavender #C8B0FF
- Chrome: `linear-gradient(180deg, #FFF, #E8F0FF 30%, #C0D0E8 55%, #FFF)`
- Rainbow: `linear-gradient(90deg, #FF6FB5, #FFD56A, #A6F068, #5BCEFF, #C8B0FF)`
- Typography: Quicksand 400/700/800 (display, headlines, body, eyebrows) + VT323 pixel monospace (every numeral, `EP.07`, char counts) + Noto Sans SC 400/700/900 (CJK fallback at matching weight)
- Signature move: 6px rainbow ribbon along the top of every screen (85% opacity). Without it the system collapses.
- Signature move: Rainbow wrapper — 2–3px outer gradient frame around the featured card and primary CTA. At most two per screen.
- Signature move: Chrome silver pills and CTA inner — 4-stop 180° gradient with inset white highlight + inset bottom shadow.
- Signature move: Double drop-shadow text on display titles (`2px 2px 0 #FFF, 4px 4px 0 <candy>`).
- Signature move: BubbleFace SVG mood system — 5 candy bubbles with cartoon eyes, pink cheek circles, glass highlight. Never emoji.
- Signature move: VT323 pixel font for every numeral.
- Signature move: Star-wrapped eyebrows (`★ DIARY.EXE ★`, `✦ TODAY ✦`).
- Signature move: Candy-color tag stickers — each tag wears its own fixed color, with a 1.2px ink border and 6px radius.
- Signature move: Tab bar press-up — active tab translates `(-1px, -1px)` with candy fill + own offset shadow.

## International / CJK Preview Note

- Quicksand and VT323 both lack CJK glyphs. Pair Quicksand with Noto Sans SC 400/700/900 at matching weight. For pixel numerals, keep numerals Latin (`14/31`, `EP.07`, `03.11.24`) and let the surrounding Chinese render in Noto Sans SC — the pixel-mono / CJK split is part of the y2k look.
- All-Chinese deployments lose some of the loudness (no Chinese bubble-font equivalent of Quicksand 800). Compensate by leaning harder on candy color and sticker chrome.
- Drop-shadow on titles works equally for CJK — Noto Sans SC 900 holds the double shadow as well as Quicksand 800.
- Tighten eyebrow tracking from Latin's +0.2em to +0.1em on CJK.
- Use `(´；ω；\`)`-style emoticons inside body — the period-correct millennial CJK style.
- Full-width Chinese punctuation in body; half-width in eyebrows/CTAs.

## Preview Rules

- Build exactly one title screen at the product's canonical canvas (phone-portrait, e.g. 393×852, inside an iOS frame with the WeChat top capsule).
- Background must be `#D4E9FF` (default) or `#FFE3F1` (alternate write screen) plus the 6px rainbow ribbon at the top. A flat pastel without the ribbon is not this system.
- Background texture pattern (pixel hearts on home/calendar; sparkles on write/comic) must be present at ~12% opacity.
- Use the user's real product title/subtitle/context; do not copy demo content (`三月日记` is a demo phrase).
- The BubbleFace SVG faces — not emoji — must render for any mood indicator.
- The display title must carry the double drop-shadow text.
- Never place internal workflow text on the screen: no `preview`, `template`, `Option A/B/C`, file names, paths, or source-doc labels.
- Never place the system codename (`y2k-bubble`) on the screen itself.
- After the team picks this system for the full build, read the full `design.md` before generating final screens, the comic-generation pipeline, or Figma library entries.
