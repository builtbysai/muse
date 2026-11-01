# Joseff (jn3008) — study

Handle: @jn3008.art · Paris, France
"Artist working with code." 7.5k followers, 64 posts. Already a generative artist, which makes him direct kin.

## Background

Paris-based code artist. Small, dense feed: every post is a loop or animation. Collaborates with other loop artists (notably @etinjcb and bleuje). Part of the seamless-loop scene alongside bleuje and beesandbombs.

## Style, in specific visual terms

- Impossible geometry: Penrose triangles, impossible rings, impossible drops, drawn as clean beveled beams
- Perfect visual loops, usually a few seconds, often with audio
- Particle systems: luminous particles converging into forms (rings, shapes) then dissolving
- 3D forms: cuboctahedrons, polyhedra, rendered clean
- Dark backgrounds, luminous elements. Monochrome or restrained color
- The "impossible" objects are drawn with precise over/under ordering so depth can never resolve

## Visual signatures

1. The impossible object: geometric paradox rendered so cleanly you keep trying to resolve it
2. The pulse: a bright element traveling an impossible perimeter forever
3. Particle convergence: chaos organizing into perfect form, holding, dissolving

## How it translates to code

- Impossible objects: draw beams with explicit over/under layering, cycle the layer order so no frame has consistent depth. Animate a highlight traveling the perimeter
- Particle convergence: N particles on harmonic paths (integer multiples of loop frequency so the loop is seamless), an attractor field that phases in and out on the loop cycle
- Seamless loops: all motion as functions of t in [0,1), mapped to 2*pi*t. This is the bleuje recipe and Joseff uses it too
- Keep palettes dark + luminous: near-black ground, one or two glow colors, additive blending

## Piece prompts

### 1. "Strides" (built as No.9083, replaced by "Undertow" after Hans verdict)
Penrose triangle, amber pulse traveling the impossible perimeter. Rejected by Hans.

### 2. "Murmur" (built as No.9084)
380 luminous cyan particles on black, harmonic field, coalescing into a rotating glowing ring then dissolving. 14s seamless loop. Touch stirs without breaking the loop.

### 3. "Undertow" (replaced "Strides" as No.9083)
Curl-noise flow field: hundreds of luminous particles drawing glowing trails, teal-to-indigo streamlines converging and shearing. 24s periodic cycle. Touch stirs with tangential swirl.

### 4. Impossible drop (not yet built)
An impossible waterfall/looping drop: water that falls forever in a closed circuit, Escher-style, rendered as clean luminous streams on black. The flow never resolves.

### 5. Convergence study (not yet built)
Particles spelling and unspelling geometric forms: triangle, square, hexagon, in sequence, each held for one loop beat then dissolved. Restrained white-on-black.
