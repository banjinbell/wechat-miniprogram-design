# Paper Folio — Preview Card

Use this small file for title-screen previews and template selection only. For final product design, read the full design doc listed below.

## Files

- Full design doc: `design-systems/paper-folio/design.md`
- Preview card: `design-systems/paper-folio/preview.md`

## Selection Metadata

- Slug: `paper-folio`
- Tagline: A bound book of plates and notes. Each dream a numbered folio, each interpretation a small essay set in serif.
- Mood: literary, archival, patient, slow
- Tone: formal, slightly archaic, editorial — never therapeutic
- Formality: high
- Density: medium (book-column reading)
- Scheme: warm cream paper
- Audience: 28–55, journal-keepers, readers, stationery buyers, slow-product users
- Best for: dream journaling treated as long-form practice, premium tiers, anniversary/year-in-review books, print/PDF exports, surfaces where retention per session matters more than session frequency. Strongest "premium heirloom" signal of the three systems. Neighbors: Day One, Substack reader, Penguin Classics app, MUBI, Are.na.
- Avoid for: rapid-tap interactions, gamification, social sharing, push-notification heavy moments, anything needing urgency. The system cannot accommodate neon, gradient, or glassmorphism without breaking.

## Visual Snapshot

A bound book pretending to be an app. Each screen is a page with a running head (`VOL. III · NO. 047`) and a signature line. Two serifs only — EB Garamond for body and Cormorant Garamond Italic for display, with sans-serif reserved for micro-labels under 11px. The palette is hand-mixed earth pigments on warm cream paper: rust, ochre, dusty rose, sage. A procedural grain overlay at 40% opacity multiplies over every page — without it the system reads as a flat web design. Illustrations are flat-color Magritte-style plates inside 1.5px ink frames with "Plate I" labels and 4px hard offset shadows. Tags are letterpress stamps at -2 to -4° rotation. Interpretations open with a rust drop cap.

## Preview Ingredients

- Palette: paper #ECE3D0; vellum #F0E6D2; ink #2A221B; ink-mark #1F1A16; rust #A64B2A; ochre #C08A3E; dusty-rose #C98A8A; sage #7A8A6A
- Typography: EB Garamond (body, 16/1.8) + Cormorant Garamond Italic (display, titles, drop caps). Inter only at ≤11px uppercase tracked. JetBrains Mono for running heads.
- Signature move: Every screen has a running head + signature line. The book metaphor is visible at all times.
- Signature move: Every interpretation opens with a 56px rust Cormorant italic drop cap.
- Signature move: Illustrations are framed plates — 1.5px ink hairline + "Plate I" label + 4px paper-lift shadow.
- Signature move: Tags are letterpress stamps with -2 to -4° rotation, 1.5px border, sans micro-label inside.
- Signature move: 40%-opacity multiplied grain overlay on every page. Skipping it collapses the system.
- Signature move: No gradients, no glow, no backdrop-blur — only hard offset shadows and paper texture.

## International / CJK Preview Note

- Pair with Noto Serif SC 400/500. No italic Chinese serif on Google Fonts — substitute italic accents with color swap to rust, weight contrast (500 inside 400), or underline.
- Drop cap works on Chinese — pick a meaningful opening character, render in rust at 56px.
- Drop uppercase + tracking for Chinese stamp chips; use Noto Sans SC 600 at 11–12px with no transform.
- Loosen line-height to 1.9–2.0 for Chinese body.
- Full-width Chinese punctuation in body; insert ASCII space between adjacent CJK and Latin.

## Preview Rules

- Build exactly one title screen / cover page at the product's canonical canvas (phone-portrait, e.g. 393×852).
- Background must be `#ECE3D0` cream with a 40% multiply grain overlay. A flat cream background is not this system.
- Every preview includes a running head (`VOL. III · NO. 0XX`) and a signature line.
- Use the user's real product title/subtitle/context; do not copy demo content.
- If the preview includes an illustration, frame it (1.5px ink hairline, Plate I label, 4px hard offset shadow).
- Never place internal workflow text on the screen: no `preview`, `template`, `Option A/B/C`, file names, paths, or source-doc labels.
- Never place the system codename (`paper-folio`) on the screen itself.
- After the team picks this system for the full build, read the full `design.md` before generating final screens or Figma library entries.
