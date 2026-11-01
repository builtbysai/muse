# JunKiyoshi (kiyoshinakauchi) — study

Handle: @kiyoshinakauchi · Site: junkiyoshi.com · Video host: neort.io
Japanese software developer. Hobbyist generative artist working in openFrameworks, posting one finished study with full source code every single day since 2016-12-16 (8-year streak marked 2024-12-16). 3,806 IG posts, ~25.4k followers. Bio: "I am software developer in Japan. My hobby is #generativeart, #creativecoding. I using #openFrameworks. I sharing video and code everyday."

Unlike the #193–#204 film/video chain, this subject's IG handle IS established and his practice is directly codable: every piece ships with its C++ source at junkiyoshi.com/openframeworksYYYYMMDD/ and a 18–20s video hosted on neort.io. Hans saved 4 of his posts; the IG Inspiration BRIEF names him as one of the working creative coders Hans follows.

## 18 works inspected (frames viewed from his neort.io videos)

2026 — the light-grey era (ofBackground(239), black forms, one neon accent):
1. **Torus with Holes** (2026-10-30, today): dark torus on light grey; green wireframe patches cluster in noise bands while cells elsewhere shrink to nothing — holes migrate as the noise field drifts. Source code read in full (see below).
2. **Waterfall of Numbers** (2026-10-15): phosphor-green seven-segment digits on dark, columns cascading at different rates like a departure board.
3. **Flock** (2026-10-10): black dash-marks on light grey, a boids flock with a conspicuous empty wake trailing a slow unseen wanderer.
4. **Heart rate** (2026-10-12): black blobby mass on light grey, concentric white isoline contours ringing its holes — a topographic heartbeat.
5. **Twin ribbon** (2026-10-17): red and cyan ribbons braiding like DNA, spiraling inward to a dark center.
6. **The Torus Tunnel** (2026-09-28): torus with black noise-eaten patches and magenta/orange streak lines wrapping it, light-grey ground.
7. **Tangled Ring** (2026-09-22): black ribbons with blue edges wrapped tangled around a sphere.
8. **Noisy sphere** (2026-09-20): full-bleed black organic blobby network on light grey — noise-displaced cell walls.

2022 — the wireframe/color era (black ground):
9. **Hexagon panels** (2022-11-16): white hexagon tiles clustering into a paisley/comma shape on black, satellite clusters drifting.
10. **Multiple boxes** (2022-11-15): red box with glitchy stepped cutouts revealing rainbow strata — faces eroded by quantized noise.
11. **wind chime** (2022-11-14): nested white wireframe squares rotating at different speeds — hanging panels turning in wind.
12. **turbulence** (2022-11-09): white flow-field hairlines advected inside a circular mask on black.
13. **Rainbow tornado** (2022-11-07): full-bleed rainbow spiral bands, hue cycling with radius, rotating.
14. **Rampaging Ring** (2022-11-05): magenta wireframe ring with noise-driven radial spikes — a spiky circular waveform.
15. **Cage of random walk** (2022-10-28): square frame of thick white worm trails (random walkers) with colored dots wandering inside.
16. **color vortex** (2022-10-16): pinwheel of rainbow gradient bands separated by white lines, full-bleed.
17. **rotate radial** (2022-10-15): tilted disc of concentric white wireframe ellipses on black.

2021 — flat 2D era:
18. **Ripple on hexagon** (2021-11-20): full-bleed hexagonal wireframe grid on black, a ripple traveling through cell sizes.

(2020 works exist on the site — e.g. 2020-01-01 "Happy New Year.. openFrameworks" — but pre-2020 pages use a different URL scheme and the oldest entries 404; the neort embed pipeline starts with the current scheme.)

## Evolution

- **2020–2021: flat 2D studies on black.** Hex grids, ripples, 2D OF drawing. The discipline is already daily; the geometry is still planar.
- **2022: the 3D wireframe era.** ofMesh wireframes of tori, spheres, boxes, rotating cameras, noise displacement. Parallel color experiments (full-bleed rainbow spirals). NFT minting begins on teia.art (objkt links appear Nov 2022). Video length standardizes ~18s.
- **2024: institutional recognition.** 7- and 8-year streak milestones; work exhibited in Ichinomiya (anthology();, ICHINOMIYA ART WALK); visits NEORT++'s CURATION_FREE in Tokyo (Dec 2022, #NEORT posts).
- **2026: the light-grey era.** ofBackground(239) replaces black; forms go black with ONE neon accent (green wireframe, phosphor digits, red/cyan ribbons, blue-edged ribbons). Studies get more sculptural — noise-eaten surfaces, isoline contours, boids. Two October works titled PCDTokyo2026_1/2 (Processing Community Day Tokyo). Videos 20s.

