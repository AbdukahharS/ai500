# AI500

Smart irrigation and crop planning service landing page built with Vue 3, TypeScript, and GSAP.

## About

AI500 provides intelligent crop planning and irrigation management using AI-powered features:
- Weather analysis
- Water calculation
- Planting recommendations
- Resource savings optimization

## Tech Stack

- Vue 3 (Composition API)
- TypeScript
- Vite
- GSAP (ScrollTrigger animations)
- Custom liquid glass effect (Apple-inspired)

## Features

- **Hero Section** - Video background with liquid glass effects and orbital animations
- **Problem Section** - Interactive video cards that play on hover
- **Solution Section** - 4 expandable video cards showcasing AI features
- **Team Section** - Team member showcase with tech stack icons
- **Liquid Glass Effect** - Custom SVG-based glassmorphism with chromatic aberration
- **Scroll Animations** - GSAP ScrollTrigger for section transitions

## Getting Started

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Project Structure

```
src/
├── components/
│   ├── Hero.vue           # Hero section with video background
│   ├── Problem.vue        # Problem section with interactive video cards
│   ├── Solution.vue       # Solution section with expandable cards
│   ├── Team.vue           # Team showcase
│   └── GlassSurface.vue   # Reusable liquid glass component
├── assets/                # Video files and images
├── App.vue                # Main app with scroll animations
└── style.css              # Global styles
```

## Technical Highlights

- Custom liquid glass effect using SVG displacement maps
- Scroll-based section transitions (400vh scroll container)
- Video cards with hover-triggered playback
- Chromatic aberration and light distortion effects
