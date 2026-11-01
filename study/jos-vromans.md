# Study #219: Jos Vromans

## Identity

- Name: Jos Vromans.
- Instagram: @josvromans.art (verified via instagram-cli user-profile read 2026-10-31: name "Jos Vromans Generative Art", bio "Art made with Python / Generative browser art in Javascript", website http://www.josvromans.art, 2277 followers, 2125 following, 284 posts, public, Netherlands).
- Dutch creative coder. Studied Applied Mathematics at Fontys University in Tilburg. Backend web developer at Maykin Media for five years; quit in 2018 to make art full time. No pre-made libraries: he writes every algorithm from scratch and can rebuild any past piece from memory. After Fidenza (Tyler Hobbs) led him to Art Blocks in 2021, he learned JavaScript and moved to browser-based art full time.
- Own site: josvromans.art (active blog documenting his algorithms). Zharta published an interview ("Jos Vromans: Exploring the Intersection of Nature, Mathematics, and Art").
- This is the final network-adjacent subject of the Generative Dialogues V cohort expansion (#215 Marcelo Soria-Rodriguez, #216 Kazuhiro Tanimoto, #217 HAL09999, #218 Eric De Giuli), per the lammetje-nl template. His "Art from code" was shown in the same Blanc! / La Nau Barcelona installation, Oct 23-24 2026.

## Research method

- instagram-cli posts pull: --account-id 17841403588745492 --user-id 17841409271754429 --post-types POST,REEL --limit 100 --sort-order desc. Pages 1-3 returned 106/100/79; page 4 empty. Total 285 posts (284 own + 1 third-party tgamxyz feature repost). All 285 carried created_at, spanning 2018-11-27 to 2026-10-23.
- 20 stratified indices across all 8 years downloaded via og:image extraction (curl, iPhone User-Agent, HTML-unescaping the content attribute per the #218 fix). All 20 fetched OK; f10 (Sierpinski Party, 2021, index 30) resolved to a 2.2KB black placeholder, marked unretrieved. The remaining 19 visually inspected frame by frame (f00-f19.jpg in hidden_files/study219/frames/).
- Web leg (browser.search + browser.open, 2026-10-31): Zharta interview (richest source: education, career timeline, the Fidenza/Art Blocks turn, no-libraries discipline, exhibition list); Art Blocks artists listing (confirms him on Art Blocks). His own site josvromans.art and the EditArt/Meraki collection pages were not opened; the mechanisms below come from his captions (which document parameters and methods unusually precisely) plus the inspected frames.
- Caption mentions found in his feed: @artblocks_io, @blancfest, @gen_dot_art, @josvromans.art.

## Core engine

THE ALGORITHM IS TRANSPARENT AND THE PARAMETER IS THE WORK: Vromans turns one small classical mathematical system into a numbered, blogged, publicly documented series, then sweeps its parameter until the output surprises him. His own workflow words: "I choose a variable to change, and then let the result surprise me." The chaos game, pursuit curves, pixel averaging, subdivision, segment fields: each is a tiny rule with one or two knobs. The piece the viewer watches is not the static image but the sweep itself, how one rule mutates as its parameter moves. His Zharta interview adds the credo behind it: randomness and even his own mistakes are deliberate tools ("the output would be different from expected, which could sometimes be very surprising"), and "mistakes can be very interesting when making art". Because he writes no-library original code, every mechanism is rebuildable and legible. Watchable behavior: a system in the middle of its sweep, a parameter mid-turn, structure mid-formation.

## Signature devices observed

1. **The chaos-game parameter sweep (2019).** The dominant early series: numbered Chaos Game (2), (8), (14), (20), (26). Caption of Chaos Game (2): "Starting with 3 points, the 'default' chaos game results in the Sierpinski triangle. However, with different percentages, the Sierpinski triangle(s) will emerge, grow, form one big triangle and eventually overlap each other." f01 (Chaos Game 2, video poster): a golden stippled Sierpinski pyramid on black. f19 (Chaos Game 8, "Many, many C's"): white lace ornament, reads like tatted lace, a crab-like motif from the caption. f18 (Chaos Game 26): red stippled triangle field on white. The mechanism: change the percentage (how far each step moves toward the chosen vertex) and the point count; the emergent figure mutates from crystal to lace to noise. Watchable: the fractal is visibly mid-transition, dots still accumulating.
2. **Double pursuit curves (2019-2020).** Agents placed on polygon vertices each chase the next one; all move at the same speed. f06 (video poster, 2020): overlapping white threadlines forming petal/flower rosettes on white. Earlier 2019 captions ("Double Pursuit Curves - Pentagons", blogged with math notes) describe the series across triangle/square/pentagon variants. Mechanism: pursuit turns polygons into flowers; the watchable behavior is the chase itself, agents spiraling inward until they collapse onto each other and the rosette closes.
3. **Random walks that fill the frame (2019-2020).** Caption (2019): "In the animation, the random walks will start at the frame and eventually fill the center." f08 (Colorful Animation, 2020): loose painterly scribbles in blue/green on white, like energetic sketch strokes. Earlier: "Here are some more random color experiments." Watchable: walks seed at the border and migrate inward, color accumulating where paths cross.
4. **Polygonal spirals and shuffling polygons (2019).** Caption (Primary Color Trip, 2019): "It just appears exactly like this when I iterate over a certain parameter in my code. So I choose a variable to change, and then let the result surprise me." f03 (Shuffling polygons, video poster): a pentagon built from spiraling grey triangle segments, camera-like aperture. f02 (Tesselation I, 2019): a warm star tessellation in red/gold/ochre on black grid. Watchable: one parameter stepped while the viewer watches, polygons reorganizing into a new symmetry.
5. **Pixel averaging to tileable color fields (2021).** The most legible algorithm of his feed. Caption: "Starting from randomly colored pixels, generate a new image where the color of every pixel is recalculated, based on the average of the previous color and the neighboring pixels. When repeating this process, areas of the same color appear." He averages edge pixels with "their 'neighbor from the other side of the image'" so every result tiles the plane perfectly ("When swiping from 1 to 2, it should not be visible where image 1 ends and where image 2 starts"). f11 (video poster): rainbow thread arcs circling a black core on mauve. Watchable: noise coalescing into color regions, frame 1 to frame N as smoothing progresses.
6. **Attraction (2021, Art Blocks project 229).** His Art Blocks piece, December 2021. f09 (mint showcase): stippled cosmic field, a glowing red triangle cloud, yellow dot grids and white Sierpinski-like triangles on black, a red header bar. The eye lineage continues into 2021 browser art: f05 (Golden Eye, video poster) is fine golden threadlines radiating from a bright central knot, "mysterious space feeling" per captions. Watchable: gravity-like accumulation, points drawn toward an unseen center until the field congeals.
7. **Segs (2022, Meraki).** Caption: "A few more variations of 'Segs' - circle segments. The first 4 pieces are part of the algorithm that is minted on Meraki" (mraki.io/collections/segs). f12: dense painterly strokes, yellow/red/black arcs curling across white. f13: marbled strata, orange/brown/cream wavy bands like agate or wood grain. Mechanism: circle segments sampled and layered until the geometry stops reading as geometry and starts reading as material. Watchable: segments accumulating until they become marble.
8. **Math Painting (2023).** Caption: "Carefully constructed by putting pixels on the canvas by a custom written algorithm." f14: textured brushstrokes on white in a vertical herringbone, muted grey, maroon, yellow, strokes with ragged watercolor edges. Mechanism: the canvas addressed pixel by pixel, strokes grown from the pixel map itself. Watchable: a painting that reveals it was never painted, only placed.
9. **More Layers (2023).** Caption: "More Layers." f15 (video poster): a grid of identical black spiky fleur/ornament motifs on light grey, pure repetition field. The repetition theme that will culminate in the 2026 piece.
10. **Deviations from Design (2025, EditArt).** Caption: "'Deviations from Design.' These are the first 100 variations, co-created by collectors on EditArt. You can view the collection here, and play with the 5 sliders to explore the algorithm." f16 (video poster): concentric rectangular rings in pink, magenta, green, black, the bands filled with textured data noise (visible glyph-like texture inside the rings). f17 (B/W version): a lattice of black radiating line-burst guilloche ornaments on off-white. Mechanism: a fixed design plus five user-controlled deviation sliders; the viewer is the parameter sweep.
11. **Art from code (2026, Generative Dialogues V).** His Blanc! piece. Caption: "'Art from code' demonstrates how art can emerge from code by drawing the actual source code on the screen as a starting point for a visual evolving artwork. Two visual themes that become apparent during the animation are repetition and reflection. Repetition represents one of the most powerful concepts of computing: using iteration to get things done that are tedious without a computer. The reflections of shapes on the screen can be a metaphor for reflecting on the use of computers for art. Can the code be the art? Is the code even part of a visual output? The longer the animation continues, the more the font characters get obfuscated, until there is no trace left of the code." f00 (video poster): dense white-on-black tiled rosette grid with spiky border. Watchable: legible source code dissolving into its own execution, text becoming pattern until nothing of the code remains but the behavior.

## Evolution

- **2018 (Processing era):** tessellations, complete graphs, modulo lines, mandala grids. First post: "Triangle" (Nov 27). Caption tag #processing. One post shows a 1000-frame sequence of modulo line art.
- **2019 (chaos-game year):** the numbered Chaos Game series dominates (2 through 26+), plus Hexagonia, snowflake variations, Eclipse, tessellanimations. Heavy posting (134 posts): this is the sweep-everything year.
- **2020 (Python experiments):** double pursuit curves, random walks, color experiments, pentagon stars, chaos spirals. Captions tag #python; he is learning to draw with code and documenting each mechanism.
- **2021 (the JavaScript turn):** Fidenza led him to Art Blocks; learned JavaScript; browser-based art from here on. Triangle subdivision, pixel averaging, the Eye, "Attraction" on Art Blocks (project 229, Dec 2021).
- **2022:** "Segs" minted on Meraki. Paintier, material-feeling outputs.
- **2023:** "Math Painting" and "More Layers". Pixel-level painting; repetition fields.
- **2025:** "Deviations from Design" on EditArt: collector co-creation with 5 sliders, 100 variations.
- **2026:** "Art from code" at Generative Dialogues V: code as visible starting material, obfuscation as the ending.

## Network (evidenced)

- **Generative Dialogues V co-artists (Blanc! festival, La Nau Barcelona, Oct 23-24 2026, presented by The Generative Art Museum):** Marcelo Soria-Rodriguez (#215), Kazuhiro Tanimoto (#216), HAL09999 (#217), Eric De Giuli (#218). His contribution "Art from code" was captioned and reposted by @tgamxyz, the same feature pipeline as the rest of the cohort.
- **Tyler Hobbs:** per the Zharta interview, Fidenza's release led Vromans to Art Blocks, which changed his career direction; he learned JavaScript for it. The influence is documented, not inferred.
- **Art Blocks:** "Attraction" (project 229), mints documented in his feed Dec 2021; @artblocks_io captioned.
- **Meraki:** "Segs" minted at mraki.io/collections/segs, some mints still available at caption time.
- **EditArt:** "Deviations from Design", collector-co-created series with 5 public sliders at editart.xyz.
- **gen.art:** @gen_dot_art mentioned in his feed captions.
- **Bridges Math Art:** exhibition in Linz, Austria (Zharta exhibition list); his feed carries #bridgesmath tags.
- **Exhibition record (Zharta):** NFCastle (Lobkowicz Palace, Prague Castle), Bridges Math Art Exhibition (Linz), Vellum LA "Immutable", Samsung at NFT.NYC; featured in Euclides magazine and Steven Rutgers' "Gallery Venetiæ".

## Honest gaps

- No motion driven live: all frame evidence is stills and video posters; animation behavior (chaos-game accumulation, pixel-averaging iterations, code obfuscation timing) rests on his detailed captions.
- f10 (Sierpinski Party, 2021) unretrieved: og:image returned a 2.2KB black placeholder on the single attempt path.
- josvromans.art (his blog), the EditArt collection page, and the Meraki "Segs" page were not opened; slider mechanics of Deviations from Design and Segs mint parameters are from captions only.
- f05 (Golden Eye) and f11 (pixel averaging) are video posters whose internal frame timing is unknown.
- No direct statement found on the exact chaos-game percentage parameter values per numbered piece; captions describe the effect, not the numbers.
- The five feature captions on @tgamxyz are reposts of his own caption text, not independent criticism.

## Frame notes

- f00 (Art from code, 2026, index 0): video poster; white tiled geometric rosette grid on black, spiky star border; legible-code stage already past, pattern stage shown.
- f01 (Chaos Game 2, 2019, index 222): video poster; golden stippled Sierpinski pyramid on black, dense dot texture.
- f02 (Tesselation I, 2019, index 252): warm star tessellation in red/gold/ochre on black grid.
- f03 (Shuffling polygons, 2019, index 138): video poster; grey pentagon aperture of spiraling triangle segments on black.
- f04 (Pentagon Star, 2020, index 114): silver 5-point star of concentric nested linework on black.
- f05 (Golden Eye, 2020, index 60): video poster; fine golden threadlines radiating from a bright central knot on black.
- f06 (Double Pursuit Curves, 2020, index 96): video poster; overlapping white threadlines forming petal rosettes on white.
- f07 (Colorful Flames, 2020, index 72): video poster; radial rainbow streak field, motion-blurred kaleidoscope.
- f08 (Colorful Animation, 2020, index 108): painterly blue/green scribble strokes on white, random-walk feel.
- f09 (Attraction mints, 2021, index 18): stippled cosmic field, glowing red triangle cloud, yellow dot grid, white triangles, black ground, red bar top.
- f10 (Sierpinski Party, 2021, index 30): UNRETRIEVED, black placeholder.
- f11 (pixel averaging, 2021, index 36): video poster; rainbow thread arcs around a black core on mauve ground.
- f12 (Segs, 2022, index 14): dense painterly strokes, yellow/red/black curling arcs on white.
- f13 (Segs variation, 2022): marbled strata, orange/brown/cream wavy bands like agate.
- f14 (Math Painting, 2023, index 6): textured herringbone brushstrokes on white, grey/maroon/yellow.
- f15 (More Layers, 2023, index 12): video poster; grid of repeated black spiky ornaments on light grey.
- f16 (Deviations from Design, 2025, index 102): video poster; concentric pink/magenta/green/black rings, bands filled with glyph-textured noise.
- f17 (Deviations from Design B/W, 2025, index 2): lattice of black radiating guilloche line-bursts on off-white.
- f18 (Chaos Game 26, 2019, index 198): red stippled triangle field on white.
- f19 (Chaos Game 8, 2019, index 216): white lace ornament on black, delicate crab-like motif.
