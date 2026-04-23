# Design System Inspired by Swiss Mono (Studio Mono)

## 1. Visual Theme & Atmosphere

Swiss Mono embodies "typographic brutalism in white space" — a rigorous, Swiss-International-style editorial aesthetic where pure black (`#000000`) and pure white (`#ffffff`) are the only colors, and every design decision flows from strict typographic and spatial discipline. The name says it all: "Swiss" (rooted in the International Typographic Style from Basel and Zurich) and "Mono" (monochrome, singular, restrained). There are no gradients, no shadows, no accent colors. The interface achieves all its hierarchy through scale, weight, spacing, and rhythm alone.

The typeface is the entire identity. Massive, condensed, all-caps display headings — sometimes spanning the full viewport width — command the page like a Neue Haas Grotesk poster. Body text is sparse and functional. The layout uses extreme asymmetry: a single leftward-anchored logo, navigation items floating in the opposite corner, and content that ignores convention to appear at deliberate, unexpected positions. The vertical rhythm of the page is intentional and editorial — long expanses of white, then a sudden collision of oversized type, then imagery, all without decorative padding.

Imagery is exclusively black-and-white photography — desaturated, high-contrast, and subordinate to the type system. The UI dissolves; there is no chrome, no card containers, no buttons with fill. Interactions are revealed through text underlines, subtle hover opacity changes, and the navigation menu expanding to full-screen takeover. Motion is minimal and purposeful: scroll-linked reveals and slow crossfades between portfolio images. The overall atmosphere is that of a high-end design agency's printed monograph — authoritative, spare, and deeply intentional.

**Key Characteristics:**

- Pure monochrome palette — only `#000000` and `#ffffff`, zero exceptions
- Swiss International Typographic Style: grid-based, disciplined, editorial
- Massive condensed all-caps display headings as the dominant visual element
- Black-and-white photography as the sole source of visual texture
- Zero decorative elements — no shadows, no fills on interactive elements, no gradients
- Interaction through text: underlines and opacity shifts replace buttons
- Full-screen navigation overlay (menu takeover) with large type
- Extreme whitespace — the negative space is a designed element, not a gap

## 2. Color Palette & Roles

### Core (The Complete Palette)

- **Pure White** (`#ffffff`): Page background — the canvas everything lives on
- **Pure Black** (`#000000`): All text, all lines, all iconography, borders

### Semantic Applications

| Role                      | Color                                             | Notes                                |
| ------------------------- | ------------------------------------------------- | ------------------------------------ |
| Background                | `#ffffff`                                         | Always white — no surface variation  |
| Body text                 | `#000000`                                         | All paragraph and label text         |
| Headings                  | `#000000`                                         | Display, section titles, nav items   |
| Navigation links          | `#000000` (active) / `rgba(0,0,0,0.4)` (inactive) | Opacity-based muted state            |
| Borders & rules           | `#000000`                                         | Hairline 1px dividers                |
| Image tint                | Desaturated / B&W                                 | All photos rendered monochrome       |
| Hover state               | `rgba(0,0,0,0.5)` opacity                         | No color change — only opacity shift |
| Overlay background (menu) | `#000000`                                         | Full-black nav takeover              |
| Overlay text (menu)       | `#ffffff`                                         | White on black in the nav overlay    |

### Philosophy

Swiss Mono uses **binary contrast only** — black or white, full opacity or reduced opacity. There is no third color, no tint, no gray scale used for surfaces. Any "gray" in the system is achieved through opacity on black (`rgba(0,0,0,x)`), not a gray hex value. This keeps the palette logically pure: one ink, one paper.

## 3. Typography Rules

### Font Families

