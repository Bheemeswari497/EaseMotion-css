# EaseMotion CSS: Bounce-Pulse Card Grid (E-Commerce Checkout Layouts)

A premium, interactive e-commerce checkout add-ons section featuring a glassmorphism product card grid, staggered spring-bounce entrance animations, and hover pulse micro-interactions using only pure CSS.

---

## Overview

The **Bounce-Pulse Card Grid** offers a beautiful, responsive, and animated user interface layer for showing recommended upgrades, complementary items, or add-ons during checkout steps.

When the grid loads, each product card performs a physics-inspired zoom-and-slide bounce entrance (`bounce-in`) using staggered animation delays. When a user hovers over a product card, the card gentle-pulses in scale and displays an elevated purple glow shadow.

---

## Features

- **Staggered Bounce Entrance**: Physics-inspired spring animations triggered on load with incremental transition delays.
- **Hover Micro-Animations**: A gentle pulse scaling keyframe accompanied by box-shadow and border-color transitions on hover.
- **Modern Glassmorphism**: Frosted glass panel backgrounds (`backdrop-filter`) combined with bright border highlights.
- **Responsive Layout**: Designed with standard CSS Grid auto-fill, collapsing columns responsively across mobile, tablet, and widescreen.
- **Accessibility & Focus Styles**: Native button elements with clear focus outlines. Supported accessibility states via `prefers-reduced-motion: reduce`.
- **Pure CSS**: Fully dependency-free implementation with no JavaScript.

---

## Folder Structure

```text
bounce-pulse-card-grid-62522/
├── README.md   # Documentation and developer instructions
├── demo.html   # Main HTML demonstration markup
└── style.css   # Component stylesheet and animation systems
```

---

## Usage

1. Include the stylesheet in your `<head>`:
   ```html
   <link rel="stylesheet" href="style.css">
   ```

2. Build the grid container and product card markup:
   ```html
   <main class="product-grid" aria-label="Product upgrades">
     <article class="product-card">
       <div class="product-image-area">
         <span class="discount-badge">Save 20%</span>
         <!-- SVG or image goes here -->
       </div>
       <div class="product-info">
         <h2 class="product-title">UltraWide Monitor</h2>
         <p class="product-description">34-inch curved IPS panel...</p>
         <div class="product-pricing">
           <span class="price-current">$399.00</span>
           <span class="price-original">$499.00</span>
         </div>
         <button class="btn-add-cart">Add to Cart</button>
       </div>
     </article>
   </main>
   ```

---

## CSS Variables

Configure design themes using CSS Custom Properties defined in `:root`:

| CSS Variable | Default Value | Description |
|---|---|---|
| `--bg-primary` | `#080a10` | Grid container page canvas color |
| `--bg-surface` | `rgba(22, 28, 45, 0.45)` | Product card background color |
| `--primary` | `#8b5cf6` | Main brand color (Purple) |
| `--accent` | `#3b82f6` | Secondary accent color (Blue) |
| `--transition-bounce`| `0.75s cubic-bezier(...)`| Spring entrance curve coefficients |
| `--transition-pulse` | `2s infinite ease-in-out` | Infinite hover pulsing speed |

---

## Customization

Adjust staggered card delays by declaring the count variables:

```css
.product-card:nth-child(1) { animation-delay: 0.1s; }
.product-card:nth-child(2) { animation-delay: 0.2s; }
```

Modify the hover pulse scale amount inside the `@keyframes gentle-pulse` block:

```css
@keyframes gentle-pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.025); } /* increase scale to increase pulse size */
  100% { transform: scale(1); }
}
```

---

## Accessibility

- **Native Controls**: Add-to-cart controls are standard `<button>` elements, facilitating keyboard accessibility without scripting listeners.
- **Aria Attributes**: Incorporates `aria-label` tags describing ratings and list structures.
- **Prefers-Reduced-Motion**: If reduced motion is requested, entrance animations are omitted, cards default to standard static visibility, and scale hover pulses are disabled.

---

## Responsive Behaviour

- **Desktop Viewport**: Grid auto-fills columns according to viewport space (3 to 4 columns).
- **Tablet Viewport**: Collapses to double columns (minimum card boundary: `280px`).
- **Mobile Viewport**: Collapses to single columns with full padding scales.

---

## Browser Compatibility

- Google Chrome (Latest)
- Mozilla Firefox (Latest)
- Apple Safari (Latest)
- Microsoft Edge (Latest)
- Mobile browsers (WebKit engine)
