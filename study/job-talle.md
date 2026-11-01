# Job Talle — koi ponds and living water

Study date: 2026-11-01. Hans-directed (no ig-artist-study number).
Subject: **Job Talle** — jobtalle.com, @jobtalle on X. Dutch indie game developer / simulation programmer.
Known for: **Koi Farm** (koi breeding game, Steam Feb 2021, open source github.com/jobtalle/Koi),
and a blog of unusually well-explained simulation write-ups, each with live interactive demos.

This study focuses on his **koi pieces and water movement**: how the fish steer, how the water
ripples, and how the two systems talk to each other.

## Works inspected (16)

### The game
1. **Koi Farm** (released 26 Feb 2021; Steam/itch.io/iOS/Android; 94% positive, ~1k Steam reviews;
   nominated for the Cinekid game & app award). A koi breeding game: crossbreed procedurally
   generated koi, discover mutations, collect them as trading cards. Open-sourced 31 Mar 2021
   (github.com/jobtalle/Koi, ~413 stars). Still maintained — latest commit Feb 2026 (Serbian
   translation). Per his X bio he is "Making a sequel."
2. **itch.io devlog posts** (Mar–Nov 2021): patch notes show the living details — lightning
   flashes during thunderstorms made toggleable for epilepsy; grass audio toggle; player-contributed
   translations (Japanese, Spanish, Serbian); Mac build contributed by community member ItchyTanuki.

### The articles (read in full, with their interactive demos)
3. **"Digital koi breeding"** (12 Jun 2022) — how Koi Farm's pattern genetics work (see Mechanisms §9).
4. **"Convolutional textures"** (7 Jan 2019) — GPGPU self-updating textures: Game of Life, falling
   sand, then the key one: a **water heightmap** (R = height, G = momentum, 16-bit precision) with
   waves painted on as blobs, and a grass/wind field (R,G = displacement, B,A = velocity).
   Credits the wave algorithm to **Hugo Elias**.
5. **"Swarm behaviour"** (1 Feb 2018) — his Boids implementation after **Craig Reynolds** (1986):
   repulsion/alignment/attraction zones, attraction angle (field of view), gravitation toward view
   center. Notes the O(n²) cost honestly.
6. **"Simulated ecosystems"** (3 Dec 2018) — closed ecosystems with **constant mass**: hex grid,
   agents (plants, rabbits, foxes) with mass-costed actions (move 10%, copy 10%, idle 1%...),
   eat-only-if-2x-heavier rule. Population graphs follow Lotka-Volterra cycles. Inspired by a real
   mason-jar ecosystem on his windowsill.
7. **"Neuroevolution in squids"** (24 Apr 2020) — spiking neural networks evolved to swim;
   tentacle segments with spring return; fitness = food eaten / body mass.
8. **"Simulating hydraulic erosion"** (14 Jun 2020) — "snowball" droplet erosion (drops gain
   sediment downhill, shed it when too big, erode at their *previous* position so they don't dig
   themselves in). **Appendix: rendering shore waves** — Voronoi diagram of the shore via the
   **jump flooding algorithm** (cites Alan Wolfe's blog.demofox.org), distance+direction to shore
   stored per-pixel, a sine wave phased by shore direction drifting shoreward, then stylized and
   broken into individual wavelets. Animation posted to his Twitter.

### The source code (read directly, github.com/jobtalle/Koi, master branch)
9. `js/koi/fish/fish.js` — steering constants, update loop, `interact()`, `chase()`, `turn()`,
   `mate()`, `constrain()`.
10. `js/koi/fish/fishBody.js` — vertebra-chain spine kinematics, `disturbWater()`.
11. `js/render/water.js` — the Water convolutional buffer (SCALE = 17), `addFlare()`.
12. `js/render/waves.js` — the full wave-propagation GLSL shader (Hugo Elias scheme).
13. `js/render/ponds.js` — the pond compositor shader (refraction, reflection, shore waves,
    weather color filter).

### Secondary (used to cross-check, not as primary evidence)
14. DeepWiki pages on jobtalle/Koi (fish behavior, water simulation, weather, rendering pipeline)
    — consistent with the code I read; used only to confirm.
15. jobtalle.com games page (Koi Farm + Locomerchant listing, Cinekid nomination).
16. TwStalker mirror of his X profile (@jobtalle, ~2k followers, bio "Made Koi Farm / Making a sequel").

Could not access: his actual X post stream (no X access in this environment); the pre-2017 blog
archive beyond the 14 latest posts. Neither is load-bearing for the mechanisms below.

## Evolution

Talle's career reads as a **technique pipeline that converges on Koi Farm**:

- **2017 — tools.** "Cubic noise" gives him his own coherent-noise primitive; it later shows up
  in the sand floor, wind gusts, and koi pattern generation. He builds primitives, not pieces.
- **2018 — behavior.** "Swarm behaviour" (Boids) becomes the koi steering core; "Simulated
  ecosystems" gives him the closed-system, mass-conserving ecology mindset (plants → rabbits →
  foxes is the dry-land rehearsal for pond → koi → player).
