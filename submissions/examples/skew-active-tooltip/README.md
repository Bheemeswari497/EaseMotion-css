# Creative Portfolio Card with Skew-Active Tooltip

A lightweight, high-performance Creative Portfolio Card featuring a kinetic **Skew-Active Tooltip** micro-interaction. Built strictly with pure HTML5 and modern CSS3 (no JavaScript, no external frameworks).

## Overview

This example demonstrates how to create a production-ready portfolio showcase card with interactive action triggers that reveal tooltips using smooth skew, scale, and fade transitions. The card itself elevates slightly on hover to deliver a layered depth effect.

## Features

- **Pure HTML & CSS**: Zero JavaScript runtime overhead or external dependencies.
- **Skew-Active Tooltip Animation**: Hardware-accelerated entrance transition combining `skewX()`, `scale()`, `translateY()`, and `opacity`.
- **Card Elevate Micro-Interaction**: Smooth vertical lift with dynamic shadow expansion on hover.
- **Tooltip Arrow**: Pure CSS triangular pointer anchored cleanly beneath the tooltip.
- **Responsive Layout**: Seamlessly adapts across desktop, tablet, and mobile screens.
- **Keyboard Accessible**: Full support for keyboard navigation using `:focus-visible` focus rings and standard ARIA attributes (`aria-describedby`, `role="tooltip"`).
- **Reduced Motion Ready**: Honors user accessibility settings via `@media (prefers-reduced-motion: reduce)`.

## Folder Structure

```text
submissions/examples/skew-active-tooltip/
├── demo.html       # Self-contained working HTML demo
├── style.css       # Raw CSS implementation & design system tokens
└── README.md       # Documentation & technical guide
```

## How to Use

1. **HTML Markup**:
   Wrap your action trigger (e.g. `<button>`) and tooltip `<div>` inside a container with `.tooltip-wrapper`:

   ```html
   <div class="tooltip-wrapper">
     <button type="button" class="action-btn" aria-describedby="tooltip-id">
       Trigger Label
     </button>
     <div id="tooltip-id" class="skew-tooltip" role="tooltip">
       <span class="tooltip-heading">Category</span>
       <p class="tooltip-content">Detailed tooltip message content.</p>
     </div>
   </div>
   ```

2. **CSS Integration**:
   Link `style.css` in your HTML `<head>` or import the CSS rules into your stylesheet.

## CSS Variables

Customization is driven by CSS variables defined in `:root`:

| Variable                | Default Value                   | Description                                       |
| ----------------------- | ------------------------------- | ------------------------------------------------- |
| `--skew-duration`       | `0.35s`                         | Duration of the skew-active tooltip entrance/exit |
| `--skew-easing`         | `cubic-bezier(0.16, 1, 0.3, 1)` | Easing curve for kinetic motion                   |
| `--skew-angle-initial`  | `-10deg`                        | Starting skew angle before activation             |
| `--skew-scale-initial`  | `0.94`                          | Starting scale transform                          |
| `--skew-offset-y`       | `12px`                          | Vertical slide offset                             |
| `--card-hover-duration` | `0.3s`                          | Card elevation transition duration                |
| `--card-bg`             | `#121824`                       | Background color of the portfolio card            |
| `--tooltip-bg`          | `#1e293b`                       | Tooltip container background color                |
| `--tooltip-border`      | `#334155`                       | Tooltip border color                              |
| `--accent-cyan`         | `#06b6d4`                       | Highlight accent color for badges & titles        |
| `--focus-ring`          | `#38bdf8`                       | Visible keyboard focus ring color                 |

## Browser Compatibility

- **Chrome / Edge**: 88+
- **Firefox**: 85+
- **Safari**: 14+
- **Mobile Browsers**: iOS Safari, Chrome for Android

## Accessibility Notes

- **Keyboard Focus**: Interactive elements include explicit `:focus-visible` styling with distinct outline rings for keyboard users.
- **ARIA Semantics**: Tooltips use `role="tooltip"` and are referenced via `aria-describedby` on trigger buttons.
- **Reduced Motion**: Under `@media (prefers-reduced-motion: reduce)`, all transforms and skew animations are disabled, displaying tooltips instantly without motion.
