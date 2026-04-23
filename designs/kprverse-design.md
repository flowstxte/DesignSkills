# Design System Inspired by KPRverse (by Resn)

## 1. Visual Theme & Atmosphere

KPRverse is the closest the web has come to a living, breathing science-fiction world. Built by Resn and awarded Awwwards Site of the Year 2022, it is the online home of KPR — a Web3 storytelling universe set in "New Eden," a post-apocalyptic stronghold divided between two factions. The design philosophy is "the interface is the world." Every surface, every transition, every interaction communicates that the user has crossed from the web into a metaverse portal.

The aesthetic sits at the precise intersection of futuristic manga/comic-book layouts, military HUD interfaces, and premium concept art cinematics. The background is deep, dark violet-purple — never pure black — and everything emits from that foundation. The primary color, `#6D64A3`, is a desaturated, moody plum: sophisticated, otherworldly, and cinematic. Text and UI elements appear in near-white, while rich concept art illustration — the "tableaux" — provides explosive visual contrast. The result is a site where darkness and color work together: the UI is restrained and grid-based, and the artwork is vibrant and overwhelming.

Typography is driven by ABC Whyte (by Dinamo), a contemporary grotesque with variable-weight and ink-trap settings — the ink traps giving letter joints a precise, slightly mechanical quality that anchors the futuristic tone. Headlines are ultrabold and large-scale; body text is minimal and readable. Layout is inspired by poster composition and manga panel grids: strong horizontal rules, deliberate asymmetry, large areas of controlled white space punctuated by full-bleed 3D imagery. Motion is the defining experience layer — GSAP-driven scroll animations, WebGL 3D character reveals, click-and-hold interactive panels, and a progressive gradient logo reveal all communicate that this is a living world, not a static page.

**Key Characteristics:**

- Deep violet-purple (`#6D64A3`) as the sole brand color — the color of the world, not an accent
- ABC Whyte (Dinamo) with variable ink-trap settings — the typographic signature
- Manga/poster grid layouts: strong rules, asymmetry, white space used as a weapon
- WebGL 3D characters and concept art tableaux as the primary visual content
- Click-and-hold interaction as a core narrative mechanic (revealing hidden world layers)
- Full-screen scroll-linked scene reveals — each section is a cinematic "tableau"
- Loader/logo reveal as a branded experience using sprite sheets and SDFs
- Minimal, restrained UI chrome — the interface recedes so the world can expand
- Monochromatic purple palette: the UI is achromatic except for a single plum hue

## 2. Color Palette & Roles

### Primary Brand

- **Plum Violet** (`#6D64A3`): The sole brand color — backgrounds, glows, tinted overlays, and all surface color
- **Deep Purple-Black** (`#0D0B1A` approx.): Darkest background layer — near-black with a violet undertone
- **Dark Surface** (`#1A1728` approx.): Cards, panels, navigation surface
- **Mid Purple** (`#2E2850` approx.): Elevated panels, secondary surfaces, hover states

### Text

- **Near White** (`#F0EEFF`): Primary text on dark surfaces — slightly warm/purple-tinted white
- **Muted Lavender** (`#9B96C4`): Secondary text, labels, inactive navigation items
- **Pure White** (`#FFFFFF`): Maximum-contrast text, loader reveals, key callouts

### Semantic

- **Glow Purple** (`rgba(109, 100, 163, 0.4)`): Ambient glow effects on interactive elements
- **Panel Border** (`rgba(240, 238, 255, 0.12)`): Subtle borders on cards and panels — white at very low opacity
- **Overlay Dark** (`rgba(13, 11, 26, 0.75)`): Scrim over full-bleed artwork for text legibility
- **Tableau Ink** (concept art): Rich full-spectrum illustration color — blues, pinks, ochres — appearing only within the artwork scenes, never as UI color

### Shadows & Glows

- **Ambient Glow** (`0 0 60px rgba(109,100,163,0.5)`): Behind interactive 3D elements
- **Panel Shadow** (`0 8px 40px rgba(0,0,0,0.6)`): Elevated interactive panels
- **Inset Rule** (`rgba(240,238,255,0.08)`): Ultra-subtle inset dividers between sections

