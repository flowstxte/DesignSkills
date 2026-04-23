# Design System Inspired by Active Theory (V6)

## 1. Visual Theme & Atmosphere

Active Theory is a Venice Beach-based creative technology studio, and their portfolio site — V6, launched in 2024, Awwwards Site of the Day — is less a website than a proof of concept: what happens when you treat a browser tab like a real-time game engine. Built entirely on Hydra, their proprietary WebGL framework, it is the most technically ambitious portfolio site in existence. The philosophy is "the portfolio _is_ the product." Every version of the site is simultaneously a case study in pushing what the web can render.

The visual atmosphere is pure cinematic dark — near-void black backgrounds lit by the warm, organic glow of neon tubes. The V6 environment is inspired by Active Theory's own offices in Venice Beach and Amsterdam: you scroll through fully 3D-rendered environments — real spaces transformed into immersive digital stages — flickering with neon light, alive with real-time particle systems, and populated by other users' cursor trails rendered as glowing colored tubes that spawn and drift across the top and bottom of the viewport. It is multiplayer. Other people on the site in real time are visible through their cursor tube signatures.

The typographic personality is described by the studio itself as "alien" and "other-worldly." The fonts have a cold, foreign-feeling precision — geometric, slightly aberrant, deliberately unfamiliar — that signals you have entered a space that operates by its own rules. UI is stripped to radical minimalism: a single pill-shaped navigation element that physically reacts to scroll velocity, an AI chat interface that can navigate the portfolio on command, and near-zero decorative chrome. Everything that isn't the 3D world or the work itself is absent.

**Key Characteristics:**

- Void-black deep backgrounds (`#000000` or near-black) with all light sourced from neon/particle effects
- Neon tube particle trails as the primary interactive and multiplayer visual layer
- Custom "alien," geometric, cold-feeling display typography — other-worldly and precise
- Minimal UI chrome: single scroll-velocity-reactive pillbox nav + AI chat as the entire navigation system
- Multiple full-3D WebGL environments (8+) representing real office locations and project histories
- Real-time multiplayer: other users' cursor movements visible as glowing colored tubes
- GLSL shader stack for contrast, curl noise, antimatter particles, and custom post-processing
- The site _is_ the portfolio — the rendering achievement is itself a demonstration of capability
- Motion is the primary medium; a static representation is inherently incomplete

## 2. Color Palette & Roles

### Core

- **Void Black** (`#000000`): Page background and all 3D scene bases — pure light-absorbing black
- **Near Black** (`#080808`–`#0d0d0d`): Subtle surface differentiation on UI panels over the 3D canvas
- **Pure White** (`#ffffff`): High-contrast text, project titles, primary labels
- **Off-White** (`#e8e8e8`–`#cccccc`): Secondary text, muted labels, inactive states

### Neon / Particle Colors (Environment-Sourced)

These are not static brand colors — they are generative, scene-dependent, and user-specific. They appear as glowing tubes, particle clusters, and environment lighting. Common values:

- **Hot Pink / Magenta** (`#ff2d78`, `#ff00aa`): Neon tube lighting, cursor trails
- **Cyan / Electric Blue** (`#00e5ff`, `#0af`): Particle streams, environment accent lights
- **Warm Amber** (`#ffaa00`, `#ff8800`): Flickering neon signs, warm environment glow
- **Acid Green** (`#aaff00`, `#7fff00`): Particle accents, secondary neon
- **Deep Red** (`#ff1a1a`): Sign lighting, warning-tone accents

> **Critical note:** These neon colors are never used as static UI palette colors. They are real-time rendered outputs from the WebGL particle and lighting system. UI elements themselves are white, near-white, and black only.

### UI-Specific (Non-3D Layer)

- **UI Text** (`#ffffff`): All navigation, labels, and body copy
- **UI Muted** (`rgba(255,255,255,0.45)`): Inactive items, secondary labels, metadata
- **UI Border** (`rgba(255,255,255,0.12)`): Subtle 1px pill borders and panel edges
- **AI Chat Background** (`rgba(0,0,0,0.75)` + `backdrop-filter: blur(16px)`): Frosted glass panel over the 3D scene
- **Pillbox Nav Background** (`rgba(255,255,255,0.08)`–`rgba(255,255,255,0.12)`): Translucent pill, barely visible against the black

