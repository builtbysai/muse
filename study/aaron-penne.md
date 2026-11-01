# Aaron Penne - expansion study #224 (2026-10-31)

Network-adjacent pick to #223 Piter Pasma: Penne is named three times in Pasma's captions (Pasma's Art Blocks interview says Skulptuur was decided "during a chat with Aaron Penne") and he curated the Feral File N=12 micro-community that Pasma participated in. First ordered candidate, verified and researched; candidates deafbeef and Dmitri Cherniak not needed.

## Profile
- Handle: @aaron_penne (business account, United States, public, not verified)
- Bio: abstract art glyph, link https://www.aaronpenne.io/, email hello@aaronpenne.io
- 11,065 followers / 3,521 following / 478 posts per profile
- Born 1988, lives and works in Seattle, WA. Artist and engineer; Director of Engineering at Art Blocks. Work sold at Sotheby's; shown at ZKM Center for Art and Media Karlsruhe, Seattle NFT Museum, CADAF, and Bright Moments (Art Blocks artist page).

## Research method
- 311 unique posts pulled over 6 instagram-cli pages (--user-id pagination with next_cursor; has_next_page still true at page 6, stopped at rate-limit caution, roughly 65 percent of 478 profile posts seen), window 2019-09-04 to 2026-09-23.
- 20 posts stratified across the full window; 20 frames downloaded via og:image extraction (curl iPhone UA plus HTML-unescape fix from #218); all 20 visually inspected.
- Web leg: Art Blocks "In Conversation with Aaron Penne on Apparitions" (Jeff Davis, 15 Mar 2021), ARTXCODE "Aaron Penne: Apparitions on Art Blocks" (algorithm background and named palettes Oracle / Three Fates / Zephyr), Jing Daily Culture on Feral File 2.0 N=12 (2023-07-13), Feral File Year in Review 2023 (Bruce Sterling), Art Blocks artist page, Kaloh podcast episode on Feral File with Casey Reas.

## Core engine
STRAIGHT LINES BENT BY NOISE UNTIL THEY READ AS ORGANIC: Penne's recurring system draws many straight lines across the canvas and perturbs each one according to an underlying noise field, every line hundreds of connected points offset by rules, then stacks the lines in colorful bands. The watchable payoff is the organic vs algorithmic tension he names himself: viewers read the work as simultaneously computer generated and hand crafted, because it is both. Apparitions (Art Blocks project 28, 1500 unique works, no artist curation) is the canonical instance, traveling from rigid cliff sides to floating fabric sheets through the same mechanism. Color is half the system: hand-picked palettes of about 20 colors (early ones sourced from photos of a friend's wedding and vintage data visualizations), named palette behaviors such as Oracle (one random color plus black and white, 20 percent programmed chance), Three Fates (three random colors), Zephyr (a new random color with every band, so no two match), and the black-and-white "Rileys" weeks named for op-artist Bridget Riley.

## Evolution
- 2019, origins: colorful organic doodles (f00: stacked wobbly blobs, pink/purple/teal with dark contour rims); Apparitions seed work from an 1893 Levi Walter Yaggy visualization (colorful layered cloud charts) and Southern California cliff sides; marble vein textures (f01) and black/white kaleidoscopic mirror symmetry (f02, f03 topographic contour marble). Code in Python's matplotlib inspired by Zach Bodtorf, learned from mentor emptymonkey, coming from a data-viz background under Edward Tufte's rules.
- 2020, system iteration: fine line fields (f04, "Heavily inspired by the plotter art of @goodbad.png"), colorful marble on black (f05), "Smooth wrinkles made with Python" (f06, pastel surreal fluid forms), parameter churning on a Raspberry Pi ("code running on my Pi so it can keep churning without affecting my laptop", f07: red/white/black striped horizontal bands disrupted by a sinuous dark ribbon), dense black/white cellular fields (f08), cell mosaic grids (f09), sheer draped planes (f10, "Colors from berries in the garden, lines from deep in the machine"), kaleidoscope tiles (f11). December 2020: announced #genuary, "our take on #inktober for creative coders".
- 2021, Apparitions and public scale: March 2021 Apparitions release on Art Blocks; the algorithm intentionally pushed toward a fabric feel, outputs ranging from rigid mountains to floating sheets; f13 caption "Apparitions 852 and 572 got stretched into the stratosphere"; physical mural installation photographed on a building (blue contour lines inside a black circle); plaid grid distortions (f12); rough proof-of-concept sketches (f14).
- 2022 to 2023, video, prints, curation: pixel-sorted mirrored video in vanilla JS/GLSL for Fingerprints DAO (f15 thumbnail); painterly red/yellow vortex print with a pixelated edge (f16); physical prints photographed ("Apparitions prints always feel so good", f17); July 2023 curated the Feral File 2.0 launch exhibition N=12, twelve generative artists across seven time zones sharing code and artistic process for months, including Piter Pasma.
- 2024 to 2026: particle-dot confetti explosions ("One More Day", f18 reel thumbnail); geometric diamond grid systems with fine line texture, captioned "generative art systems by way of Soravia" (f19, 2026-09).