### Philosophy

KPRverse operates on a **single-hue monochromatic system**. The world is purple; the only color variation comes from the concept art. No greens, no oranges, no reds appear in the UI itself. All UI differentiation — active vs inactive, surface vs background, foreground vs border — is achieved through lightness and opacity steps on the same violet hue.

## 3. Typography Rules

### Font Families

- **Primary (Display & Body)**: ABC Whyte / ABC Whyte Inktrap — variable grotesque with ink trap settings, by Dinamo. The ink traps (angular cutouts at stroke joints) give the letterforms a precision-engineered, slightly mechanical quality. Variable weight axis used: lighter weights for body, maximum weight for display.
- **Fallback stack**: `"Helvetica Neue", "Arial", sans-serif` — preserves the clean grotesque character.
- **Monospaced / HUD labels**: `"JetBrains Mono", "Courier New", monospace` — used sparingly for console-style labels, coordinates, and system-status text that evokes an in-world interface terminal.

### Hierarchy

| Role             | Size             | Weight             | Line Height | Letter Spacing | Transform  | Notes                         |
| ---------------- | ---------------- | ------------------ | ----------- | -------------- | ---------- | ----------------------------- |
| Hero / Logotype  | 8vw–12vw         | 900 (max ink trap) | 0.85–0.9    | -0.04em        | Uppercase  | SDF-rendered, gradient reveal |
| Section Headline | 4rem–6rem        | 800–900            | 0.9–1.0     | -0.03em        | Uppercase  | Manga-panel scale             |
| Tableau Title    | 2rem–3.5rem      | 700                | 1.05        | -0.02em        | Mixed case | Over concept art              |
| Navigation       | 0.75rem–0.875rem | 500                | 1.0         | 0.12em         | Uppercase  | Minimal chrome nav            |
| Body             | 0.9rem–1.05rem   | 400                | 1.65        | 0              | Mixed case | Whyte Regular                 |
| HUD Label        | 0.65rem–0.75rem  | 400                | 1.2         | 0.2em          | Uppercase  | Monospaced, console-style     |
| Caption / Tag    | 0.7rem           | 500                | 1.4         | 0.15em         | Uppercase  | Category badges               |
| Footer           | 0.75rem          | 400                | 1.6         | 0.05em         | Mixed case | Address, contact              |

### Principles

- **Ink traps as identity**: The ink-trap setting on ABC Whyte is not decorative — at large sizes, the angular cuts at letter joints become visible and communicate technological precision. Use variable font `font-variation-settings: 'wdth' 100, 'wght' 900` at display sizes to maximize this effect.
- **Bold/light binary**: Display text runs at maximum weight (800–900); body text runs at Regular (400). There are very few mid-weight stops — this extreme contrast between weights drives all typographic hierarchy.
- **Uppercase as architecture**: Every headline, navigation item, and label is uppercase. Mixed case is for body paragraphs only.
- **HUD monospace as world-building**: Monospaced labels styled as coordinate readouts or system logs ground the UI in its sci-fi world, implying the user is viewing a real interface from within the KPR universe.

## 4. Component Stylings

### Navigation (Persistent)

- Background: `rgba(13, 11, 26, 0.85)` — translucent dark, blurred backdrop
- Logo: top-left, ABC Whyte, max weight, near-white, uppercase
- Nav links: top-right, uppercase 0.8rem, weight 500, `#9B96C4` inactive, `#F0EEFF` active
- No border on nav itself; a 1px bottom rule in `rgba(240,238,255,0.08)` optional
- Hover: opacity shifts from 0.5 → 1.0 on link text
- No background fill on hover — opacity only

### Loader / Intro Reveal

- Full-screen takeover: `#0D0B1A` background
- KPR logotype appears via **progressive gradient reveal** (sprite sheet + SDF morphing)
- Gradient on logo: diagonal sweep from muted lavender → near-white → plum violet
- Surrounding elements "bleed" and morph via SDF technique during reveal
- Duration: 2.5–4 seconds, no skip option
- After reveal: smooth crossfade into hero section

