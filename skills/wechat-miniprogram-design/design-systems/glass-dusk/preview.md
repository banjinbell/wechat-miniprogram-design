# Glass Dusk — Preview Card

Use this small file for title-screen previews and template selection only. For final product design, read the full design doc listed below.

## Files

- Full design doc: `design-systems/glass-dusk/design.md`
- Preview card: `design-systems/glass-dusk/preview.md`

## Selection Metadata

- Slug: `glass-dusk`
- Tagline: A diary that opens onto the sky at golden hour. Frosted glass plates float on a four-stop sunset gradient.
- Mood: atmospheric, intimate, iOS-native, soft golden-hour warmth
- Tone: a friend texting you at golden hour — soft, sensory, quietly observational, never therapy-speak
- Formality: medium-low
- Density: spacious (lots of sky breathing room)
- Scheme: dusk gradient (peach → pink → lilac → dusk-blue)
- Audience: 22–38, evening-diary writers, users primed for Apple Journal / iOS 17 liquid-glass aesthetic
- Best for: evening/end-of-day diaries, gentle self-care products, AI-comic apps where the comic is treated as an emotional artifact rather than a strip, iOS-first mini-programs. Neighbors: Apple Journal, Stoic, Calm's Daily Calm hero, Substack reader, iOS 17 Control Centre.
- Avoid for: daytime productivity, gamification, social-share moments (dark gradient kills screenshots), audiences over 50, anything snappy/transactional. Backdrop-blur usage is heavy — performance budget on older phones is real.

## Visual Snapshot

A four-stop sunset gradient (peach #FFB89A → dusty pink #E89AB8 → lilac #A684D6 → dusk-blue #5D6FBF) full-bleed behind every screen. A 200×200 sun orb floats top-right; a 240×240 violet aura blob blurs bottom-left; 5–8 sub-pixel stars scatter above the sun line. Every container is a frosted-glass plate — 22% white fill, 24px backdrop-blur + 140% saturate, 1px white stroke, ambient violet drop shadow + inset top highlight — that floats on top of the sky. The hero/today card per screen uses the stronger 34%-fill variant. Mood is rendered as 5 translucent gradient beads (`warm/hot/soft/dream/quiet`), each its own micro-palette, each with a soft halo glow; the selected bead grows to 44px with a 1.5px white stroke. The primary CTA is a soft peach→pink→lilac warm gradient pill with a warm-glow shadow, reading as lit from inside. The floating tab bar at the bottom is dark glass (40% ink + 30px blur) with a white pill on the active tab. DM Serif Display italic carries every emotional moment ("March 11," diary titles, intensity labels); Noto Sans SC carries everything functional. White text on sky carries a faint 1px violet shadow; ink color is only used on glass.

## Preview Ingredients

- Sky stops: g1 #FFB89A · g2 #E89AB8 · g3 #A684D6 · g4 #5D6FBF
- Ink: #221836 (deep plum) + 62% / 38% soft variants — used only on glass, never on sky
- Glass: rgba(255,255,255, 0.22 / 0.34) fills, rgba(255,255,255, 0.55) stroke, 24px backdrop-blur + 140% saturate
- Mood beads: warm #FFD79A · hot #FFA68A · soft #E695C8 · dream #A68CDA · quiet #7E9ADB
- Gold: #F5D682 (sun orb, rare hero accent)
- Typography: DM Serif Display Italic (display, dates, titles, emphasis) + Noto Sans SC 400/500/600 (body, eyebrows, labels)
- Signature move: 4-stop dusk gradient, full bleed, never partial
- Signature move: Glass plates everywhere — 22% fill / 24px blur / 1px white stroke / soft drop shadow + inset top highlight
- Signature move: Three atmospheric textures always on — sun orb (top-right), aura blob (bottom-left), 5–8 stars (above sun line)
- Signature move: Mood beads — 5 gradient spheres with halo glow. Active bead grows and brightens
- Signature move: Date motif `March 11,` in DM Serif italic with terminal comma
- Signature move: White text on sky always carries a 1px violet text-shadow; ink color only on glass
- Signature move: Floating dark-glass tab bar with white-pill active state
- Signature move: Primary CTA = warm gradient (peach→pink→lilac) with warm-glow shadow

## International / CJK Preview Note

- Pair DM Serif italic with Noto Serif SC 500. There is no italic Chinese serif on Google Fonts — substitute italic emphasis with weight contrast (Serif 500 inside Sans 400) or color shift (`--gd-soft`).
- The `March 11,` date motif is Latin-only. For all-Chinese builds, render as `三月十一日` in Noto Serif SC 500 — accept the loss of italic motion and trust the gradient + glass to carry the warmth.
- Mood-bead labels are single CJK characters (`暖 · 热 · 柔 · 梦 · 静`) — they pair beautifully with the bead glow.
- Letter-spacing 0 on CJK body; eyebrows tighten from +0.25em (Latin) to +0.15em (CJK).
- Insert ASCII space between adjacent CJK and Latin runs (盘古之白).

## Preview Rules

- Build exactly one title screen at the product's canonical canvas (phone-portrait, e.g. 393×852, inside an iOS frame with the WeChat top capsule).
- Sky background must be the full 4-stop dusk gradient, full bleed. No flat-color regions.
- Sun orb (top-right), aura blob (bottom-left), and 5–8 stars must be present.
- Every container must be a glass plate; never a solid panel.
- White text on sky must carry the 1px violet text-shadow.
- Use the user's real product title/subtitle/context; do not copy demo content (`拿铁里漂着一颗小小的心` is a demo phrase).
- Never place internal workflow text on the screen: no `preview`, `template`, `Option A/B/C`, file names, paths, or source-doc labels.
- Never place the system codename (`glass-dusk`) on the screen itself.
- After the team picks this system for the full build, read the full `design.md` before generating final screens, the comic-generation pipeline, or Figma library entries.