- **2019 — water.** "Convolutional textures" is the breakthrough: the GPU ping-pong heightmap
  that becomes Koi Farm's water *and* its wind. He publishes the technique two years before the
  game that depends on it.
- **2020 — craft.** "Hydraulic erosion" (with its shore-wave appendix) and "Neuroevolution in
  squids" (procedural swimming) are the last two missing organs: believable shores and
  believable locomotion.
- **2021 — synthesis.** Koi Farm ships: Boids fish + convolutional water + weather state machine
  + genetic patterns, all in one pond. Open-sourced a month later.
- **2022–2023 — deepening.** "Digital koi breeding" documents the genetics; "Distance field
  transparency" polishes rendering edges.
- **2026 — maintenance + sequel.** Still committing translations; X bio says a sequel is in
  development.

The pattern: **every article is a subsystem audition; Koi Farm is the cast that got hired.**
Nothing in the game was invented for the game — each system had already survived its own
write-up and demo.

## Network (all evidenced, no guesses)

1. **Craig Reynolds** — cited by name in "Swarm behaviour": "One of the first algorithms for
   flocking called *Boids* was made by Craig Reynolds in 1986. The simulation I have implemented
   mostly follows his design." The koi schooling in Koi Farm is a direct descendant.
2. **Hugo Elias** — credited in "Convolutional textures": "I won't go into the method that
   updates the heightmap, but I borrowed it from the website of *Hugo Elias*." The entire water
   simulation (and the waves.js shader I read) is the Elias discrete wave equation.
3. **Alan Wolfe (blog.demofox.org)** — cited in the "Simulating hydraulic erosion" shore-wave
   appendix: "This blog post explains the *jump flooding algorithm* which was used to generate
   the Voronoi diagram on the GPU." His shore-distance wave field comes from Wolfe's technique.
4. **Community collaborators** — itch.io devlog, 21 Jun 2021: "Thanks to ItchyTanuki (who paints
   lovely watercolors), a Mac build for koi farm is now available." Players contributed Japanese,
   Spanish, and Serbian translations. He builds in the open and absorbs contributions.

## Mechanisms — what makes the koi and water feel alive

All of the following are read from his articles and/or source code (file + line context given).
Nothing here is inferred from screenshots.

### M1. The wake is a record of tail effort (fishBody.js: disturbWater)
Each frame, the body measures how far the **tail vertebra** (spine[length-2]) moved since the
last frame. If that displacement exceeds `SPEED_WAVE_THRESHOLD` (.055), it paints a flare into
the water heightmap at the tail's position with
`intensity = WAVE_INTENSITY_MIN (.05) + (tailSpeed − threshold) × WAVE_INTENSITY_MULTIPLIER (2)`,
jittered by `WAVE_TURBULENCE` (.4). Radius .15.
Watchable behavior: a gliding fish leaves almost no wake; a fish that flicks its tail hard
throws a visible ring. **The water remembers effort, not position.** The same function also
fires positional tail-splash audio (pan by x-position, volume by tail speed, different samples
for big vs. small fish).

### M2. Nibble ripples (fish.js: update)
When a fish's speed decays below `SPEED_NIBBLE` (.0155), a countdown (20–40 ticks) fires: the
fish gets a small random turn (`NIBBLE_TURN_FORCE` .07) **and paints a water flare**
(`NIBBLE_RADIUS` .1, `NIBBLE_DISPLACEMENT` .25) at its own position.
Watchable behavior: slow fish periodically dip and release a small expanding ring — it reads as
feeding. The pond is never still because the fish themselves keep plucking it.