### Interactive Tableaux (Core Section Panels)

- Full-viewport-width panels with concept art illustration as background
- Overlay: `rgba(13, 11, 26, 0.4)` — just enough to keep text readable
- 3D WebGL character composited on top of 2D art
- Section title: 4rem–6rem, max weight, uppercase, near-white, top or bottom anchor
- Scroll-triggered parallax: art moves at a different rate than type
- "Click-and-Hold" zones: cursor changes on hover, pressed state reveals a second scene layer via stencil buffer masking

### Click-and-Hold Panel (Second Layer)

- Activated by sustained press on a designated zone
- Reveals a new scene underneath via WebGL stencil buffer masking
- Panel frame: thin 1px rule in `rgba(240,238,255,0.25)` — like a viewport window
- Content inside: HUD-style labels, coordinates, world lore, micro-illustrations
- CSS transforms only for positioning (no heavy JS layout) — performance-first
- Release: smooth transition back to primary scene

### Cards / Info Panels

- Background: `#1A1728` or `rgba(109, 100, 163, 0.1)` tinted glass panel
- Border: 1px solid `rgba(240, 238, 255, 0.12)` — hairline white
- Radius: 2px–4px maximum — very slight, nearly rectilinear
- Padding: 24px–32px
- Shadow: `0 8px 40px rgba(0,0,0,0.6)`
- Hover: background brightens slightly, border opacity increases to 0.25

### Buttons / CTAs

- Primary: text-only or outlined — no filled background
- Outlined style: 1px solid `rgba(240,238,255,0.5)`, padding 10px 24px, uppercase, 0.8rem weight 500, letter-spacing 0.12em
- Hover: border opacity → 1.0, subtle ambient glow `0 0 20px rgba(109,100,163,0.4)`
- No pill/rounded shapes — 2px radius maximum
- Text CTA (inline): `#F0EEFF`, underline on hover, no border

### HUD / Console Labels

- Font: monospaced, uppercase, 0.65rem–0.7rem
- Color: `#9B96C4` (muted lavender) or `rgba(240,238,255,0.5)`
- Character: coordinate-style ("X: 448.2 / Y: 192.6"), status labels ("SECTOR 04 // ACTIVE")
- Used as section numbers, location identifiers, lore callouts
- No background — appears as floating terminal text over dark surfaces

## 5. Layout Principles

### Spacing System

- Base unit: 8px
- Scale: 8, 16, 24, 32, 48, 64, 80, 96, 128, 160, 240px
- Section padding: 80px–160px vertical
- Content max-width: 1280px–1440px, centered
- Horizontal gutter: 48px–80px on desktop

### Grid & Structure

- Inspired by **manga panel grids and futuristic poster composition**: strong horizontal rules, deliberate asymmetry between text and image zones
- Full-bleed tableaux sections break the container — 100vw artwork with contained typography
- Sections separated by thick horizontal rules (2px–3px, `rgba(240,238,255,0.15)`) rather than whitespace gaps alone
- Column layout: varies per section — no single global grid. Each section is a bespoke composition.
- Negative space is structural: large voids of dark purple between content clusters create cinematic breathing room

### Whitespace Philosophy

- **Space as world-building**: Long stretches of dark violet with no content communicate vastness — the emptiness of New Eden. Whitespace is not padding; it is narrative.
- **Grid lines over fills**: Horizontal rules define section boundaries rather than background color changes.

### Border Radius Scale

- 0px: Horizontal rules, dividers, hero frames
- 2px: Buttons, card corners
- 4px: Modals, large panels
- **No pill shapes. No 50% radius. No rounded-full buttons** — the geometry is rectilinear and architectural throughout.

## 6. Depth & Elevation

