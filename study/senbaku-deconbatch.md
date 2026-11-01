# Senbaku (センバク / deconbatch) — study #207

**Identity:** Japanese creative coder behind "deconbatch's Land of 1000 Creative Codings"
(deconbatch.com, Blogger, 150 posts, 2019-03 → 2026-09). Twitter/X: @deconbatch.
Illustration background; first speaker at Processing Community Hangout Japan vol.1
(May 2020). Works mainly in Processing (Java) and p5.js. Every post ships full
source code, usually GPL3/CC0. No accessible Instagram handle found (account-search
for likely variants returned no match); this is a WEB-ROUTE study via the blog.

**Core engine: THE RESOURCEFUL TRANSLATOR + THE POOR MAN'S SUBSTITUTE.**
She takes an effect seen elsewhere — Takawo's `drawingContext.filter` blur, Delaunay's
Orphism, Richter's 4900 Colors, textbook DLA, Turing patterns — and rebuilds it from
the poorest means available in her stack, publishing the code. The translation gap
IS the art: "My loving Processing must get over the p5.js drawingContext!",
"The Beauty of Mistakes: My Julia Set 'Fail'", "Poor Man's DLA." Her stated
pleasure: "I love to deal resourcefully with how can I make something with the
available stuff only... this delight brings me the real pleasures of creative coding."

**Signature devices (observed, code-verified):**
1. **Rhythmic shooting instead of randomness.** Poor Man's DLA (2019-10, revisited
   2026-02): cells fired in straight lines from an angle that doubles each step
   (`entryR += entryR; entryR %= TWO_PI`) toward a seed ring; collision sticks the
   cell. Final iteration uses NO `random()` at all — pure rhythm grows moss that
   looks like real diffusion-limited aggregation. "Complexity doesn't always require
   randomness; sometimes, pure rhythm is enough."
2. **Stacked transparent layers with per-layer blur.** To fake p5.js's
   `drawingContext.filter = "blur(...)"` in Processing: 12 transparent PGraphics
   layers, random circles per layer, `filter(BLUR, random)` per layer, composited.
   Applied twist: the black-halo bug (transparent background RGB 0,0,0 bleeding
   into blurred edges) diagnosed and turned into *colored shadows* — blur radius as
   a color-delivery mechanism.
3. **Vector-field watercolor.** Particles advected through a noise/attractor field
   with high-transparency strokes; thousands of soft overlapping circles become
   watercolor washes (Walk Between Raindrops, 2019-08; greens/teals on warm paper,
   with node-garden line clusters knitting through the wash).
4. **Characteristic circle packing.** (2021-07) Dense packing where each circle gets
   "character" — faces, rings, hatching, varied fills — plus a big organic
   negative-space void in the center holding a symmetric fern/plant motif. Packing
   is the substrate; character is the content.
5. **Environmental Game of Life.** "Castle Walls" (2019-09, refactored 2026-09):
   cells hold continuous health 0–100, a *global* envFactor sweeps 0.1→0.8 so the
   cause-and-effect is visibly obvious (2026 refactor explicitly fixes the 2019
   version's "fatal lackluster visual impact"), corner-rounding joins when full-life
   neighbors touch, offline frame rendering. Rules bend to the environment.

**Evolution (early vs recent):**
- **2019 (blog launch, Mar):** near-daily Processing sketches with whimsical
  song-title English names ("Neckar…", "Blood of the Sun", "Broken Tea Cup").
  Vector fields, node gardens, recurrence formulas, Poor Man's DLA, seamless
  Twitter loops, Tsubuyaki Processing explainers. Output-first, code-included.
- **2020:** community era — PCJ Hangout vol.1 speaker, TDSW x PCJ show, Tanabata
  exhibit animation; Worley/Perlin noise studies; "adorable sketches" illustration
  pole (ghost-sheet folklore figures per #206 network notes).
- **2021:** art-history homages (Vera Molnár's (Des)Ordres, Delaunay later),
  "Garg" — a p5.js library customizing Takawo's Generativemasks (Oct 2021);
  rotary-movement compositions (epicycle rosettes).
- **2022:** systems year — Truchet, Turing/reaction-diffusion, Moiré "Big Holes"
  (circle×square interference), Richter 4900 Colors as nested outlined squares,
  the blur translation project, hand-drawn organic rectangles (jittered corners,
  Redon reference), "composition with the code" (continuous multi-line zigzag
  paths with rounded U-turns).
- **2023:** mistakes-as-method (Julia Set fail kept and published), custom
  p5.Vector attraction/repulsion physics, saveGif workflow tutorials.
- **2025–2026:** "Creative Coding Cooking in 3 Minutes" + p5.js/Processing code
  examples; SEO-polished titles; code-remix culture ("The Joy of Modifying Existing
  Sketches"); revisiting and refactoring decade-old works with hindsight
  (Castle Walls v0.2). Less daily-sketch energy, more teaching — the translator
  became the teacher.

**Network (evidenced):**
1. **Shunsuke Takawo** — two-way code exchange: she remixed his
   `drawingContext.filter` blur tweet into Processing (Sept 2022); he praised her
   applied work; she wrote the 'Garg' library for his Generativemasks (Oct 2021).
2. **Processing Community Japan / Naoto Hieda** — first speaker at PCJ Hangout
   vol.1 (naotohieda.com: "Given her background in illustration, she creates
   adorable sketches and also incorporates techniques from the Coding Train");
   TDSW x PCJ exhibitor (Oct 2020); NEORT Patterns of Flow co-exhibitor.
3. **The Coding Train (Daniel Shiffman)** — cited as her technique source for
   pushing illustration past its boundary (per Hieda's writeup).
4. **@emeen231** — tipped her off to the transparent-background black-halo cause
   in the blur investigation (deconbatch.com/2022/10).
5. Art-history one-way references: Delaunay, Richter, Molnár, Turing.

**Works visually inspected (24 sampled, 20 inspected):** Poor Man's DLA radial
moss ring (green→rust age gradient); vector-field watercolor wash (greens/teals,
node-garden clusters); De Jong attractor "flesh" tentacle creature
(reds/pinks, paper ground); Moiré circle×square interference; structured node
garden (concentric blue-green chord rings); characteristic circle packing with
faces + central fern void; rotary epicycle rosette; Perlin-polar rainbow torus;
Julia Set "fail" dotted scatter ring; blur-layer circle stacks; continuous
zigzag multi-line path; Richter reinterpretation (nested outlined squares);
Delaunay homage (reference painting); hand-drawn rectangles (Redon reference);
Castle Walls env-GoL frames; p5.Vector physics diagrams; Creative Surrender
polar diagrams. Full code read: Poor Man's DLA, Castle Walls v0.2, blur stack.

**Palette habits:** HSB-first; Processing grey (90 brightness) grounds; watercolor
era in sage/teal on warm paper; attractor creatures in flesh reds/pinks/yellows;
teaching diagrams in single-hue line work. Restraint by construction: one idea,
one mechanism, one palette per post.

**Interaction stance:** almost entirely watch-only generative loops; the
"interaction" is the reader remixing published code. Tap-to-reseed belongs where
a new rhythm/character set appears; drag belongs where a continuous parameter
(blur radius, moiré offset) is the instrument.