- **Display / Headings**: Condensed grotesque sans-serif — visually closest to **Bebas Neue**, **Neue Haas Grotesk Display**, or **Aktiv Grotesk Condensed**. All-caps, extreme weight (700–900), very tight tracking. In implementation, a system fallback stack of `"Helvetica Neue", "Arial Narrow", Arial, sans-serif` preserves the spirit.
- **Body / UI**: Clean grotesque sans-serif — **Inter**, **Helvetica Neue**, or `system-ui`. Regular weight (400), natural tracking, generous line-height.
- **Labels / Tags / Navigation**: Same grotesque as body, weight 500–600, all-caps with moderate letter-spacing (0.05em–0.15em).

### Hierarchy

| Role            | Transform  | Size            | Weight  | Line Height | Letter Spacing     | Notes                            |
| --------------- | ---------- | --------------- | ------- | ----------- | ------------------ | -------------------------------- |
| Hero Display    | uppercase  | 10vw–15vw       | 700–900 | 0.85–0.95   | -0.03em to -0.05em | Full-width, viewport-relative    |
| Section Marquee | uppercase  | 6vw–9vw         | 700     | 0.9         | -0.02em            | Scrolling or static large titles |
| Section Heading | uppercase  | 2.5rem–4rem     | 700     | 1.0         | -0.01em            | e.g. "ABOUT US", "OUR WORKS"     |
| Service Number  | uppercase  | 0.75rem         | 500     | 1.0         | 0.15em             | e.g. "01", "02", "03"            |
| Service Label   | uppercase  | 0.75rem         | 500     | 1.0         | 0.12em             | e.g. "CREATE", "SHAPE", "MOVE"   |
| Card Title      | mixed case | 1.5rem–2rem     | 700     | 1.1         | -0.01em            | Project/work titles              |
| Body            | mixed case | 0.9rem–1rem     | 400     | 1.6–1.7     | 0                  | Paragraph descriptions           |
| Navigation      | uppercase  | 0.75rem–0.85rem | 500–600 | 1.0         | 0.1em              | Nav links                        |
| Footer Labels   | uppercase  | 0.75rem         | 400–500 | 1.6         | 0.08em             | Address, contact info            |
| Caption / Tag   | uppercase  | 0.65rem–0.75rem | 500     | 1.4         | 0.15em             | Project category labels          |

### Principles

- **Scale as the only hierarchy**: Swiss Mono has no color to differentiate levels — all hierarchy is expressed through dramatic scale contrasts. A 12vw heading next to 0.9rem body creates the tension.
- **All-caps is structural, not decorative**: Every label, navigation item, and heading is uppercased. Mixed case is reserved exclusively for body copy.
- **Negative tracking on large type**: All display-size text pulls letter-spacing inward (-0.02em to -0.05em) — a hallmark of Swiss editorial typography.
- **Line-height below 1.0 on display**: Large headings collapse their line-height to 0.85–0.95, creating a dense, poster-like typographic block.

## 4. Component Stylings

### Navigation (Default State)

- Background: transparent
- Logo: top-left, black, uppercase, bold
- Nav links: top-right, uppercase 0.75rem, weight 500, `#000000`, letter-spacing 0.1em
- "MENU" toggle: text-only, no button chrome, uppercase
- Hover: opacity drops to ~0.4 on inactive items
- Border: none

### Navigation Overlay (Open State)

- Background: `#000000` — full viewport takeover
- Text: `#ffffff`
- Links: large-scale (2rem–4rem), weight 700, uppercase, stacked vertically
- Close trigger: same "MENU" toggle (now labeled or styled to indicate close)
- Animation: fast opacity/translate fade-in

### Project / Work Cards

- Background: none (image fills the card area directly)
- Image: full-bleed, B&W, aspect ratio ~4:3 or 3:2
- Category label: uppercase, 0.65rem, weight 500, above the project title
- Project title: 1.5rem–2rem, weight 700, black, below image
- No border, no shadow, no rounded corners (0px radius everywhere)
- Hover: slight opacity shift on image (0.85–0.9 opacity)

### Service Sections

- Layout: numbered list (01, 02, 03) with large mixed-case heading and body paragraph
- Number + label: top-left, small uppercase, weight 500, `rgba(0,0,0,0.5)`
- Service name: 1.5rem–2.5rem, weight 700, black
- Body text: 0.9rem, weight 400, line-height 1.65, max-width ~480px
- Divider: 1px solid `#000000` horizontal rule above each item