| Level                 | Treatment                                        | Use                                        |
| --------------------- | ------------------------------------------------ | ------------------------------------------ |
| Base (Level 0)        | `#0D0B1A` — deep violet-black                    | Page background, deepest layer             |
| Surface (Level 1)     | `#1A1728` or `rgba(109,100,163,0.08)`            | Panels, cards, nav                         |
| Artwork (Level 2)     | Full-bleed concept art illustration              | Tableau sections — visually dominant       |
| WebGL 3D (Level 3)    | Composited on top of artwork                     | Characters, interactive 3D objects         |
| HUD Overlay (Level 4) | `rgba(13,11,26,0.75)` scrim + white text         | Click-and-hold second layer                |
| Glow (Ambient)        | `0 0 60px rgba(109,100,163,0.5)`                 | Around 3D characters, interactive elements |
| Dialog / Modal        | `0 8px 40px rgba(0,0,0,0.6)` + `#1A1728` surface | Informational overlays                     |

**Shadow Philosophy**: KPRverse uses glow over shadow. On a dark background, box-shadows from light sources don't read — instead, luminous `rgba` glows around key elements communicate elevation and interactivity. The 3D WebGL characters have a purple ambient rim light that bleeds onto the background, reinforcing their presence in the scene.

## 7. Do's and Don'ts

### Do

- Use `#6D64A3` and its opacity/lightness variants as the entire UI color system
- Apply ABC Whyte at maximum weight for all display typography — use variable font ink trap at full depth
- Set all headings and labels to uppercase; reserve mixed case for body paragraphs only
- Use full-viewport-width "tableau" sections as the primary layout unit
- Apply WebGL 3D elements composited over 2D concept art for hero and section reveals
- Use click-and-hold as an interaction pattern for revealing layered world information
- Let dark violet empty space dominate between content sections — the void is the design
- Apply monospaced HUD labels (coordinates, status text) for in-world UI system elements
- Use glow effects (`rgba` ambient light) instead of hard drop shadows for elevation
- Keep border-radius minimal (0–4px) — rectilinear geometry is core to the identity

### Don't

- Don't introduce non-purple accent colors in UI elements — only concept art contains other hues
- Don't use filled/colored button backgrounds — buttons are outlined or text-only
- Don't use pill shapes or high border-radius on any interactive element
- Don't use hard drop shadows — on dark surfaces they're invisible and the wrong language; use glows
- Don't apply the concept art's color palette (blues, pinks, ochres) to UI chrome
- Don't compress vertical spacing — dense layout destroys the cinematic breathing room
- Don't use light-mode surfaces — the entire experience lives in deep dark violet
- Don't use regular-weight text at display sizes — max weight is required for the typographic impact
- Don't use generic icons or UI ornaments — all visual elements should feel world-specific
- Don't reduce the loader experience — the reveal sequence is a brand ritual, not a loading screen

## 8. Responsive Behavior

### Breakpoints

| Breakpoint      | Width         | Key Changes                                                                          |
| --------------- | ------------- | ------------------------------------------------------------------------------------ |
| Mobile Portrait | < 640px       | Single column; display type 14vw–18vw; WebGL replaced with static concept art stills |
| Tablet          | 640px–1024px  | Reduced 3D complexity; display type ~8vw–10vw; stacked tableau sections              |
| Desktop         | 1024px–1440px | Full layout; WebGL active; multi-column compositions                                 |
| Wide            | > 1440px      | Max-width container; artwork remains full-bleed                                      |

### Collapsing Strategy

- **Landscape mobile**: Explicitly blocked — site shows "resolution not supported, please rotate to portrait" message. This is intentional — the WebGL experience cannot be properly delivered in landscape on small screens.
- WebGL 3D scenes: hidden on mobile, replaced by high-res static PNG exports of concept art
- Click-and-hold interaction: converted to tap-and-hold on touch; panels still accessible
- Navigation: collapses to mobile-friendly overlay menu
- Section type: viewport-relative `vw` units ensure automatic scaling across breakpoints
- HUD labels: hidden on mobile to reduce information density
- Tableau sections: maintain full-bleed width; text repositions from overlay to below

### Touch Behavior

- Minimum tap target: 48×48px
- Click-and-hold → tap-and-hold (sustained touch, 400ms threshold)
- Parallax scroll effects converted to simple scroll reveals on mobile (no gyroscope)
- No hover states on touch — only press/tap states

