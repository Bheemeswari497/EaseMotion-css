# Quantum Teleportation Photon-Number Resolving Detectors (PNRD-110)

An ultra-complex, high-performance pure CSS component visualizing a Superconducting Nanowire Photon-Number Resolving Detector (SNSPD PNRD-110) array utilized in quantum teleportation protocols and Bell State Measurement (BSM) telemetry.

---

## Table of Contents

1. [Overview & What it Does](#1-overview--what-it-does)
2. [Quantum Physics & Mathematical Background](#2-quantum-physics--mathematical-background)
   - [Photon-Number Resolving Detection (PNRD)](#photon-number-resolving-detection-pnrd)
   - [Quantum Teleportation & Bell State Measurement](#quantum-teleportation--bell-state-measurement)
3. [Component Architecture & HTML Structure](#3-component-architecture--html-structure)
4. [CSS Design System & Keyframe Breakdown](#4-css-design-system--keyframe-breakdown)
   - [CSS Custom Properties](#css-custom-properties)
   - [Hardware Acceleration & Performance Tokens](#hardware-acceleration--performance-tokens)
   - [Keyframe Animations](#keyframe-animations)
5. [Interactive Execution States](#5-interactive-execution-states)
6. [Accessibility & Reduced Motion Compliance](#6-accessibility--reduced-motion-compliance)
7. [Installation & Usage Example](#7-installation--usage-example)
8. [Browser Compatibility & Benchmarks](#8-browser-compatibility--benchmarks)

---

## 1. Overview & What it Does

The **Quantum Teleportation Photon-Number Resolving Detectors (PNRD-110)** component provides a fully-rendered, animated visualization of an advanced quantum optical detector module. It features:

- **Superconducting Nanowire Single-Photon Detector (SNSPD) Arrays**: Real-time channel telemetry monitoring cryogenic temperatures (4.2 K), timing jitter (0.02 ns bias), and detection efficiency (99.8% ETA).
- **Fock State Number Counter**: Dynamic pure CSS state readouts displaying quantum state vectors ($|0\rangle$, $|\psi^+\rangle$, $|n=2\rangle$, $|n=4\rangle$).
- **Triple-Ring Quantum Flux Visualizer**: Counter-rotating boundary tracks representing spatial mode overlap and polarization beam splitting.
- **Bell State Measurement (BSM) Core**: Concentric glowing core with pulsating orb flux.
- **Pure CSS Execution Controls**: Radio input triggered state switches between Standby, Entanglement Lock, Teleportation Stream, and PNRD Resolution modes without JavaScript.

---

## 2. Quantum Physics & Mathematical Background

### Photon-Number Resolving Detection (PNRD)

Conventional single-photon detectors (such as avalanche photodiodes) operate in a click/no-click regime, unable to distinguish between the arrival of one photon and multiple photons simultaneously. Photon-Number Resolving Detectors (PNRDs) resolve the exact photon number $n$ in an incident optical mode:

$$\hat{N} |n\rangle = n |n\rangle$$

For a multi-photon Fock state input $|n\rangle$, the PNRD probability distribution follows:

$$P(n) = \frac{\langle \hat{N} \rangle^n}{n!} e^{-\langle \hat{N} \rangle}$$

### Quantum Teleportation & Bell State Measurement

In a standard quantum teleportation protocol between Alice and Bob, an unknown quantum state $|\psi\rangle = \alpha |0\rangle + \beta |1\rangle$ is transmitted using an entangled EPR pair $|\Phi^+\rangle$:

$$|\Phi^+\rangle = \frac{1}{\sqrt{2}} \left( |0\rangle_A |0\rangle_B + |1\rangle_A |1\rangle_B \right)$$

The joint state of the input photon and Alice's half of the entangled pair is projected onto the four maximally entangled Bell states via joint PNRD detection:

$$|\Psi^\pm\rangle = \frac{1}{\sqrt{2}} \left( |01\rangle \pm |10\rangle \right)$$

$$|\Phi^\pm\rangle = \frac{1}{\sqrt{2}} \left( |00\rangle \pm |11\rangle \right)$$

The PNRD-110 module registers photon coincidence counts across channels CH-01 to CH-04 to resolve the exact Bell state for feed-forward unitary transformation.

---

## 3. Component Architecture & HTML Structure

The component relies on semantic HTML5 containers nested for 3D stacking contexts and spatial alignment:

```html
<main class="pnrd-dashboard-wrapper">
  <header class="pnrd-header">
    <div class="header-badge">
      <span class="badge-dot"></span>
      <span class="badge-text">PNRD-110 QUANTUM MODULE</span>
    </div>
    <h1>Quantum Teleportation Detector</h1>
    <p>Superconducting Nanowire Photon-Number Resolving Detector Array...</p>
  </header>

  <section class="pnrd-main-stage">
    <!-- State Controls -->
    <input type="radio" name="pnrd-state" id="pnrd-entangle" class="pnrd-radio" checked>

    <div class="quantum-detector-chassis">
      <!-- Grid & Rings -->
      <div class="detector-ring-assembly">
        <div class="ring-track ring-outer"></div>
        <div class="ring-track ring-middle"></div>
        <div class="ring-track ring-inner"></div>

        <div class="quantum-core-chamber">
          <div class="fock-state-display">
            <span class="fock-value">|ψ⁺⟩ (Bell Pair)</span>
          </div>
        </div>
      </div>

      <!-- Sensor Grid -->
      <div class="pnrd-sensor-grid">
        <div class="sensor-channel ch-1">...</div>
        <div class="sensor-channel ch-2">...</div>
      </div>
    </div>
  </section>
</main>
```

---

## 4. CSS Design System & Keyframe Breakdown

### CSS Custom Properties

The component utilizes scoped HSL/HEX custom properties for light and dark theme adaptation:

```css
:root {
  --bg-color: #03131a;
  --panel-bg: #061e27;
  --text-main: #f0fdf4;
  --text-muted: #6ee7b7;
  --border-color: rgba(16, 185, 129, 0.25);
  
  --emerald-bright: #10b981;
  --emerald-glow: rgba(16, 185, 129, 0.45);
  --cyan-bright: #06b6d4;
  --cyan-glow: rgba(6, 182, 212, 0.4);
  --teal-accent: #14b8a6;
  
  --shadow-outer: 0 20px 40px rgba(0, 0, 0, 0.6), 0 0 30px rgba(16, 185, 129, 0.15);
  --font-family: 'Outfit', sans-serif;
  --font-mono: 'Space Mono', monospace;
}
```

### Hardware Acceleration & Performance Tokens

To ensure 60fps rendering during continuous rotations:
- `will-change: transform, opacity, filter` is applied to active keyframe elements.
- `transform: translate3d(0, 0, 0)` forces GPU compositing layers.
- Avoided `box-shadow` animations on large containers during rotation loops to prevent repaints.

### Keyframe Animations

1. **`quantumRingSpin`**: Rotates the concentric boundary tracks:
   ```css
   @keyframes quantumRingSpin {
     0% { transform: rotate(0deg); }
     100% { transform: rotate(360deg); }
   }
   ```
2. **`orbPulse`**: Pulsating quantum core flux orb:
   ```css
   @keyframes orbPulse {
     0% { transform: scale(0.85); filter: drop-shadow(0 0 4px var(--emerald-bright)); }
     100% { transform: scale(1.15); filter: drop-shadow(0 0 16px var(--cyan-bright)); }
   }
   ```
3. **`teleportGlowPulse`**: Teleportation activation beam glow:
   ```css
   @keyframes teleportGlowPulse {
     0% { box-shadow: 0 0 12px var(--emerald-glow); }
     100% { box-shadow: 0 0 32px var(--cyan-bright), inset 0 0 16px var(--cyan-glow); }
   }
   ```

---

## 5. Interactive Execution States

| Mode | Radio ID | Core Fock State | Sensor Channel Bar Width | Status Telemetry |
|---|---|---|---|---|
| **Standby** | `#pnrd-idle` | `|0⟩ (Vacuum)` | 25% | `SYSTEM STANDBY` |
| **Entangle** | `#pnrd-entangle` | `|ψ⁺⟩ (Bell Pair)` | 75% | `ENTANGLEMENT LOCKED` |
| **Teleport** | `#pnrd-teleport` | `|n=2⟩ (Beam Teleport)` | 90% | `TELEPORTATION ACTIVE` |
| **Resolve** | `#pnrd-resolve` | `|n=4⟩ (PNRD Resolved)` | 100% | `PHOTON COUNT RESOLVED` |

---

## 6. Accessibility & Reduced Motion Compliance

- **Keyboard Navigation**: All control labels have `tabindex="0"` and visible focus rings (`outline: 2px solid var(--emerald-bright)`).
- **ARIA Attributes**: `aria-label` attributes provide semantic context for assistive technologies.
- **Prefers Reduced Motion**:
  ```css
  @media (prefers-reduced-motion: reduce) {
    .badge-dot,
    .ring-track,
    .orb-core-pulse,
    .orb-ring-spin,
    .quantum-core-chamber,
    .ch-bar,
    .pnrd-btn {
      animation: none !important;
      transition: none !important;
    }
  }
  ```

---

## 7. Installation & Usage Example

Simply include `style.css` in your HTML document:

```html
<link rel="stylesheet" href="submissions/examples/quantum-teleportation-photon-number-resolving-detectors-110/style.css">
```

Copy the markup from `demo.html` into your project dashboard or quantum computing visualizer.

---

## 8. Browser Compatibility & Benchmarks

- **Chrome / Chromium**: 100+ (Full hardware acceleration)
- **Firefox**: 95+ (Smooth CSS grid & keyframe performance)
- **Safari**: 14+ (Full WebKit transform support)
- **Mobile Safari / Chrome**: Tested responsive down to 320px screen widths.
