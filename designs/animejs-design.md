# Design System Inspired by Anime.js (V4)

## 1. Visual Theme & Atmosphere

Anime.js is Julian Garnier's JavaScript animation engine — one of the most-starred open-source libraries on GitHub — and its V4 website is a masterclass in developer-documentation design done with genuine artistic conviction. The philosophy is "the demo _is_ the documentation." Every section of the page is alive: squares rotate, paths draw themselves, dots stagger in grids, springs bounce, SVG shapes morph. The site proves its own thesis by being an animated experience, not just a description of one.

The visual language is deep-dark with a warm, ember-like accent. The background is a rich near-black with a faint cool undertone — not pure black, not cold charcoal, but something that reads as a dark studio or dark room environment. Against this, a bold orange-to-pink accent (`#FF4E4E` family, warm coral-red range) burns with deliberate heat. It signals energy, motion, and creative confidence without tipping into aggression. The accent is used sparingly — on interactive demo elements, the live animation targets, CTAs, and the logo mark — so when it appears, it commands full attention.

Code is first-class content. Syntax-highlighted JavaScript blocks appear throughout the page as the primary vehicle for communicating feature ideas — not as an afterthought but as the main event, displayed at generous size with a custom dark theme that keeps the warmth of the overall palette. Monospaced text and live animation demos are paired side-by-side in a layout reminiscent of a well-designed IDE or REPL: code on one side, live result on the other.

Typography is clean and functional — a grotesque sans-serif for prose and UI, a premium monospaced font for all code. There are no decorative flourishes. All hierarchy is established through scale, weight, and the contrast between the prose type and the animated demo elements. The result is a site that feels like it was designed by a developer who also has exquisite taste — technically rigorous, visually warm, joyful in motion.

**Key Characteristics:**

- Deep near-black background with a warm undertone — dark studio, not cold void
- Warm coral-orange accent (`#FF4E4E`–`#FF6B6B` range) as the sole brand color — energetic, not aggressive
- Code blocks as primary content: generous size, custom warm dark syntax theme, prominently featured
- Live animated demos paired with their source code — "demo + code" is the core layout unit
- Monospaced type for all code; clean grotesque for all prose and UI
- Animated demo targets: simple geometric shapes (squares, circles, dots, paths) in accent and neutral tones
- Bundle size meter as a UI component — communicates the library's lightweight philosophy visually
- Motion everywhere, but always purposeful — every animation demonstrates a real API feature
- Minimal navigation chrome: simple top nav, clean footer, attention stays on content

## 2. Color Palette & Roles

### Core Background & Surface

- **Deep Background** (`#0d0d0f` approx.): Primary page background — near-black with a faint cool-dark undertone
- **Surface** (`#161618` approx.): Card surfaces, code block backgrounds, elevated sections
- **Raised Surface** (`#1e1e22` approx.): Hover states, secondary panels, subtle differentiation
- **Border** (`rgba(255, 255, 255, 0.08)`): Subtle dividers between sections and around code blocks

### Accent / Brand

- **Coral Red** (`#FF4E4E`): Primary brand accent — logo mark, primary CTAs, animated demo fill color
- **Warm Orange** (`#FF6B6B`–`#FF8060`): Hover state of accent, gradient companion, demo element highlights
- **Accent Glow** (`rgba(255, 78, 78, 0.15)`): Soft background glow behind key demo elements

### Text

- **Primary Text** (`#EDEDF0`): All body copy and prose — slightly warm off-white
- **Secondary Text** (`#8B8B9A`): Muted descriptions, metadata, nav items, sidebar labels
- **Tertiary Text / Placeholder** (`rgba(255,255,255,0.3)`): Inactive states, very soft labels
- **Code Text Base** (`#E0E0E8`): Default code text in blocks

### Syntax Highlighting (Code Blocks)

The syntax theme is warm-dark, harmonized with the page palette:

- **Keywords** (`#FF6B6B`–`#FF4E4E`): `import`, `const`, `animate`, function names — warm coral, matching the brand accent
- **Strings** (`#98D982`–`#8BC88B`): String values — muted green, pleasant contrast
- **Numbers / Values** (`#F0A96B`–`#E8965A`): Numeric animation values — warm amber-orange
- **Properties / Params** (`#85C1E9`–`#79B8F3`): Object keys, parameters — cool blue, readable contrast
- **Comments** (`rgba(255,255,255,0.25)`): Inline comments — ghosted, not distracting
- **Punctuation** (`#888896`): Brackets, colons, semicolons — neutral mid-gray