The arc: flat pattern → wireframe volume → noise-sculpted surface. The palette arc: black ground + white lines → rainbow maximalism → restrained light-grey + black + one neon. The constant: one mechanism per day, run to exhaustion, code published.

## The core engine: THE DAILY STUDY

One idea per day, shipped with source. The mechanism IS the piece: pick a single system (a noise field, a hue cycle, a flock, a ripple), set it running inside a tight constraint (square 720×720 canvas, 25fps, ~20 seconds), and let it play to exhaustion. No narrative, no compositional fuss — the watchable behavior is the noise field doing its one thing.

Technical signatures (read from his published code, e.g. Torus with Holes 2026-10-30):
- Square canvas: `ofSetupOpenGL(720, 720, OF_WINDOW)`, `ofSetFrameRate(25)`
- Parametric (u, v) grids over torus/sphere/box formulas; code comments cite 数学デッサン教室 (the math-drawing classroom book lineage — draw math, don't decorate it)
- `ofNoise` sampled in 4D (position × frame) drives per-cell size: cells shrink to zero inside a noise band → holes; faces + wireframe drawn as separate meshes
- Render pipeline fossilized in commented code: dump frames as img_%04d.jpg from frame 150, `ffmpeg` to mp4, upload to neort.io, post to IG. The 18–20s length is a pipeline constant, not an artistic choice — and it became the style
- Dual render habit: dark faces + neon wireframe of the same mesh (the wireframe is the drawing, the faces are the ground)

## Visual signatures

1. The noise-eaten surface: a clean parametric solid with cells deleted where a drifting noise field crosses a threshold band — holes that migrate
2. The hue tornado: full-bleed spiral, hue = f(angle, radius, time), white separators
3. The spiky ring: wireframe circle with noise-driven radial spikes, one neon color
4. The turbulence disc: hairline streaklines advected through a noise field, masked to a circle
5. The worm cage: random walkers as thick trails inside a frame, colored dots loose within
6. The hex ripple: hex lattice with a traveling size/brightness wave
7. The isoline blob: black mass ringed by concentric contour lines on light grey
8. The braid: two ribbons in complementary neons weaving along a spiral path
9. The digit waterfall: seven-segment glyphs as cascading data texture
10. The flock wake: boids as dash marks parting around an invisible slow mover

## Network (evidenced)

1. **Shunsuke Takawo** — the parallel daily-coder. Leads the Processing community in Japan with his own daily coding practice; founded the Japan Generative Art Foundation (JGAF); lead artist of NEORT++'s "Patterns of Flow" (Sept–Oct 2024, a show explicitly about daily-coder generative artists); author of 『数学から創るジェネラティブアート』 (Generative Art from Mathematics) — the book-form of the math-drawing lineage visible in JunKiyoshi's code comments. Same practice, same community, same lineage.
2. **NEORT++** — his publishing infrastructure, not just a gallery: every daily video is hosted on neort.io (the embed pipeline on his site). He attended CURATION_FREE at NEORT++ Tokyo (Dec 2022, posted with #NEORT). The platform is part of the practice.
3. **Processing Community Day Tokyo (Naoto Hieda / Ayumu Nagamatsu)** — two Oct 2026 works are titled PCDTokyo2026_1 and PCDTokyo2026_2, i.e. made for the event. PCD Tokyo was founded by Naoto Hieda with Ayumu Nagamatsu; Nagamatsu also appears in NEORT's dialog() Asia touring network. Community-level tie, evidenced by the titled works.

## How it translates to code (for fly)

The JunKiyoshi skeleton, distilled from his published sources:

```
// square canvas, fixed short duration
size(720, 720); frameRate(25); duration = 20s
// parametric grid over a solid: torus, sphere, box, hex lattice
for (u, v) in grid:
    p = solidPoint(u, v)                       // the clean math shape
    n = noise4(p * k, frame * speed)            // drifting field
    cellSize = n in band ? 0 : full            // THE GATE: holes where band
    draw face (dark) + wireframe (one neon)
// camera: slow orbit or fixed; let the noise do the moving
```

Rules he never breaks: one mechanism per piece; square frame; the field moves, the camera barely does; black ground era = white/neon lines, light-grey era = black forms + one neon accent; never more than one accent color; no text except when glyphs ARE the material (digits); the loop is a fixed 18–20s excerpt of an endless system, not a composed beginning-middle-end.

## What to avoid (his anti-patterns, from 8 years of negatives)

Never: decorative gradients (his rainbows are hue FUNCTIONS, not blends); more than one accent color; photorealism or lighting fakery (his 3D is wireframe + flat faces, never shaded); text labels or titles on screen; camera gymnastics (the motion belongs to the field); beginning-middle-end narrative arcs; mid-tone muddy grounds (black or light grey, never in between).
