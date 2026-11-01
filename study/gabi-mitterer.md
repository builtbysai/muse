# Gabi Mitterer (@gabi_mitterer) — study for fly

Instagram: https://www.instagram.com/gabi_mitterer · website: gabimitterer.at
Saved posts that triggered this study: WIST_2 (post 17925438856887706) and "6 rings" (post 17907983330101434), both from the Abstract & Geometric folder.

## Who

- Gabi Mitterer, born 1967, Austrian painter and visual artist. Country code AT, works out of Vienna; shows across Austria and Germany (Vienna, Klagenfurt, Krems, Bregenz, Hamburg) and internationally (Paris art fair, Seattle, Budapest).
- About 20 years working with geometry, construction, abstraction and digital aesthetics. Interested in optical structures and optical contexts.
- Works in oil, acrylic, objects, drawings, textiles, collages. Moves between media freely: "My main focus is on painting, but whenever an idea or a thought can be better conveyed in another medium I can switch to photography, sculpture or embroidery."
- Exhibitions (selected): solo "Löcher im Licht" (Holes in Light), Bildraum Bodensee, Bregenz, Dec 2023–Feb 2024; "Impossible Objects", Davidson Gallery, Seattle, 2019; LAYERS / LAYERING group shows of geometric women artists (37 Gallery Budapest 2025, Sehsaal Vienna); Künstlerhaus Sootbörn, Hamburg, 2024; Erich Grabner Preis, paper unlimited_2, museum krems, 2026. Upcoming autumn 2026: BILDSTÖRUNG (Oct 18), APCC at Kunstverein Kärnten (Oct 22), "Der unsterbliche Apfel" at Künstlerhaus Klagenfurt (Oct 23–Nov 20).
- About 4.4k followers, 481 posts. Working series visible on IG through 2026.

## Method (in her own terms)

- She starts from sketches created on the computer, then translates her image compositions into painting, objects, drawings, textile works, collages.
- Her stated interest: "retranslating these interpolated, artificial-looking gradients and possibilities of shading into the traditional medium of painting, with the intention of arriving at new sensual results."
- Gradients of color, corporeality, and the constant interplay between flatness and depth, between 2D and 3D, are characteristic. The work balances on the narrow threshold between digital and analogue aesthetics.

## Signature curatorial reading (Creative Austria, "Löcher im Licht")

- "She is particularly interested in optical structures and contexts."
- "In meticulous colour gradients, Gabi Mitterer explores the interplay of colours." Grey is the common thread: "Grey functions as an element of identity and difference."
- "Missing pixels and image distortions become the zero points of this pictorial analysis," and the work unfolds "a game with perception" that refuses any ideology of a naturalness of seeing.

## Series and works

- 22 Stripes (2005, 110 x 130 cm, oil/acrylic): early stripe painting, achromatic band field.
- WIST_2 (2017, 140 x 140 cm, acrylic): black-and-white hard-edge line composition, "lines poetry" register.
- NOC_1 / NOC_3 (2012/2013, acrylic on wooden cube, 8 in): painted wooden cubes, shown under the "impossible objects" framing (optical illusion, concretism, op-art).
- FLUPES (FLuide/striPES): loose strips of canvas with rounded ends, held by metal clips on a brass rod, arranged into new variable image constellations. The achromatic gradient and rounded ends reinforce the fluid element. Shown as expanded painting / object.
- CUBE_6 rings / RINGCUBE (2022, 30 cm): the open shape of a cube indicated by rings assembled and held together with metal clips. Reads like a sketch made graphic in the room; 2D cube logic lifted into 3D with wire and hardware.
- 6 rings (2021, 60 x 60 x 25 cm): metal rings and metal clips wall object.
- PLUS_GW / MINUS_GW (2023/24, oil on wooden panel, 15 x 30 x 9 cm): minimal plus and minus forms on small deep panels, visual research.
- BOGRYB / BOV_WBG (2019, oil on wooden panel, 30 x 30 x 9 cm): geometric formalism, coded two-color titles.
- INTERPOLATION_WF (2024, oil on canvas): the interpolation idea made explicit.
- Gradient roll / GW (2024, oil on canvas with brass rod): gradient as rolled object.
- unspace series (2023–2026, 80 x 80 cm, oil on canvas): current large-format paintings.
- DIMORPHIA (2026, colour pencil on paper, A3): drawings, on show at museum krems.
- GEMINING (2026, 60 x 60 cm, oil on canvas): title fuses Gemstone, Gemini (twins, and a well-known AI model), and mining. Dark holes or openings in the field "reveal a glimpse of something." The missing-pixel idea as dark apertures.
- HONESPHERE (2026, 190 x 140 cm, oil): large current painting.