### M3. Turn contagion (fish.js: interact)
Fish pair up within `RADIUS_ATTRACTION` (1.5). `recognizes(other)` is true only when both fish
share the same **palette index** — same-colored koi are the same "species" and school together;
different colors ignore each other. Within the pair:
- **Speed matching** (`SPEED_CATCH_UP` .0045): the slower fish accelerates toward the faster —
  schools converge on a common pace.
- **Repulsion** (`FORCE_REPULSION` .45, radius .6): proximity-weighted push, applied symmetrically.
- **Turn copying** (`TURN_FOLLOW_CHANCE` .025): if one fish is mid-turn and its neighbor isn't,
  the neighbor may copy the turn direction with `TURN_CARRY` (.95) of the force.
Watchable behavior: one fish decides to wheel, and the turn **ripples through the school** like
a rumor. This is the single most alive-looking thing in his fish code.

### M4. Pulse-glide locomotion (fish.js: update)
Speed decays by `SPEED_DECAY` (.996) every tick toward `SPEED_MIN` (.015); a random
`BOOST_CHANCE` (.003) triggers a tail-flick burst (`BOOST_POWER` .0015/tick, 5–30 ticks, capped
at `SPEED_MAX` .078). Random turns fire with `TURN_CHANCE` .0016 — but **`.05` when raining**
(30× more restless in rain). Speed scales with body size: bigger fish cruise faster.
Watchable behavior: fish don't swim at constant speed — they **surge and coast**, and the whole
pond gets agitated when rain starts. Weather is a behavior parameter, not just a backdrop.

### M5. Vertebra-chain spine (fishBody.js: update)
The body is a chain of vertebrae. The head is placed, then each vertebra follows the previous
at fixed `spacing`, corrected by a spring term that pulls the chain toward the head's heading
(springiness increases for small fish). The head's target angle **oscillates**:
`direction.angle() + π + cos(phase) × speedFactor × SWIM_AMPLITUDE (11)` — wiggle amplitude
grows with speed above `SPEED_SWING_THRESHOLD` (.01). The phase advances by
`SWIM_SPEED (6) × speed / size` — **large fish undulate slowly, small fish buzz**.
Watchable behavior: the whole body S-curves through turns; the tail lags the head exactly like
a real fish. No keyframed swim cycle anywhere.

### M6. Convolutional water (water.js, waves.js, "Convolutional textures")
The water is a GPU ping-pong texture at **1/17 scene scale**. Each pixel: R = height, G =
previous height (momentum), B unused. The fragment shader (Hugo Elias scheme):
`newHeight = (left + right + up + down) − 2.0 − momentum`, then `× DAMPING (.997)`,
re-centered on 0.5. **16-bit channel precision** (8-bit rounding would eat the subtle waves).
NEAREST filtering during simulation, LINEAR only for display. Influences (fish tails, nibbles,
rain, cursor) are painted by a **separate influence-painter shader** so alpha blending can't
contaminate the momentum channel.
Watchable behavior: ripples from different sources **interfere and pass through each other**;
everything calms to glass via the .997 damping. One cheap texture does the whole pond.

### M7. The pond compositor (ponds.js)
The final water look is a shader that:
- derives **surface normals from heightmap gradients** (finite differences of the .gr channels,
  time-interpolated),
- **refracts** the pond floor: background sampled at `uv − depth × normal.xz` — the sand visibly
  bends under ripples,
- **reflects**: a reflections texture sampled at `uv + height × normal.xz`, weighted by
  `REFLECTIVITY` (.15), with shore distance in its alpha,
- draws **shore-hugging wave bands**: `cos(shift − shoreDistance × 6.0)` — foam lines that cling
  to the pond edge and drift,
- tints everything with a **weather color filter** (overcast cools the water, sunset warms it).
Watchable behavior: you see the *floor* wobble before you notice the surface — depth is faked
by bending the sand, not by drawing water.

### M8. Shore waves from a distance field ("Simulating hydraulic erosion", appendix)
A Voronoi diagram of the shoreline (jump flooding, GPU) gives every water pixel its
**distance and direction to the nearest shore**. A sine wave's phase is set by the shore
direction so crests travel **toward the beach**; the pattern is then stylized and broken into
wavelets so each wave reads as its own entity.
Watchable behavior: waves arrive at the shore instead of sliding past it — the edge of the
water feels like a place, not a crop.