### Shadows & Glows

- **Neon Glow** (`0 0 40px rgba(255,45,120,0.8)`, variant per tube color): Particle and tube halos
- **Ambient Light Bleed** (`0 0 120px rgba(0,229,255,0.3)`): Scene-level diffuse lighting onto UI
- **Panel Blur** (`backdrop-filter: blur(16px)`): Frosted glass on floating UI surfaces

## 3. Typography Rules

### Font Families

- **Display / Identity**: Custom "alien" geometric typeface — described by the founders as giving the site an "alien, otherworldly feel." Based on publicly observed characteristics: rigid, angular, slightly irregular geometric sans, with unusual letterform proportions. Closest publicly available analogs: **Neue Machina** (Pangram Pangram), **Monument Extended** (Pangram Pangram), or **Space Grotesk** in heavy weights. May use a custom-cut proprietary typeface.
- **Body / Interface**: Clean grotesque sans — likely **Inter**, **Helvetica Neue**, or a custom system-ui stack — used for project descriptions, AI chat, and all secondary reading text.
- **Monospaced / Technical**: `"JetBrains Mono"`, `"Courier New"`, or `monospace` — for counter readouts, technical labels, and any terminal-adjacent UI elements in the AI chat.

### Hierarchy

| Role                       | Size            | Weight  | Line Height | Letter Spacing | Transform  | Notes                               |
| -------------------------- | --------------- | ------- | ----------- | -------------- | ---------- | ----------------------------------- |
| Studio Name / Logo         | 1rem–1.2rem     | 700     | 1.0         | 0.2em          | Uppercase  | Small, precise, top-left            |
| Project / Scene Title      | 3rem–8vw        | 700–900 | 0.9–1.0     | -0.02em        | Uppercase  | Dominant in scene, WebGL rendered   |
| Section Label              | 0.7rem–0.8rem   | 500     | 1.0         | 0.2em–0.3em    | Uppercase  | Category tags, project index labels |
| Pillbox Nav                | 0.75rem–0.85rem | 500     | 1.0         | 0.12em         | Uppercase  | "WORK" and "CONTACT" only           |
| Body / Project Description | 0.9rem–1rem     | 400     | 1.6–1.7     | 0              | Mixed case | Max-width ~520px                    |
| AI Chat Input              | 0.85rem–0.95rem | 400     | 1.5         | 0              | Mixed case | Conversational, monospace optional  |
| AI Chat Response           | 0.85rem         | 400     | 1.6         | 0              | Mixed case | Readable prose                      |
| Client / Year Label        | 0.65rem–0.75rem | 400–500 | 1.2         | 0.15em         | Uppercase  | Metadata on project cards           |
| Counter / Index            | 0.65rem         | 400     | 1.0         | 0.1em          | Monospaced | "01/24"-style project numbers       |

### Principles

- **Alien geometry as identity**: The display font must feel slightly _wrong_ — not Swiss precision, not humanist warmth. It should read as if designed by a machine intelligence that studied grotesque fonts from a distance. Rigid angles, unexpected counter shapes, cold rhythm.
- **Extreme weight contrast**: Display text runs at maximum weight (700–900); body text is Regular (400). No middle-weight usage in primary layouts.
- **Wide tracking on small text**: Labels and tags use 0.15em–0.3em letter-spacing at small sizes — this reads as deliberate, technical, and alien alongside the display type.
- **Uppercase for all UI, mixed case for all content**: Project descriptions and AI chat responses break into mixed case as the only "human" voice in the interface.
- **WebGL text rendering**: Major scene titles and display type may be rendered directly in WebGL using MSDF (Multi-channel Signed Distance Field) technique for crisp text at any resolution within the 3D environment.

## 4. Component Stylings

### Pillbox Navigation

