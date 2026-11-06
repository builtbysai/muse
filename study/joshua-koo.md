# Joshua Koo: Study Notes

**Site:** Joshua Koo — GitHub @zz85, X @blurspline, Seattle (from Singapore). Ex-Zopim/Zendesk employee #12, now at AWS. Core contributor to three.js. His site is one line of self-description: "I'm Joshua and this is my playground." He calls himself "random. Codes. Cycles. Climbs. Cold jokes. Organizes creative coding meetups." He uses `.random()` frequently in code and experiments on random ideas in his free time.

**Doorway:** Hop from the Inti-Illimani study: Inti-Illimani made many instruments sound as one band; Koo makes many particles, many fish, many brushstrokes behave as one system. The doorway is the same question — how does a multitude become a single living thing? Hans sent the koi pond, and the pond sent us to its maker.

**Depth:** ~20 works inspected. Deep: the koi pond (BLOG.md and README.md read end to end; koi.js, glsl.js, ink.js, pond.js read in part — heads, caustic and ink-step code, and greps, not all 2,457 lines), Aquarelle (README read end to end), Sorairo (README read end to end). Medium: file listings of the other vibes sketches (ink-bleed, brain-waves, night-sky, alkan-etude-8bit). Via secondary sources: photo particles (CreativeJS), three.js GPGPU flocking and sparks.js (CampJS bio, sparks.js wiki, PhysicsRenderer), SimplifyModifier (CodePen source, three-stdlib), Preetham sky (CodePen, three.js ShaderLib), threejs-path-flow (DeepWiki, his site, three.js issue #13553), threejs-term (npm.io, jsDelivr), soft-body cloth (his own 2012 Hacker News post), the 512K-particle fluid sim (Hacker News, Hatena). NOT accessible: his X timeline directly (x.com is not fetchable here); the koi pond, Sorairo, or Aquarelle running live (no browser render in this task — the repo's own screenshots were not viewed as images); the full koi/pond/paint source line by line; most early jsdo.it and CodePen pieces firsthand, only via secondary descriptions. Nothing here is invented; where a mechanism is described from a secondary source, the source is named.

## The spine: bend a fixed body in the shader

The koi is the clearest statement of Koo's central trick. Each fish is a fixed mesh in its rest pose that the vertex shader bends along a moving spine. The CPU only moves 16 spine points per fish.

The body is a lofted tube: 52 rings with 24 points around each. Three profile functions of position along the body, `s`, set its width from above, the height of its back, and the depth of its belly. Each rises with a quarter-ellipse, peaks about a third of the way back, tapers, and closes with a cap at the tail root. The fins are six small grids in one mesh: paired pectorals and pelvics, a dorsal strip, and a forked tail tilted so it shows from above. Butterfly koi get pectorals 1.85× longer and a tail twice as long.

The spine is a chain. Point 0 is the head. Every later point follows the one in front at a fixed spacing, like a chain dragged along a path, with each bend limited to 0.2 rad and relaxing back toward straight. The body therefore follows the path the head took, and in a turn the tail traces the same curve.

In the shader, each vertex interpolates a Catmull-Rom curve through the nearest spine points to get a centre and a forward direction, then adds a swimming wave, `amp · env(s) · sin(phase − 5.4·s)`, where `env` keeps the head still and grows toward the tail, so the wave travels from head to tail. The wave's derivative tilts the frame, so cross sections stay square to the bent body. Fins add their own lagged motion on top: the dorsal trails the body's sway, the tail's trailing edge lags further, and the paired fins fold in, spread out, and paddle. The shadow pass reuses the same vertex code.

The colour patterns are two 3D noise fields evaluated at the fragment's rest-pose position and thresholded, so they bend and move with the body. Twelve varieties are table entries: colours, thresholds, whether black stays on the back or wraps the body, red on the head, the darkness of the net pattern of scale edges, and metallic sheen. Asagi and tancho get special cases for the blue back and the single red spot. Overlapping scale rows, eyes, and nostrils are placed by position on the rest body.

This is the same mechanism as his earlier threejs-path-flow (2018): a mesh bent along a curve, path positions and Frenet frames (tangent, normal, binormal) generated from a three.js Curve, stored in a DataTexture in 4 rows, the vertex shader reading the texture and transforming the position by its offset. Path-flow came from seeing @leon196's curve modifier for Unity3D and thinking there was no reason it could not be done in js/web/three.js. The koi is path-flow with the curve replaced by a living spine — the same deformation, now driven by behaviour instead of a spline the user drags.

**Takeaway:** Build the body once, in rest pose, and bend it in the shader. The CPU should move a handful of control points; the GPU does the deformation. If a creature's motion can be expressed as a spine plus a travelling wave, the mesh never needs to be rebuilt.

## Beat and glide: rhythm is what makes it read

Each fish adds up steering wishes: wander, look ahead to avoid walls, keep clear of fish at a similar depth, and loosely line up with neighbours. Touch adds pellets to chase, a held finger that calls fish over, and ripples they shy away from.

But the thing that makes them read as koi rather than generic fish is the rhythm. They swim by beat and glide: below 90% of target speed a fish beats its tail and accelerates, and above 112% it glides with the tail nearly still. Tail frequency follows speed and amplitude follows thrust. The pectorals are folded when gliding, spread to brake when slow, and the one on the inside of a turn spreads further. Cruising speed is about 0.3 body lengths per second. Koo says this rhythm does more than anything else to make the fish read as koi.

**Takeaway:** The motion's rhythm is the identity, not the shape. A creature is recognised by how it moves in time — beat, then coast; thrust, then stillness — before it is recognised by its outline. When building a moving thing, design the gait first and the geometry second.

## The surface is never stored: analytic water and caustics

The realistic water is one full-screen pass that traces each pixel through the moving surface, plus a caustic pass, a shadow pass, and a tone-mapping pass. The surface is never stored as a height map. Its slope is computed analytically wherever it is needed: a long low swell, short wind waves 16–35 cm long with capillary-gravity dispersion (`ω = √(gk + σk³/ρ)`, at half speed for calm), stronger in drifting patches where a breath of wind touches the water; up to 24 touch ripples, each a ring-shaped wave packet that spreads, widens, and fades; standing waves across the pond when the phone is tilted or shaken.

Refraction: the view ray meets the surface plane, bends through the surface normal (`refract`, n = 1.333), and hits the bottom 1.1 m down. The pebble bottom is generated once into a texture with mipmaps: rounded stones in a jittered grid, seven kinds of rock, silt between them, baked light on the domes and dark crevices.

Caustics are simulated every frame on the GPU from the same wave and ripple slopes. For each texel of the bottom, the pass finds where its sunlight crossed the surface, stepping back along the sun direction and correcting for the bend, then takes the light's concentration as `1 / det(J)`, where J is the Jacobian of the surface-to-bottom map, built from the Hessian of the surface height. Where the waves focus light, the determinant shrinks and the bottom brightens. That gives the moving net of bright lines without tracing any photons.

Light under water combines four things: sun dimmed by Beer-Lambert absorption down the water column, with red lost first; dappled shade from a swaying maple canopy, as drifting noise; the caustic net; and blurred shadows of the fish, pads, and leaves, from a shadow map rendered along the sun direction — plus blue ambient sky light. On the way back up, the water absorbs the colour again along the view path and adds the light the water scatters back, so deep water turns green-blue and murky.

The fish are rendered normally into their own target. The composite then shifts where it reads that target by the screen distance between where the bent ray and the straight ray reach the fish's depth, so the fish wobble and shift under the ripples just as the bottom does, without being rendered once per ray. The canopy and sky reflect with a Fresnel weight (Schlick, 2% at normal incidence), so the reflection is faint looking straight down and strong at grazing angles. A final pass applies a vignette, ACES tone mapping at exposure 1.25, gamma, and dither. Colour is linear throughout and stored as `sqrt` in 8-bit targets so the dark water does not band — no float render targets are needed, which keeps older phones working.

**Takeaway:** Do not store what you can compute. A surface that exists only as a formula for its slope is cheaper than a heightmap and more flexible — the same slopes feed the refraction, the caustics, and the shading. When a physical effect has a closed form (1/det J for focusing, Beer-Lambert for absorption), use the formula and skip the simulation.

## One simulation, three paintings

The koi pond has three styles — realistic, watercolour, and ink — and all three share the same fish and the same water simulation. They differ only in how the result is drawn. It is plain ES modules with no build step and no dependencies beyond three.js, and it installs as a PWA and works offline after the first visit. It is made to leave open on a phone.

The watercolour pass blurs the frame into flat washes. The deep water is lifted to a mid tone and saturated, then converted to pigment density and laid over cold-pressed paper with `paper * exp(-density)`. Pigment pools at the edges between washes, settles in the paper's tooth, flocculates in darker washes, and blooms unevenly. A ragged border of paper is left bare. The outlines "boil" at 8 frames a second while the paper stays still, like a hand-painted animation, and the koi go on swimming through it.

The same watercolour physics is a whole separate piece, Aquarelle: watercolour painting in the browser, built on a fluid simulation rather than textured stamps. Paint is pigment carried by water: it flows while the paper is wet, blooms when you drop wet into wet, darkens at the edges as it dries, settles into the paper's tooth, and glazes over dried layers. Ten brushes (Round, Wash, Flat, Rigger, Dry brush, Splatter, Soft pastel, Pastel pencil, Clear water, Lift), plus Smudge, Eraser, and an eyedropper. Made for Apple Pencil / stylus first. No backend, no build step, no dependencies: plain ES modules and WebGL2.

**Takeaway:** Build one system, render it many ways. If the simulation is honest, the style is a choice of renderer, not a rebuild. A pond that can be realistic, watercolour, and ink from the same fish is three pieces for the price of one system — and each style teaches you something about the others.

## Ink is a density field, not a drawing

Ink mode's reference is CCTV's "Ink" commercial (Weareflink / Troublemakers, 2010): animals in dense, dark brushwork at the head that dissolve into smoke behind. Ink mode keeps two separate clocks. Keyframes at 8 fps: the fish, pads, and petals are rendered as pigment onto a white target only 8 times a second (the fps button can drop it to 4, 2, 1, ½, or ¼). Between keyframes the painting holds still. Ink simulation every frame: a density field of ink is advected, diffused, and faded at the display rate, so the smoke keeps moving while the fish jump between poses.

The field is one channel of density in ping-pong targets: half-float where available, otherwise 8-bit storing a quarter of the density. One pass per frame: velocity, added up analytically with no pressure solve (a slow pond current from the curl of drifting noise; a little drag along each fish's body; a jet behind each tail, flicked left and right with each beat, plus swirls shed by the tail that alternate direction; curl noise confined to each fish's wake; and the push from touch ripples); semi-Lagrangian advection (each pixel looks up where its ink came from); diffusion toward the four neighbours, with small noise eddies that fray thin edges into wisps; and fade that is faster for dense ink and faster near a fish that is swimming hard. A beating fish's trail clears in about a second, and a gliding fish's lingers.

Every source is either a curl or a local jet, so the flow is close to divergence-free and needs no projection step. On a phone that is the difference between one pass and a dozen.

Stamping keyframes straight in left a sharp ghost of every fish, and within seconds the pond was marbled with black bands. The stamp is now read from a blurred mip level and laid down at 45% strength. The fish push the water gently and mostly control how fast their ink fades, so a trail still shows how the fish swam without being thrown across the pond. The current keyframe goes on top, read slightly blurred and wobbled by noise of about 2 pixels, with a softer copy behind it like ink bleeding into damp paper. Density becomes colour through a per-channel absorption that leaves thin ink a cool blue-grey and thick ink a warm, purplish black. All of it sits on cold-pressed paper: noise bumps and fibres lit from the top left, with ink settling darker in the hollows.

**Takeaway:** Separate the clocks. A painting that updates at 8 fps and a fluid that updates at 60 fps gives you both the crispness of a keyframe and the continuity of smoke. And make the velocity divergence-free by construction (curls and jets only) so you never pay for a pressure solve.

## Particles live in a texture

Koo's particle work is the thread that runs from his earliest pieces to the koi. His particle library sparks.js was, in his own CampJS bio's words, "his most popular github repository" — "a guy who fell in love with particles and javascript." The sparks.js wiki, "Different Methods to Animate Particles in the Browser," walks the ladder: DOM manipulation + CSS, 2D canvas, WebGL canvas, and particle simulation with shaders. Each step exists because the previous one ran out of room — DOM for tens, canvas for thousands, WebGL for hundreds of thousands.

The photo-particles demo decomposes an image into a bazillion dancing particles. CreativeJS: "Decomposing images into a bazillion dancing particles certainly isn't a new idea, but this three.js based demo from @BlurSpline is a particularly nice example. Spherical repulsion and noise are among the transition effects available, and while the reformation of each subsequent image could be a bit smoother, the overall effect is still rather pleasing. The majority of the heavy lifting is in the shaders, which are fairly readable in the source."

His three.js GPGPU flocking examples became part of the canon: the PhysicsRenderer tutorial cites "ThreeJS GPGPU Examples — a great example of flocking by @BlurSpline" alongside Soulwire's GPGPU particles and mrdoob's Sporel.

The technique that travelled furthest is a single tweet (Jan 2023): store particle positions and velocity vectors in a float32 texture's RGBA values, and update them by rendering a quad in one draw call — the update is a fragment shader. A later author of a 512K-particle fluid sim wrote: "For the massive speed I'm updating the particle data with a clever fragment shader trick that I've learned from https://twitter.com/BlurSpline/status/161806273602519040. The main idea is that the particle positions (and the velocity vectors too, each 2D only) are stored in a texture's rgba values (float32). So updating the particles data is in fact a render process of a quad in one draw call." The particles live in a 1024×512 texture — 524,288 of them, all visible. There is no direct interaction between any two particles; the particles are projected to a density texture that is diffused with an optimised two-pass Gaussian blur and several resolution reduction steps, and the gradient of the diffused density updates each particle's velocity with verlet integration.

The fluid sim itself is Evgeny Demidov's WebGL GPU fluid shaders. The 512K-particle author is explicit: "the fluid simulation code is not by me! Evgeny Demidov is the original author of the WebGL shaders for that. I'm only adding to the current advection matrix." And the Hatena bookmark that surfaced it: "Fluid simulation with 512K particles by Flexi23 GPU fluid simulation originally by Evgeny Demidov. This would also not have been possible without the preparatory work of zz85 / @BlurSpline, Kudos!"

**Takeaway:** Put the state in a texture and let a fragment shader be the update loop. A particle system where position and velocity live in RGBA and the step is one quad render scales to half a million particles with the CPU idle. And when the particles need to interact, do not compute pairwise forces — project them to a density field, blur it, and let the gradient of the blur steer them.

## The sky is a formula

The Preetham sky is the same analytic instinct applied to the atmosphere. "A Practical Analytic Model for Daylight" (Preetham, Shirley, and Smits) gives the sky's colour as a formula of sun position and view direction. First implemented by Simon Wallner, improved by Martin Upitis, the three.js integration is by zz85 — `THREE.Sky`, `ShaderLib['sky']`, still in three.js today. No skybox texture, no cubemap: the sky is a function, evaluated per pixel.

**Takeaway:** When a natural phenomenon has a published analytic model, port the model, not a picture of it. A sky that is a formula works at every sun angle, costs nothing to store, and never repeats.

## Simplify by collapsing the cheapest edge

SimplifyModifier is Koo's other long-lived three.js contribution, and it shows the same taste for a cheap, greedy rule that converges. It is based on Stan Melax's 1998 "A simple, fast, and effective polygon reduction algorithm" — a Progressive Mesh type polygon reduction. The cost of collapsing an edge is its length times the local curvature, plus a term that preserves borders. Repeatedly collapse the cheapest edge. The modifier is still in three.js and three-stdlib, and it powers in-browser tools like the 3D Low Poly Generator, which decimates a 100K-triangle bunny in the browser with three.js alone.

**Takeaway:** A greedy local rule, applied repeatedly, is often enough. You do not need a global optimiser to simplify a mesh, a path, or a field — collapse the cheapest thing, re-evaluate, repeat, and stop when it looks right.

## Cloth is a massless spring net

The earliest work in this study is the soft-body series from 2012, and Koo describes it himself on Hacker News: "This set of experiments started from a simple hook's law doodle, to spring simulation, string simulation, and I realized I once again stepped onto physics and particle simulation, this time, more specifically soft body physics. Based on the 'Advanced Character Physics' article, this experiment attempts to use a 'massless' cloth simulation model." The article is Thomas Jakobsen's "Advanced Character Physics" — verlet integration with distance constraints, the same verlet that later shows up in his particle updates. The flagwaver code is his. He signs the post "Graphics Noob (aka @Blurspline, zz85)."

The ladder is the method: a doodle (Hooke's law), then a spring, then a string, then a cloth. Each step is the previous one with one more degree of freedom. He does not start from the cloth; he grows into it.

**Takeaway:** Grow the system one degree of freedom at a time. A doodle that becomes a spring that becomes a string that becomes a cloth is a surer path than designing the cloth up front. Each step is testable, and each step is a piece in itself.

## The same water paints twice

Aquarelle and the koi watercolour mode are the same water twice: pigment carried by a fluid, not stamps on a canvas. In Aquarelle the fluid is the painting surface itself — the brush drops pigment into water, the water carries it, it blooms wet-into-wet, darkens at the edges as it dries, settles into the paper's tooth. The piece is a PWA, made for Apple Pencil first, and it carries its own headless test (90 checks through real pen/touch/mouse events, plus 10 pigment-optics tests). The smoke test is part of the piece, not an afterthought — the koi has one too (`node smoke.js`: every fish swims, stays in the pond at a calm speed, keeps its spine whole; touches ripple; food is eaten; holding a finger gathers the fish; tilt is followed; the watercolour frame is painted).

**Takeaway:** Test the piece the way a user will touch it. A headless check that drives real input events through the UI — pen, touch, mouse — is worth more than a screenshot. And if the paint is a fluid, the painting tool and the pond are the same code.

## A hillside that lives in real time

Sorairo (空色, "sky blue") is the koi's sibling in the vibes folder and the clearest statement of his ambient ambition: an anime / Makoto Shinkai-style hillside in three.js — a lone tree dropping leaves or petals, wind-blown grass, towering cumulus, birds and contrails, a painterly post-process. About 1,900 lines of plain ES modules on three.js 0.160, no build step, no npm dependencies.

Its lighting is one shared uniform set (sun direction and colour, ambient, fog, wind, shadow map, cloud cover), spread by reference into every material, so when the time-of-day slider changes a value once per frame, everything updates together. The anime look comes from `celLight`: a two-tone light model with a narrow, slightly soft terminator, shadows filled with blue-violet ambient instead of darkened toward black. A wind field of gusts rolls across the scene in the wind direction (`windBend` / `gustAt`). The post-process is light shafts, bloom, flare, tone map and grade, anisotropic Kuwahara, and a canvas finish.

And it has three time-lapse animations: a day cycle (round the clock), four seasons (a year on the hill), and a time zoom that starts at your real clock and date in real time, then speeds up through a few whole days and nights to month-by-month seasons. The piece knows what time it is where you are and starts there.

**Takeaway:** One uniform set, spread by reference, is how a whole world changes time of day in a single assignment. And a piece that starts at the viewer's real clock and date is not a loop — it is a place that happens to be rendered. The ambient piece earns its keep by being correct about the world outside the frame.

## The renderer is the toy

A surprising amount of Koo's work is not a picture but a way of seeing. threejs-term runs three.js in a terminal — ASCII and colour-block rendering, `m` toggling modes (plain → colour blocks → colour + ascii → ascii colours), built with node-canvas, v3.0.0 on npm: "Sysadmins can now run three.js in remote ssh sessions!" ThreeLabs is experimental features and prototypes for three.js. crayon.js is a node-based shader library (archived). three-raytracing-renderer is a pure JavaScript raytracing renderer with no canvas and no WebGL. mrdoobapproves is a fun approval bot. Even space-radar — disk and memory visualisation with Electron and d3.js, 1.4k+ stars, his most-starred repo — is a way of seeing something invisible (disk usage) as a picture. The timeline library timeliner (731 stars) is a way of seeing time.

**Takeaway:** Build the instrument, not just the image. A renderer, a timeline, a visualiser — each one is a tool that makes the next ten pieces possible. Koo's catalogue is half pictures and half instruments, and the instruments are what let the pictures keep coming.

## Aesthetic logic

Koo's work has a recognisable logic, and it is not a look. It is a set of commitments:

- **The system is the piece.** A pond, a hillside, a watercolour brush, a flock — each is a small world with its own physics, and the picture is what the world happens to look like right now. He does not animate a scene; he simulates a world and points a camera at it.
- **One simulation, many renderings.** The koi is realistic, watercolour, and ink from the same fish. The water is one fluid that paints twice. The instrument is reused until it is exhausted, and then a new one is built.
- **Analytic over stored.** Slopes computed, not heightmaps kept. Caustics from a Jacobian, not photons traced. Ink velocity from curls, not a pressure solve. A sky that is a formula. He prefers a closed form to a dataset, and the work is lighter for it.
- **The CPU is idle; the GPU is busy.** Sixteen spine points per fish. A texture for particle state. One quad render for the update. The division of labour is the architecture.
- **Physics is the aesthetic.** Beat-and-glide makes a koi. A massless cloth makes a flag. Capillary-gravity dispersion makes the water. The look emerges from the dynamics, and when the dynamics are right the picture is right.
- **Leave it open.** The koi is "a quiet koi pond to leave open for hours," a PWA that works offline. Sorairo starts at your real clock. The pieces are ambient — they are meant to be lived with, not consumed and closed. The test suite proves it: the smoke test checks that every fish swims, stays in the pond, and keeps its spine whole, because the piece has to survive being left alone.
- **Random as a method.** He is random by self-description, and the repo is called random-sketches. The method is to pick an idea, build it properly, open-source it, and move on. The catalogue is the accumulation of that habit — 205 public repos, from a Bomberman clone to an eBPF profiler in Rust to a koi pond.

## Network

- **mrdoob (Ricardo Cabello), three.js.** Koo is a core contributor to the library mrdoob created. The relationship is the work: SimplifyModifier, the Preetham sky, the GPGPU examples, and the Path Flow Modifier issue (#13553, Mar 2018) all landed in or beside three.js. Without three.js there is no Koo catalogue; without contributors like Koo there is no three.js ecosystem.
- **Evgeny Demidov, GPU fluid.** Demidov wrote the WebGL GPU fluid shaders (ibiblio.org/e-notes/webgl/gpu/fluid.htm). Koo's three.js GPGPU work — the flocking examples, the particle-texture trick — is the preparatory layer that let others build a 512K-particle fluid sim on Demidov's shaders. The credit runs both ways: Demidov supplied the fluid, Koo supplied the pattern for putting state in a texture.
- **@leon196, curve modifier.** Leon built a curve modifier for Unity3D. Koo saw it and thought there was no reason it could not be done in js/web/three.js — and built threejs-path-flow. The koi's spine bending is the descendant of that borrowing. A technique carried across engines, from Unity to the browser, is how his best mechanisms arrive.
- **Soulwire (Justin Windle), GPGPU particles.** Soulwire's GPGPU particles are cited alongside Koo's flocking as the inspirations for the PhysicsRenderer tutorial. Both belong to the same early-three.js GPGPU canon: state in textures, shaders as the update loop, the CPU idle.
- **Thomas Jakobsen and Stan Melax, the methods lineage.** Jakobsen's "Advanced Character Physics" is the basis for the massless cloth; Melax's 1998 polygon reduction is the basis for SimplifyModifier. Koo's habit is to take a published method, implement it faithfully in the browser, and then build something new on top of it.
