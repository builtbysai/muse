# Artist study: Ruud de Rooij (@ruuddotorg)

Studied 2026-10-14. Source post: involutions piece (media 18106939907188334),
"Generative Art" saved folder, first unstudied post in page order.

## Identity
- Name: Ruud de Rooij. Instagram @ruuddotorg. Dutch name, account country US.
- 3,533 followers / 896 following / 319 posts (2026-10-14). Site: ruud.org
  (near-empty page, no bio on IG). Not verified, personal account.
- Practice: pen-plotter artist (AxiDraw), regular in the monthly #plotparty
  community, did Genuary 2023 (day 1: perfect-loop infinite maze;
  day 10: generative music on Novation Circuit Tracks + Cre8audio East Beast).
- Posts timelapse videos of the plotter drawing, participates in Advent of
  Code (2024 day 10 hiking-map visualization).

## The distinctive thing
Exhaustive combinatorial enumeration as art. He does not sample or randomize:
he picks a discrete mathematical object, generates EVERY configuration of it,
and plots them all as a tidy grid of line-art panels. The count IS the title
of the piece. The caption cites an OEIS sequence number as a certificate of
completeness ("enumerated by OEIS sequence A000085"). The work has the feel
of a beautifully drawn mathematical inventory, a census of possibilities.

## Works analyzed (from ~40 recent posts)
- The 76 involutions of 6 items (saved post): grid of 76 small diagrams, each
  six dots (three filled black, three open white) with lines pairing some
  dots. From no connections to multiple disjoint pairs and crossings.
  1,776 likes, his most-liked recent post.
- Per OEIS A007341: 192 perfect mazes from a 3x3 grid, one large maze holds
  them all.
- The 19 ways to split a 2x2x2 cube into two equal tetracubes.
- 35 shapes from partitioning a 3x3 grid into unequal-area blobs.
- 92 shapes from partitioning a 4x4 grid into two connected blobs (A068392).
- Combinatorics trivia as art: N tetris pieces in a 2x2N rectangle = Nth
  Fibonacci number squared; 2025 ways to pick letters of WONDERFUL from a
  grid (one per row/column) as a New Year piece; 20/76 ways to place sticks
  on a 3x3 point grid; 90/2040 ways to place node pairs with exactly one
  pair per row and column (A1499-ish).
- Snake-in-a-box hypercube (via xkcd 3125), tangled squares, two loops where
  exactly two form a knot, isometric patterns, distorted grids, flow fields,
  concentric "Circles", font experiments, "each tile connects perimeter
  points in a unique way", Advent of Code hiking map.

## Visual signatures (what makes it his, not generic generative art)
1. **The full census.** Never 20 random samples. If the object has 76
   members, all 76 are shown, one per panel, on a strict grid.
2. **Dots: filled vs open.** The saved post's atom is six dots, three filled
   black and three white with black outlines, connected by thin straight or
   slightly curved pairing lines. Minimal ink, no shading.
3. **Monoline pen-plotter linework on light paper.** Everything reads as
   single-pass pen work: uniform stroke weight, no fills except the dots,
   no decoration. Occasional single accent color (a Valentine hearts row,
   four colored variations of one theme); default is black ink.
4. **The count as caption.** Titles are statements of number + object +
   enumeration ("The 19 ways to split a 2x2x2 cube into two equal
   tetracubes"). The OEIS citation is the signature flourish.
5. **The plot is the artifact.** He posts timelapse videos of the AxiDraw
   drawing the piece; the physical line quality is part of the work.

## How the style translates to code
- **Enumerate, don't sample.** Use backtracking/recursion to generate the
  complete configuration list (involutions, matchings, spanning trees,
  polyominoes, cube nets), then lay them out on a grid, one panel each.
  Completeness is the concept; the algorithm must provably cover all cases.
- **Fixed dot placement.** Choose a canonical node layout (points on a
  circle, or a 3x2 / 4x4 lattice). Dots are small circles: filled #1a1a1a
  or white with #1a1a1a outline. Pair/edge lines are single thin strokes;
  keep them straight or barely curved so they read as plotted lines.
- **Grid layout math.** panels = configurations; cols = ceil(sqrt(n)) with
  aspect tuned to the page; generous margins like a print on paper.
- **Palette.** Ground near-paper #f4f1ea or #efe9dc, ink #1a1a1a, accent
  at most one flat color (rust #b5542d or indigo #2b3a67). No gradients,
  no glow, no photorealism.
- **Plotter honesty in digital pieces.** Thin strokes, no thick outlines,
  avoid fills larger than dots. The digital piece should look like it
  COULD be plotted in one pass.

## Fit for the doodle pipeline
Hans's taste (from the 2026-10-13 direction): motion loops, motion, 3D are
the direction; static gets discarded. Ruud's static grids become pieces by
turning enumeration into time: one hero panel cycling through all
configurations (a net folding, edges regrowing, chords retargeting), or the
full grid as a scan that sweeps row by row. Touch/drag scrubs the
enumeration; idle auto-plays the loop. No click-to-reload.