### Team / About Cards

- Full-height portrait photography, B&W
- Name: oversized display type, all-caps, overlaid or adjacent
- Role title: small uppercase label, weight 500
- Social links (LinkedIn, Instagram): text-only, uppercase, 0.75rem, hover underline
- No containers, no card borders

### Footer

- Background: `#ffffff`
- Layout: multi-column grid — studio name, team names, address, contact
- All text: uppercase, 0.75rem–0.85rem, weight 400
- Social links: two-letter abbreviations (IN, FB, X), uppercase, bold
- Separator: 1px black horizontal rule at top of footer
- Copyright: inline with studio name, same small type size

### Interactive Text Links

- Default: no underline
- Hover: underline, opacity 0.6
- No button fills, no pill shapes, no rounded corners — ever

## 5. Layout Principles

### Spacing System

- Base unit: 8px
- Scale: 8, 16, 24, 32, 48, 64, 80, 96, 128, 160, 200px
- Section gaps: 96px–200px — whitespace is generous between sections
- Content margins: 40px–80px horizontal padding on desktop

### Grid & Structure

- **No fixed grid columns** — layout is editorial and asymmetric
- Content appears at unexpected horizontal positions (flush left, center, offset right)
- Max content width: ~1200px, centered
- Full-bleed sections break the container at key moments (hero, image galleries)
- Navigation: fixed top bar, full-width, transparent background

### Whitespace Philosophy

- **Whitespace is the material**: The page breathes dramatically between sections. Empty white space is not wasted — it creates tension and makes the next element more impactful.
- **Anti-card**: Nothing is contained in a box. Images float, text floats, sections transition with lines or sheer scale rather than containers.

### Border Radius Scale

- **0px everywhere** — no rounded corners, no pills. This is a non-negotiable identity rule. Every shape is rectilinear.

## 6. Depth & Elevation

Swiss Mono has **no elevation system**. There are no shadows, no blurs, no z-axis depth cues.

| Level   | Treatment      | Use                                  |
| ------- | -------------- | ------------------------------------ |
| Base    | `#ffffff` flat | Entire page — single layer           |
| Overlay | `#000000` flat | Full-screen nav menu only            |
| Image   | No shadow      | Images sit flat on the white surface |
| Text    | No shadow      | All text is flat black on white      |

**Depth Philosophy**: Depth is achieved through typography scale and spatial rhythm — not shadows or elevation. A 12vw heading is "above" a 0.9rem paragraph not because it's elevated, but because it occupies more of the visual field. This is the Swiss grid principle: hierarchy through proportion, never through decoration.

## 7. Do's and Don'ts

### Do

- Use `#000000` and `#ffffff` exclusively — the palette is binary and closed
- Apply all-caps to every heading, label, navigation item, and tag
- Use dramatic scale contrasts — pair 10vw+ display type with 0.9rem body text
- Set letter-spacing negative on large headings (-0.02em to -0.05em)
- Set line-height below 1.0 on display type (0.85–0.95)
- Let whitespace dominate — section gaps should feel extravagant
- Desaturate all photography to pure black-and-white
- Use text-only interactions (underline on hover, opacity shift) — never filled buttons
- Keep border-radius at 0px on every element, always
- Use horizontal 1px black rules as the only structural dividers

### Don't

- Don't introduce any third color, tint, or gray hex value — use `rgba(0,0,0,x)` for muted states
- Don't round any corners — pills and rounded shapes are foreign to this identity
- Don't add shadows, glows, or blur effects of any kind
- Don't use filled/background buttons — all CTAs are text links or text-with-arrow
- Don't use color photography — all imagery must be monochrome
- Don't over-compress whitespace — density breaks the editorial rhythm
- Don't use mixed-case for labels, tags, or navigation — body copy is the only exception
- Don't use more than two font weights prominently on a single section (400 body, 700 display)
- Don't add card backgrounds or container borders around content blocks
- Don't use decorative icons, illustrations, or ornaments — type and image only