- Shape: Capsule / pill — full border-radius (9999px)
- Background: `rgba(255,255,255,0.08)` — barely visible translucent white
- Border: `1px solid rgba(255,255,255,0.12)`
- Text: uppercase, 0.8rem, weight 500, letter-spacing 0.12em, `#ffffff`
- Content: two items only — "WORK" and "CONTACT"
- **Scroll-velocity reactivity**: The pill physically stretches/compresses or shifts position based on scroll speed — a micro-interaction that makes it feel like a live object, not a static nav
- Hover: border opacity increases to 0.3; no background fill change
- Position: fixed top-center or top-right, floating above the 3D canvas

### AI Chat Interface

- Trigger: text prompt input, floating in the scene or docked bottom-right
- Panel: `rgba(0,0,0,0.75)` background, `backdrop-filter: blur(16px)`, subtle `1px solid rgba(255,255,255,0.1)` border
- Radius: 12px–16px on the panel
- Prompt style: "Show me a fun project" — conversational NLP navigation
- Response: AI returns project suggestions, highlights work matching the query, can navigate the 3D environment
- Input field: minimal, white text on dark, no heavy chrome
- Dismiss: click outside or press Escape

### Project Cards / Index

- No card background — projects appear as direct title + thumbnail over the dark environment
- Thumbnail: project video or static image, full-bleed within a fixed aspect ratio
- Hover: video plays, subtle scale or opacity shift
- Title: 1.5rem–2.5rem, max weight, uppercase, `#ffffff`
- Client name: 0.7rem uppercase, `rgba(255,255,255,0.5)`, letter-spacing 0.2em
- Year: monospaced or small sans, same muted treatment as client name
- No borders, no card fills, no rounded corners on the image container

### Neon Tube Cursor Trails (Multiplayer Layer)

