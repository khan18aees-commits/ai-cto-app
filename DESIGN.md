---
name: Obsidian Nexus
colors:
  surface: '#131313'
  surface-dim: '#131313'
  surface-bright: '#3a3939'
  surface-container-lowest: '#0e0e0e'
  surface-container-low: '#1c1b1b'
  surface-container: '#201f1f'
  surface-container-high: '#2a2a2a'
  surface-container-highest: '#353534'
  on-surface: '#e5e2e1'
  on-surface-variant: '#cfc2d6'
  inverse-surface: '#e5e2e1'
  inverse-on-surface: '#313030'
  outline: '#988d9f'
  outline-variant: '#4d4354'
  surface-tint: '#ddb7ff'
  primary: '#ddb7ff'
  on-primary: '#490080'
  primary-container: '#b76dff'
  on-primary-container: '#400071'
  inverse-primary: '#842bd2'
  secondary: '#c0c1ff'
  on-secondary: '#1000a9'
  secondary-container: '#3131c0'
  on-secondary-container: '#b0b2ff'
  tertiary: '#c6c4da'
  on-tertiary: '#2f2f40'
  tertiary-container: '#908fa3'
  on-tertiary-container: '#282839'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#f0dbff'
  primary-fixed-dim: '#ddb7ff'
  on-primary-fixed: '#2c0051'
  on-primary-fixed-variant: '#6900b3'
  secondary-fixed: '#e1e0ff'
  secondary-fixed-dim: '#c0c1ff'
  on-secondary-fixed: '#07006c'
  on-secondary-fixed-variant: '#2f2ebe'
  tertiary-fixed: '#e3e0f7'
  tertiary-fixed-dim: '#c6c4da'
  on-tertiary-fixed: '#1a1a2a'
  on-tertiary-fixed-variant: '#464557'
  background: '#131313'
  on-background: '#e5e2e1'
  surface-variant: '#353534'
typography:
  display:
    fontFamily: Inter
    fontSize: 48px
    fontWeight: '700'
    lineHeight: '1.1'
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Inter
    fontSize: 32px
    fontWeight: '600'
    lineHeight: '1.2'
    letterSpacing: -0.01em
  headline-lg-mobile:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '600'
    lineHeight: '1.2'
  headline-md:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '500'
    lineHeight: '1.3'
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.6'
  code-sm:
    fontFamily: JetBrains Mono
    fontSize: 14px
    fontWeight: '400'
    lineHeight: '1.5'
  label-caps:
    fontFamily: JetBrains Mono
    fontSize: 12px
    fontWeight: '600'
    lineHeight: '1'
    letterSpacing: 0.05em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 4px
  xs: 0.5rem
  sm: 1rem
  md: 1.5rem
  lg: 2rem
  xl: 4rem
  gutter: 1.5rem
  sidebar-width: 280px
---

## Brand & Style

The design system is engineered to evoke a sense of absolute technical mastery and premium innovation. It targets CTOs, lead engineers, and high-growth founders who require a high-fidelity interface that feels both powerful and invisible.

The aesthetic leans heavily into **Glassmorphism** and **Minimalism**, utilizing deep obsidian voids to create infinite canvas depth. Visual interest is generated through light—specifically, "contained neon" glows and refracted light through semi-transparent surfaces—rather than heavy textures or illustrative clutter. The interface should feel like a high-end command center: silent, responsive, and authoritative.

## Colors

This design system utilizes a "Deep Space" palette. The foundation is `#050505` (Obsidian), providing a true-black base that allows glass elements to pop. 

- **Primary (Electric Purple):** Used exclusively for high-priority actions, active states, and critical data highlights.
- **Secondary (Indigo):** Used for supporting accents and gradients within glass containers.
- **Surface Strategy:** Surfaces are built using semi-transparent grays (`#1A1A1A` at various opacities) to create layers of depth.
- **Glows:** Use low-opacity radial gradients of the primary color to simulate light emission from active components.

## Typography

The typography strategy pairs the clinical precision of **Inter** with the technical aesthetic of **JetBrains Mono**. 

- **Headlines:** Use Inter with tight tracking and medium-to-bold weights. Large display text should feel architectural.
- **Body:** Inter provides maximum legibility for complex AI-generated insights.
- **Technical Accents:** Use JetBrains Mono for metadata, labels, code snippets, and system status indicators to reinforce the "AI CTO" narrative.
- **Hierarchy:** Lean into font-weight contrast rather than just size to maintain a sophisticated, dense information display.

## Layout & Spacing

The layout is defined by a **Sidebar-first philosophy**, optimized for deep navigation and complex toolsets. 

- **Grid:** A 12-column fluid grid for desktop with 24px gutters. For mobile, a single column with 16px side margins.
- **Sidebar:** The sidebar is a fixed glass panel. On mobile, it transitions to a full-screen overlay with a frosted backdrop.
- **Rhythm:** Use an 8px base unit. Components should be spaced generously to prevent the dark UI from feeling claustrophobic. 
- **Containment:** Content is housed in "Glass Modules" which use internal padding of `md` (24px) to ensure breathing room around technical data.

## Elevation & Depth

Depth is not communicated via shadows, but through **Tonal Layering** and **Backdrop Blurs**.

1.  **Level 0 (Floor):** Pure `#050505`.
2.  **Level 1 (Cards/Panels):** Background: `rgba(25, 25, 25, 0.6)`, Backdrop Blur: `20px`, Border: `1px solid rgba(255, 255, 255, 0.08)`.
3.  **Level 2 (Modals/Popovers):** Background: `rgba(35, 35, 35, 0.8)`, Backdrop Blur: `40px`, Border: `1px solid rgba(255, 255, 255, 0.15)`.
4.  **Active State:** Use a 1px solid Primary Purple border with a subtle 4px outer glow (`spread: 0, blur: 12px`).

Avoid drop shadows that cast "darkness"; instead, use "inner glows" or light borders to define where one surface ends and another begins.

## Shapes

The design system utilizes a **Medium Rounded** approach to balance professional structure with modern softness.

- **Standard Radius:** 8px (`0.5rem`) for cards, input fields, and buttons.
- **Large Radius:** 16px (`1rem`) for primary layout containers or hero sections.
- **Icons:** Use linear, 2px stroke icons with slightly rounded corners to match the UI's geometry.
- **Interactive Elements:** Buttons maintain a consistent 8px radius; avoid pill-shapes to keep the interface looking like a high-end software tool rather than a consumer app.

## Components

### Buttons
- **Primary:** Solid Electric Purple background, white text, 8px radius. On hover, add a `0 0 15px rgba(168, 85, 247, 0.4)` glow.
- **Ghost:** Transparent background, `1px solid rgba(255, 255, 255, 0.1)` border. Purple text on hover.

### Cards
- Always glassmorphic. Background: `rgba(255, 255, 255, 0.03)`, Blur: `12px`.
- Border-top should be slightly brighter than the sides to simulate a top-down light source.

### Input Fields
- Dark, inset background (`#0A0A0A`).
- 1px border that turns Electric Purple on focus.
- Monospaced font for input text to emphasize the technical nature.

### Chips & Badges
- Used for "System Status" or "AI Confidence."
- Small, uppercase Monospace labels.
- Backgrounds are low-opacity versions of the status color (e.g., 10% Green for 'Healthy').

### Side Navigation
- High-blur background (`40px`).
- Active items use a vertical purple line on the left edge and a subtle gradient background from left to right.

### The "AI Pulse"
- A specific component for AI processing states: A subtle, breathing radial gradient (Electric Purple) that sits behind the primary content area.