### M9. Noise-slice pattern genetics ("Digital koi breeding")
Patterns come from **slicing 3D cubic noise with a plane** and thresholding: above threshold =
spot. **Mutation = nudging the plane** a little through the same noise (small visual steps);
**crossbreeding = interpolating the parents' planes** (offspring land between the parents, then
mutate). Multiple pattern layers stack for 3+ colors; stripes/ridges/brindle are variants.
Fish bodies are shaded by **darkening toward the edges** (no 3D lighting), fins and eyes drawn
on top of the pattern texture.
Watchable behavior: breeding is *legible* — you can watch a spot migrate toward the head over
generations, because the parameter space is continuous.

### M10. Weather as a system (weather.js, rain.js)
A 5-state machine (SUNNY → OVERCAST → DRIZZLE → RAIN → THUNDERSTORM) with a transition matrix.
Rain particles that "land" call `water.addFlare()` — **every raindrop is a ripple**. Wind gusts
(cubic noise) displace the **air buffer**, which the vegetation vertex shader samples — plants
sway in the same wind that ruffles the water. Fish turn-chance jumps 30× in rain (M4). Ambient
audio crossfades per state.
Watchable behavior: a storm is one event expressed in four media at once — sky, water, plants,
fish. Nothing is decorative; every visual has a simulation behind it.

## Piece prompts

Each prompt is grounded in ONE mechanism above. Interaction follows Hans's rule: only where the
system earns it, never click-to-reload; watch-only where the motion is the point.

### P1. "The Wake Remembers" (mechanism M1)
- **Visual:** top-down pond at dusk. Three koi cruise slow loops. Wherever a tail sweeps hard, a
  luminous ring blooms and fades over ~20 seconds; overlapping wakes interfere into moiré.
- **Palette:** deep indigo water, warm amber wake-rings, pale sand floor visible through the
  shallows.
- **Composition:** full-bleed pond, no shore visible — the water is the whole world.
- **Motion/interaction:** watch-only. The piece earns stillness: the wakes *are* the event.
- **Technical approach:** heightmap ping-pong at 1/16 scale (M6); tail-vertebra displacement
  above a threshold paints flares (M1); vertebra-chain bodies (M5). Wake brightness ∝ tail
  speed so bursts read as flashes.
- **Avoid:** constant-speed fish (kills M4's pulse-glide); wakes that follow the body instead of
  the tail; decorative particle trails.
- **Ref:** studies/job-talle.md M1, M5, M6.

### P2. "Rumor of a Turn" (mechanism M3)
- **Visual:** a school of twelve same-colored koi (pale gold) drifting. Every so often one fish
  wheels sharply — and the turn propagates through the school fish by fish, a visible wave of
  turning.
- **Palette:** gold fish on slate-blue water, white sand.
- **Composition:** the school starts as a loose ellipse center-frame; turns carry it across the
  frame and it re-forms.
- **Motion/interaction:** tap anywhere to startle the nearest fish (chase() + boost) and watch
  the turn contagion do the rest. Tap is a *disturbance*, not a reload.
- **Technical approach:** Boids with palette-gated recognition, speed matching, and
  turn-copying at low probability (M3); pulse-glide speed model (M4). One instigator is enough —
  emergence does the choreography.
- **Avoid:** scripting the school's path; making all fish turn at once (the delay *is* the
  beauty); mixing colors (breaks the recognition rule).
- **Ref:** studies/job-talle.md M3, M4.

### P3. "Nibbling Hours" (mechanism M2)
- **Visual:** shallow pond, morning. Koi drift almost motionless; every few seconds one dips its
  head and a perfect small ring expands from it, overlapping with others into a slow lace of
  circles.
- **Palette:** pale jade water, soft white rings, dark green lily pads for contrast.
- **Composition:** sparse — six fish maximum, lots of empty water so each ring reads.
- **Motion/interaction:** watch-only. A meditation on small disturbances.
- **Technical approach:** speed-decay locomotion with nibble countdowns that paint flares
  (M2); high damping (.999) so rings live long; minimal fish count.
- **Avoid:** busy water — more than a few rings at once turns lace into noise; fish that never
  slow down.
- **Ref:** studies/job-talle.md M2, M6.

