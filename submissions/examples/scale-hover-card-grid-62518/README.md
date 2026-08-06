# CSS Scale-Hover Card Grid for E-Commerce Checkout Layouts

A premium, responsive, and pure CSS-only interactive product card grid layout designed for e-commerce checkout systems. It showcases elegant scale-up animations on hover, using glassmorphic UI design cards without any JavaScript dependencies.

## Overview

The Scale-Hover Card Grid provides a high-fidelity catalog display optimized for e-commerce checkouts. By leveraging CSS transitions, each card subtly elevates and scales up when hovered or focused, producing a fluid and premium feel.

## Features

- **Smooth Scale-Hover Transitions**: Dynamic `scale(1.04)` transition combined with shadow elevation upon cursor hover.
- **Glassmorphic Layout**: Stylish cards styled using `backdrop-filter` blur, semi-transparent border borders, and deep color surfaces.
- **Pure CSS Layout**: 100% markup and styling; zero JS required.
- **Semantic Structure**: Modern HTML5 nodes (`<article>`, `<section>`, `<header>`, etc.) with appropriate labels and attributes.
- **Customizable Variable System**: Built entirely with easy-to-customize CSS variables.
- **A11y Compliant**: Clear outline states on focus for keyboard navigators, supporting ARIA descriptions.
- **Prefer-Reduced-Motion**: Overrides scale transformations when motion settings are minimized.

## Folder Structure

```text
submissions/examples/scale-hover-card-grid-62518/
├── demo.html
├── style.css
└── README.md
```

## Usage

1. Open `demo.html` inside your web browser.
2. Hover over any product card to trigger the scale elevation effect.
3. Use `Tab` on your keyboard to navigate through elements and verify the focus state outline.

## HTML Example

```html
<article class="product-card">
  <div class="product-image-placeholder">⌚</div>
  <div class="product-rating">...</div>
  <h2 class="product-title">Product Title</h2>
  <p class="product-description">Description goes here.</p>
  <div class="product-footer">
    <div class="product-price-box">
      <span class="price-label">Price</span>
      <span class="product-price">$189.00</span>
    </div>
    <button type="button" class="buy-button">Buy Now</button>
  </div>
</article>
```

## CSS Variables

Configure styles by adjusting variables inside `style.css`:

```css
:root {
  --bg-primary: #08090e;
  --bg-surface: rgba(17, 23, 41, 0.5);
  --primary: #6366f1;
  --accent: #f59e0b;
  --border-color: rgba(255, 255, 255, 0.06);
  --glass-blur: 20px;
}
```

## Customization

To edit grid cards or change hover scaling parameters, update:
- **Card grid layout**: `.card-grid` grid-template-columns.
- **Hover scale factor**: `.product-card:hover` scale value (default: `scale(1.04)`).

## Accessibility

- Cards utilize `:focus-within` to display focus outlines when any inner elements (like the Buy button) are focused.
- Screen readers are provided with full context via proper element semantic nesting and `aria-label` settings.

## Responsive Behaviour

- **Desktop**: Three columns grid.
- **Tablet**: Adjusts down to two columns automatically.
- **Mobile**: Stacks as a single column.

## Browser Compatibility

- Google Chrome (latest)
- Mozilla Firefox (latest)
- Apple Safari (latest)
- Microsoft Edge (latest)
