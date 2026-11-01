# Etienne Jacob (bleuje) — study

Handle: @bleuje · Site: bleuje.com · GitHub: @Bleuje
French generative artist and mathematics teacher, based in Rennes. The master of the seamless loop.

## Background

Math teacher by day, loop artist by night. Active since ~2016. Huge following on Instagram (@bleuje), Tumblr (necessary-disorder), and X (@etiennejcb). Author of the widely-cited seamless-looping tutorials that taught a generation the technique: "Noise loop / noise propagation", "Making animations with a time variable", "Motion blur template". 200 selected loops archived at bleuje.com (2017-2026). 29 public GitHub repos, works in C++ as well as Processing. Has an interactive-physarum project. Released generative loops on fxhash. Collaborated with jn3008 (Joseff) on a 2025 Gosper-hexagon-cubes animation.

## The core technique (his actual recipe)

Time as a looping parameter. A global t in [0,1) maps to angle 2*pi*t, and every animated quantity is a periodic function of t, so the last frame equals the first: a truly seamless loop.

Then: propagate one periodic motion across space with a spatial phase offset (delay by distance or index). This single move produces traveling waves, ripples, breathing lattices.

Toolkit:
- Cyclic noise: sample Perlin noise on a circle in noise-space, so the randomness itself loops
- Particle systems on trigonometric paths
- Metaballs / isovalue contouring
- Distance-field patterns
- Custom easing and gain functions
- Motion-blur template (adapted from beesandbombs) for buttery frames

## Style, in specific visual terms

- Predominantly high-contrast monochrome: white forms on black, or inverted. Grayscale gradients
- When color appears it is restrained: a single hue ramp or a duotone. The work is about motion and form, not color
- Clean geometric primitives: dot grids, small circles/spheres, lines, filled contours
- Crisp anti-aliased edges, subtle motion blur, occasional soft radial shading faking 3D relief
- Flat backgrounds, no grain
- Hypnotic, mechanical-yet-organic loops of a few seconds: phase-offset waves sweep across grids, particles orbit and re-converge, contours pulse and invert

## Visual signatures

1. The traveling wave: a dot grid where each dot's phase is offset by its distance from center, so waves ripple outward forever
2. The breathing lattice: a grid of shapes that expand and contract in sequence, like a lung made of geometry
3. Particle convergence: particles on trig paths that gather into a form and release, on the loop beat
4. Metaball pulse: blobby contours merging and splitting, black on white or white on black

## How it translates to code

This is the most directly codable artist studied so far. The recipe is explicit:

```
// the bleuje loop skeleton
t = (frame / totalFrames) % 1        // t in [0,1)
angle = t * 2 * PI                    // every motion is periodic in angle
phase = angle - distanceFromCenter * k // spatial phase offset = traveling wave
value = sin(phase)                    // or cyclic noise sampled on a circle
```

- Dot grid wave: grid of circles, radius = base + amp * sin(angle - dist * k). Monochrome. Motion blur via frame blending
- Cyclic noise field: noise sampled at (cos(angle)*r + x*s, sin(angle)*r + y*s) so the field itself loops; contour it or displace a grid with it
- Metaballs: sum of 1/d^2 fields from N blobs on trig paths, threshold the field, fill the contour. Black and white only
- Keep it monochrome. Resist color. The discipline is the style

## Piece prompts

### 1. "Phase" (not yet built)
Dot grid, white on black. Each dot's radius oscillates with phase offset by radial distance: waves ripple outward from center forever. 6s seamless loop. Subtle motion blur. This is the canonical bleuje piece; build it first.

### 2. "Converge" (not yet built)
120 particles on trigonometric paths (integer harmonics of the loop frequency). They gather into a perfect circle at t=0.5, hold for a beat, release. White on black, additive glow. 8s loop.

### 3. "Bloom" (not yet built)
Metaball field: 7 blobs orbiting on Lissajous paths, contour threshold rendered as filled black shapes on white. The blobs merge and split hypnotically. Inverted palette from the others. 6s loop.

### 4. "Field lines" (not yet built)
Distance-field pattern: concentric contour rings around 3 moving seed points, rings interfering where fields overlap. Thin white lines on black, like a topographic map breathing. 8s loop.
