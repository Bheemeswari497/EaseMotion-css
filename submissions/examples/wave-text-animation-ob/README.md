# Pure CSS Wave Text Animation Component (#86795)

A lightweight, accessible, pure HTML and CSS wave text animation component for the EaseMotion CSS library.

This component animates individual characters in a word or phrase using a single CSS keyframe definition combined with CSS custom properties (`--i`) to generate phase-offset wave displacement without JavaScript or external dependencies.

---

## Features

- **Pure HTML & CSS**: Zero JavaScript overhead or external build tools required.
- **Single `@keyframes` Definition**: Efficiently animates arbitrary string lengths with a single keyframe rule.
- **Customizable CSS Variables**: Effortlessly modify wave speed, amplitude, rotation angle, and staggered delays.
- **Screen Reader Accessible (A11y)**: Wraps characters with `aria-hidden="true"` while placing complete text in `aria-label` to prevent screen reader fragmentation.
- **Dark Mode Support**: Built-in automatic dark mode theme switching via `@media (prefers-color-scheme: dark)`.
- **Reduced Motion Support**: Clean `@media (prefers-reduced-motion: reduce)` fallback that stops movement for sensitive users.
- **Responsive Layout**: Designed to adapt gracefully to all screen sizes from mobile to desktop.

---

## Usage Guide

### HTML Markup

Wrap each character in a `<span>` with `--i` indicating its zero-indexed position, and provide full text for screen readers on the container using `aria-label`:

```html
<span class="wave-text" aria-label="EaseMotion">
  <span aria-hidden="true">
    <span class="wave-char" style="--i: 0">E</span>
    <span class="wave-char" style="--i: 1">a</span>
    <span class="wave-char" style="--i: 2">s</span>
    <span class="wave-char" style="--i: 3">e</span>
    <span class="wave-char" style="--i: 4">M</span>
    <span class="wave-char" style="--i: 5">o</span>
    <span class="wave-char" style="--i: 6">t</span>
    <span class="wave-char" style="--i: 7">i</span>
    <span class="wave-char" style="--i: 8">o</span>
    <span class="wave-char" style="--i: 9">n</span>
  </span>
</span>
```

### CSS Custom Properties

| Custom Property | Default | Description |
| :--- | :--- | :--- |
| `--wave-duration` | `1.6s` | Full cycle duration of one complete wave oscillation |
| `--wave-delay-step` | `0.07s` | Delay step per character index (`--i`) |
| `--wave-amplitude` | `-0.45em` | Maximum vertical displacement at peak wave height |
| `--wave-rotate` | `-4deg` | Subtle character tilt at peak wave height |

---

## File Structure

```text
submissions/examples/wave-text-animation-ob/
├── demo.html
├── style.css
└── README.md
```

---

## Accessibility Notes

Splitting words into individual element spans often causes screen readers to read characters individually (e.g. "E - a - s - e"). To maintain accessibility compliance:
1. The letter spans container uses `aria-hidden="true"`.
2. The main parent container provides the complete unbroken string via `aria-label="<Text>"`.
3. `@media (prefers-color-scheme)` and `@media (prefers-reduced-motion)` ensure full inclusion for high contrast and vestibular motion sensitivity.