## 8. Responsive Behavior

### Breakpoints

| Breakpoint | Width        | Key Changes                                                                                |
| ---------- | ------------ | ------------------------------------------------------------------------------------------ |
| Mobile     | < 640px      | Single column; display type scales down to 16vw–18vw; nav collapses to full-screen overlay |
| Tablet     | 640px–1024px | Two-column grids; display type ~10vw–12vw; reduced section padding                         |
| Desktop    | > 1024px     | Full asymmetric layout; display type 8vw–12vw; multi-column work grids                     |

### Collapsing Strategy

- Hero display type: viewport-relative (`vw` units), scales naturally without breakpoints
- Navigation: always collapses to full-screen overlay on mobile
- Work grid: 3-column → 2-column → 1-column
- Team section: horizontal scroll or vertical stack on mobile
- Section padding: 200px vertical gap → 96px on tablet → 64px on mobile
- Font minimum: body text never below 14px; labels never below 11px

### Touch & Mobile Behavior

- All tap targets minimum 44×44px (text links get generous line-height padding)
- Navigation overlay is the primary mobile nav — no hamburger icon, text "MENU" toggle
- Horizontal image carousels on mobile for project galleries (swipe-enabled)
- No hover states on touch — interactions rely on tap only

## 9. Agent Prompt Guide

### Quick Color Reference

- Background: `#ffffff`
- All text: `#000000`
- Muted / inactive text: `rgba(0,0,0,0.4)`
- Overlay background: `#000000`
- Overlay text: `#ffffff`
- Accent: none — there is no accent color

### Quick Type Reference

- Display: condensed grotesque, uppercase, 700–900 weight, 8vw–14vw, tracking -0.03em, line-height 0.9
- Body: grotesque, mixed-case, 400 weight, 0.9rem–1rem, tracking 0, line-height 1.65
- Label/Nav: grotesque, uppercase, 500–600 weight, 0.75rem, tracking 0.1em

### Example Component Prompts

- "Create a hero section: white background, full-viewport-width condensed black heading in uppercase at ~12vw, weight 700, letter-spacing -0.03em, line-height 0.9. Below, a 0.9rem body paragraph in mixed case, max-width 480px."
- "Design a project card: no background, no border, no radius. Full-bleed B&W image at 4:3 ratio. Below: uppercase category label at 0.65rem weight 500 rgba(0,0,0,0.5), then project title at 1.75rem weight 700 black."
- "Build a navigation bar: transparent background, logo top-left in bold uppercase black, 'MENU' toggle top-right in uppercase 0.75rem weight 500. No border, no fill. Hover reduces opacity to 0.4."
- "Create a full-screen nav overlay: background #000000, stacked nav links in #ffffff, uppercase, 3rem, weight 700, left-aligned with 64px left margin."
- "Design a footer: white background, 1px black top border. Four columns: studio name, team list, address, contact. All uppercase, 0.75rem, weight 400, black."
- "Make a service entry: top 1px black rule. Left: '01' and 'CREATE' stacked in 0.75rem uppercase rgba(0,0,0,0.5). Right: service name at 2rem weight 700 black, then body paragraph at 0.9rem weight 400 line-height 1.65."

### Iteration Guide

1. Start with pure `#ffffff` canvas — resist any surface color
2. Set all text `#000000`, all headings uppercase, all labels uppercase
3. Use viewport-relative units (`vw`) for display type — this is what creates the Swiss poster feel
4. Pull letter-spacing inward on display, push it outward on small labels
5. Design the whitespace first — section gaps at 128px+ before adding content
6. Convert all imagery to B&W — the monochrome photo is the only visual richness allowed
7. Test every border-radius: it must be 0px. Round anything and the identity collapses
8. Interactions are text-only: underline on hover, opacity shift — no filled buttons ever