### Semantic / Functional

- **Success / Live State** (`#6BCB77`): "Live" indicators, positive feedback on demos
- **Demo Shape Fill** (`#FF4E4E`): Animated squares, circles, and paths in demo areas
- **Demo Shape Neutral** (`rgba(255,255,255,0.15)`): Inactive demo targets, un-animated state

## 3. Typography Rules

### Font Families

- **UI / Prose**: Clean grotesque sans-serif — visually consistent with **Inter** or **DM Sans**. Weight range 400–700. Used for all body text, navigation, section headings, and feature descriptions.
- **Code / Monospaced**: Premium developer monospace — consistent with **JetBrains Mono**, **Fira Code**, or **Geist Mono**. Used for all code blocks, npm install snippets, API parameter names, and technical labels. Supports ligatures (e.g., `=>`, `===`).
- **Logo / Wordmark**: The "anime.js" logotype uses a custom or tightly tracked sans-serif, paired with a circle-slash mark in the coral accent.

### Hierarchy

| Role               | Size            | Weight | Line Height | Letter Spacing | Notes                              |
| ------------------ | --------------- | ------ | ----------- | -------------- | ---------------------------------- |
| Hero Headline      | 3rem–4.5rem     | 700    | 1.1         | -0.02em        | "All-in-one animation engine."     |
| Section Heading    | 1.75rem–2.25rem | 700    | 1.2         | -0.01em        | Feature section titles             |
| Feature Subtitle   | 1rem–1.1rem     | 600    | 1.4         | 0              | Under section headings             |
| Body / Description | 0.95rem–1rem    | 400    | 1.65        | 0              | Feature explanations, prose        |
| Nav Item           | 0.875rem        | 500    | 1.0         | 0.01em         | "Docs", "Easings", "Learn"         |
| Code (display)     | 0.85rem–0.95rem | 400    | 1.6         | 0              | Code blocks on homepage            |
| Code (inline)      | 0.875em         | 400    | inherit     | 0              | Inline `code` references in prose  |
| Feature Bullet     | 0.875rem        | 400    | 1.5         | 0              | Feature sub-points under headings  |
| Bundle Label       | 0.75rem         | 500    | 1.2         | 0.05em         | Module size labels in bundle chart |
| Footer / Small     | 0.8rem          | 400    | 1.5         | 0              | Copyright, footer nav              |
| Version Badge      | 0.7rem          | 600    | 1.0         | 0.05em         | "4.0.0" pill badge in nav          |

### Principles

- **Two-font discipline**: Grotesque for all prose, monospace for all code — these two worlds never mix. A body paragraph never goes monospace; a code block never uses the UI font.
- **Weight-based hierarchy**: Headings run at 700; body at 400. The 600 weight appears only in subtitles and secondary labels. No mid-weight heading confusion.
- **Tight tracking on large headings**: Hero and section headings use negative letter-spacing (-0.01em to -0.02em) for a crisp, confident feel at large sizes.
- **Code at readable sizes**: Code blocks are never micro-sized — they display at 0.85rem–0.95rem with generous line-height (1.6) so the syntax colors can breathe. Code is content, not a footnote.
- **Ligatures enabled on monospace**: `=>`, `!==`, `===`, `>=` render as proper ligatures where the font supports them.

## 4. Component Stylings

### Navigation

- Background: transparent on scroll start; `rgba(13,13,15,0.9)` + `backdrop-filter: blur(12px)` on scroll
- Logo: left-aligned, "anime.js" wordmark with circular accent mark in coral red
- Version selector: pill badge showing current version ("4.0.0"), secondary versions ("3.2.2", "2.1.0") in smaller muted text — inline, clickable
- Nav links: 0.875rem, weight 500, `#8B8B9A` muted default, `#EDEDF0` on hover; no underline, no background
- Right side: "GitHub" and "Sponsor" links — text only, muted
- No border on nav bar; sticky with blur once user scrolls past hero

### Hero Section

- Full-width, generous vertical padding (120px–160px)
- Headline: "All-in-one animation engine." — 3.5rem–4.5rem, 700 weight, `#EDEDF0`
- Subheadline: "A fast and flexible JavaScript library to animate the web." — 1.1rem, 400 weight, `#8B8B9A`, max-width ~480px
- npm install block: inline code block — `npm i animejs` — monospaced, dark pill background `#1e1e22`, 1px border `rgba(255,255,255,0.08)`, copy button on hover
- CTA: "Learn more" — text link with arrow, `#EDEDF0`, no button fill
- Background: optional subtle radial gradient glow in `rgba(255,78,78,0.04)` centered behind headline

