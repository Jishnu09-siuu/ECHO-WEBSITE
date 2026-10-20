---
name: string-tune
description: >-
  Use this skill when configuring, implementing, or debugging interactive web animations, scroll effects, parallax, magnetic cursor, split text, and progress animations using the @fiddle-digital/string-tune library.
---

# StringTune Integration & Development Guide

`@fiddle-digital/string-tune` is a modular, high-performance web motion library engineered by Fiddle.Digital with a **CSS-first, JS-light, attribute-driven** architecture. It minimizes JavaScript runtime overhead by leveraging HTML attributes and CSS custom properties for declarative animations.

---

## 1. Installation & Import

### A. NPM / Bundlers (Vite, Next.js, Webpack)
```bash
npm install @fiddle-digital/string-tune
```

In your JavaScript / TypeScript entry point:
```javascript
import StringTune, {
  StringParallax,
  StringMagnetic,
  StringProgress,
  StringCursor,
  StringSplit,
  StringSpotlight,
  StringVideoAutoplay,
  StringScrollbar
} from '@fiddle-digital/string-tune';
```

### B. Direct Script Tag (Local or CDN)
For standalone HTML pages or static sites without a bundler:

**Local bundle:**
```html
<script src="assets/string-tune.js"></script>
```

**CDN (Unpkg / jsDelivr):**
```html
<script src="https://cdn.jsdelivr.net/npm/@fiddle-digital/string-tune@1.2.0/dist/index.js"></script>
```

> **Note on CDN namespace**: When included via a standard `<script>` tag, access the runtime through `StringTune.StringTune.getInstance()` or inspect `window.StringTune`.

---

## 2. Initialization Workflow

Initialize the singleton instance, register required modules, and start the animation loop:

```javascript
// 1. Obtain singleton instance
const stringTune = typeof StringTune.getInstance === 'function'
  ? StringTune.getInstance()
  : StringTune.StringTune.getInstance();

// 2. Register required modules (modular architecture saves memory)
stringTune.use(StringParallax);
stringTune.use(StringMagnetic);
stringTune.use(StringProgress);
stringTune.use(StringCursor);

// 3. Start update loop (e.g., 60 FPS)
stringTune.start(60);
```

### Key Lifecycle Methods
- `stringTune.start(fps = 60)`: Starts the update loop.
- `stringTune.stop()`: Pauses updates.
- `stringTune.onResize(force = false)`: Forces a re-measurement of all DOM boundaries and offsets.
- `stringTune.scrollTo(target)`: Smooth scrolls to an offset number, CSS selector, or HTMLElement.
- `stringTune.destroy()`: Cleans up all event listeners and DOM observers.

---

## 3. Core Modules & Markup Patterns

StringTune uses declarative `string="..."` attributes on DOM elements.

### 1. Parallax (`StringParallax`)
Applies scroll-linked transform offsets to elements.
```html
<!-- Moves with a 0.5 parallax multiplier -->
<div string="parallax" string-factor="0.5">
  <img src="hero.jpg" alt="Parallax Hero">
</div>

<!-- Negative factor moves opposite to scroll -->
<span string="parallax" string-factor="-0.3">Floating Text</span>
```

### 2. Magnetic Pull (`StringMagnetic`)
Draws elements toward the mouse cursor when hovered.
```html
<button class="cta-btn" string="magnetic" string-cursor-target="target">
  Hover over me!
</button>
```

### 3. Scroll Progress (`StringProgress`)
Tracks scroll position across sections to trigger state changes, progress bars, or active indicators.
```html
<section string="progress" string-id="portfolio-section">
  <h2>Featured Projects</h2>
</section>
```

### 4. Split Text (`StringSplit`)
Splits text into characters, words, or lines for staggered kinetic animations without layout jitter.
```html
<h1 string="split" string-split="chars" string-delay="0.05">
  Monochrome Editorial
</h1>
```

### 5. Spotlight (`StringSpotlight`)
Tracks cursor coordinates to render dynamic radial spotlight gradients.
```html
<div class="card" string="spotlight" style="--spotlight-radius: 300px;">
  <h3>Interactive Card</h3>
</div>
```

### 6. Viewport Video Autoplay (`StringVideoAutoplay`)
Automatically plays videos when they enter the viewport and pauses when offscreen to preserve resources.
```html
<video string="video-autoplay" muted playsinline loop>
  <source src="showreel.mp4" type="video/mp4">
</video>
```

---

## 4. Attributes Reference

| Attribute | Typical Values | Description |
| :--- | :--- | :--- |
| `string="parallax"` | Token | Activates parallax module for element |
| `string-factor` | `-2.0` to `2.0` (e.g. `0.6`) | Parallax intensity / speed factor |
| `string="magnetic"` | Token | Activates magnetic attraction to cursor |
| `string-cursor-target` | `"target"`, selector | Target bounding box for magnetic effect |
| `string="progress"` | Token | Exposes scroll progress for element |
| `string-id` | Unique string | Identifier for referencing progress in CSS or JS |
| `string="split"` | Token | Activates typography splitting |
| `string-split` | `"chars"`, `"words"`, `"lines"` | Unit granularity for text splitting |
| `string="spotlight"` | Token | Activates cursor-reactive spotlight |
| `string="video-autoplay"`| Token | Automatically controls video playback in view |
| `string-copy-from` | `#source-element-id` | Reuses state and metrics from another element |
| `string-lerp` | `0.01` to `1.0` (e.g. `0.1`) | Smoothing interpolation rate |

---

## 5. Recipes & Best Practices

### Recipe: Modern Editorial Hero with Parallax & Magnetic Links
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>StringTune Hero</title>
  <style>
    .hero { min-height: 100vh; display: grid; place-items: center; }
    .hero-title { font-size: 4rem; will-change: transform; }
    .badge { padding: 12px 24px; border-radius: 9999px; background: #000; color: #fff; display: inline-block; }
  </style>
</head>
<body>
  <section class="hero" string="progress" string-id="hero">
    <h1 class="hero-title" string="parallax" string-factor="0.4">
      Digital Craftsman
    </h1>
    <a href="#work" class="badge" string="magnetic">
      Explore Projects
    </a>
  </section>

  <!-- Load StringTune script -->
  <script src="assets/string-tune.js"></script>
  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const ST = window.StringTune?.StringTune || window.StringTune;
      if (!ST) return;
      
      const st = ST.getInstance();
      st.use(window.StringTune.StringParallax || ST.StringParallax);
      st.use(window.StringTune.StringMagnetic || ST.StringMagnetic);
      st.use(window.StringTune.StringProgress || ST.StringProgress);
      st.start(60);
    });
  </script>
</body>
</html>
```

---

## 6. Verification & Troubleshooting
1. **Script loading errors:** If using CDN or vanilla script tag, ensure the path points to `assets/string-tune.js` or `https://cdn.jsdelivr.net/npm/@fiddle-digital/string-tune@1.2.0/dist/index.js`.
2. **Missing animations:** Verify that `stringTune.start(60)` has been called and that the corresponding module was registered with `stringTune.use(...)`.
3. **Layout shifts after dynamic content loads:** Call `stringTune.onResize(true)` whenever images or dynamic DOM elements finish rendering.
