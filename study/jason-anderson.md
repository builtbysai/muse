# Jason Anderson — study

Handle: @jasonandersonart · Site: jasonandersonartist.com · Based in Dorset, UK
Contemporary landscape painter, 255k IG followers, 592 posts. Sells out consistently.

## Background

Started as a stained-glass apprentice. Worked on restoration at York Minster, Gloucester, and Wells cathedrals. That training is the whole engine of his work: he composes like stained glass, breaking subjects into a jigsaw of bold color blocks. Did the cover art for Billie Eilish's "Everything I Wanted" (2019).

## Style, in specific visual terms

- Thick impasto laid with a palette knife, paint standing proud of the surface like relief sculpture
- Mosaic composition: the canvas reads as fractured shards of color, each shard a single confident daub
- Landscapes, harbors, skylines, and seascapes abstracted into luminous color fields, never literal
- Strong palettes: sunsets in tangerine and violet, seas in teal and deep blue, skies in saturated bands
- From a distance: an impressionistic landscape. Up close: pure abstraction, color shapes with no subject
- Light plays across the paint ridges, so the painting changes as you move past it

## Visual signatures

1. The jigsaw fracture: no soft blending, every color region has a hard knife-cut edge
2. The sun band: a horizontal blaze of warm color cutting through cooler surroundings
3. Knife direction as texture: each daub's stroke direction visible, giving the surface a woven grain
4. Dark leading between cells, like the lead came in stained glass

## How it translates to code

- Voronoi tessellation for the jigsaw cells, weighted by a seeded landscape layout (sky band, sun band, land band)
- Each cell filled with a palette-knife "blade": an elongated rounded shape in a bold color, with a darker leading edge
- Simulated impasto: per-cell ridge highlight along the blade direction, shadow on the lee side
- Raking light: animate a light angle orbiting the canvas; recompute each cell's highlight alpha from the knife-to-light angle. This is the "walking past the painting" effect and it is the motion of the piece
- Palette per piece: pick a landscape mood (seascape, sunset, harbor dusk) and pull 6-8 colors from it

## Piece prompts

### 1. "Impasto" (built as No.9079)
Stained-glass jigsaw Voronoi cells in landscape bands. Raking light orbits; highlights slide across ridges. Drag swings the light toward the pointer. Double-tap reseeds.

### 2. "Swell" (built as No.9081)
Seascape mood: pale-blue sky cells, foam-white horizon band, teal-to-black water. Same engine, different palette seed.

### 3. "Afterglow" (built as No.9082)
Sunset mood: violet-magenta sky, orange-gold sun band, dark plum land. Same engine, different palette seed.

### 4. Harbor dusk (not yet built)
Mood: deep indigo water, amber window-lights as small bright cells scattered in the lower third, slate sky. Small cells for the lights, large cells for water. Light orbit slow.
