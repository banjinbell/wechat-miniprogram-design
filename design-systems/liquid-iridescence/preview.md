# Liquid Iridescence — Preview Card

Use this small file for title-screen previews and template selection only. For final product design, read the full design doc listed below.

## Files

- Full design doc: `design-systems/liquid-iridescence/design.md`
- Preview card: `design-systems/liquid-iridescence/preview.md`

## Selection Metadata

- Slug: `liquid-iridescence`
- Tagline: Dreams as creative material. Loud, saturated, generationally now — a CD's surface in motion under a black light.
- Mood: vibrant, expressive, shareable, current
- Tone: curious, poetic, semiotic, never clinical
- Formality: low
- Density: medium-high (data-friendly)
- Scheme: dark with saturated color
- Audience: 18–35, social-native, lucid-dreaming / consciousness-exploration framings
- Best for: social/share-heavy surfaces, premium tier signaling, lucid-dream features, marketing screens, Spotify-Wrapped-style year-in-review moments. Neighbors: Linear marketing, Spotify Wrapped, Arc Browser, Bambu Labs, "tech with feeling" wave.
- Avoid for: therapeutic surfaces, audiences over 50, moments of distress, surfaces where the product should disappear behind the content. The system has high visual ego.

## Visual Snapshot

A loud, saturated, generationally-now system. Dreams treated as creative material instead of sacred ritual. Surfaces are deep purple-black voids painted by 2–4 soft color blobs (pink, cyan, amber, violet) blurred at 50–80px and screen-blended where they overlap. Containers are glass-fill — 4% white + 10% stroke + 12px backdrop-blur, never solid. Type pairs Instrument Serif Italic (romantic display, gradient text) with Space Grotesk (current, technical body and labels). The signature iris gradient (135° pink→amber→cyan) appears only as: brand mark, gradient text on one display word, or a 2px border on the single featured card per screen. Depth is blur and glow — never hard shadow.

## Preview Ingredients

- Palette: midnight #1A0A3E → #0D0820; pink #FF6BD6; cyan #5EEAD4; amber #FFB86B; violet #B794F6; iris linear-gradient(135deg, #FF6BD6, #FFB86B, #5EEAD4); ink #FEF5FF
- Typography: Instrument Serif Italic (display, titles, ledes — one gradient word per title) + Space Grotesk (body, labels, uppercase tag chips). Mix Chinese serif italic and Latin grotesk on the same line freely.
- Signature move: One gradient-text word per display title, never two.
- Signature move: 2–4 large blurred color blobs behind every screen, bleeding off-screen, screen-blend at overlaps.
- Signature move: Every container is glass-fill (4% white + 10% stroke + 12px backdrop-blur). Never solid.
- Signature move: Exactly one featured card per screen with an iris-gradient 2px border.
- Signature move: Floating 68px round iris CTA at bottom-center. No persistent tab bar.
- Signature move: Every chart bar is a gradient; flat fills do not exist.

## International / CJK Preview Note

- Instrument Serif has no CJK; pair with Noto Serif SC 500. No italic Chinese serif exists — substitute italic with gradient-text or weight contrast on that word.
- Drop `text-transform: uppercase` for Chinese tag labels; use Noto Sans SC 600 at 11–12px with no transform.
- Loosen line-height to 1.8 for Chinese body; keep letter-spacing at 0.
- Insert an ASCII space between adjacent CJK and Latin characters.

## Preview Rules

- Build exactly one title screen at the product's canonical canvas (phone-portrait, e.g. 393×852).
- Background must carry 2–4 blurred blobs + glass-fill content layer. A flat dark screen is not this system.
- Use the user's real product title/subtitle/context; do not copy demo content.
- Apply the gradient-text treatment to exactly one display word.
- Never place internal workflow text on the screen: no `preview`, `template`, `Option A/B/C`, file names, paths, or source-doc labels.
- Never place the system codename (`liquid-iridescence`) on the screen itself.
- After the team picks this system for the full build, read the full `design.md` before generating final screens or Figma library entries.