## What is distinctive (visual signatures, not art-speak)

1. Achromatic stripe fields. Parallel bands stepping through greys from near-black to near-white, hard edges between bands. Her gradients look "interpolated," i.e. like digital banding made by hand. This is quantizable: grey steps are discrete, countable.
2. Missing pixels / zero points. Small dark punctures or apertures that interrupt the field and become the compositional event. In GEMINING they read as holes cut through the painting revealing something behind. One aperture changes the whole field.
3. Grey as identity and difference. The same grey reads as different shades depending on context. She engineers simultaneous-contrast and Mach-band-like optical effects on purpose.
4. Open cubes from segments and rings. The cube is never solid: it is 12 edges suggested by partial segments, rings marking vertices, metal clips as joints. The cube hovers between 2D drawing and 3D object.
5. Plus/minus minimal objects. Tiny charged forms (a plus, a minus) on small deep panels; the title codes the work (PLUS_GW, MINUS_GW, BOV_WBG). Naming is part of the visual system.
6. Rounded strip constellations (FLUPES). Parallel canvas strips with rounded ends, overlapping, held by clips; the arrangement is variable. A strip field with physical joints.
7. Digital-analogue threshold. Everything reads as a screenshot of a render made physical: banding, interpolation artifacts, pixel dropouts rendered in oil. She is a computer-sketch artist working in paint, which is exactly why she translates cleanly to code.

## Evolution

- 2005–2013: stripe fields and painted cubes; concrete, hard-edged, achromatic.
- 2017: black-and-white line compositions ("lines poetry").
- 2019–2022: the work leaves the wall: FLUPES strips, ring cubes, metal-clip assemblies. Objects that read like expanded painting.
- 2023–2026: return to canvas with holes and apertures (GEMINING, unspace), plus minimal plus/minus panels and gradient rolls. The digital-analogue idea stated outright ("Interpolation," "Gradient roll").

## How the style translates to code (concrete techniques)

- Stripe fields: fill the canvas with N parallel bands (vertical or horizontal), each band a flat grey from a quantized ramp (8–22 steps, seeded order or monotonic). Hard edges, no anti-alias blur across boundaries. Her gradients translate as STEPPED bands, never smooth gradients (this also satisfies Hans's no-gradient rule).
- Missing pixels: punch apertures into the band field. Implementation: after drawing bands, draw dark shapes (rounded rects, circles, irregular blobs) in flat near-black over the bands. Apertures move between band positions, open (scale up) and close. Seeded positions; never more than ~7 at once.
- Grey identity/difference: identical grey tiles placed on different grey grounds. Use simultaneous contrast: a #808080 square on #3a3a3a reads lighter than the same #808080 on #c8c8c8. Rearrange by drifting tiles between grounds; the "work" is the perceptual event, so keep the drawing trivially simple.
- Ring cube: 12 edges of a cube projected from 3D. Draw each edge as a thin line with a gap pattern (dashes with round caps) and place a small ring (circle outline) at each vertex, plus a dot for the metal clip. Slow 3D rotation; orthographic projection is fine.
- Plus/minus: two panels side by side (like her diptychs). Each panel holds one minimal form built from 1–2 modules: a minus (one horizontal bar), a plus (two crossed bars). Morph between them by growing/shrinking the vertical bar. Seeded panel grounds in greys.
- Strip constellations: N parallel rounded-end strips (capsule shapes) in greys, overlapping, offset; one strip set slowly re-overlaps. The clip points: small dots where strips cross.

## Sources

- IG profile: https://www.instagram.com/gabi_mitterer (481 posts, AT, ~4.4k followers).
- Saved posts: https://www.instagram.com/p/CXdDDoAI8mu/ (WIST_2), https://www.instagram.com/p/CTXs0RpsO9K/ (6 rings).
- Creative Austria, "Gabi Mitterer – Löcher im Licht / Bildraum Bodensee": https://www.creativeaustria.at/en/2023/11/30/gabi-mitterer-locher-im-licht-bildraum-bodensee-vorarlberg/
- Davidson Gallery, "Impossible Objects" (Seattle, 2019): http://www.davidsongallery.com/exhibitions/impossible-objects
- LAYERS group show notes (FLUPES description), museu.ms: https://museu.ms/exhibition/details/8955/layering-group-exhibition
- Artist statement on the digital-analogue threshold (via foryouandyourcustomers.com exhibition 87 notes)
- 37 Gallery, LAYERING Budapest/Vienna 2025: https://www.37gallery.com/hu/event-details-registration/layering-1