- Rendered in WebGL at top and bottom edges of the viewport
- Each active user generates a unique-colored glowing tube that follows their cursor/touch position
- Tubes have physics — they trail, curve, and fade naturally
- Colors: neon spectrum, randomly assigned per session or user-derived
- Glow: intense bloom effect (`0 0 40px` at the tube's assigned color)
- No UI interaction — purely ambient, communal, presence-indicating

### 3D Environment Scenes

- Full-viewport WebGL canvas as the page background
- 8+ distinct environments: Venice Beach exteriors, Amsterdam canal reflections, neon alleys, and project-world hybrids
- Scroll-triggered transitions between scenes using smooth crossfades and spatial movement
- Lighting: warm neon from signs and tubes, cold blue from environmental ambient, zero sunlight simulation
- Post-processing stack: contrast adjustment, bloom, color dodge blend modes, curl noise on particles

### Contact Form / Page

- Minimal: name, email, message fields
- Background: same void-black with 3D canvas persisting
- Field styling: no visible borders on default; 1px white bottom border (underline-style) on focus
- Labels: uppercase 0.7rem, weight 500, letter-spacing 0.2em, white
- Submit: pill-shaped button, same treatment as pillbox nav
- No decorative elements whatsoever

## 5. Layout Principles

### Spacing System

- Base unit: 8px
- Scale: 8, 16, 24, 32, 48, 64, 80, 96, 128, 160, 240px
- UI elements have minimal padding — the 3D world should dominate

### Grid & Structure

- **There is no traditional page grid.** The layout is a vertically scrollable 3D scene with floating UI elements composited on top.
- Project work appears as a vertically scrolling index — each project as a horizontal band or featured card
- Sections transition via 3D environment swaps, not section padding or dividers
- Max readable content width: ~600px for body text blocks
- Horizontal margins: 32px–64px on desktop

### Whitespace Philosophy

- **The darkness is the space.** Active Theory's version of whitespace is the black void between neon elements in a 3D environment. It is not padding or empty columns — it is the ambient emptiness of the rendered world.
- UI floats as minimal as possible — elements that aren't actively serving information are removed entirely.
- The two-link navigation is the radical extreme of this: every page in the site reduced to "WORK" and "CONTACT."

### Border Radius Scale

- 0px: Project image containers, all rectangular frames
- 8px–12px: AI chat panel corners
- 16px: Frosted glass overlay panels
- 9999px: Navigation pillbox, submit buttons — the only soft shape in the system
- **Key rule**: Pills are for navigation/action. Everything structural is rectilinear.

## 6. Depth & Elevation

| Level                     | Treatment                              | Use                                              |
| ------------------------- | -------------------------------------- | ------------------------------------------------ |
| Void (Level 0)            | `#000000` — pure black                 | Base canvas, infinite background                 |
| 3D Scene (Level 1)        | WebGL-rendered environments            | Venice Beach, Amsterdam, neon alleys — the world |
| Particle Layer (Level 2)  | Real-time GLSL particles + tube trails | Neon cursor tubes, atmospheric particles         |
| Post-Processing (Level 3) | Bloom, contrast shaders, color dodge   | Applied globally over the 3D scene               |
| UI (Level 4)              | `rgba(0,0,0,0.75)` + `backdrop-filter` | Chat panel, pillbox nav, project index overlay   |
| Focus Element (Level 5)   | Full opacity white, no blur            | Active nav items, selected project title         |

**Depth Philosophy**: Active Theory inverts the standard web layering model. The richest, most complex content (3D WebGL world) is _beneath_ everything, and the UI floats as the shallowest layer with the least visual weight. There are no simulated shadows between HTML elements — all depth cues come from the 3D engine's real lighting, bloom, and perspective.

## 7. Do's and Don'ts

### Do

- Use `#000000` as the total base — every surface either is void-black or floats above the 3D world
- Apply neon colors exclusively through WebGL particle/lighting systems — never as static CSS color values on UI
- Use the "alien" geometric typeface for all display and identity text — it must feel engineered, not warm
- Restrict navigation to its minimum: one pill, two links (work + contact)
- Use pill shape (9999px radius) exclusively for navigation and action buttons — never on content containers
- Apply `backdrop-filter: blur()` on floating UI panels — they should feel like frosted glass above the 3D world
- Let the 3D environments carry all visual richness — UI stays colorless (white on black)
- Implement scroll-velocity reactions on navigation elements — the UI should feel physically alive
- Keep uppercase for all labels and nav; mixed case only for body/conversational text
- Use wide letter-spacing (0.15em–0.3em) on small-scale uppercase text

### Don't

- Don't use neon colors (`#ff2d78`, `#00e5ff`, etc.) in HTML/CSS UI elements — they live in WebGL only
- Don't add decorative borders, backgrounds, or containers to project listings — the work floats directly
- Don't round project image or video containers — 0px radius, always rectilinear
- Don't add more than two primary navigation links — radical minimalism is the identity
- Don't use drop shadows on HTML UI — all depth comes from the 3D scene beneath
- Don't use light backgrounds anywhere — the entire experience is void-black
- Don't use mid-weight type (500–600) at display sizes — heavy/regular binary only
- Don't add ambient music or autoplay sound — the visual motion is the sensory layer
- Don't use icon sets or decorative illustrations — all visual expression is through rendering
- Don't compress the neon tube particle trails into static imagery — they must be live and generative

## 8. Responsive Behavior

### Breakpoints

| Breakpoint | Width         | Key Changes                                                                                                                               |
| ---------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Mobile     | < 640px       | Simplified 3D (reduced poly count, lighter shaders); single-column project list; pillbox nav scales down; tube trails from touch position |
| Tablet     | 640px–1024px  | Moderate 3D complexity; 2-column project grid; pillbox visible                                                                            |
| Desktop    | 1024px–1440px | Full 3D environment; all 8 scenes active; multiplayer tubes fully visible                                                                 |
| Wide       | > 1440px      | Expanded scene, wider particle spread                                                                                                     |

### Collapsing Strategy

- **3D Environments**: Polygon count reduced on mobile via LOD (level of detail); complex GLSL post-processing simplified or disabled; static environment screenshot fallback at lowest tier
- Cursor tube trails: convert to touch-position trails on mobile — same concept, touch-driven
- Navigation pillbox: maintains pill shape, scales from 0.85rem to 0.75rem; still scroll-velocity reactive
- AI chat: maintains full functionality; panel docks to bottom of screen on mobile
- Project grid: 2-column → 1-column on mobile; video autoplay deferred to tap
- Font sizes: viewport-relative values auto-scale; minimum body size 14px

### Touch & Multiplayer

- Touch events generate the same particle tube trails as mouse events — mobile users are visible to desktop users in real time
- Minimum touch target: 48×48px on all interactive elements
- Scroll-velocity detection continues on touch via `touchmove` velocity calculation
- The site enforces portrait-or-landscape support on all screen sizes (no resolution lock unlike KPRverse)

## 9. Agent Prompt Guide

### Quick Color Reference

- Background (all): `#000000`
- UI text: `#ffffff`
- Muted text / labels: `rgba(255,255,255,0.45)`
- UI border: `rgba(255,255,255,0.12)`
- Panel background: `rgba(0,0,0,0.75)` + `backdrop-filter: blur(16px)`
- Neon colors: WebGL-only — not applied in CSS/HTML

### Quick Type Reference

- Display: "alien" geometric sans (Neue Machina / Monument Extended as analogs), uppercase, 700–900, 5vw–9vw, tracking -0.02em
- Nav / Labels: clean grotesque, uppercase, 500, 0.75rem–0.85rem, tracking 0.12em–0.3em
- Body: clean grotesque, mixed case, 400, 0.9rem–1rem, tracking 0, line-height 1.65
- Technical: monospaced, uppercase, 0.65rem, tracking 0.15em

### Example Component Prompts

- "Create a pillbox navigation: `rgba(255,255,255,0.08)` background, `1px solid rgba(255,255,255,0.12)` border, `9999px` radius. Two links: 'WORK' and 'CONTACT'. Uppercase 0.8rem weight 500 white. On scroll, the pill stretches horizontally proportional to scroll velocity."
- "Design a frosted glass AI chat panel: `rgba(0,0,0,0.75)` background, `backdrop-filter: blur(16px)`, `1px solid rgba(255,255,255,0.1)` border, 14px radius. Input field: no border by default, `1px solid rgba(255,255,255,0.4)` on focus. White text, 0.85rem, mixed case."
- "Build a project listing row: no background, no border. Left: project number `01` in monospaced 0.65rem uppercase `rgba(255,255,255,0.4)`. Center: project title in alien display font 2.5rem uppercase weight 800 white, letter-spacing -0.02em. Right: client name 0.7rem uppercase `rgba(255,255,255,0.45)` tracking 0.2em + year."
- "Create a contact field: no box border, only `1px solid rgba(255,255,255,0.25)` bottom border (underline style). Label: uppercase 0.7rem weight 500 white tracking 0.2em floating above. Input text: white 0.95rem weight 400. On focus: bottom border brightens to full white."
- "Design a WebGL neon particle tube element: render as a glowing curved tube from mouseX/Y, color `#ff2d78`, with `0 0 40px rgba(255,45,120,0.8)` bloom. Tube persists for 2 seconds before fading, follows cursor with physics-based trail."

### Iteration Guide

1. Start with pure `#000000` — resist any surface variation. The void is the canvas.
2. All UI is white text floating above black — never add color to HTML/CSS elements
3. Neon and particle colors live in WebGL exclusively — they are not your brand palette, they are your atmosphere
4. Navigation must be radical minimalism: one pill, two words. Any more is too much.
5. The "alien" font at display sizes is what makes the design feel otherworldly — don't substitute a warm humanist grotesque
6. Wide letter-spacing (0.2em+) on all uppercase labels — it reads as machine-output, not editorial
7. Pillbox radius only on action/nav elements; everything structural stays at 0px radius
8. The site only works when in motion — static mockups are unfinished by definition; always plan for the scroll-triggered scene transitions
9. Multiplayer is not optional in spirit — even in a simplified version, indicate that the space is shared (show other "presences")
10. AI navigation is the third pillar alongside the 3D world and the work itself — build it as a first-class feature, not an afterthought