### Feature Sections ("Demo + Code" Units)

The core repeating layout pattern of the site:

- Two-column layout: animated demo on the left (or right), code block on the right (or left)
- Demo area: dark surface `#161618`, rounded corners (12px–16px), contains live looping animation
- Animated targets: simple shapes (`.square`, `.circle`, `.dot`) filled with `#FF4E4E` or neutral `rgba(255,255,255,0.15)`
- Code block: same dark surface, syntax-highlighted, monospaced, no line numbers (clean)
- Section heading: above the two-column unit, 2rem, 700, `#EDEDF0`
- Feature bullets: below heading, 3 sub-points with `→` or `·` prefix, 0.875rem, `#8B8B9A`
- Divider between sections: `1px solid rgba(255,255,255,0.06)` horizontal rule or just generous vertical spacing (80px–120px)

### Code Blocks

- Background: `#161618` or `#1a1a1f`
- Border: `1px solid rgba(255,255,255,0.08)`
- Border-radius: 10px–12px
- Padding: 20px–24px
- Font: monospaced, 0.875rem–0.9rem, line-height 1.65
- Syntax theme: warm-dark (see Color Palette › Syntax Highlighting section)
- Copy button: appears on hover, top-right corner, icon only, `rgba(255,255,255,0.4)` default → `rgba(255,255,255,0.9)` hover
- No line numbers on homepage demos — clean, distraction-free

### npm Install Snippet

- Inline pill: background `#1e1e22`, 1px border `rgba(255,255,255,0.1)`, border-radius 8px
- Padding: 10px 16px
- Font: monospaced, 0.875rem, `#EDEDF0`
- Copy icon: right side, `#8B8B9A`, hover → `#EDEDF0`

### Bundle Size Visualizer

- Horizontal stacked bar chart showing total bundle size (24.50 KB) broken into modules
- Each module: label + size + proportional bar segment
- Bar segments: coral accent for primary module, graduated to cooler tones for smaller modules
- Typography: monospace for sizes, grotesque for module names
- Communicates the "lightweight and modular" philosophy visually — this is a designed data visualization, not just a table

### Version Selector Pill

- Inline pill with version numbers: "4.0.0" (primary, white) / "3.2.2" / "2.1.0" (muted, clickable)
- Background: `rgba(255,255,255,0.06)`, border-radius 9999px
- Padding: 3px 10px
- Current version: `#EDEDF0`, weight 600; older versions: `#8B8B9A`, weight 400
- Appears in the nav bar next to the logo

### Sponsor Cards

- Grid of sponsor logos on dark surface tiles
- Background: `#1e1e22`, border: `1px solid rgba(255,255,255,0.06)`, border-radius 10px
- Padding: 16px 24px
- Logos: white/mono versions of sponsor marks
- "Become a sponsor" CTA: outlined button, `1px solid rgba(255,255,255,0.2)`, no fill, `#EDEDF0` text

### Buttons / CTAs

- Primary: coral fill `#FF4E4E`, `#000000` or `#EDEDF0` text, border-radius 6px–8px, padding 10px 20px, weight 600
- Secondary / Outlined: `1px solid rgba(255,255,255,0.2)`, transparent background, `#EDEDF0` text
- Ghost / Text link: no border, no background, `#8B8B9A` default → `#EDEDF0` hover, optional `→` arrow
- No pill shapes on content buttons — only on version badges and small utility elements

## 5. Layout Principles

### Spacing System

- Base unit: 8px
- Scale: 4, 8, 12, 16, 24, 32, 48, 64, 80, 96, 120, 160px
- Section vertical gap: 80px–120px between feature sections
- Hero padding: 120px–160px top
- Feature demo padding: 24px–32px internal

### Grid & Structure

- Max content width: 1100px–1200px, centered
- Horizontal page padding: 24px (mobile) → 48px (tablet) → auto with max-width (desktop)
- Feature sections: 2-column CSS grid — `1fr 1fr` split between demo and code block
- Some sections: single-column centered (intro, bundle visualizer, sponsor section)
- Documentation sidebar (on /documentation): fixed left sidebar (~240px) + scrollable content area

### Whitespace Philosophy

