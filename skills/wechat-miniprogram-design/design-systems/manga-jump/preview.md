# Manga Jump — Preview Card

Use this small file for title-screen previews and template selection only. For final product design, read the full design doc listed below.

## Files

- Full design doc: `design-systems/manga-jump/design.md`
- Preview card: `design-systems/manga-jump/preview.md`

## Selection Metadata

- Slug: `manga-jump`
- Tagline: A weekly shōnen magazine for the user's own life. Every diary entry is a numbered episode set in heavy ink, screentone, and jump-red.
- Mood: serialized, inked, loud, editorial-collectible
- Tone: bilingual JP/CN editorial — `第 07 話`, `撰稿中 · DRAFTING`, `FIN.`
- Formality: medium
- Density: medium-dense (magazine spread)
- Scheme: newsprint cream
- Audience: 16–35, manga readers, mini-program users who want their diary to feel collectible
- Best for: diary apps with AI-generated comics as the headline feature, mini-programs that want serialized/monthly-issue feel, users primed for manga vocabulary, comic-first products. Neighbors: Weekly Shōnen Jump covers, Mangadex, *Honey and Clover* tankōbon, Risograph zines.
- Avoid for: meditation/therapeutic apps, financial or productivity tools, audiences over 45 unprimed for manga, surfaces where the comic is incidental rather than central. The system has high visual ego — strip the masthead and comic and it loses its identity.

## Visual Snapshot

A 1990s weekly manga magazine compressed into a phone screen. Pages open with a `DIARY MAG / 日記マガジン` red banner skewed -8°, then a 2.5px ink rule, then a 44px Anton `VOL.07` next to a Noto Sans 900 `三月号`. Cards and CTAs are hard-edged 2px-ink-bordered blocks with 4px hard offset shadows in ink — except exactly **one** featured element per screen, whose shadow shifts to brand red `#D8321F`. The generated diary illustration is a real 4-panel manga page (2×2 grid, 6px gutters, screentoned skies, white figures, hand-drawn speech bubbles, `01–04` Anton page numbers). Mood is rendered as 5 hand-built `MangaMood` SVG faces — never Unicode emoji. Body is opened by a red Anton drop-cap on the first character. Yellow `NEW!` and `FIN.` stickers rotate 4–8° in card corners. Backgrounds carry a faint 8%-opacity screentone (radial dot) field — without it the system collapses to a generic notes app.

## Preview Ingredients

- Palette: newsprint #F4EFE3; paper #FAF7EE; ink #0B0B0B; ink-soft #5A5448; red #D8321F; yellow #F4CC2A; (rare) blue #2A4E8A
- Typography: Anton/Bebas Neue (Latin chrome — `VOL.07`, eyebrows, page numbers) + Noto Sans SC 900 (CJK headlines, tab labels, `三月号`) + Noto Sans SC 700 (body-heavy, CTA labels) + Noto Serif SC 400 (diary body only)
- Signature move: Masthead on every home/calendar — skewed red `DIARY MAG / 日記マガジン` banner + 2.5px rule + Anton `VOL.07` + Noto 900 `三月号` + Anton sub-issue
- Signature move: Hard 2–4px offset shadows in ink everywhere; **exactly one** red-shadow element per screen
- Signature move: 5-face `MangaMood` SVG (calm / happy / sad / angry / tired). Never Unicode emoji
- Signature move: 4-panel comic in a 2×2 grid, 6px gutters, screentoned sky/ground, `01–04` Anton page numbers in the corners
- Signature move: Body opens with a red Anton drop-cap on the first character (Latin or CJK)
- Signature move: Yellow `NEW!` / `FIN.` rotated stickers (4–8°)
- Signature move: Bilingual eyebrows — every chrome label reads `中文 / ENGLISH`

## International / CJK Preview Note

- CJK-first by design. The magazine voice mixes Japanese (`日記マガジン`, `第 07 話`, `ふきだし`) into Chinese chrome — this is intentional editorial flavor and should be preserved.
- Pair Anton/Bebas (Latin) with Noto Sans SC 900 (CJK). Anton must be preloaded — fallback to system geometric sans breaks the masthead weight.
- No italic mode. Emphasis = weight (900), color (red/yellow span), or skew (red banner).
- Full-width Chinese punctuation in body; half-width inside Latin eyebrows.
- Drop cap is usually a Latin or numeric Anton character — pair with the masthead voice.

## Preview Rules

- Build exactly one title screen at the product's canonical canvas (phone-portrait, e.g. 393×852, inside an iOS frame with the WeChat top capsule).
- Newsprint `#F4EFE3` background must carry the 8%-opacity screentone overlay. Flat cream is not this system.
- Every preview includes the masthead (red `DIARY MAG / 日記マガジン` skewed banner + 2.5px rule + `VOL.0X` + 月号 + sub-issue).
- Use the user's real product title/subtitle/context; do not copy demo content (`初春的拿铁` is a demo phrase, not real content).
- The MangaMood SVG faces — not emoji — must render for any mood indicator.
- Never place internal workflow text on the screen: no `preview`, `template`, `Option A/B/C`, file names, paths, or source-doc labels.
- Never place the system codename (`manga-jump`) on the screen itself.
- After the team picks this system for the full build, read the full `design.md` before generating final screens, the comic-generation pipeline, or Figma library entries.
