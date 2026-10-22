# ECHO — Editorial Developer & Designer Portfolio

<div align="center">

  [![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v3-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
  [![WebGL](https://img.shields.io/badge/Graphics-OGL_WebGL-black?style=for-the-badge&logo=webgl&logoColor=white)](https://github.com/oframe/ogl)
  [![License](https://img.shields.io/badge/License-MIT-000000?style=for-the-badge)](LICENSE)

  <p align="center">
    <strong>A bespoke, high-performance monochrome editorial portfolio showcasing digital craftsmanship, spatial web animations, and interactive design engineering.</strong>
  </p>

  <p align="center">
    Crafted by <strong><a href="https://github.com/Jishnu09-siuu">Jishnu Mondal</a></strong> — Designer & Full-Stack Creative Developer.
  </p>

</div>

---

## ✦ Overview

**ECHO** is an editorial developer and designer portfolio engineered with a focus on typography, fluid physics, and cutting-edge web graphics. Built around a curated monochrome aesthetic, it marries brutalist minimalism with rich micro-interactions, hardware-accelerated scroll animations, and interactive 3D drum reel navigation.

Whether presenting production landing pages, full-stack applications, or bespoke brand identities, ECHO provides an immersive editorial reading and browsing experience.

---

## ✦ Key Features & Interactive Architecture

### 1. 🪐 Custom ECHO Orbital Preloader
- Seamless intro experience with an orbital wavy dot animation synchronized via `requestAnimationFrame`.
- Auto-detects first load and dissolves smoothly to unveil the editorial hero section.

### 2. 🗞️ Editorial Hero & Metallic Typography Shaders
- Fluid responsive typography driven by dynamic viewport calculations (`clamp` / `vw`).
- Multi-layer metallic header effects and integrated portrait depth masking.
- Intersection-observer-powered entrance reveals that gracefully retrigger on revisit.

### 3. 🔍 `ScrollExpandMedia` Kinetic Canvas
- Scroll-driven media expansion stage that smoothly interpolates card dimensions, aspect ratio, and blur filters.
- Dual-layer GPU-accelerated unblur rendering running at 120 FPS without reflow penalties.
- Minimalist perimeter content layout ensuring 100% unobscured artwork visibility.

### 4. 🧭 Horizontal Spatial Experience Canvas
- Sticky horizontal timeline translating vertical user scroll into horizontal spatial progression.
- Interactive timeline panels displaying milestones, career history, and "living flow" energy animations.
- Accessible fallback honoring user OS preferences (`prefers-reduced-motion`).

### 5. 🎡 WorksWheel 3D Drum Reel
- Mathematical 3D cylindrical drum projection with radial ring transformations (`rotateX`, `rotateZ`, `translateZ`).
- Physics-based smooth drag gestures, momentum inertia, wheel scrolling, and step navigation.
- Deep project integration linking directly into dynamic modal inspection.

### 6. 🌊 FlexCarousel (OGL WebGL Liquid Preset)
- Interactive card slider powered by **OGL** (lightweight WebGL engine) with liquid lens bending and real-time mesh displacement.
- Dynamic accordion states, focus-on-click navigation, and full keyboard/touch support.

### 7. 🪟 Interactive Project Inspection Modal
- Glassmorphic modal viewer with animated backdrop blur (`cubic-bezier` spring easing).
- Comprehensive project metadata: client background, deliverable scopes, tech stacks, and direct links to live deployments.

---

## ✦ Tech Stack

| Domain | Technology | Description |
|---|---|---|
| **Structure** | HTML5 / Semantic Web | SEO-optimized, accessible markup with meta hierarchy |
| **Styling** | Vanilla CSS + Tailwind CSS v3 | Custom dark/light design tokens, typography & CSS variables |
| **Graphics & WebGL** | [OGL](https://github.com/oframe/ogl) | High-performance WebGL 3D meshes & shaders for liquid bending |
| **Logic & Motion** | Vanilla JavaScript (ES Modules) | Lightweight, zero-framework overhead, modular components |
| **Typography** | Plus Jakarta Sans | Editorial modernist sans-serif loaded from Google Fonts |
| **Components** | `flex-carousel`, `works-wheel`, `scroll-expand-media` | Bespoke modular UI engines |

---

## ✦ Featured Projects

The portfolio indexes a curated roster of production web applications, landing pages, and client systems:

- **Aether AI**: Cognitive workspace engineered for deep systemic research and reasoning canvas telemetry.
- **Aether Protocol**: Monolithic preview portal and executive onboarding architectural briefing flow.
- **Afterform S01**: Minimalist architectural lookbook and editorial digital showcase.
- **Cafe Website (Mocha & Miso)**: Full-stack cafe management system with order processing and real-time reservation portal.
- **Design Studio**: Bold creative agency identity website with fluid layout systems.
- **Julian Vance Photography**: Analog & editorial photography archive showcasing visual storytelling.
- **Sen Cruzo Client Portfolio**: Luxury architectural client presentation portfolio with custom typography.

---

## ✦ Project Structure

```bash
ECHO-WEBSITE/
├── index.html                   # Core single-page portfolio layout & markup
├── flex-carousel.js             # WebGL / OGL-powered liquid carousel engine
├── FlexCarousel.css             # Stylesheet for carousel layout & states
├── FlexCarousel.tsx             # React / TypeScript source reference
├── works-wheel.js               # 3D Cylindrical drum reel component
├── scroll-expand-media.js       # Scroll-driven media expansion engine
├── ScrollExpandMedia.tsx        # Component source reference
├── experience-section.js        # Horizontal spatial timeline engine
├── package.json                 # Project configuration & scripts
├── assets/                      # Brand assets, portrait imagery, and icons
├── Project Images/              # Production portfolio preview captures
└── Landing Page Assest/         # Full-length landing page showcase assets
```

---

## ✦ Getting Started Locally

This project is built using native ES modules and standard web technologies. You can run it with any local HTTP server:

### Prerequisites
- Python 3.x **or** Node.js installed on your machine.

### Option 1: Python Simple HTTP Server (Recommended)
```bash
# Clone the repository
git clone https://github.com/Jishnu09-siuu/ECHO-WEBSITE.git
cd ECHO-WEBSITE

# Run local development server
npm start
# or directly:
python3 -m http.server 8080
```
Then navigate to `http://localhost:8080` in your browser.

### Option 2: Node.js / Vite / `npx serve`
```bash
npx serve .
# or
npx live-server
```

---

## ✦ Deployment

Because ECHO is completely static and modular, it can be deployed instantly to any edge hosting provider:

- **Vercel**: Run `vercel` from the root directory or connect the GitHub repository.
- **Netlify**: Drag and drop the folder or connect via Git with publish directory set to `/`.
- **GitHub Pages**: Head to repository **Settings > Pages** and set source to branch `main` and folder `/ (root)`.

---

## ✦ Connect & Socials

- **Portfolio**: [Jishnu Mondal](https://jishnumondal.vercel.app/)
- **GitHub**: [@Jishnu09-siuu](https://github.com/Jishnu09-siuu)
- **LinkedIn**: [jishnu-mondal](https://www.linkedin.com/in/jishnu-mondal/)
- **X / Twitter**: [@Jishn8m](https://x.com/Jishn8m)

---

## ✦ License

This project is open-source and available under the [MIT License](LICENSE).
