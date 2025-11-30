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

The app uses a fixed-position layout with scroll-based section transitions:

- [App.vue](src/App.vue) - Root component with scroll event handling. Creates a 200vh scroll container while keeping content fixed, triggering section visibility based on scroll position
- [Hero.vue](src/components/Hero.vue) - Hero section with video background, liquid glass effects, and orbital animations
- [Problem.vue](src/components/Problem.vue) - Problem section that transitions in via scroll, featuring interactive video cards that play on hover
- [GlassSurface.vue](src/components/GlassSurface.vue) - Reusable Apple liquid glass component using SVG displacement maps for light distortion effects on top of glassmorphism

### Scroll Interaction Pattern

The application uses a scroll-based reveal mechanism in [App.vue](src/App.vue:8-21):
- A `.scroll` div creates a 200vh scrollable area
- The actual content (`.app`) is position fixed
- JavaScript listens to scroll events and toggles the `active` class on sections
- CSS transitions handle the visual reveal (e.g., Problem section uses `clip-path: circle()` animation)

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
- [hero-bg.mp4](src/assets/hero-bg.mp4) - Background video for hero section (autoplay, loop, muted)
- [problem1.mp4](src/assets/problem1.mp4), [problem2.mp4](src/assets/problem2.mp4), [problem3.mp4](src/assets/problem3.mp4) - Interactive videos in Problem section that play on hover with 400ms delay

## TypeScript Configuration

Project uses TypeScript project references:
- [tsconfig.json](tsconfig.json) - Root config with references
- [tsconfig.app.json](tsconfig.app.json) - App source configuration
- [tsconfig.node.json](tsconfig.node.json) - Node/Vite config files

## Important Notes

- This project uses `rolldown-vite` as a Vite replacement (see package.json overrides)
- GSAP is a dependency but not currently used in the code
- All text content is in Russian
- The application is designed for desktop viewing with specific viewport-based layouts
- The liquid glass effect is computationally expensive; test performance when adding multiple instances