### P4. "Arriving Waves" (mechanism M8)
- **Visual:** an island pond seen from above. Wavelets form in open water and travel visibly
  *toward* the shore, breaking into stylized foam arcs as they arrive, then dissolving.
- **Palette:** turquoise shallows grading to deep teal, white foam, warm sand island.
- **Composition:** island off-center, occupying a third of the frame; open water for waves to
  cross.
- **Motion/interaction:** watch-only loop. Drag could stir a gust (M10's air buffer) but the
  piece doesn't need it — keep it still.
- **Technical approach:** shore distance+direction field (jump flooding or a static SDF);
  sine-wave phase keyed to shore direction, amplitude growing as distance → 0 (M8); pond
  compositor for refraction (M7).
- **Avoid:** waves sliding parallel to shore; uniform sine grids (break them into wavelets);
  foam that doesn't fade.
- **Ref:** studies/job-talle.md M8, M7.

### P5. "Rain Makes Them Restless" (mechanisms M4 + M10)
- **Visual:** the pond under a passing shower. Raindrops stipple the water with tiny rings;
  the koi, calm a moment ago, begin darting and wheeling — then settle as the rain eases.
- **Palette:** grey-green overcast water shifting back to blue; silver rain rings.
- **Composition:** full pond with a few lily pads; weather is the protagonist.
- **Motion/interaction:** watch-only. The storm arrives on its own 90-second cycle.
- **Technical approach:** weather state machine driving rain-particle → water-flare coupling
  (M10) and a 30× turn-chance multiplier on the fish (M4); color filter lerps with the state.
- **Avoid:** rain as a visual overlay with no simulation behind it; fish ignoring the weather.
- **Ref:** studies/job-talle.md M4, M10.

### P6. "One Fish, Swimming" (mechanism M5)
- **Visual:** a single large koi, close up, turning slow figure-eights. The body S-curves, the
  tail lags and sweeps, pectoral fins flutter. Nothing else moves except its wake.
- **Palette:** white-and-vermillion koi (Kohaku) on near-black water — a portrait.
- **Composition:** the fish fills a third of the frame; camera gently follows.
- **Motion/interaction:** drag to lead the fish — it steers toward your pointer with the same
  turn physics, body lagging behind. Touch earns its place: you feel the spine.
- **Technical approach:** vertebra-chain spine with speed-scaled wiggle amplitude and
  size-scaled phase rate (M5); tail-effort wake (M1). One fish, all budget on the body.
- **Avoid:** keyframed tail wag; the head turning without the body following; trailing the
  pointer rigidly.
- **Ref:** studies/job-talle.md M5, M1.

### P7. "The Spot Migrates" (mechanism M9)
- **Visual:** a koi seen from directly above, slowly rotating. Its pattern — a red patch —
  drifts across its body over a minute, morphing from saddle to head-spot, as if generations
  are passing.
- **Palette:** white fish, vermillion pattern, still pale-blue water (the fish is the exhibit).
- **Composition:** centered fish, generous negative space, museum-calm.
- **Motion/interaction:** watch-only. Tap to reseed the noise field (a fresh lineage), not to
  reload.
- **Technical approach:** pattern = thresholded slice of 3D cubic noise; animate the slice
  plane drifting through the noise volume (M9); edge-darkened body shading, fins on top.
- **Avoid:** crossfading between textures (the morph must be continuous through the noise
  space); spots popping in/out.
- **Ref:** studies/job-talle.md M9.

### P8. "The Floor Bends" (mechanism M7)
- **Visual:** a shallow pond over rippled sand. There are no fish. A breeze crosses the water in
  gusts; wherever a ripple passes, the sand floor visibly bends and shimmers beneath it —
  depth rendered as refraction.
- **Palette:** sunlit aqua shallows, golden sand, white glints.
- **Composition:** low sun angle implied by long soft shadows; the floor is the subject.
- **Motion/interaction:** drag across the water to rake ripples with your finger and watch the
  floor warp under them. Direct, physical, earned.
- **Technical approach:** heightmap normals → background UV offset by depth × normal (M7);
  gust field from cubic noise displacing an air buffer that also sways a few reeds (M10).
- **Avoid:** drawing "water" as a blue overlay; caustics without a heightmap behind them.
- **Ref:** studies/job-talle.md M7, M10.
