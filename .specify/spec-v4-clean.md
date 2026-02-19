# Sum Calculator v4 (Clean Run) — Fart Sound Effect

## Overview
Add a short fart sound on successful calculation, playing alongside the existing fireworks animation.

## Requirements

1. On successful calculation, play a fart sound (~1-2 seconds)
2. Audio synthesized via Web Audio API — no external files
3. Plays alongside fireworks (same trigger point: right before `launchFireworks()`)
4. Error cases (invalid input, divide by zero) do NOT play sound
5. Works on desktop and mobile browsers (user gesture from Calculate click satisfies autoplay policy)
6. All v3 functionality unchanged (operations, fireworks, error handling, Enter key)
7. Single `index.html`, vanilla JS only

## Implementation
- Create AudioContext lazily on first use
- Synthesize fart: low-frequency sawtooth oscillator sweeping ~80Hz→30Hz over ~0.7s
- Layer with filtered brown noise for texture
- Gain envelope: quick attack, sustain, fade out
- Total duration ~0.7-1.0 seconds
- Call `playFartSound()` right before `launchFireworks()` in the calculate handler

## Files
- `index.html` — add fart synth function, wire into calc success path
