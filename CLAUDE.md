# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

AI500 is a Vue 3 + TypeScript landing page for a smart irrigation and crop planning service. The application uses advanced visual effects including Apple's liquid glass effect, scroll-based animations, and video backgrounds to create an immersive user experience.

## Development Commands

```bash
# Start development server
npm run dev

# Build for production (runs TypeScript check + Vite build)
npm run build

# Preview production build
npm run preview
```

## Tech Stack

- **Framework**: Vue 3 with `<script setup>` SFC syntax
- **Language**: TypeScript
- **Build Tool**: Vite (using rolldown-vite variant)
- **Animation**: GSAP
- **Styling**: Scoped CSS with nested selectors

## Architecture

### Application Structure

The app uses a fixed-position layout with GSAP ScrollTrigger-based section transitions:

- [App.vue](src/App.vue) - Root component with GSAP ScrollTrigger animations. Creates a 400vh scroll container while keeping content fixed, triggering circular reveal animations for each section
- [Hero.vue](src/components/Hero.vue) - Hero section with video background, liquid glass effects, and orbital animations
- [Problem.vue](src/components/Problem.vue) - Problem section featuring interactive video cards that play on hover with 400ms delay
- [Solution.vue](src/components/Solution.vue) - Solution section with 4 expandable video cards showcasing AI features (weather analysis, water calculation, planting recommendations, resource savings)
- [Team.vue](src/components/Team.vue) - Team section displaying three team members (UI/UX Designer, Mobile Developer, Web Developer) with their tech stacks and portfolio links
- [GlassSurface.vue](src/components/GlassSurface.vue) - Reusable Apple liquid glass component using SVG displacement maps for light distortion effects on top of glassmorphism

### Scroll Interaction Pattern

The application uses GSAP ScrollTrigger for scroll-based animations in [App.vue](src/App.vue:13-175):
- A `.scroll` div creates a 400vh scrollable area (100vh per section)
- The actual content (`.app`) is position fixed
- GSAP ScrollTrigger creates three separate timelines for Problem (0-25%), Solution (25-50%), and Team (50-75%) sections
- Each section starts as a 32px circle dot positioned on the left edge, vertically stacked
- On scroll trigger, sections animate to full viewport using `clip-path: circle()` transition
- Animations include: size expansion, position changes, filter removal (grayscale/contrast), and border-radius transitions
- All sections remain in DOM as absolute positioned elements, layered with z-index (Problem: 10, Solution: 20, Team: 30)

### GlassSurface Component (Apple Liquid Glass)

[GlassSurface.vue](src/components/GlassSurface.vue) recreates Apple's signature liquid glass effect, which goes beyond standard glassmorphism by adding light distortion:

**How it works:**
- Uses SVG `feDisplacementMap` filters to create chromatic aberration and light distortion
- Generates three separate displacement maps for R, G, B channels with different offsets
- The displacement map is dynamically generated with gradient-based distortion patterns
- Combines channel separations with Gaussian blur for the characteristic liquid glass shimmer
- Generates unique filter IDs to avoid conflicts when multiple instances exist
- Implements ResizeObserver to regenerate displacement maps on size changes
- Falls back to standard backdrop-filter on browsers without SVG filter support
- Detects dark mode via `prefers-color-scheme` media query

**Key props:**
- `distortionScale` - Controls intensity of light distortion effect (negative values invert)
- `redOffset`, `greenOffset`, `blueOffset` - Fine-tune chromatic aberration per channel
- `xChannel`, `yChannel` - Control which color channels drive X/Y displacement
- `mixBlendMode` - Blend mode for gradient mixing in displacement map
- Standard props: `width`, `height`, `borderRadius`, `blur`, `opacity`, etc.

**Browser compatibility layers:**
1. SVG filters supported: Full liquid glass effect with distortion
2. Only backdrop-filter: Standard glassmorphism without distortion
3. No backdrop-filter: Fallback to semi-transparent backgrounds with borders

### Styling Conventions

- Global styles in [style.css](src/style.css) - minimal reset only
- Component styles are scoped and use nested CSS selectors
- Custom fonts loaded from Google Fonts: Kalnia, Labrada, Livvic
- Colors: Primary brand yellow `#E0F540`, white text, semi-transparent backgrounds
- Layout uses viewport units (vw/vh) for responsive scaling

### Video Assets

Video files are imported directly from assets and bound to video elements:
- [hero-bg.mp4](src/assets/hero-bg.mp4) - Background video for Hero section (autoplay, loop, muted)
- [problem1.mp4](src/assets/problem1.mp4), [problem2.mp4](src/assets/problem2.mp4), [problem3.mp4](src/assets/problem3.mp4) - Interactive videos in Problem section that play on hover with 400ms delay
- [solution1.mp4](src/assets/solution1.mp4), [solution2.mp4](src/assets/solution2.mp4), [solution3.mp4](src/assets/solution3.mp4), [solution4.mp4](src/assets/solution4.mp4) - Video backgrounds for Solution section's expandable cards (weather, water, planting, resources)

## TypeScript Configuration

Project uses TypeScript project references:
- [tsconfig.json](tsconfig.json) - Root config with references
- [tsconfig.app.json](tsconfig.app.json) - App source configuration
- [tsconfig.node.json](tsconfig.node.json) - Node/Vite config files

## Component Features

### Solution Section
- 4 interactive video cards that expand on hover (270px → 332px width)
- Cards have overlapping layout (margin-left: -10px) for compact arrangement
- Hover reveals additional content: description text and feature list with glass surface background
- Curtain overlay darkens on non-hover (70% opacity → 30% on hover)
- Uses GlassSurface component for feature list background (300x124px with 18px border-radius)

### Team Section
- Displays 3 team members with role titles, names, tech stack icons, and portfolio links
- Decorative elements: SVG loopers (top, left, right corners) and large semi-transparent circles
- Tech stack icons: Figma, Photoshop (Designer); Swift, Kotlin (Mobile); React, Vue, Node.js (Web)
- Portfolio links for Mobile and Web developers with hover underline effect

## Important Notes

- This project uses `rolldown-vite` as a Vite replacement (see package.json overrides)
- GSAP with ScrollTrigger plugin is actively used for all section transition animations
- All text content is in Russian
- The application is designed for desktop viewing with specific viewport-based layouts (not responsive)
- The liquid glass effect is computationally expensive; test performance when adding multiple instances
- Section animations use `will-change: transform, filter, width, height, clip-path, border-radius` for performance optimization
