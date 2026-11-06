# Sam Palmer: Study Notes

**Site:** Sam Palmer, London. Software developer at QuaisrLabs. Previously a PhD student in computational physics at Imperial College London. Art under @sjpalmer1994 (X, 2K followers) and @sjpalmer1994@genart.social (fediverse); main account @sampalmmer1994. GitHub: sp94. Nine objkts minted on Tezos (hicetnunc) in 2021, all square looping GIFs.

**Doorway:** Hop from the zz85/BlurSpline koi study: where Koo bends a fish along a spine in a shader, Palmer bends a whole grid along a field in Processing. Both are code artists whose subject is a system, not a picture — but Koo's system is a body that swims, and Palmer's is a field that deforms. This study is the field half of that pair.

**Depth:** Inspected 9 objkts on-chain via the Tezos API (token IDs, names, descriptions, tags, MIME types, artifact URIs); viewed 8 of them as still thumbnails (HashQuine hicetnunc archive) and 1 Sierpinski GIF frame (Tenor CDN, 20s, 640x640). Read his GitHub repo list (10 repos, all computational physics). Read his X bios and the hicetnunc rating page. NOT accessible: the objkt GIFs in motion (IPFS gateways blocked in this sandbox, so motion is inferred from titles, stills, and format, not observed); the full X timelines (logged-out X shows only 5 posts; the art handle's timeline was not viewable); the genart.social profile (JS-heavy, no extractable content); his Processing/Julia source code (not public — GitHub holds only physics repos). The "Sunrise" #5722 thumbnail returned a 404. Nothing here is invented; where motion is inferred rather than seen, it is marked as such.

## The warped grid — a regular tessellation deformed by a smooth field

Every objkt is the same construction: a perfectly regular grid of identical tiles, deformed by a smooth mathematical field that varies with position and time. The grid is the constant; the field is the variable, and the field is what makes each piece distinct.

- **Ebb and flow (#2190):** a grid of rounded squares in blue/cyan, displaced by a traveling wave. In the still, the tiles swell and recede in a sinusoidal pattern, like a wave passing through a tiled floor. The wave is the subject; the tiles are just the medium that makes it visible.
- **Rebound (#27873):** a pink/magenta checkerboard, warped as if pushed by a radial force — the squares bulge and curve, the grid inhales. The title says the motion: a bounce, a spring returning.
- **Lurch (#29355):** a black-and-white checkerboard, violently sheared. The squares stretch and compress in a wave with a visible fold at the center where the grid collapses inward. The high contrast makes the warp unavoidable — this is the most aggressive deformation in the set.
- **Churn (#30022):** rounded squares in coral, tilted and displaced in a rotational field. The squares swirl around centers like a liquid being stirred. The "churn" is a vortex.
- **Crossover (#28323):** plus-sign/cross tiles in soft mint on cream, interlocking. The crosses slide past each other — a woven lattice. The quietest piece in the set; the deformation is subtle, almost a texture.
- **Relay (#34043):** orange circles at grid points with white squares between them. A clean lattice of nodes. The title implies the motion: a signal passing cell to cell, like a baton.

The mechanism is a field function f(x, y, t) applied to a grid. The grid's regularity is what makes the field legible — if the grid were irregular, you could not see the wave. The discipline is: keep the grid perfect, let the field do all the work.

**Takeaway:** A regular grid + a smooth time-varying deformation field is a complete generative system. The grid is the paper; the field is the drawing. To make a piece from this, pick one field (traveling wave, radial pulse, vortex, shear) and let it deform a perfect tessellation — do not decorate the tiles, do not vary the grid.

## The perfect loop — periodic time as the medium

All nine objkts are square looping GIFs, 750x750, at 50fps (33fps for the two Blender pieces). The loop is not a delivery format; it is the medium. The work is meant to be watched on repeat, with no beginning and no end.

The construction is standard for a seamless loop: every time-dependent term is a periodic function whose period divides the loop duration — sin(2*pi*t/T) and its harmonics — so that at t = T the field returns exactly to its start state. The loop closes because the math closes. His pinned X post (Jan 31, 2021) tags the work #PerfectLoop, and the format is consistent across all nine mints: same square, same frame rate, same GIF.

**Takeaway:** A seamless loop is a constraint on the time function, not on the picture. Make every time term periodic with a period that divides the loop length, and the loop will close by construction. The loop length is a compositional choice — 50fps at 750x750 is his house format, and the consistency of format across the whole body of work is part of the identity.

## One hue + white — palette as discipline

Each piece uses exactly one hue plus white/cream, or black plus white. Blue/cyan (Ebb and flow), coral/salmon (Inflation, Churn), pink/magenta (Rebound), mint (Crossover), orange (Relay), black/white (Lurch). The color is a flat fill, never a gradient — except Sunrise, which is a gradient across a 3D field and is the exception that proves the rule.

The restraint is functional: color does not compete with the field. If the tiles were multicolored, the eye would read color variation instead of deformation. By keeping color to a single hue, the only thing that varies is the shape of the grid — and therefore the only thing you see is the field.

**Takeaway:** One hue + white (or black + white) is enough. The color is a carrier, not a subject. Pick a hue that fits the process named in the title (cool blue for a tide, warm coral for an expansion, black/white for a violent shear) and let the deformation carry the piece.

## Physics vocabulary as titles — the work is a process, not a picture

The titles are all names of physical processes: Ebb and flow (tides), Inflation (cosmic inflation — "Something from nothingness"), Rebound, Crossover, Lurch, Churn, Relay. These are verbs and nouns of motion and change, and each title tells you what motion to look for. The work is a visualization of a named process.

"Inflation: Something from nothingness" is the clearest example: the still shows small triangles arranged in concentric rings, dense at the edges, opening to an empty white center. The pattern radiates outward from nothing — a visual cosmology. The title is not decoration; it is the brief. This is a physicist titling his work the way a physicist names an experiment: by the process under study.

**Takeaway:** Name the process, then build the field that performs it. A title that names a motion (ebb, rebound, churn, relay, inflation) is a better brief than a title that names a picture. The viewer watches for the named motion, and the piece succeeds when the motion is legible.

## The Julia + Processing pipeline — compute the field, render the grid

The medium is stated in the descriptions: "Made with Processing and Julia" (Ebb and flow, Lurch, Churn), "Made with Processing" (Inflation, Rebound, Crossover, Relay), "Made with Blender" / "Made with Blender and Animation Nodes" (the two Sunrises). Julia is his scientific language — fast, built for numerical fields — and Processing is his art language. The pipeline is: define a field mathematically, evaluate it over a grid, render the deformed grid.

His GitHub confirms the split: all 10 public repos are computational physics in Julia (Peacock.jl for photonic crystals, Yee.jl for Maxwell's equations on a Yee grid, TransferMatrixMethod.jl, LorentzDrudeMetals.jl, CubicSplines.jl, etcmm for metamaterials). No art code is public. The art code is private, but the pipeline is legible from the tools named: the field is computed numerically (Julia's strength), the grid is rendered (Processing's strength). The two Sunrises, made in Blender with Animation Nodes, show the same pipeline in 3D: a procedural node graph generating a field of interlocking cross-shaped tiles, with a sunrise gradient (blue to pink) across it.

**Takeaway:** Separate the field from the rendering. Compute the deformation as a pure function (in whatever language is fastest for numbers), then render the deformed grid (in whatever language is best for drawing). The field is the artwork; the grid is just the paper it draws on. Do not mix them.

## The fractal — recursive subdivision as a second mechanism

The Sierpinski triangle GIF (Tenor, June 25, 2021, 20s, 640x640) is a different mechanism from the grid-warp: recursive self-similarity rather than a deformation field. Three large Sierpinski triangles — green, purple, orange — on a black background, arranged in a triangular composition, with "@sjpalmer1994" at the bottom right. Each triangle is a fractal gasket, subdivided to several levels.

This shows range: he is not only a field artist. The fractal is a second kind of math — recursion instead of a field — and it uses a different palette discipline (three saturated colors on black, rather than one hue on white). The 20-second duration is also much longer than the objkt loops, suggesting a slower, more meditative piece (the triangles likely grow, shift, or scale over the 20 seconds).

**Takeaway:** Recursive subdivision is a second generative system, distinct from the field. A Sierpinski triangle (or any recursive fractal) gives a self-similar structure that reads as both mathematical and organic. Use it when the piece needs depth through scale rather than motion through a field.

## The 3D woven field — Sunrise, Blender + Animation Nodes

The two "Sunrise" pieces (#5722 Blender, #5728 Blender + Animation Nodes) break the flat 2D pattern. The still for #5728 shows a 3D field of interlocking cross/plus-shaped tiles, extruded, with a gradient from blue at the top to pink/lavender at the bottom — a sunrise across a woven surface. The tiles are three-dimensional, with visible depth and shadow, and the weave is a basketweave pattern.

This is the one piece where color is a gradient rather than a flat fill, and where the grid has depth rather than being flat. It shows that the field idea survives the jump to 3D: the same interlocking tile logic, now extruded, with light and a color gradient doing the work that flat color did in the 2D pieces.

**Takeaway:** The grid-warp idea is not limited to 2D. Extrude the tiles, give them depth, and let a color gradient (dawn, dusk, tide) wash across the field. The 3D version trades the flat graphic clarity for depth and light — use it when the piece needs atmosphere, not just pattern.

## Aesthetic logic — the field made visible

The work is a physicist's art, and its beauty comes from a single discipline: make one invisible thing visible. The invisible thing is a mathematical field — a wave, a vortex, a radial expansion, a shear. The visible thing is a regular grid. The grid is perfect so that the field is legible; the color is quiet so that the deformation is the only variation; the time is periodic so that the loop closes and the field cycles forever.

Everything is in service of legibility. The grid is regular because a regular grid shows deformation. The palette is one hue because one hue shows shape. The loop is seamless because a seamless loop shows the field's cycle without a seam. The title names the process because a named process tells the viewer what to watch for.

The work is not about the tiles. The tiles are the paper. The work is about the field — and the field is a piece of physics, rendered as a pattern, looped forever.

## Network

- **GaloAndStuff** — "Auto Painting" series on hicetnunc (March 2021), also Processing, "a painting painting itself." Same medium, same platform, same era. A direct parallel: a system that paints, rather than a painting.
- **Wouter van der Berg (@wblut)** — "TinyTree" generative geometry, 5400x5400 PNGs, also on hicetnunc March 2021. A fellow generative-geometry artist in the same cohort, working with mathematical forms at high resolution.
- **Jonathan Joseph (@jonjojojon)** — fediverse (qoto.org), math and transforms. Sam requested his help debugging rotation/translation matrices, showing Sam is embedded in the fediverse math-art community and thinks in transforms.
- **genart.social** — the Mastodon instance where Sam's art account lives (@sjpalmer1994@genart.social). The instance is the home of the generative-art community; his presence there (rather than only on X) marks him as part of that community, not just a poster.
