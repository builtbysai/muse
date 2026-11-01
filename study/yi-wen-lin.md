# Study #214: Yi-Wen Lin

## Identity

- Name: Yi-Wen Lin (styled Yi-Wen LIN on fxhash and in exhibition listings).
- Instagram: @yiwen (verified via instagram-cli profile read 2026-10-30: name "Yi-Wen Lin", bio "Creative coder / Generative artist.", link https://linktr.ee/yiwenl, 2,339 followers, 912 posts reported, public account).
- Own site: https://yiwenl.github.io ("WENSDAY is the portfolio of Yi-Wen LIN, creative coder and generative artist from Taiwan. Based in London, UK. Working remotely with clients and partners worldwide."). The site links to instagram.com/yiwen, confirming the handle.
- Third-party bio (Interactive Architecture Lab people page, UCL Bartlett): "A freelance creative coder from Taiwan who has worked in Paris and London for the past ten years on a range of commercial and artistic projects. His work is inspired and explores combinations of eastern with western cultural influences. His work has been featured by Experiments with Google, and Samsung at Milan Design Week."
- Commissions: IBM Observability Solutions interactive data visualisation; Brain Virtual Theater (collective consciousness + VR); Data Face Print (Barbican Centre, AI: More Than Human); FC Bayern Pulse (football game visualisation); Sibos 2018. All listed on yiwenl.github.io.

## Research method

- instagram-cli posts pull via `--user-id` (note: pagination with `--username` silently ignored `--after` and repeated page 1; switching to `--user-id 17841401181130002` per the connector's read-results.md pagination rule fixed it). 984 unique posts, 2026-07-03 back to 2010-10-19, saved to hidden_files/study214/posts_raw.json; index at hidden_files/study214/posts_index.txt.
- 20 frames downloaded via og:image extraction (curl, iPhone User-Agent), all 20 retrieved OK, saved as hidden_files/study214/frames/f00-f19.jpg with metadata in frames_meta.json. All 20 visually inspected frame by frame with muse.read.
- Web leg (browser.search + browser.open, 2026-10-30): Ars Electronica Festival 2022 Planet B pages (Project Percentage listing Yi-Wen Lin TW among six artists), taiwaninvienna.com (Project Percentage: FAB DAO invited five generative artists, including Yi-Wen Lin, to create mountain ranges of Taiwan in code), niewmedia.com (dialog() Asian Generative Art Exhibition 2024, Taipei lineup naming Yi-Wen LIN with Che-Yu Wu, Newyellow, Jinyao Lin, Aluan Wang and others), paragraph.com/@kaloh (Maze and Hex, 128 pieces each, noted for striking palettes and textures), tender.art (Bruno Imbrizi interview, Dec 18 2021: "A chat with Yi-Wen Lin about his first eight projects on fxhash"), 80.lv (Sept 1 2023: interactive hand-controlled fluid simulation, TensorFlow.js hand tracking, with a public demo), forum.tezosagora.org (akaDrop case: Nuit Blanche Taipei 2022, akaSwap with Yi-Wen Lin, La nuit lumiere, 1,200 editions generated from 12 hours of participant data as RGB ratios), interactivearchitecture.org/people (biography).
- Note: this subject was candidate 1, shortlisted in studies #211 and #213, never attempted. Attempted first this round and verified on the first try, so Marcelo Soria-Rodriguez (the fallback) was not researched.

## Core engine

THE WORK IS A WEATHER SYSTEM TRAPPED IN A GRID AND COMMITTED TO PAPER: curl noise, 1D/2D noise and particle advection build recognisable natural phenomena (raindrop ripple rings, storm tracks, mountain ridges, thread nests, firefly swarms) inside strict masks, grids, hex tiles or circular voids, and the digital loop always terminates in physical ink on paper via the pen plotter; the watchable behavior is invisible field agents leaving visible trails that resolve into a landscape, a seal, a knot, or a forecast.

## Signature devices observed

1. **The ripple as primitive.** The "Rippling" series (dozens of posts, 2022-2023) is his longest-running motif. Each rain drop is an origin that emits expanding concentric rings; rings overlap and interfere. Three render modes observed: (f09) monochrome ink-wash night scene, rings as white ink on black with rain streaks and spatter; (f12) sepia daytime variant where rings are built from scattered mosaic chips in white and rust on tan; (163) a close-look variant with a written note: "I enjoy the rainy days a lot when I was a kid, and can stand in rain and watch the ripples for hours." The mechanism is propagation plus interference, not decoration: rings that meet make moire.
2. **The mountain as stacked noise.** "Fold of mountains" (2026, penplotter, physical framed prints), "Wire mountain" (2024, white pen on black paper, mountain drawn as dense layered wireframe contour strokes), "Ink mountain" (f13, monochrome shan shui peak with ink bleed), "Jade mountain" (f16, glitchy pixel-sorted teal nocturne with moon and scanlines), "Different views of the mountain ranges" (f15, translucent pink atmospheric bands). The Project Percentage commission (2022) asked five artists to render Taiwan's top-100 peaks in code. Mechanism: 1D/2D noise-displaced ridges stacked with depth; the plotter renders them contour by contour.
3. **The void that organises the tangle.** "Disorder" (f03, made for dialog() Taipei 2024): dense copper thread nest on teal, tangled around two clean circular voids. Threads grow along curl-noise paths but are repelled by mask discs; the composition is the tension between the chaotic web and the perfect circles. Same idea in "Threads." (f07): red horizontal threads across white, density modulated in vertical bands, producing a woven moire.
4. **Hex-grid hatching (fxhash Hex).** (f10) Diagonal hatched parallelograms in cream, teal and rust on near-black; each cell filled with fine parallel hatching, the lattice read at an angle. Kaloh's review notes 128 editions and striking palettes. Mechanism: hex lattice, per-cell hatch angle and palette assignment from the seed. "Maze" (companion fxhash drop, also 128) was not posted to IG, but the dialog() "Seal" piece (f06) shows the same carving instinct: thick white glyph-like strokes like a Chinese seal stamp character in negative space on black.
5. **Particle advection as bloom.** (f17) "Mixing 2d fluid and curl noise": a radial flower of thousands of red, white and grey particle strokes spiralling out of a dark centre. (f11) "La nuit lumiere" (Nuit Blanche Taipei 2022): a particle fountain erupting from a glowing wireframe sphere; per akaSwap, 1,200 editions were generated by 12 hours of participant data, expressed as ratios of RGB values standing for avant garde, guarding and balance. (f18) "Fireflies" (2021, captioned in Japanese "Grave of the fireflies"): sparse glowing dot agents drifting over a dark plane. (f19) "The dot effect with fluid" (2019): thousands of white dots advected into a spiral vortex with a dense bright knot.
6. **The plotter as the final instrument.** From 2024 onward the machine is on camera: overhead plotter videos (f02, f04) show the pen arm drawing on dark paper. "Back at plotting" (2025): "Inspired by the movement of solar systems as they orbit the centre of a galaxy." "Storm path predictions. #Weathernext2" (f01, 2026): an ensemble of blue storm-track curves plotted over a latitude/longitude grid with coastline contours. The digital piece is a rehearsal; the plot is the performance.
7. **Interaction as input to the field.** The 80.lv-covered 2023 fluid simulation: hands tracked by TensorFlow.js steer a particle fluid; without a camera it follows the cursor, particle count adjustable. The La nuit lumiere piece: participant behaviour is the seed data. His systems accept the body as a data source.

## Evolution: early vs recent

- 2010-2017: personal photography. Travel, family, a pet bunny, everyday life. No generative work. The account is a decade-old personal diary that became a practice log.
- 2018-2019: the engine appears. "Weaving" (Dec 2018, monochrome and coloured thread weaves), "Fluid." (Feb 2018 video), "The dot effect with fluid" (Oct 2019), "Particles form face" (2019), libcinder AR experiments, "Good old curl noise" (Aug 2020). The primitives are all here: noise, particles, fluid advection, threads.
- 2021-2022: the fxhash era. Eight projects on fxhash by Dec 2021 (per the Bruno Imbrizi interview); Maze and Hex as the flagship 128-edition drops; "The Fire Within" noted by collectors; fireflies (June 2021). The mountains become a commission: Project Percentage at Ars Electronica 2022 (Taiwan's top-100 peaks in code, exhibited plus an audiovisual performance in Deep Space 8K); La nuit lumiere at Nuit Blanche Taipei (Oct 2022). The Rippling series runs through all of 2022-2023 in multiple render modes. "Disorders" (Apr 2022): six tilted white squares with hard shadows on ochre, a minimal geometric detour.
- 2023-2024: scale and physicality. Rippling becomes video (reels, "Heavy rain in the night", "Pink Sunset"). Threads return (Jan 2024). "Seal", "Disorder" for dialog() Taipei (Oct 11-20, 2024, C-LAB). "Cubes" (May 2024): hundreds of isometric cubes, red/orange/charcoal, scattered by noise. "Wire mountain" plotted. The practice visibly shifts from screen renders to the plotter as the destination.
- 2025-2026: the plotter years. Solar-system orbits, storm-path forecasts (#Weathernext2), folded mountain ranges framed on a wall. He now documents the machine working as much as the image: the drawing is the artwork.

## Network (evidenced interactions)

- **Aluan Wang (study #211):** co-listed with Yi-Wen Lin on the Project Percentage artist roster at Ars Electronica 2022 (ars.electronica.art Planet B tag page; taiwaninvienna.com: "Formosa Art Bank DAO (FAB DAO) invites five generative artists (Lien-Cheng Wang, Aluan Wang, Yi-Wen Lin, Jinyao Lin, and Che-Yu Wu)"). Both on the dialog() 2024 Taipei lineup (niewmedia.com).
- **Che-Yu Wu (study #209), Jinyao Lin (study #212), Newyellow (study #210):** same dialog() 2024 Taipei lineup as Yi-Wen Lin (niewmedia.com); Project Percentage's five/seven-artist roster also includes Che-Yu Wu, Jinyao Lin and Newyellow alongside his (taiwaninvienna.com).
- **Bruno Imbrizi:** host of the tender.art "Arbitrarily Deterministic" interview series; his Dec 18, 2021 episode is "A chat with Yi-Wen Lin about his first eight projects on fxhash" (tender.art/editorial/av). Imbrizi also interviewed William Mapan in the same series (Dec 13, 2021), placing Yi-Wen in the early-fxhash artist circle.
- **akaSwap / Nuit Blanche Taipei:** the tezosagora.org akaDrop case study names "the generative artist Yi-Wen Lin" as the collaborator on La nuit lumiere at Nuit Blanche Taipei 2022: 1,200 limited editions "generated by the data of participants accumulated throughout the 12 hours," the RGB ratios standing for avant garde, guarding and balance.
- **Kaloh (collector/writer):** paragraph.com "8 Exciting FxHash NFT Artists You Need To See" ranks "Maze and Hex by Yi-Wen LIN" first, citing "striking palettes and textures in a small sampling space (there are only 128 pieces in each collection)."
- **80.lv editorial:** covered his hand-controlled TensorFlow.js fluid simulation (Sept 1, 2023), noting the public demo and adjustable particle counts. Editorial attention, not a collaboration.

## Honest gaps

- f00 ("Fold of mountains") og:image resolved to the carousel's second image: framed prints on a brick wall, not the digital artwork. The framed-plot look is documented, the screen version is not.
- f02 ("Back at plotting", solar-system orbits) og:image is the plotter machine itself (overhead view, pen arm over dark paper); the actual orbit artwork is unretrievable from the poster.
- f09, f18, f19 are video posters (play-button overlays); motion is inferred from captions only ("Heavy rain in the night", "Fireflies", "The dot effect with fluid").
- "Maze" and "The Fire Within" have no IG posts under those names; only "Hex" appears (2022-12-31). The Kaloh article supplies the Maze facts (128 editions, palette richness).
- The La nuit lumiere RGB-ratio mechanism comes from the akaSwap case study, not from his own captions; his IG caption only gives the event details.
- The Tender interview content is cited from its listing blurb ("about his first eight projects on fxhash"); the audio was not transcribed.
- Caption-only posts (e.g. "Animated patterns", "Saw this effect somewhere on pinterest") were not opened individually; the study rests on the 20 inspected frames plus web sources.
- Note on names: several sources use "his" for Yi-Wen Lin; the IG account name is "Yi-Wen Lin" with no gender stated in bio. The study avoids pronouns.

## Frame-by-frame notes (all 20 inspected)

- f00 (2026-07-03, "Fold of mountains", carousel, penplotter): the og:image landed on the carousel's second image, a gallery-wall photo of framed mountain plots on white brick (black frames, navy and charcoal prints). The digital fold artwork itself is unretrieved; what the frame proves is the endpoint of his pipeline: the plot is a physical object that gets framed and hung. Caption hashtag: #penplotter.
- f01 (2026-06-22, "Storm path predictions. #Weathernext2", carousel, penplotter): cream paper with a hand-drawn-looking latitude/longitude grid and coastline contour in thin grey-brown ink; from the lower right an ensemble of dense blue storm-track curves sweeps up-left, thickest where the tracks agree, fanning where they split. The blue pen work has the pressure variation of a real plotter. The series tag "#Weathernext2" marks this as an ongoing forecast project, not a one-off.
- f02 (2025-09-18, "Back at plotting. Inspired by the movement of solar systems as they orbit the centre of a galaxy.", carousel): og:image is the plotter machine itself, overhead, pen arm over dark grey paper on a gridded cutting mat. The artwork is unretrieved, but the caption documents his 2025 subject matter: orbital mechanics as drawing. The machine is the protagonist of the post.
- f03 (2024-08-10, "Disorder. For @dialog.asia exhibition", carousel): the dialog() Taipei 2024 piece. Square teal field, a dense copper thread nest filling the frame, tangled strokes with visible strand shadows giving a woven depth, and two clean circular voids (one large upper-right, one smaller lower-left) of flat teal. The threads crowd the rims of the voids. Play-button overlay in the retrieved frame (reel poster). This is the most compositionally disciplined piece inspected: chaos with absolute still points.
- f04 (2024-08-04, "Wire mountain", carousel, penplotter): video poster showing the plotter mid-draw, white pen on black paper, a mountain ridge rendered as dense horizontal wireframe contour strokes with fine hatching. The drawing half-completes the ridge; the mechanism is unmistakable: the mountain is a stack of noisy polylines, the plotter is drawing them in real time.
- f05 (2024-05-03, "Cubes", carousel): hundreds of small isometric cubes on a graph-paper ground, dense pile at center, scattered singles at the edges. Cube faces in red, orange, charcoal, white; many faces carry fine hatch shading. The scattering reads as noise-driven (denser center, sparse periphery) with slight per-cube rotation. No animation, a pure composition study.
- f06 (2024-02-07, "Seal", carousel): a red-square-seal composition, thick white strokes like a seal-script character carved in negative space on black, occupying the lower two thirds, white void above. The strokes have the rounded corners of carved seal paste. It reads as a generative seal stamp: glyph-like, but invented, not a real character.
- f07 (2024-01-15, "Threads.", carousel): red horizontal threads across white, thread density modulated in vertical bands to form a woven moire, threads slightly wavy, ends ragged at the frame edge. A study in interference between two regular systems (rows vs columns). Caption is one word plus a thread emoji.
- f08 (2023-09-12, "Mixing 1D and 2D noise.", carousel): rows of small arc glyphs on warm grey, arcs colored per noise value in terracotta, ochre, sage and umber, arc orientation flipping in row bands. The caption is the whole mechanism: the piece is a noise sampler made visible, each mark a probe reading the field.
- f09 (2023-03-12, "Rippling - Heavy rain in the night", reel): monochrome ink-wash night pond, concentric ripple rings in white ink on black water, rain streaks slanting, spatter at the edges. The play-button poster is the money shot of his signature series: rings as the only light source.
- f10 (2022-12-31, "Hex", carousel): near-black field of hatched parallelograms (hex lattice read at an angle) in cream, teal and rust, each cell filled with fine diagonal hatching, a few cells left empty. The hatching is the texture Kaloh praised in his roundup. Palette discipline: three muted tones, no more.
- f11 (2022-09-27, "La nuit lumiere.", carousel): dark field with circuit-like texture, a glowing wireframe sphere low in frame, a fountain of blue/white/gold particle grains erupting upward and raining down. Caption dates it to Nuit Blanche Taipei, Oct 1 2022, 6PM to Oct 2 6AM. The akaSwap case study supplies the mechanism: 12 hours of participant data mapped to RGB ratios.
- f12 (2022-06-06, "Rippling.", carousel): the daytime variant, concentric ripple rings built from scattered mosaic chips in white and rust on tan. Same primitive as f09, different renderer: the rings here are discrete grains, not ink strokes, proving the ripple system is renderer-agnostic in his practice.
- f13 (2022-07-01, "Ink mountain.", carousel): monochrome shan shui peak, bold black silhouette with ink bleed, layered ridge strokes dissolving into white mist below. The most painterly frame inspected, and the one that most directly ties his code mountains to Chinese ink landscape tradition (his IAL bio: eastern with western cultural influences).
- f14 (2022-04-27, "Disorders", carousel): six slightly rotated white squares with hard drop shadows on flat ochre. The minimal detour: ordered grid, noise perturbation, flat color. It sits apart from everything else and reads like a deliberate palette cleanser between the mountain and ripple years.
- f15 (2022-01-19, "Different views of the mountain ranges.", carousel): translucent pink and peach mountain silhouettes in atmospheric perspective, soft bands receding. This is the Project Percentage register: the same noise ridges rendered as pure color atmosphere.
- f16 (2022-04-06, "Jade mountain", carousel): teal nocturne, pixel-sorted glitchy mountain silhouette, glowing white moon, falling snow/rain grains, scanline and circuit textures overlaid. The glitch register: the mountain rendered as corrupted signal.
- f17 (2021-03-28, "Mixing 2d fluid and curl noise because I haven't figured out 3d fluid yet. Also playing with shadow", carousel): radial flower of thousands of red, white and grey particle strokes spiraling from a dark center. The caption is candid about the mechanism and its limits; the frozen frame reads as a chrysanthemum made of trajectories.
- f18 (2021-06-21, "Fireflies" (video) plus caption "火垂るの墓。 Grave of the fireflies."): play-button poster, sparse glowing dots over a dark angled plane. The Grave of the Fireflies reference (the 1988 film) gives the piece its melancholy register: the dots are souls as much as insects.
- f19 (2019-10-02, "The dot effect with fluid.", video): thousands of white dots advected into a spiral vortex on black, a dense bright knot off-center where the flow converges. The earliest pure-field piece inspected: no renderer tricks, just particles and a vortex.

## The collections (fxhash)

- Maze and Hex: both 128 editions (Kaloh, paragraph.com, 2022). Maze was his maze-carving system; Hex the hatched hex lattice. Striking palettes and textures "in a small sampling space" was the reviewer's praise, meaning his parametric space is tuned so almost every seed is hangable. The IG account carries Hex posts but no Maze posts, suggesting Maze lived mostly on fxhash.
- The Fire Within: noted by the Collector's Corner newsletter (Oct 2022) as a highlighted fxhash work. No IG post under that name; mechanism undocumented in the sources read.
- Eight projects on fxhash by Dec 2021 (tender.art listing). The interview with Bruno Imbrizi is the earliest long-form record of his thinking about the platform.
- Project Percentage (2022): not a personal drop but a commission. FAB DAO (Formosa Art Bank DAO) invited five generative artists, Yi-Wen Lin among them, to create the mountain ranges of Taiwan in code; 10,000 generative art NFTs total, the count symbolising Taiwan's top-100 peaks; a Web3 crowdfunding campaign for charitable causes with collectors forming a DAO; exhibited at Ars Electronica 2022 (Planet B) with an audiovisual performance in Deep Space 8K by Aluan Wang, Tsung-Yun Lai, Lien-Cheng Wang and Jinyao Lin (taiwaninvienna.com). His mountain obsession is not decorative: it was institutionalised by this commission.

## The interactive lineage

- 2023 fluid simulation (80.lv, Sept 1 2023): TensorFlow.js hand tracking drives a particle fluid; with a camera the hands steer it, without one the cursor does; particle count adjustable. 80.lv framed it as "feel like a wizard." A public demo was provided. This is his only documented interactive web piece, and it sets the interaction rule for his work: the body is an input to the field, never a button.
- La nuit lumiere (2022): the crowd is the input. Twelve hours of Nuit Blanche participants accumulated into RGB ratios (avant garde, guarding, balance), generating 1,200 editions (tezosagora.org akaDrop case).
- The plotter videos (2024-2026): the machine is the performer. He films the pen arm working, not just the finished plot. In the prompts this becomes the rule: the drawing is the animation, the completion is the resting state.

## What the study did not establish

- Whether Maze's carving algorithm is depth-first or another solver (inferred as depth-first from the Maze genre and his coding style; the fxhash page was not opened).
- The exact RGB-ratio mapping in La nuit lumiere (which ratio maps to which concept) beyond the case study's one line.
- The tender.art interview audio content (listing blurb only).
- The content of the fxhash "The Fire Within" project.
- Post-2026-07-03 activity (the pull covers up to 2026-07-03; nothing newer exists in the account as of 2026-10-30).

## Prompt grounding map (how each PP871-878 traces to an observed work)

- PP871 Rain Watch (YL1): from the Rippling series (f09 heavy rain night, f12 sepia mosaic day, plus dozens of 2022-2023 posts). Mechanism: raindrop origins emit expanding concentric rings; interference is the composition. Interaction: press-and-hold as a storm cell, because rain is the only input the system understands.
- PP872 The Hatch Field (YL2): from fxhash Hex and the 2022-12-31 IG post (f10). Mechanism: hex lattice with per-cell hatch angle, density and palette slot; 128 editions in his drop, twelve modelled in the prompt. Interaction: tap cycles palette editions without re-seeding geometry, matching his edition logic.
- PP873 The Still Points (YL3): from "Disorder" for dialog() Taipei 2024 (f03). Mechanism: curl-noise thread agents repelled by circular mask voids; the composition is the tension between tangle and emptiness. Interaction: drag the large void, because the void is the compositional device.
- PP874 Weathernext (YL4): from "Storm path predictions. #Weathernext2" (2026, f01). Mechanism: an ensemble of perturbed path integrations through a noise field from a seed point over a lat/long grid; divergence is the content. Interaction: tap re-seeds on the sea, because a forecast is a seed plus divergence.
- PP875 The Plotter's Mountain (YL5): from the 2024-2026 plotter era ("Wire mountain" f04, "Fold of mountains" f00). Mechanism: 1D-noise ridge stacked into contour echoes; the pen drawing left to right is the animation. Interaction: drag bends the ridge locally, because the wire mountain is bendable wire.
- PP876 Grave of the Fireflies (YL6): from the June 2021 "Fireflies" video (f18) captioned with the film reference. Mechanism: sparse wander agents on individual blink cycles with occasional loose synchrony. Interaction: drag sweeps a breeze (his 2023 hand-tracked fluid sim made the body a wind source).
- PP877 The Carving (YL7): from fxhash Maze (companion to Hex, 128 editions, documented by Kaloh) and the "Seal" study (f06). Mechanism: recursive-backtracker maze carved in real time in one of twelve muted palettes; a solver traces the solution after the carve. Interaction: tap re-carves in the next palette edition. Never a playable maze.
- PP878 La Nuit (YL8): from "La nuit lumiere" at Nuit Blanche Taipei 2022 (f11, akaSwap case study). Mechanism: particle fountain from a wireframe sphere, per-particle color drawn from a live RGB ratio; in his installation the ratio came from 12 hours of participant data. Interaction: drag feeds the ratio, because the viewer is the participant.

## dialog() Taipei 2024 in detail

- dialog() was a four-city generative art exhibition (Tokyo, Taipei, Seoul, Beijing), curated by NEORT's NIINOMI, framed as dialogue through algorithms across language barriers (niewmedia.com).
- The Taipei stop ran Oct 11-20, 2024 at C-LAB Art Space IV 1F and East Lawn. The Taipei artist list (niewmedia.com): Natalie.J, Yi-Wen LIN, Newyellow, Che-Yu Wu, Alvis Lee, Jinyao Lin, PING SHENG WU, Chih-Yu Chen, Aluan Wang, eziraros.
- Yi-Wen Lin's contribution: "Disorder" (f03), posted 2024-08-10 with the caption "Disorder. For @dialog.asia exhibition". He also posted an "Artists Question Relay" carousel for the show (2024-09-04) and story highlights from the Taipei stop (2024-08-07, 2024-08-18), which document his preparing for the exhibition.
- Five of the ten Taipei artists are also studies in this pipeline: #209 Che-Yu Wu, #210 Newyellow, #211 Aluan Wang, #212 Jinyao Lin, #214 Yi-Wen Lin. The studies form a cluster around this single exhibition, which is the lammetje-nl template working as designed.

## Project Percentage in detail

- A nonprofit social innovation experiment based in Taiwan, combining digital art and social action (ars.electronica.art, Planet B tag page). Total: 10,000 generative art NFTs, the number symbolising Taiwan's top-100 peaks. Collectors form a DAO; donations pool into cryptocurrency public funds for charitable causes.
- Artist roster per taiwaninvienna.com: Lien-Cheng Wang, Aluan Wang, Yi-Wen Lin, Jinyao Lin, Che-Yu Wu, plus Newyellow as the sixth artist "juxtaposing five works in unique styles." The Ars Electronica listing names all six with (TW) marks.
- At Ars Electronica Festival 2022 (Sept 7-11, Linz, theme "Welcome to Planet B"), Project Percentage exhibited and presented an audiovisual performance in the Deep Space 8K venue as part of the Taiwan Special, with artists Aluan Wang, Tsung-Yun Lai, Lien-Cheng Wang and Jinyao Lin, co-organised by NTSEC and TNUA. The curatorial engagement came through TAICCA's co-production with Ars Electronica.
- This commission explains the density of mountain posts in 2022: "Ink mountain.", "Jade mountain", "I see mountains.", "Weekends are for mountains.", "Different views of the mountain ranges." The mountains were work, not a phase.

## Network entries

- Aluan Wang (study #211): Project Percentage co-artist (ars.electronica.art; taiwaninvienna.com) and dialog() 2024 Taipei co-exhibitor (niewmedia.com). Both are generative artists working with code-based landscapes; his practice includes audiovisual performance, his interactive installation. The study pipeline covered him as #211 before reaching his as #214.
- Che-Yu Wu (study #209): dialog() Taipei 2024 co-exhibitor and Project Percentage co-artist (same two sources). Pipeline study #209.
- Jinyao Lin (study #212): dialog() Taipei 2024 co-exhibitor, Project Percentage co-artist, and co-performer in the Project Percentage audiovisual performance at Ars Electronica (taiwaninvienna.com). Pipeline study #212.
- Newyellow (study #210): dialog() Taipei 2024 co-exhibitor; Project Percentage's sixth artist. Notably, #210's study records Newyellow training in Sableraph's Weekly Creative Coding Challenge (#213's host), which links the #213 and #214 subjects through a shared peer.
- Bruno Imbrizi: creator of the tender.art "Arbitrarily Deterministic" podcast; his Dec 18, 2021 episode with Yi-Wen Lin covers his first eight fxhash projects. The series also features William Mapan, Marius Watz, Andreas Rau and others, placing his in the early fxhash interview circuit.
- akaSwap: the Tezos martech tool's team collaborated with his on La nuit lumiere for Nuit Blanche Taipei 2022 (tezosagora.org forum, akaDrop case study). The case is cited as a flagship example of interactive generative art driven by crowd data.
- Kaloh: generative-art writer/collector whose paragraph.com roundup put "Maze and Hex by Yi-Wen LIN" at number one of eight fxhash artists to watch, calling out the palette and texture work across only 128 editions each.
- 80.lv: editorial coverage of the hand-controlled fluid simulation (Sept 1, 2023). Not a collaboration; an editorial signal that his interactive work travels beyond the Tezos community.

## Palette language

His palettes are disciplined and repeat across years, which makes them promptable without guessing:

- Monochrome ink: near-black ground, white ink marks (Rippling night, Wire mountain, Fireflies, Dot effect with fluid). The marks are the only light.
- Paper and pen: cream or white paper, one ink color (red threads, blue storm tracks, black contours). The paper is the ground, the ink is the system.
- Muted edition sets: cream/teal/rust (Hex), terracotta/ochre/sage/umber (1D+2D noise arcs), pink/peach atmospheric bands (mountain ranges). Three or four tones, never more, always earthy or mineral.
- Teal nocturnes: jade/teal grounds with copper or white marks (Jade mountain, Disorder). His two most "designed" pieces live here.
- Ochre minimalism: flat ochre ground, white shapes, hard shadows (Disorders). The outlier, and proof he can do flat graphic work when he wants.

A fly prompt in his register must pick ONE of these families and stay inside it. Mixing them is the fastest way to miss his.

## The pen-plotter era (2024-2026) in detail

- "Wire mountain" (2024-08-04): white pen on black paper, the plotter filmed mid-draw. The ridge is a wireframe of dense horizontal contour strokes. This is the first post where the machine, not the image, is the subject.
- "Back at plotting" (2025-09-18): "Inspired by the movement of solar systems as they orbit the centre of a galaxy." The subject matter has gone astronomical; the plotter is now the instrument for drawing orbits. The retrieved frame is the machine itself (overhead, pen arm over dark paper), which is honest evidence that by 2025 the performance of plotting is part of the work.
- "Storm path predictions. #Weathernext2" (2026-06-22): a numbered series (at least two). Forecast tracks as plotted ink. The hashtag format suggests he intends more Weathernext installments, making this a living project, not a closed one.
- "Fold of mountains" (2026-07-03): framed plots on a wall. The endpoint: the digital mountain becomes a physical object with a frame, glass, and a wall. The og:image shows navy and charcoal prints in black frames on white brick.
- For the prompts this era supplies the master rule: the drawing is the animation. A piece in his register does not fade in; it is drawn, line by line, and then it rests.

## Why this subject matters for the pipeline

- He is the fifth of the dialog() Taipei 2024 Taipei-ten to be studied (#209, #210, #211, #212, #214), which completes the exhibition cluster and gives fly a full set of prompt lineages from one curated show.
- He is the only studied artist whose signature move is the physical plot as the terminus of the digital system. Every other study ends on screen; his ends on paper. That gives the prompts a distinct motion grammar: draw, rest, re-draw.
- He is the only studied artist with a documented body-as-input lineage (TensorFlow.js hand-tracked fluid, crowd-data RGB ratios), which earns interactions that other subjects cannot justify. The prompts use this: press-as-storm-cell, breeze, gesture-fed color ratios.
- He is the only studied artist with a long-form commission structure (Project Percentage's 10,000 editions for Taiwan's top-100 peaks), which gives the mountain prompts a civic register the pipeline has not used before.
- The eight prompts deliberately avoid his personal-photography era and his commission portfolio (IBM, Barbican, FC Bayern); they stay inside the generative practice the gallery cares about.

## Research method (full)

- instagram-cli: account-search for "yi_wen_lin" and "yi-wen lin" returned multiple namesakes; the correct account was found via the artist's own site (yiwenl.github.io links to instagram.com/yiwen), then confirmed by profile read (name "Yi-Wen Lin", bio "Creative coder / Generative artist.", linktr.ee/yiwenl, 2,339 followers, 912 posts reported by profile, 984 unique post URLs retrieved by the paginated pull, public, not verified).
- Pagination note for future studies: instagram-cli `posts --username` silently ignores `--after` and repeats page 1; `posts --user-id <fbid>` with `--after <next_cursor>` paginates correctly (134 posts on page 1, then 50 per page). The account's fbid came from account-search. 19 pages, 984 unique posts, saved to hidden_files/study214/posts_raw.json.
- posts_index.txt built from created_at, media_type, url and the first 100 caption characters: 271 carousels, 419 images, 294 videos, 2010-10-19 to 2026-07-03.
- Frame indices chosen to span eras and mechanisms: 0, 1, 2 (2025-2026 plotter), 4, 6, 8, 12, 14 (2024 threads/seal/cubes/disorder), 45, 56 (2023 noise/rippling video), 177, 193 (2022 Hex, La nuit lumiere), 226, 215, 240, 288, 249 (2022 rippling/ink/disorders/mountain views/jade), 360 (2021 fluid+curl), 341 (2021 fireflies), 467 (2019 fluid dots). Downloaded via og:image extraction with an iPhone User-Agent (dl_frames.py, adapted from study213's dl.py), 20/20 retrieved, metadata in frames_meta.json.
- All 20 frames visually inspected with muse.read on 2026-10-30. Video posters (f09, f18, f19, and the plotter videos f02, f04) carry play-button overlays; motion described only where captions support it.
- Web sources (browser.search/browser.open, 2026-10-30): taiwaninvienna.com (2022-08-30), ars.electronica.art Planet B tag and digital-communities pages, ars.electronica.art Plan B Day blog (2022-08-29), niewmedia.com dialog() news (045930), paragraph.com/@kaloh fxhash roundup, tender.art/editorial/av (Bruno Imbrizi episode, Dec 18 2021), 80.lv fluid simulation article (2023-09-01), forum.tezosagora.org akaDrop thread, interactivearchitecture.org/people, yiwenl.github.io. All facts in the study trace to these sources or the IG pull; nothing is invented.

## Chronology (from the IG pull and web sources)

- 2010-2015: personal photography. Travel, family, pets, daily life. The account is a personal diary.
- 2016-2017: sparse posting, mostly life photos. No generative work yet.
- 2018: the engine appears. "Fluid." (Feb, video), "Weaving" and "Weaving - coloured." (Dec, thread weaves), early particle studies.
- 2019: fluid and particle years. "The dot effect with fluid." (Oct), "Particles form face" (Jul), "Particles" (Dec), "Another walk, trying cubes instead of plane" (Feb). libcinder AR experiments.
- 2020: noise and shadows. "Good old curl noise" (Aug), "Adding some shadows on the particles. #AR #libcinder" (Apr), "Testing some noises" (May), mountains begin ("Mountains." Sep, "Crater / mountain" Aug).
- 2021: fxhash era. Eight projects by December (tender.art). "Mixing 2d fluid and curl noise" (Mar), "Fireflies" / "Grave of the fireflies" (Jun), "Threads." (Nov). First eight fxhash projects discussed with Bruno Imbrizi (Dec 18).
- 2022: the commission years. Maze and Hex on fxhash (128 editions each; Hex posted Dec 31). Project Percentage at Ars Electronica (Sept, mountains of Taiwan in code, Deep Space 8K performance). La nuit lumiere at Nuit Blanche Taipei (Oct 1-2, 1,200 editions from participant data). The Rippling series runs all year in multiple render modes ("Reworkings on these ripples" Jan, ink and mosaic variants through the year). "Disorders" (Apr), "Ink mountain." (Jul), "Jade mountain" (Apr), "Different views of the mountain ranges." (Jan). The year everything converges: fxhash, commissions, exhibitions.
- 2023: scale and video. Rippling becomes reels ("Heavy rain in the night", "Pink Sunset", Mar). The hand-tracked TensorFlow.js fluid simulation (covered by 80.lv, Sept). "Mountains" in September, "Mixing 1D and 2D noise" (Sep).
- 2024: physicality. "Threads." and "Thread" (Jan), "Seal" (Feb, twice), "Animated patterns" (Feb), "Disorder" (Feb, and the dialog() piece in Aug), "Cubes" (May), "Weaving thoughts" (May), "Wire mountain" plotted (Aug), "Rippling" plotted (Aug), dialog() Taipei exhibition (Oct 11-20, C-LAB). The plotter moves from tool to subject.
- 2025: the plotter years begin. "Back at plotting. Inspired by the movement of solar systems as they orbit the centre of a galaxy." (Sep). The machine on camera.
- 2026: forecasts and folds. "Storm path predictions. #Weathernext2" (Jun), "Fold of mountains" framed (Jul). The account's latest posts are plotted weather and plotted mountains, hung on walls.

## Field notes on verification

- The namesake problem was real: account-search for "yi_wen_lin" returned eight accounts named Yi-Wen Lin or close variants, including a private zero-post "yiwen_lin_" (bio "brown") that was briefly a false lead. The resolution path was the artist's own site, not the search results: yiwenl.github.io links to instagram.com/yiwen, and the profile read confirmed the bio, the linktr.ee/yiwenl link, and the follower/post counts. Future studies on common names should go site-first, search-second.
- The pagination problem: instagram-cli `posts` with `--username` accepts `--after` syntactically but ignores it server-side and returns page 1 repeatedly. The first backgrounded pull (killed after ~7 minutes) would have looped forever printing growing totals only by overlap; it was killed before writing anything. The fix is `posts --account-id <own> --user-id <target fbid> --after <next_cursor>`, per the connector's references/read-results.md. This is worth adding to the study-run playbook.
- og:image retrieval was 20/20, better than study #213's 20/20 with one unusable frame. The two weak frames here (f00's framed-prints photo, f02's machine photo) are documented honestly in the gaps section rather than discarded, because what they show (framed endpoint, machine as subject) is itself evidence about his practice.
- Pronouns: multiple English sources say "his"; the IG bio and site state no gender. The study avoids pronouns throughout, per the discipline for unverified personal attributes.

## Prompt inventory (for the fly prepend, PP871-PP878)

- PP871 Rain Watch (YL1): ripple propagation and interference, press-as-storm-cell.
- PP872 The Hatch Field (YL2): hex lattice hatching, tap cycles the twelve palette editions.
- PP873 The Still Points (YL3): curl-noise thread nest around draggable mask voids.
- PP874 Weathernext (YL4): ensemble storm-track integration over a lat/long grid, tap re-seeds.
- PP875 The Plotter's Mountain (YL5): live contour drawing of a noise ridge, drag bends it.
- PP876 Grave of the Fireflies (YL6): sparse blink-cycle agents, drag sweeps a breeze.
- PP877 The Carving (YL7): real-time depth-first maze carve in edition palettes, tap re-carves; never a game.
- PP878 La Nuit (YL8): participant-fed RGB-ratio particle fountain, drag feeds the ratio.
