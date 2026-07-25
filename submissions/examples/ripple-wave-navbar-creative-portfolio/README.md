# CSS Ripple-Wave Navbar for Creative Portfolio Layouts

A high-performance, GPU-accelerated CSS navigation bar designed for modern creative portfolios. Featuring dynamic ripple-wave hover animations using pure CSS keyframes, zero JavaScript dependencies, full keyboard accessibility, and a pure CSS responsive mobile navigation drawer.

---

## Features

- **Pure CSS Ripple-Wave Animation**: Radial wave expansion effects on hover and focus using pure CSS keyframe animations.
- **GPU-Friendly & 60fps Smooth**: Uses high-performance CSS properties (`transform: scale()` and `opacity`) to eliminate layout reflows and repaints.
- **Zero JavaScript Dependency**: Fully functional interactive navigation and mobile toggle built using clean HTML5 semantics and CSS pseudo-selectors.
- **Accessible & Accessible First**: Full support for `:focus-visible` custom focus rings, keyboard navigation, and `@media (prefers-reduced-motion: reduce)`.
- **Pure CSS Responsive Mobile Menu**: Smooth slide-in mobile navigation overlay driven by CSS state switches.
- **Customizable CSS Variables**: Fully compliant design system powered by CSS custom properties for effortless theme adjustments.

---

## Folder Structure

```
submissions/examples/ripple-wave-navbar-creative-portfolio/
├── demo.html     # Interactive HTML5 showcase & live demonstration page
├── style.css     # Modular, variable-driven CSS stylesheet containing ripple keyframes & layout
└── README.md     # Technical documentation, usage guidelines, and specifications
```

---

## Usage

### 1. Include the Stylesheet
Link the `style.css` file in your HTML document's `<head>`:

```html
<link rel="stylesheet" href="style.css">
```

### 2. Add Semantic Navigation HTML Structure

```html
<!-- Mobile Toggle Input -->
<input type="checkbox" id="nav-toggle" class="nav-toggle-input" aria-hidden="true">

<header class="portfolio-header">
  <nav class="portfolio-navbar" aria-label="Main Navigation">
    <!-- Brand Logo -->
    <a href="#" class="nav-logo">
      <div class="nav-logo-icon">✦</div>
      <div class="nav-logo-text">Creative<span>Studio</span></div>
    </a>

    <!-- Mobile Hamburger Button -->
    <label for="nav-toggle" class="nav-toggle-label" aria-label="Toggle navigation menu" tabindex="0" role="button">
      <span></span>
      <span></span>
      <span></span>
    </label>

    <!-- Navigation List -->
    <ul class="nav-menu">
      <li class="nav-item">
        <a href="#work" class="nav-link active">
          Work
          <span class="ripple-wave-effect"></span>
          <span class="nav-link-indicator"></span>
        </a>
      </li>
      <li class="nav-item">
        <a href="#about" class="nav-link">
          About
          <span class="ripple-wave-effect"></span>
        </a>
      </li>
    </ul>

    <!-- Call to Action Button -->
    <div class="nav-actions">
      <a href="#contact" class="nav-cta">Let's Talk</a>
    </div>
  </nav>
</header>
```

---

## CSS Variables

Customize colors, layout sizes, and animation timings directly via CSS custom properties in `:root`:

| Variable | Default Value | Description |
| :--- | :--- | :--- |
| `--bg-dark` | `#090a0f` | Main background color |
| `--bg-nav` | `rgba(15, 17, 26, 0.75)` | Navigation bar backdrop color |
| `--text-primary` | `#f8fafc` | Primary text color |
| `--accent-primary` | `#6366f1` | Primary accent color (Indigo) |
| `--accent-secondary` | `#ec4899` | Secondary accent color (Pink) |
| `--ripple-color-1` | `rgba(99, 102, 241, 0.45)` | Inner ripple wave tint |
| `--ripple-color-2` | `rgba(168, 85, 247, 0.35)` | Outer ripple wave tint |
| `--nav-height` | `80px` | Navigation bar height |
| `--ease-ripple` | `cubic-bezier(0.1, 0.8, 0.3, 1)` | Wave animation timing function |

---

## Accessibility

- **Keyboard Navigation**: All links and interactive controls feature explicit `:focus-visible` focus rings with high-contrast outlines.
- **Prefers Reduced Motion**: Disables complex keyframe wave expansions for users with motion sensitivity via `@media (prefers-reduced-motion: reduce)`, offering instantaneous color and background transitions instead.
- **Semantic Structure**: Built with standard HTML5 elements (`<header>`, `<nav>`, `<ul>`, `<li>`, `<a>`) and appropriate `aria-label` attributes.

---

## Browser Support

- Chrome / Edge (100+)
- Firefox (100+)
- Safari (15.4+)
- Opera (86+)
