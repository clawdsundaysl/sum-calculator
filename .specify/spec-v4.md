# Sum Calculator v4 — Fart Sound Effect Spec

## Overview
Add a short fart sound effect on successful calculation, playing alongside fireworks.

## Requirements

### Functional
1. On successful calculation, play a fart sound (~1-2 seconds)
2. Sound plays alongside the fireworks animation (same trigger point)
3. Error cases (invalid input, divide by zero) do NOT play sound
4. Audio generated via Web Audio API synthesis (oscillator with frequency sweep + noise) — no external files, no base64 audio
5. All v3 functionality unchanged

### Constraints
- No external audio files
- Vanilla JS only
- Single `index.html`
- Sound must work on desktop and mobile (user gesture from Calculate click qualifies)

### Implementation Notes
- Use Web Audio API: create an AudioContext on first user click
- Fart = low-frequency oscillator (80-40Hz sweep down) with brownian noise, short duration ~0.5-1s
- Apply gain envelope: quick attack, medium sustain, fade out
- Call the sound function right before/alongside `launchFireworks()`

## Files to Modify
- `index.html` — add Web Audio API fart synth function, trigger on successful calc
