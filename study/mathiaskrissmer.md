# Mathias Krissmer (@mathiaskrissmer) — study

Handle: @mathiaskrissmer · Mathias Krißmer, digital artist + architect, Freiburg im Breisgau, Germany
2,853 followers, 224 posts, business account. Saved post: "II000I000I0I0III00, Katalog 217D" (from Hans's "Abstract & Geometric" folder).

## Background

Trained architect who works as a digital artist in the concrete-art / op-art lineage. Affiliations: Stiftung konkrete Kunst (concrete art foundation), konstruktiv.ist virtual exhibitions, EST Art Foundation. Solo exhibition "Kinetische Malerei" (Kinetic Painting) at MUWA, the Museum of Perception, Graz, 14.06.2025 to 09.01.2026. His site krissmer.com is a single page: one work, "III0I0I0I00IIIII00, Katalog 467A, 1920 x 1920 px, 30 sec Loop".

## Style, in specific visual terms

- "Kinetic Paintings": geometric compositions built for digital projection at architectural scale. Wall-to-wall lines in dark rooms, projected, not hung
- Predominantly black and white, occasional single bright color that dramatizes the otherwise monochrome field
- The line is a trail: smooth, luminous curves that read as the path of a moving point through 3D space, projected flat. Thin lines, soft glow, no hard strokes
- Overlapping elliptical loops and long parabolic arcs crossing each other, Moiré-like intersections, optical disorientation
- Binary titles: every work is named as a string of I and 0 characters plus a catalogue number ("Katalog 217D"). The title system is part of the work
- Square format (1920x1920), seamless loops around 30 seconds. His IG tags: concreteart, kineticart, opticalart, generativeart, creativecoding, processing, lightart

## Visual signatures

1. Luminous trails on black: white glowing curves on a black void, long-exposure light-painting quality
2. Rotation implied: nested loops and arcs that look like 3D wireframe rings mid-rotation
3. Scale ambiguity: the same work reads intimate at phone size and architectural at projection size
4. Restraint: usually only 3 to 6 lines; the black field does the heavy lifting
5. The I/0 title: a coded name that doubles as a generative seed

## How it translates to code

- Points moving in 3D (on rings, Lissajous paths, rotating planes), orthographically projected to 2D, rendered as luminous trails with additive glow on #000 or near-black
- Seeded work: the I/0 title string IS the parameter set. Fly can generate a binary title from a seed and map each character to a parameter (amplitude, phase, speed, arc on/off)
- Motion: seamless loops (30s like his, or shorter). Slow rotation around one axis plus slow morph of the curve family. Idle auto-plays; drag rotates the viewpoint or scrubs phase
- Palette discipline: lines white #ffffff or warm white; accent (when used) one flat saturated color, never gradients
- Keep line counts low: 3 to 8 luminous curves. Glow via layered strokes with low alpha, not blur filters (perf on phones)

## Piece prompts

### 1. "Light Orbit" (Krißmer study)
3D rings projected as luminous trails on black. Three great-circle rings of a sphere, each rotating slowly around a different axis, rendered as additive white strokes with soft layered glow. ~28s seamless loop. Drag to rotate the viewpoint; idle auto-rotates. Palette: #050505 ground, #ffffff lines. No UI text, no color.

### 2. "Katalog 217D" (Krißmer study, direct homage)
Binary-seeded arc field: a 14-character I/0 string (generated from the doodle seed) maps to 14 concentric tracks. Each I track draws a luminous white arc of seeded length and phase; each 0 track stays dark. Tracks rotate at speeds proportional to radius, slow drift plus gentle phase wobble so the pattern never quite repeats within the loop. Drag scrubs rotation. Title of the piece is the generated binary string plus its Katalog number. Palette: #000 ground, #ffffff arcs, one track in acid cyan #00e5ff.

### 3. "Wall of Light" (Krißmer study)
Architectural projection feel on a phone: long luminous curves sweep wall-to-wall across the full-bleed canvas like a projector beam on a dark gallery wall. Two or three curves, each a cubic Bezier chain whose control points orbit slowly; curves cross and overlap, brightness peaking at crossings (additive blending). Subtle parallax on tilt/drag. Palette: #050505 ground, #ffffff curves with glow. No borders, no framing, full-bleed.

### 4. "Color Break" (Krißmer study)
Krissmer's monochrome with the occasional dramatizing color: a black field of 5 slowly rotating luminous white elliptical loops. A single saturated accent zone (soft-edged radial field, vermilion #ff2e1f) drifts across the canvas on its own slow path; wherever a white line crosses inside the zone, that segment renders in vermilion, flat, no gradient. Idle loop ~32s. Drag moves the accent zone. Discipline: at most 5 lines, at most one accent, never full saturation across the field.

### 5. "Thirty Seconds" (Krißmer study)
His signature loop length as the concept: a 3D Lissajous point set (7 points, seeded frequencies) projects to 2D; each point leaves a persistent luminous trail, rendered additively on black; trails fade over exactly 30 seconds so the loop is seamless (f(t) == f(t+30)). Drag scrubs time within the loop. Minimal: trails only, no points drawn, no labels. Palette: #000 ground, trails #ffffff with per-point alpha falloff. What to avoid: multiple colors, trail clutter (cap trail length), any visible loop seam.