## 9. Agent Prompt Guide

### Quick Color Reference

- Background (deepest): `#0D0B1A`
- Surface: `#1A1728`
- Brand / accent: `#6D64A3`
- Primary text: `#F0EEFF`
- Secondary text / muted: `#9B96C4`
- Panel border: `rgba(240, 238, 255, 0.12)`
- Glow: `rgba(109, 100, 163, 0.5)`

### Quick Type Reference

- Display: ABC Whyte Inktrap, uppercase, weight 900, size 5vw–12vw, tracking -0.04em, line-height 0.9
- Body: ABC Whyte, mixed case, weight 400, 0.9rem–1rem, tracking 0, line-height 1.65
- HUD: monospaced, uppercase, 0.65rem, tracking 0.2em
- Nav: ABC Whyte, uppercase, 0.8rem, weight 500, tracking 0.12em

### Example Component Prompts

- "Create a hero section: `#0D0B1A` background, full-bleed concept art illustration behind a `rgba(13,11,26,0.4)` overlay. Centered headline at 10vw, ABC Whyte Inktrap weight 900, uppercase, `#F0EEFF`, letter-spacing -0.04em, line-height 0.9. Below: 0.95rem body text in mixed case, max-width 560px."
- "Design a navigation bar: translucent `rgba(13,11,26,0.85)` background, backdrop-blur 12px. Logo top-left, max-weight uppercase white. Nav links top-right: 0.8rem uppercase weight 500 `#9B96C4`, hover → `#F0EEFF`. 1px bottom border `rgba(240,238,255,0.08)`."
- "Build an info card: `#1A1728` background, 1px border `rgba(240,238,255,0.12)`, 2px radius, 28px padding, shadow `0 8px 40px rgba(0,0,0,0.6)`. Title: 1.5rem weight 700 uppercase `#F0EEFF`. Body: 0.9rem weight 400 `#9B96C4`. HUD label above title: monospaced 0.65rem uppercase `rgba(240,238,255,0.5)` letter-spacing 0.2em."
- "Create an outlined CTA button: transparent background, 1px solid `rgba(240,238,255,0.5)` border, 2px radius, 10px 24px padding, uppercase 0.8rem weight 500 `#F0EEFF`, letter-spacing 0.12em. Hover: border opacity 1.0, box-shadow `0 0 20px rgba(109,100,163,0.4)`."
- "Design a HUD status label: monospaced uppercase 0.65rem `rgba(240,238,255,0.5)`, letter-spacing 0.2em. Content: 'SECTOR 04 // ACTIVE — X: 448.2 / Y: 192.6'. No border, no background. Float over dark surface."
- "Create a full-bleed tableau section: 100vw width, 100vh height. Background: concept art illustration. Overlay: `rgba(13,11,26,0.45)`. Bottom-left: HUD label 'THE KEEP // FACTION 01'. Below it: section title 5rem weight 900 uppercase `#F0EEFF`. Right side: 0.9rem body paragraph, `#9B96C4`, max-width 400px."

### Iteration Guide

1. Start with `#0D0B1A` — every surface must have a violet-black undertone, never pure black
2. `#6D64A3` is both the brand color and the ambient light source — it tints surfaces, glows around interactive elements, and colors all opacity overlays
3. ABC Whyte Inktrap at maximum weight for all display text — the ink traps are visible at large sizes and that's the point
4. All uppercase for headings, labels, nav; mixed case for body only
5. Design in full-viewport sections (tableaux) — each section is a scene, not a content block
6. HUD monospaced labels add world credibility — scatter "coordinates" and "status" text at small scale
7. Glow over shadow: `rgba(109,100,163,0.5)` ambient glow communicates elevation, not drop shadows
8. Keep button styles outlined-only or text-only — filled button backgrounds break the premium UI language
9. Border-radius maximum 4px — if it looks rounded, it's wrong
10. Motion is mandatory: scroll-linked reveals, fade-in on enter, parallax on tableaux — a static KPRverse-style layout is incomplete by definition
