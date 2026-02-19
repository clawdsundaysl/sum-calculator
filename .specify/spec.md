# Sum Calculator v3 — Fireworks Animation Spec

## Overview
Add a fireworks particle animation triggered on successful calculation. Extends existing v2 calculator.

## Requirements

### Functional
1. On successful calculation (valid inputs, no divide-by-zero), play a fireworks animation for 2-3 seconds
2. Animation overlays the page via a full-viewport Canvas element (doesn't displace content)
3. Result number remains clearly readable during and after animation
4. Error cases (invalid input, divide by zero) do NOT trigger fireworks
5. Animation auto-stops after 2-3 seconds; canvas is cleaned up
6. All v2 functionality unchanged: four operations (+−×÷), error handling, Enter key, decimal/negative support

### Non-Functional
- Smooth 30fps+ on average hardware
- Vanilla JS + CSS/Canvas only — no external animation libraries
- Single `index.html` maintained
- No sound effects

### Implementation Notes
- Add a `<canvas>` element positioned `fixed` over the viewport with `pointer-events: none`
- Fireworks = particles that launch upward, explode into colorful sparks, fade out with gravity
- Use `requestAnimationFrame` for smooth rendering
- Multiple rockets (3-5) launched in quick succession with random positions
- Each rocket explodes into 30-50 particles with random colors, velocities, and fade rates
- After all particles fade, clear canvas and hide it

## Files to Modify
- `index.html` — add canvas element, fireworks JS logic, trigger on successful calc

## Acceptance Criteria
- [x] Clicking Calculate with valid inputs triggers visible fireworks
- [x] Fireworks last 2-3 seconds then stop automatically
- [x] Result number readable during animation
- [x] Error cases do NOT trigger fireworks
- [x] No performance degradation
- [x] All v2 functionality unchanged
- [x] Works on desktop and mobile browsers