- **Breathing room around demos**: Each feature demo gets generous padding — it is a stage for a live animation, not a cramped content block.
- **Section gaps as narrative pacing**: The 80px–120px gaps between sections aren't just spacing — they act as visual pauses between demonstrations, like page turns in a book.
- **Code deserves space**: Code blocks are never squeezed. They have comfortable internal padding and generous line-height so the syntax colors can be read comfortably.

### Border Radius Scale

- 4px: Inline code pills, small badges
- 6px–8px: Buttons
- 10px–12px: Code blocks, demo containers, cards
- 16px: Larger panels, modal-sized elements
- 9999px: Version selector pill, utility badges only — used very sparingly

## 6. Depth & Elevation

| Level             | Treatment                                            | Use                                                 |
| ----------------- | ---------------------------------------------------- | --------------------------------------------------- |
| Base (Level 0)    | `#0d0d0f`                                            | Page background                                     |
| Surface (Level 1) | `#161618`                                            | Code blocks, demo areas, cards                      |
| Raised (Level 2)  | `#1e1e22`                                            | Hover states, npm snippet background, sponsor tiles |
| Focus (Level 3)   | `1px solid rgba(255,255,255,0.12)` + Level 2 bg      | Active/focused code blocks or interactive panels    |
| Glow (Accent)     | `rgba(255,78,78,0.08)–0.15` radial                   | Behind hero headline, around primary CTA            |
| Nav (Floating)    | `rgba(13,13,15,0.9)` + `backdrop-filter: blur(12px)` | Sticky nav after scroll                             |

**Shadow Philosophy**: Anime.js uses almost no drop shadows. Depth is created through background color stepping (each level is a slightly lighter dark) and through the contrast between the glowing animated elements and their dark containers. A subtle box-shadow (`0 1px 0 rgba(255,255,255,0.04)` on top of cards, `0 4px 24px rgba(0,0,0,0.3)` for elevated panels) appears rarely, and only to reinforce a meaningful elevation difference.

## 7. Do's and Don'ts

### Do

- Use `#0d0d0f` as the base — warm-dark, not pure black, giving the coral accent room to breathe
- Apply coral red (`#FF4E4E`) exclusively to interactive demos, animated targets, logo, and primary CTAs
- Feature code blocks at full size with the warm-dark syntax theme — code is a first-class visual element
- Use the "demo + code" two-column unit as the primary layout pattern for every feature section
- Keep animated demo targets as simple geometric primitives (squares, circles, dots, paths) — simplicity makes the animation the star
- Pair every live animation with its actual API code in the adjacent block — always show the source
- Use monospaced type for all code; grotesque for all prose — never mix these two worlds
- Apply negative letter-spacing (-0.01em to -0.02em) on display headings
- Keep border-radius at 10px–12px on demo containers and code blocks — comfortable, not pill-shaped
- Animate entry of page elements using the library itself — dogfood the API

### Don't

- Don't use the coral accent on large background areas — it is an element color, not a surface color
- Don't use filled coral buttons for every CTA — reserve the filled style for the single highest-priority action
- Don't use rounded-full / pill shapes on content containers or buttons — reserved for small utility badges only
- Don't show code without a live demo alongside it — the pairing is the identity
- Don't use complex 3D scenes, photography, or illustration — the animated geometric shapes are the visual language
- Don't apply drop shadows liberally — depth comes from background stepping, not shadow stacking
- Don't mix the grotesque and monospace fonts outside their defined roles
- Don't use color in the prose text — all body copy is near-white or muted gray, never colored
- Don't skip syntax highlighting on code blocks — un-highlighted code breaks the warm-dark language
- Don't compress section spacing — the breathing room between demos is part of the pacing

## 8. Responsive Behavior

### Breakpoints

| Breakpoint | Width        | Key Changes                                                                                      |
| ---------- | ------------ | ------------------------------------------------------------------------------------------------ |
| Mobile     | < 640px      | Single column; demo above, code below; hero text ~2.25rem; nav collapses to hamburger or minimal |
| Tablet     | 640px–1024px | 2-column demo+code maintained where possible; slight type scaling                                |
| Desktop    | > 1024px     | Full 2-column grid; sticky sidebar on /documentation; max-width container                        |

### Collapsing Strategy

- Feature "demo + code" units: stack vertically (demo top, code bottom) below 640px
- Demo areas: maintain live animations at all sizes — no static fallbacks; just resize the canvas/container
- Code blocks: horizontal scroll within block on narrow viewports, never wrapping mid-token
- Navigation: top nav simplifies on mobile — links may collapse into a minimal menu; logo and version badge always visible
- Bundle visualizer: collapses to vertical stacked bars on mobile
- Section padding: 80px–120px → 48px–64px on mobile

