# Cosmic Nocturne Preview Card

Use this small file for title-screen previews and template selection only. For final product design, read the full design doc listed below.

## Files

- Full design doc: `design-systems/cosmic-nocturne/design.md`
- Preview card: `design-systems/cosmic-nocturne/preview.md`

## Selection Metadata

- Slug: `cosmic-nocturne`
- Tagline: A dream as a small celestial event — observed from a dark room, with a serif sentence whispered alongside it.
- Mood: reverent, intimate, luminous, archetypal
- Tone: mystical, Jungian, slow, slightly vulnerable
- Formality: medium-high
- Density: spacious
- Scheme: dark
- Audience: 25–45, users with an interest in psychology, archetypes, journaling, slow rituals
- Best for: dream journaling, meditation, journaling apps, astrology, nighttime-only surfaces, vulnerable first-person content, premium reflective tools. Neighbors: Calm, Co-Star, the quieter screens of Headspace.
- Avoid for: playful onboarding, gamified streaks, social/share moments, daytime utility, anything that needs to feel light or celebratory. The serif italic on cosmic dark will read as funereal if used for upbeat content. Do not pair with bright photography or product-marketing UI — the system assumes near-black backgrounds and breaks on white.

## Visual Snapshot

A reverent nighttime system for a dream journal. The product reads as a small celestial event observed from a dark room — deep cosmic indigo grounds, warm gold moonlight, a soft violet nebula behind illustrations, and a romantic italic serif (Cormorant Garamond) carrying every emotional sentence. A second voice — system sans, uppercase, wide-tracked — carries dates, modes, and process labels. Borders are veils (rgba whites at low alpha), shadows are glows, and a faint star field lives behind every dark surface.

Cosmic Nocturne's structural premise is light against dark. Every surface assumes a vignetted radial cosmic background, never flat. Every accent emits a little light — the moon, the halo, the CTA. Italic — not bold — is the serif's only emphasis tool. Each screen has exactly one focal point that emits light; two focal points compete and break the spell.

## Preview Ingredients

- Palette: cosmos radial #2A1A5E → #14102E → #0A0B2E; void #0A0B2E; nebula #A78BFA; moon-gold #FDE68A / #F59E0B; rose-aura #F9A8D4; ink #F5E9FF; stroke-veil rgba(245,233,255,0.08)
- Typography: Cormorant Garamond for everything emotional (display, titles, body, italic accents). Inter / SF Pro uppercase tracked for everything functional (dates, modes, labels). See full design doc.
- Signature move: Two-voice type — Cormorant Garamond (everything emotional) and Inter (everything functional). Never cross-mix.
- Signature move: Italic — not bold — is the serif's emphasis. One or two italicized words inside an otherwise plain sentence is the system's heartbeat.
- Signature move: Moon-gold is always a radial gradient, never a flat fill — it should feel like a real light source.
- Signature move: Star field of 25–50 sub-pixel dots lives behind every dark surface as texture, never decoration.
- Signature move: One focal point per screen (moon, halo, or glowing CTA). Two compete and break the spell.
- Signature move: All borders are stroke-veil (rgba white at 8% alpha). Opaque grays do not exist in the system.

## International / CJK Preview Note

- Cormorant Garamond has no CJK glyphs. Pair with Noto Serif SC 400/500.
- There is no italic Chinese serif on Google Fonts — substitute the italic-accent treatment with color (moon-gold) or weight (500 inside 400) rather than faux-italic.
- Keep CJK letter-spacing at 0; loosen line-height to 1.85–1.95 for Chinese body.
- Keep `text-transform: uppercase` on Latin eyebrows; for Chinese dates use full-width forms (三月十二).
- Insert an ASCII space between adjacent CJK and Latin characters (盘古之白).

## Preview Rules

- Build exactly one title screen at the product's canonical canvas (phone-portrait, e.g. 393×852).
- Preserve the cosmos radial background, star field, type roles, focal-point discipline, and decorative vocabulary described above.
- Use the user's real product title/subtitle/context; do not copy demo content.
- The rendered preview must look like a real first screen of the product, not a template-selection card.
- Never place internal workflow text on the screen: no `preview`, `generated from`, `preview.md`, `template`, `preset`, `style option`, `Option A/B/C`, file names, paths, or source-doc labels.
- Never place the system codename (`cosmic-nocturne`) on the screen itself; mention it only in the chat or document chrome.
- Use only real product content for visible chrome: product name, real screen title, date, page indicator, or genuine content phrases.
- After the team picks this system for the full build, read the full `design.md` before generating final screens, components, or Figma library entries.