## Network (evidenced)
- Piter Pasma: three caption mentions in study #223; Pasma's Art Blocks interview says Skulptuur was decided "during a chat with Aaron Penne", concluding the Monte Carlo pathtracer would be "groundbreaking and never seen before on Art Blocks". Penne curated Pasma's Feral File N=12 micro-community (opened July 13, 2023) alongside Anna Lucia, Nadieh Bremer, Daniel Catt, Reva Fan, Elsif, Lia Coleman, RalenArc, Bart Simons, Nicole Vella, ippsketch, and Melissa Wiederrecht, who shared code and critiqued each other's aesthetics with weekly meetings and code reviews.
- goodbad.png: plotter artist cited directly in the f04 caption ("Heavily inspired by the plotter art of @goodbad.png") behind Penne's line-field system.
- Casey Reas and Feral File: Reas co-founded Feral File (with Bitmark's Sean Moss-Pultz); Penne curated its 2.0 inaugural exhibition; a Kaloh podcast episode names Penne among artist-curators (with Rick Silva) of Feral File shows.
- Soravia: f19 caption (2026-09), "generative art systems by way of Soravia", attached to his diamond-grid system. Identity unconfirmed beyond the caption.
- Influences he names himself (Art Blocks interview): mentor emptymonkey ("I learned to love code from my friend and mentor emptymonkey"), Zach Bodtorf's matplotlib art, Bridget Riley (the black/white "Rileys" palette weeks), Levi Walter Yaggy's 1893 chart as Apparitions' seed, and Erick Calderon explaining the NFT space while Art Blocks was in development, which convinced him to participate.
- Shared history: Penne announced #genuary in December 2020; study #223 documents Piter Pasma as lead organizer of Genuary 2021 and 2022, making the two linked through that community as well.

## Honest gaps
- Only 311 of 478 profile posts were pulled (pagination still open at page 6; stopped at rate-limit caution, about 65 percent coverage), so some eras may be underrepresented.
- Carousels: only the first frame is visible via og:image; interior frames were not inspected.
- The two video works (f15, a 2022 JS/GLSL pixel-sort piece for Fingerprints DAO; f18, the 2024 "One More Day" particle-dot reel) were inspected only as still thumbnails; their motion, pacing, and any sound are unobserved.
- No access to the Apparitions source; mechanism details come from the two interviews (Art Blocks, ARTXCODE) as summaries, not code reads.
- N=12 co-creation details come from press (Jing Daily Culture, Feral File year in review), not participant observation.
- "Soravia" in the f19 caption is unverified beyond the caption naming.

## Frame notes (20, all visually inspected)
- f00 (2019-09-04): Stacked wobbly organic blobs like a totem, pink/purple/teal with thick dark contour rims and subtle 3D shading, caption "Here's some colorful doodles!". Early organic-layered doodle era.
- f01 (2019-10-10): Marble vein texture in beige/brown, branching organic veins like wood grain or agate, caption fragment "Argento series". Natural-material simulation.
- f02 (2019-11-03): Black/white kaleidoscopic mirror symmetry, concentric warped bands and dotted rings radiating from a central disc. Op-art phase.
- f03 (2019-12-31): White topographic contour lines on dark olive, a bright organic blob at bottom right; marble-as-map aesthetic.
- f04 (2020-03-23): Dense fine line field, dark purple streamlines flowing diagonally across white, caption "Heavily inspired by the plotter art of @goodbad.png". The noise-perturbed line mechanism at its purest.
- f05 (2020-04-28): Colorful neon marble veins (pink, yellow, cyan, grey) on black, "Calumet iterations" caption family.
- f06 (2020-07-14): Pastel surreal fluid forms in mauve and cyan with a cream ribbon contour, "Smooth wrinkles made with Python". Mirror-smooth organic blobs.
- f07 (2020-08-06): Red/white/black horizontal striped bands with a sinuous dark ribbon cutting diagonally through them, marbled at the edges; caption about Raspberry Pi parameter churning and "vertical lines sourced from doodles in my work notebook". Disruption intruding on a regular field.
- f08 (2020-08-25): Dense black/white cellular pattern, tiny organic cells filling the frame with a few larger cream contour rings. Maximalist noise field.
- f09 (2020-09-11): Bright rounded-square mosaic grid, yellow/orange cells in blue frames with purple and teal interstitial space, hand-painted edges.
- f10 (2020-11-02): Sheer translucent draped planes in grey, pink, and cream, layered like fabric over ghostly geometry; caption "Colors from berries in the garden, lines from deep in the machine".
- f11 (2020-12-11): Kaleidoscopic symmetric tile in pink, blue, orange, and navy on dark ground; the #genuary announcement post.
- f12 (2021-02-17): Beige/red/black woven plaid grid, distorted symmetrically like fabric viewed through water. Grid era begins.
- f13 (2021-04-26): Photo of a building-mounted mural, blue contour-line waves inside a large black circle on a pink wall. Physical installation work.
- f14 (2021-07-22): Scratchy noisy texture in red and green with dripping vertical marks; "quite rough sketches. Proofs of concept. Much more refinement to come."
- f15 (2022-03-24): Video thumbnail, black/white pixel-sorted mirrored columns forming a symmetric glyph pattern in a dark frame; caption "Generative artwork made with vanilla JS/GLSL - coming soon from @fingerprintsdao". Motion unobserved.
- f16 (2022-06-27): Painterly vortex, red/yellow/black swirl with a pixelated stair-step edge along the top arc. Print-era physicality.
- f17 (2023-04-06): Photo of a physical print on paper, flowing red liquid bands with black contours, glossy highlights; caption "Apparitions prints always feel so good".
- f18 (2024-05-21): Reel thumbnail, colorful particle dots (blue, yellow, pink, black) exploding across white with a couple of long diagonal strokes; caption "One More Day". Motion unobserved.
- f19 (2026-09-23): Blue diamond grid with fine hairline texture on light grey, crisp geometric; caption "generative art systems by way of Soravia".