### Touch Behavior

- All buttons minimum 44×44px tap target
- Draggable API demos: fully touch-compatible (drag, snap, flick)
- Code blocks: tap-to-copy on mobile (no hover reveal)
- Animated demos: play on page load, no interaction required — passive visual showcase

## 9. Agent Prompt Guide

### Quick Color Reference

- Background: `#0d0d0f`
- Surface: `#161618`
- Raised surface: `#1e1e22`
- Primary text: `#EDEDF0`
- Secondary / muted text: `#8B8B9A`
- Accent / brand: `#FF4E4E`
- Accent hover: `#FF6B6B`
- Border: `rgba(255, 255, 255, 0.08)`
- Code keyword: `#FF6B6B`
- Code string: `#8BC88B`
- Code number: `#E8965A`
- Code property: `#79B8F3`

### Quick Type Reference

- Display: grotesque sans, 700, 3.5rem–4.5rem, tracking -0.02em, `#EDEDF0`
- Section heading: grotesque sans, 700, 2rem, tracking -0.01em, `#EDEDF0`
- Body: grotesque sans, 400, 0.95rem–1rem, line-height 1.65, `#8B8B9A`
- Code: monospaced, 400, 0.875rem–0.9rem, line-height 1.6

### Example Component Prompts

- "Create a dark code block: `#161618` background, `1px solid rgba(255,255,255,0.08)` border, 12px radius, 24px padding. Monospaced 0.875rem, line-height 1.6. Keywords in `#FF6B6B`, strings in `#8BC88B`, numbers in `#E8965A`, properties in `#79B8F3`, comments in `rgba(255,255,255,0.25)`, default text `#E0E0E8`."
- "Design a demo + code feature section: two-column grid. Left: `#161618` demo area with 12px radius, 32px padding, containing live animated `.square` elements filled `#FF4E4E`. Right: code block showing the animejs source. Above both: 2rem 700 section heading `#EDEDF0`. Below: 3 feature bullets at 0.875rem `#8B8B9A`."
- "Build a hero section: `#0d0d0f` background, subtle `rgba(255,78,78,0.04)` radial glow centered. Headline 4rem 700 `#EDEDF0` tracking -0.02em. Sub-headline 1rem 400 `#8B8B9A` max-width 480px. Below: npm pill `npm i animejs` — `#1e1e22` background, 8px radius, 1px border `rgba(255,255,255,0.1)`, monospaced 0.875rem `#EDEDF0`."
- "Create a nav bar: transparent default, `rgba(13,13,15,0.9)` + `backdrop-filter: blur(12px)` on scroll. Left: anime.js logo with `#FF4E4E` circular mark + version pill `rgba(255,255,255,0.06)` background 9999px radius. Right: links at 0.875rem 500 `#8B8B9A`, hover `#EDEDF0`."
- "Design a CTA button pair: Primary — `#FF4E4E` background, `#000000` text, 700 weight, 8px radius, 10px 20px padding, hover brightens to `#FF6B6B`. Secondary — transparent, `1px solid rgba(255,255,255,0.2)`, `#EDEDF0` text, same sizing."
- "Build a sponsor card grid: `#1e1e22` tiles, `1px solid rgba(255,255,255,0.06)` border, 10px radius, 16px 24px padding. White/mono sponsor logo centered. Plus 'Become a sponsor' outlined card: `1px solid rgba(255,255,255,0.15)`, same size, `#8B8B9A` text centered."

### Iteration Guide

1. Start with `#0d0d0f` — the warm near-black that makes coral glow without harshness
2. Apply `#FF4E4E` to exactly three things first: the logo mark, the animated demo shapes, and the primary CTA — build the accent restraint from day one
3. The "demo + code" two-column unit is the atomic design pattern — build it first, then repeat it for every feature
4. Syntax-highlight every code block with the warm-dark theme — un-highlighted code breaks the whole aesthetic
5. Use simple geometric shapes (squares, circles, dots) as demo targets — their simplicity makes the animation readable
6. Monospace for code, grotesque for prose, never mixed — this two-font discipline is the system's backbone
7. Keep border-radius in the 10px–12px range on all containers; 9999px only on tiny utility badges
8. Respect section breathing room (80px–120px) — the gaps are part of the demonstration rhythm
9. Bundle size chart and version selector pill are brand-defining UI components — include them in any documentation page template
10. The site is the demo — if nothing is animated, it isn't finished yet
