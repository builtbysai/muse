# Lucien Groen — study

Handle: @luciengroen · Arnhem, Netherlands
Geometric abstract painter, oil on canvas, working since the 1980s. 10.8k followers, 1527 posts. Shows at De Pont museum, Tilburg.

## Background

Dutch concrete-art lineage. Decades of geometric abstraction, minimal and maximal by turns. Posts studio views, series from 1986 to 2026, museum visits. The work is patient: hard-edge geometry in oil, built up over long series.

## Style, in specific visual terms

- Hard-edge geometric abstraction: rectangles, circles, triangles, bars, arcs
- Flat color, no texture, no blending. Crisp edges
- Muted, thoughtful palettes: stone greys, bone, ochre, with one bold accent (vermilion, deep teal)
- Grid-based or architecturally structured compositions
- Restraint is the aesthetic: negative space does as much work as the shapes
- Bauhaus / De Stijl / concrete art tradition, but contemporary and personal

## Visual signatures

1. The single accent: a field of muted shapes with exactly one loud color
2. Architectural placement: shapes sit like floor plans or elevations, deliberate and still
3. Flatness as depth: overlapping flat shapes create space without any shading

## How it translates to code

- Rule-based geometric composition on a strict grid (5x7, 6x6, etc.)
- Flat fills, zero gradients, crisp anti-aliased edges
- Muted palette array + one accent color, assigned by seeded rule
- Motion: slow reconfiguration. One shape glides to a new grid cell every 8-12 seconds. Shapes breathe subtly (scale 1.0 to 1.03). Tap triggers an immediate reconfiguration
- The beauty is in proportion and relationship, so keep counts low: 8-15 shapes

## Piece prompts

### 1. "Concrete" (built as No.9080)
Strict 5x7 grid, mixed shapes (rectangles, circles, triangles, bars) in muted stone tones on warm paper. One shape reconfigures every ~9s. Tap to trigger.

### 2. "Orbit" (built as No.9085, replaced by "Fission" after Hans verdict)
Circles and arcs: concentric rings, quarter-arcs, dot constellations. Rejected by Hans.

### 3. "Shear" (built as No.9086)
Diagonals: bars and triangular wedges along a diagonal energy band, deliberate negative space. Restrained inks, one deep teal accent. Tap flips nearest element.

### 4. "Fission" (replaced "Orbit" as No.9085)
Recursive subdivision: the canvas binary-space-partitions into a Mondrian-adjacent grid of flat muted cells, one or two vermilion accents. Cells split and merge on a slow cycle. Tap a cell to split it.

### 5. Bars (not yet built)
Horizontal/vertical bars of varying widths like a beautiful barcode. Muted greys with one ochre bar. Bars slowly resize; the composition never repeats exactly.
