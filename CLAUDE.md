# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Early AI-dopters is an AI consulting agency website targeting small to medium-sized businesses (SMBs). The project will be a modern, single-page application (SPA) with a non-generic, world-class aesthetic that differentiates from typical tech sites through custom design elements and AI-inspired animations.

**Key Differentiators:**
- Custom color palette blending cosmic futurism with earthy trust (Deep Space Navy, Vivid Cyan, Golden Amber)
- Asymmetric grids with AI-themed patterns (hex grids, node connections)
- Dedicated "Audit My Business" lead capture form with shiny green CTA button
- Bespoke approach avoiding cookie-cutter solutions

## Tech Stack & Architecture

**Frontend:** Next.js 14 with TypeScript, Tailwind CSS, Framer Motion
**Styling:** Tailwind CSS with custom configuration + Headless UI components
**CMS:** Contentful or Sanity for blog/portfolio management
**Forms:** Next.js API routes + Resend for emails or Vercel Postgres for leads
**Deployment:** Vercel with CI/CD
**Analytics:** Google Analytics + Hotjar

### Project Structure
The site follows Next.js 14 App Router conventions with:
- Single-page application structure with smooth scrolling sections
- Mobile-first responsive design (60%+ mobile traffic expected)
- Server-side rendering (SSR) for SEO optimization

## Custom Design System

### Color Palette (tailwind.config.js)
```javascript
colors: {
  primary: '#1A1A2E',      // Deep Space Navy
  secondary: '#16213E',    // Midnight Indigo
  accent: '#0EA5E9',       // Vivid Cyan
  'accent-warm': '#EAB308', // Golden Amber
  success: '#10B981',      // Emerald Green
  warning: '#F59E0B',      // Warm Orange
  neutral: {
    light: '#F8FAFC',
    medium: '#E2E8F0',
    dark: '#334155'
  }
}
```

**Design Requirements:**
- Gradients: Linear from primary to accent for hero backgrounds (navy to cyan "neural glow")
- WCAG AA compliance (contrast >4.5:1 for text)
- Dynamic color shifts on hover (amber glow on cards)
- Subtle AI-themed patterns (hex grids, node connections) as backgrounds

### Typography
- **Primary:** Inter (variable weights 300-700)
- **Secondary:** Space Grotesk (headings, geometric/futuristic feel)
- H1: 48px bold, 1.2 line-height
- H2: 32px semi-bold
- Body: 16px regular

### Component Standards
- **CTA Buttons:** All caps, rounded corners, bold font, full-width on mobile
- **Primary CTAs:** Success green (#10B981) with subtle radial gradient for gloss + hover animation (scale + glow)
- **Icons:** Custom SVGs with amber/cyan fills, AI motifs (lightbulbs evolving into networks)
- **Animations:** Subtle GSAP/Framer Motion transitions (fade-ins on scroll, parallax hero)
- **Layout:** Asymmetric grids for visual interest with ample whitespace

## Key Pages & Sections

### Home Page Sections
1. **Hero:** Bold headline, subheadline, CTA
2. **Services Teaser**
3. **Audit My Business Section** (critical lead capture):
   - Form fields: First Name, Last Name, Company Name, Company Description (textarea), Email, Phone
   - Prominent "AUDIT MY BUSINESS" button (shiny green, all caps)
   - Initially implemented as functional mock-up (React state, static "Thank you" message, no backend)
4. **Why Us?** (unique value propositions)
5. **Testimonials Carousel**
6. **Footer** with quick links

### Other Pages
- **Services:** Detailed offerings with icons, bullet points, pricing tiers ($5K+ starting)
- **Portfolio/Case Studies:** 3-5 examples with before/after metrics
- **About:** Team bios, philosophy (human-centered AI), company story
- **Blog/Resources:** SEO-driven content, gated resources for email capture
- **Contact:** Form mirroring Audit section, CRM integration

## Development Commands

### Initial Setup
```bash
npx create-next-app@latest agency-site --typescript --tailwind --eslint
cd agency-site
npm install framer-motion @headlessui/react
```

### Development
```bash
npm run dev          # Start dev server (http://localhost:3000)
npm run build        # Production build
npm run start        # Start production server
npm run lint         # Run ESLint
```

### Testing & Quality
```bash
npm run lint         # Lint checking
npm run type-check   # TypeScript type checking (if configured)
```

**Performance Target:** Lighthouse score >90

## Content Strategy

**Tone:** Confident, empathetic, jargon-free (8th-grade readability)
**SEO Keywords:** "AI consulting for small business," "prompt engineering services," "custom AI apps"

### Sample Copy Guidelines
- Headline: "Elevate Your Business with AI That Feels Effortless"
- Value Props: "Bespoke, Not Boilerplate" | "Proven SMB Wins" | "Human Touch"
- Audit Section: "Ready for Your Free AI Business Audit?" with reassuring post-form note

## Implementation Phases (14-day timeline)

1. **Setup (Day 1):** Next.js init, Tailwind custom config, GitHub repo
2. **Design & Wireframing (Days 2-3):** Figma sketches including Audit form layout
3. **Build Core (Days 4-7):** Home page, Audit form mock, global styles, responsive testing
4. **Content Integration (Days 8-10):** Full copy, portfolio, contact form
5. **Advanced Features (Days 11-12):** Animations, SEO (Next/SEO, sitemap.xml), CMS hookup
6. **Testing & Launch (Days 13-14):** Cross-browser, accessibility audit (WAVE), Vercel deployment

## Critical Implementation Notes

### Audit My Business Form
- Must feel interactive despite being initial mock-up
- Implement strong focus states, submit animation
- Use React state for input handling
- Static "Thank you! We'll review your submission." message on click
- No validation or backend submission initially (focus on UI polish)

### Non-Generic Visual Requirements
- Avoid blue/gray overload - infuse warmth via Golden Amber accents
- Custom Tailwind config prevents off-the-shelf theme appearance
- AI-inspired elements: neural network motifs in animations, subtle hex grids
- Inspiration: Notion (clean, playful) + Midjourney aesthetic (artistic, emergent)

### Responsive Design
- Mobile: Stacked sections, touch-friendly CTAs
- Desktop: Multi-column portfolio
- Test with Chrome DevTools across breakpoints

### Accessibility
- WCAG AA compliance minimum
- Test with WAVE tool before launch
- Ensure form usability (labels, focus states, error messaging for future)

## Deployment

**Platform:** Vercel (free tier initially)
**Cost:** ~$20/month hosting
**Domain:** Custom domain setup post-deployment
**CI/CD:** Automatic via Vercel GitHub integration

### Pre-Launch Checklist
- Cross-browser testing (Chrome, Firefox, Safari, Edge)
- Mobile responsiveness verification
- Accessibility audit with WAVE
- Lighthouse performance score >90
- Meta tags and SEO optimization
- Analytics integration (Google Analytics + Hotjar)

## Post-Launch
- Monitor traffic and user behavior
- A/B test copy variations
- Iterate based on lead generation metrics
- Plan for future features (client portal, backend form submission)
