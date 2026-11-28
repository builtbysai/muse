# Ivan Sutherland: Study Notes

**Site:** Ivan Edward Sutherland -- born Monday 16 May 1938, Hastings, Nebraska; living. Ph.D. electrical engineering, MIT, 1963, advisor Claude Shannon, committee Marvin Minsky and Steven Coons; thesis "Sketchpad: A Man-Machine Graphical Communication System," submitted 7 January 1963, MIT Lincoln Laboratory Technical Report No. 296, dated 30 January 1963. Turing Award 1988, Kyoto Prize 2012. The study rests on the thesis read end to end, not on the reputation. [C39158]

**Doorway:** The 469th doorway. Takes up the open question from the Michel Beaudouin-Lafon study (#848), quoted verbatim: "when the instrument between hand and object thins to nothing -- when the hand touches the drawing itself, as in Sutherland's Sketchpad -- what is lost when there is no tool left to learn, and who carries the meaning then, the gesture or the object?" Sutherland answers it, and his answer is stranger than the question expects: the hand never touches the drawing at all. What it touches is a bright dot the machine calls the point of the pencil, and the dot always lands on meaning, never on raw coordinates. What is lost is the accident of position; what is gained is a drawing that is a system of promises, kept by a solver, not by the hand. [C39159]

**Depth:** Read end to end: the Sketchpad Ph.D. thesis (149 pp., Cambridge TR-574 reissue, all 4,785 lines of extracted text, Ch. I-IX and App. A-G); the AFIPS 1963 Sketchpad paper (19 pp., pp. 329-346); "The Ultimate Display" (IFIP 1965, 2 pp.); "A Head-Mounted Three Dimensional Display" (AFIPS FJCC 1968, as CHM final-report Part II); Sketchpad III by Timothy E. Johnson (AFIPS 1963, pp. 347-353); "Computer Graphics: Ten Unsolved Problems" (Datamation, May 1966); "Reentrant Polygon Clipping" (CACM, January 1974, except the final half-page of Appendix A, partially rendered); Sutherland's October 2024 CV (12 pp.). Read in substance: "A Clipping Divider" (1968); "A Characterization of Ten Hidden-Surface Algorithms" (1974, abstract, introduction, taxonomy, conclusions, Appendix A); "Micropipelines" (Turing lecture, CACM 1989, introduction, control/storage, conclusion); Oral History Part 2 (CHM, 2017, pp. 1-16 of 94). NOT watched: the Sketchpad film(s) -- no frames viewed, no archive.org copy found. No figure anywhere was viewed as a rendered image -- all figures read as OCR text and captions only. Not read: "Technology and Courage," "The Tyranny of the Clock," "Computer Displays" (Scientific American, June 1970), the asynchronous-systems papers after 1989, the Sketchpad program listings, and the middle sections of the works listed as read in substance. [C39160]

**Relevance:** (1) Sutherland's Sketchpad (1963) asks what a drawing is when the hand touches it directly -- a line is not ink but a constraint the machine must satisfy, so the question is who carries the meaning when there is no mediating instrument left: the gesture or the constrained object. (2) Evidence: the thesis documents concrete, executable mechanisms -- light-pen drawing, rubber-band lines, constraint satisfaction, master/instance copies, a solver that keeps the drawing true -- all directly transferable to generative pieces about drawing as a system of promises. [C39161]

## M1 -- Relaxation: error as a visible, draining quantity

**Subject:** A drawing whose parts are bound by promises, and a solver that keeps them.

**Visual principle:** Tension made visible. Each violated constraint is a small wrongness -- a gap, a tilt, a stretch -- and the drawing visibly shudders, creeps, and settles as error drains. The eye reads the *settling* as the event, not the final shape.

**Computational mechanism:** Every constraint is an error subroutine returning a scalar to drive to zero; the partial derivative of the error with respect to any component must be under 2, and errors are balanced so the derivative is about 1 (error is approximately displacement). Relaxation, verbatim from the thesis: "Choose a variable. Re-evaluate it to reduce the total error introduced by all constraints in the system. Choose another variable and repeat." Each step makes "some net reduction of total error," so "monotonic decrease of error and thus stability is assured." The SOLVE macro (from Lawrence G. Roberts) linearizes the constraints on a variable and finds the point of minimum mean squared error -- minimum change from the existing value where the solution is not unique. Constraint lookup is cheap because all constraints applying to a variable are collected together in a ring whose "hen" is in the variable. Parameters: constraint set, relaxation step size/damping, iteration budget per frame, error threshold for "settled."

**Artistic opportunity:** The solver *is* the motion. A drawing that repairs itself in front of you is a different object from a drawing that merely appears -- it has a temperament (fast, sluggish, trembling) set by damping and constraint density. Over-constrain it and it never settles: a drawing with anxiety.

**Takeaway:** Error is not a defect in Sketchpad; it is the medium. The drawing is a quantity draining toward zero, and watching it drain is the piece. [C39162]

## M2 -- Two speeds of truth: one-pass propagation vs relaxation fallback

**Subject:** The same drawing solved two ways.

**Visual principle:** Contrast of tempi. A chain of directly connected parts snaps true instantly (one-pass); a loop of interdependent parts grinds slowly toward truth (relaxation). The viewer can *see* which kind of truth a shape is.

**Computational mechanism:** One-pass: a "free" variable, a FREEDOMS ring, a Moore's-algorithm analogy -- re-evaluate in reverse order with the first-found free variable last; the ordering is computed only when conditions change. When the one-pass method fails, Sketchpad "falls back on the reliable but slow method of relaxation"; for "directly connected instances, relaxation is unacceptably slow" -- and it is exactly there that one-pass "shows the most striking success." It works for linkages and common constructions, NOT for bridge trusses. The piece can classify its own constraint graph each frame (acyclic vs cyclic) and switch solvers, exposing the switch as a visible change of pace.

**Artistic opportunity:** A piece about two kinds of knowing -- the instant deduction and the slow negotiation -- staged as two different motions in one drawing.

**Takeaway:** Truth has a tempo, and the tempo tells you the shape of the dependency. A chain snaps; a loop argues. [C39163]

## M3 -- Rubber band: the line as a stretched promise

**Subject:** A line that does not yet exist.

**Visual principle:** The unfinished line is the most alive thing on screen: it stretches, trembles, and snaps to its anchor. The drawing is a field of maybe-lines.

**Computational mechanism:** While the pen is down, a straight segment "stretches like a rubber band from the initial to the present location of the pen." Returning near the first line's end, the pen will "lock on" to it exactly. While the pointer is down/dragging, render a provisional segment from the anchor point to the current pseudo-pen location, re-evaluated every frame; on release (or on a flick, M4), commit the segment as a stored object with endpoints. Provisional geometry is never stored -- it is pure function of pointer position. Parameters: anchor point, snap radius, whether the provisional line shows constraint previews (a ghost of horizontal/vertical).

**Artistic opportunity:** Drawing becomes a performance of intention rather than a record of movement. Every line is born as a negotiation between the hand's wobble and the machine's straightness.

**Takeaway:** In Sketchpad a line is provisional until it is committed, and the provisional state is where all the life is. [C39164]

## M4 -- Loss of tracking as the ending: the flick that means "done"

**Subject:** An ending that is a failure, used on purpose.

**Visual principle:** The gesture ends not with a button but with disappearance -- the hand moves too fast, the cross falls behind, tracking is lost, and that loss *is* the full stop. Endings have a speed.

**Computational mechanism:** The tracking cross is redisplayed about 100 times per second, 1 ms per display; maximum pen speed 20 in/sec, so successive crosses sit about 0.2 in apart. "I use the loss of tracking as the so-called termination signal for all pen tracking operations." Predictive tracking was tried -- constant-velocity and constant-acceleration -- then abandoned. In a piece: a velocity threshold on pointer movement; crossing it commits the current stroke and starts the next state. Parameters: tracking rate (simulated), max trackable speed, the state entered on loss (commit, discard, or transform).

**Artistic opportunity:** A drawing tool whose only "enter key" is moving too fast to be followed. It makes speed a semantic act -- a flick is a period, a slow drag is a sentence. No button, no click-to-confirm.

**Takeaway:** Sutherland turned a hardware limitation into the grammar of ending. The fastest gesture is the period. [C39165]

## M5 -- Master and instance: one drawing, many bodies

**Subject:** A motif that exists once and appears many times.

**Visual principle:** Multiplicity with a single soul. Edit the one and the many shiver in unison; the eye tracks the family resemblance across scale, rotation, and position.

**Computational mechanism:** "Except for size, rotation, and location, all instances of one master look the same." An instance is a 4-component variable (size x cos, size x sin, x, y); change the master and every instance changes at once -- the thesis prefers the equation with master size sm for exactly this reason. Instances can contain other instances. The opening demonstration: a hexagon inscribed in a circle, its six lines made equal by five statements, and the hexagonal pattern built from it in under five minutes. Change the master hexagon to a semicircle and the whole pattern becomes fish-scale. One face, three interchangeable eye types, and the girl winks (Nefertite, traced from a photograph via a facsimile outline plus wax pencil on the display face; enlarging the mouth changes her character). Parameters: master geometry, instance transforms, nesting depth, per-instance overrides (none in Sketchpad -- that absence is itself a rule worth keeping or deliberately breaking).

**Artistic opportunity:** The piece is a population, not a picture. The viewer edits one thing and watches a crowd change -- the most economical possible interaction with the largest possible visible consequence. The tension: every instance is identical in structure yet different in placement, so the piece is about sameness under transformation.

**Takeaway:** The instance is a role, not a copy. Swap the eyes and the meaning changes while the structure holds. [C39166]

## M6 -- The ring: the drawing as topology, not ink

**Subject:** What a drawing is when it is stored as relationships.

**Visual principle:** Lines are not marks; they are edges between points, and points are shared. Move one corner and two lines follow because they are the *same point*. The drawing holds together the way a net holds together.

**Computational mechanism:** n-component elements; hen/chicken register pairs; four basic operations (insert a member, remove a member, transfer ring members, apply an operation to each member); the UNIVERSE block sits at relative address 1. A new type costs a generic block plus subroutines; new constraint types were built "literally at fifteen minute intervals." Merging two points merges their lines, so closed polygons form; merging two lines forces pairwise endpoint merges and carries constraints over -- parallelism lives on endpoints, not on lines. A merging result takes the historically older variable's value ("older" = lower address). Recursive functions: instance expansion, recursive deletion, recursive merging, recursive moving; push-down lists formed inside the data structure. Mirror images are NOT supported -- a stated omission. Parameters: graph structure; which rings are exposed to the viewer (highlight the ring of everything attached to the point under the pointer).

**Artistic opportunity:** Show the rings. Let the viewer see the drawing's skeleton -- the shared points glowing where lines meet, the constraint rings drawn as faint halos -- so the picture and its structure are the same image. A drawing that shows its own joints.

**Takeaway:** Sketchpad's drawing is not a pile of marks; it is a topology with no searching. Connectedness is the data structure. [C39167]

## M7 -- The window into the page: a quarter mile of paper

**Subject:** A drawing far larger than the screen.

**Visual principle:** Scale as a place. The screen is a small window sliding over a vast sheet; detail lives far away from the whole, and the journey between them is the experience.

**Computational mechanism:** The drawing lives in fixed page coordinates (36-bit signed fractions; 29-30 bits of precision); a "page to scope transformation" views "any portion of the page desired, at any degree of magnification, as if through a magnifying glass." The magnification range is 2000 -- one can work "on a 7-inch square portion of a drawing about 1/4 mile on a side." The largest displayed part is 1/256 of the page. Knob changes are proportional to SCSZ (the half-length of the scope square), i.e. exponential; there is a center-on-pen function. An instance is not expanded if its center is more than 1.5x its box size from the scope edge. Parameters: window center, magnification, zoom speed/easing, what is drawn at each scale (detail appears only when close -- a real level-of-detail rule, not decoration).

**Artistic opportunity:** A piece that cannot be seen whole and cannot be seen in detail at the same time. The viewer must choose a scale, and the piece rewards the choice: fine structure hidden at 1x, the grand pattern invisible at 2000x. The doorway question returns here in another key -- the hand touches only a patch, never the drawing.

**Takeaway:** The screen is a hole, not a page. Sketchpad's drawing is a quarter mile wide, and the window is the only part of it you ever touch. [C39168]

## M8 -- The display file and the flicker budget: drawing as re-performance

**Subject:** A picture that exists only because it is redrawn, many times a second.

**Visual principle:** The image has a pulse. Too much picture and it flickers, dims, stutters; the right amount and it stands steady. Complexity is visible as instability.

**Computational mechanism:** The TX-2 scope: 10 bits per axis, about 100,000 spots/sec maximum; display file 32,000 words; 20 microseconds per spot; a 36-bit word carries 20 bits of coordinates plus 16 bits of tag (the ring address of the element responsible for the spot). The picture is a list of spots the beam replotted many times a second; "scrambling the order of the display spot locations in the display file" produced a result "pleasing to the eye and avoids flicker entirely." Moving parts are stored at the end of the display file, invisible to the pen. About three-quarters of all Sketchpad computation sits in 15 instructions: the line difference equation (5 instructions) and the circle equation (10). Parameters: spot budget, refresh rate, scramble on/off, what happens over budget (dim, drop, flicker).

**Artistic opportunity:** A piece that must *earn* its complexity. The drawing grows until it flickers, then must shed lines or scramble itself to survive -- a drawing with a metabolism. The flicker is not a bug to hide; it is the piece's heartbeat, made visible.

**Takeaway:** The image is a performance repeated many times a second, and the budget for that performance is a physical fact. A drawing can be too much to keep alive. [C39169]

## M9 -- The stored promise: a relationship that outlives the gesture

**Subject:** The difference between a line that happens to be parallel and a line that *must* be parallel.

**Visual principle:** Two drawings that look identical but behave differently: tug one and the first falls apart while the second holds its shape. The invisible difference is the whole piece.

**Computational mechanism:** In December 1961 Claude Shannon visited, asked for paper to sketch on first, and Sutherland concluded that parallel/perpendicular lines drawn by imitation "carried no permanent trace of the relationship other than the accident of their position" -- the moment that made constraints, not imitation, the point. Constraints are stored objects attached to geometry, not accidents of position. The 17 atomic constraints (App. A): T instance-point; L collinear; C equal distance from first = circle center; E erect; H horizontal/vertical with a 45-degree cutoff via the Horv button; I parallel-to-horizontal = upright; M distance ratios 1/3, 1/2, 1, 2, 3; S size ratios; D scalar = distance in inches; B scalar = size in inches; F full size; X midpoint; 6 size 1/32 to 1 inch; P parallel or perpendicular; O space for a 5-digit number; W maintain distance as of toggle-22 meta; Y scalar = change in distance since toggle-22 meta (bridge forces). The constraint set grew from 5 to 17 in about two days of use, behind roughly 100 hours of drawing experience. Point-on-line and point-on-circle constraints are auto-created when a point is created or moved onto a line or circle. A constraint is displayed as a fixed-size circle plus a code letter at the average location of its constrained variables. Parameters: constraint set per object, disturbance force, solver on/off per population.

**Artistic opportunity:** The purest staging of the doorway question: the gesture (how the line was drawn) vs the object (what the line promises). The viewer learns the difference by touching -- the unconstrained drawing betrays its maker the moment it is moved.

**Takeaway:** A promise is a stored thing. The difference between accident and intention is not visible until something is pulled. [C39170]

## M10 -- Linkages and trusses: constraints as physics

**Subject:** A machine drawn, then set running; a bridge drawn, then loaded.

**Visual principle:** A drawing that moves like a machine and carries weight like a structure. The linkage's joints trace curves no hand could draw; the truss's members thicken or redden under load.

**Computational mechanism:** A linkage is a closed loop of constrained bars (equal lengths, pinned joints = shared points); animating one joint and re-solving the loop each frame (relaxation, M1) traces the coupler curve. The thesis's demonstrations: a Peaucellier straight-line linkage; a three-bar linkage, a perpendicular-shaped instance with 6 attachers, built in 5 minutes and played with for over an hour, shown in the AFIPS paper in a 15-second time exposure; a conic linkage first built in 15 minutes, rebuilt to about 3 minutes from scratch once the definition was understood. A bridge: a bay is drawn, its constraints deleted, and its members become beams of constant length; change is shown by a number, and cross-section is made proportional to length so the numbers ARE the forces (the Y constraint, code 50). A 6-bay bridge takes under 10 minutes to draw; new force values appear in about 30 seconds. Note the honest limit in the thesis itself: the one-pass solver does not handle bridge trusses, so this is relaxation territory. Parameters: linkage geometry, driver joint motion, load position/magnitude, force visualization mapping.

**Artistic opportunity:** Drawing as engineering without the engineering -- the pleasure of a mechanism that works, drawn by hand and then alive. The truss under load is also a quiet metaphor the piece doesn't need to state: promises under stress.

**Takeaway:** A linkage is a definition, not a drawing -- and once the definition is right, the machine runs itself. [C39171]

## M11 -- The perspective that follows the head: the cube in the room

**Subject:** A wireframe object that stays put while you move.

**Visual principle:** Parallax as presence. The cube does not move; *you* move, and the view recomputes. The object feels more real than the screen because it refuses to follow you.

**Computational mechanism:** "The fundamental idea behind the three-dimensional display is to present the user with a perspective image which changes as he moves." Up to 3,000 lines, 30 times per second, stereo. The headset: 2 miniature CRTs, a virtual image about 18 in in front of each eye, 40-degree field of view, half-silvered mirrors (see-through -- the display can coincide with maps, desks, typewriter keys), a 1/2-in square picture, a 0.6-mil spot. Head pose from a ceiling linkage with six rotary encoders (the mechanical-arm sensor; an ultrasonic alternative at 37, 38.6, 40.2 kHz was also built). The six subsystems: "a clipping divider, matrix multiplier, vector generator, headset, head-position sensor, and a general-purpose computer." The clipping divider's rule: clipping must precede division (negative or zero Z); 250 ns clock, worst case 42 cycles = 10.5 microseconds per line. The head moves 3 ft off axis, turns fully around, tilts 30-40 degrees. The objects shown are transparent wire frames; the kinetic depth effect is more important than stereo. The system ran on a PDP-1 at Harvard only briefly in August 1968, to be reassembled at Utah in fall 1968. Parameters: object geometry, viewpoint mapping gain, field of view (40 degrees in the original), clip behaviour at the FOV edge.

**Artistic opportunity:** The only piece in the set where the viewer moves instead of the drawing. It stages the doorway question from the other side: when the hand touches nothing and only the head moves, who carries the meaning -- the gaze or the object? The cube's indifference is the point.

**Takeaway:** Presence comes from the object's indifference. The cube stays; you move; the view is recomputed. [C39172]

## The pseudo-pen location: the hand never touches raw coordinates

The doorway's question answers itself inside the thesis, in chapter 4. The pseudo pen location -- a bright dot displayed at the point the machine believes the pen to be -- is "the point of the pencil." It snaps and locks onto nearby picture parts, so a corner can be placed exactly on a line or circle without a steady hand. The pen field of view is 1/2-in in diameter; the aiming rejection distance is about 1/8 in. "Inking-up": touch a line or a spot and the pen draws in that style. Even in the first direct-manipulation system, the touch is mediated: the hand never touches raw coordinates, it touches the machine's belief about where the pen is, and that belief is always already on meaning. What is lost when there is no tool left to learn is the raw coordinate -- and what is gained is a pencil point that always lands on meaning. The instrument did not disappear; it shrank to a dot. [C39173]

## The retraction: a mechanism can be beautiful, simple, and wrong

In the 2017 Computer History Museum oral history, Sutherland disowned the central argument of his own Turing lecture. "I talked a lot about transition signaling and in retrospect I wish I hadn't done that, because it set the asynchronous community off on a bad track. What I believe now is a bad track. I would advise anybody who got into this to avoid building a micropipeline. It's got too much symmetry. It's got front-to-back symmetry, it's got Vdd to ground symmetry." The Micropipelines paper (CACM 1989) had argued that transition signalling -- any transition, rising or falling, meaning an event -- might offer twice the speed potential of conventional clocking, and that composability "may be their most important property." The retraction does not make the paper worthless; it makes it instructive. A mechanism can be beautiful, simple, and wrong, and its author can be the one to say so. The study's pieces should carry that same willingness to be corrected by their own later reading. [C39174]

## The flop: circuits, or where the promise runs out

The thesis is honest about its one failure, and the failure names the boundary of the system. An attempt to draw circuits in Sketchpad: about 40 transistors, 10 hours of work by a new user, still incomplete -- "a big flop." Circuits need connection semantics Sketchpad does not have -- wires that mean something, not just lines that happen to touch. Constraints keep geometry true, but they do not know what a circuit is. For a study about drawing as a system of promises, the flop is as instructive as the successes: it shows where the promise runs out. The same honesty appears in the scale argument that did work: about 900 hexagons on a 30x30-in plotter page, about 30 minutes to generate and 25 to plot, where the drafting department estimated 2 days; a delay line of 500 zigs in a row, 4 rows 1/2-in apart, 45 minutes plus 15 to plot; a 6-degree wedge made by trisecting a right angle (30 degrees) and cutting it into 5; wedges as small as 1/128 of a circle in 5 minutes; 60 radial lines; crosses placed in 20 minutes. A definition plus a solver beats a drafting department by two orders of magnitude -- where the definition knows what it is defining. [C39175]

## The arc

Hand draws (1960-62: Raffel's suggestion in summer 1960, TX-0 in winter 1960-61, first light-pen drawing program November 1961, Shannon's visit December 1961, ring structure in use by 1 February 1962, a motion picture by Memorial Day 1962, about 600 hours of TX-2 time in total) -- machine keeps promises (1963: the thesis, the solver, the 17 constraints) -- drawing becomes a place (1965: the Ultimate Display's room "within which the computer can control the existence of matter. A chair displayed in such a room would be good enough to sit in. Handcuffs displayed in such a room would be confining, and a bullet displayed in such a room would be fatal... the Wonderland into which Alice walked") -- and then the long second career, in which the man who made drawing into computation spent the rest of his life removing the clock from computation (Micropipelines 1989, Logical Effort 1991/1999, Counterflow Pipeline 1994, "Computers Without Clocks" 2002, the Asynchronous Research Center from 2008). The arc is a thinning: from the hand, to the dot, to the room, to the event with no clock at all. The doorway into #850 is what the thinning leaves behind: when the hand, the instrument, and even the clock are gone, what does the gesture still mean -- and who is it for?

## Aesthetic logic

Sketchpad's beauty is not in its pictures -- the thesis's own figures are hexagons, linkages, bridges, a winking girl -- but in the economy of its promises. One rule (a constraint is an error to drive to zero) generates the hexagon, the linkage, the bridge, and the face. The aesthetic is the aesthetic of the least that is enough: a bright dot, a rubber band, a ring of constraints, a solver that drains error monotonically. Nothing decorative is present; everything visible is a mechanism, and every mechanism is visible. That is why the work transfers to the gallery so directly: the thesis is already a catalog of systems that can be watched, disturbed, and repaired, and its failures (the circuits, the mirror images it cannot do, the bridge trusses the one-pass solver cannot handle) are as load-bearing as its successes, because they say where the system ends. A piece built from Sketchpad should look like a promise being kept -- spare, ink-dark, with the error visible as warmth and the settling visible as motion -- and it should be willing, like its author, to be wrong in public. [C39176]

## Rejections

Twelve candidates were considered and rejected in the mechanisms leg (leg 3, claims C39267-C39286): (1) a literal Sketchpad clone -- a history demo, not a piece; (2) a light-pen demo -- a drawing app with no constraints is just input; (3) a CAD tool / parametric sketcher -- a utility, not an artwork; (4) a hexagon demo replica -- restaging the thesis's example beat-for-beat with no new question (SUT1 keeps the figure but changes the question to the hand's withdrawal); (5) a Sword of Damocles VR clone -- unbuildable in this medium, literal illustration; SUT6 takes the mechanism (head-tracked perspective) instead of the apparatus; (6) a literal Ultimate Display room -- illustration of a quote, not a mechanism; M12 has no executable rules; (7) a truss engineering visualization -- a diagram, not a visual system; (8) a constraint-type menu toy -- a feature demo; the constraint must be pinned by touch inside a drawing (SUT1) or felt as error (SUT2) to earn the piece; (9) a zoom demo -- a viewer, not a piece; SUT5 keeps the window only because the drawing is 2000x larger than the screen with a real level-of-detail rule; (10) a biography / timeline piece -- a life is not a computational mechanism; (11) an asynchronous-circuit piece -- only a one-line profile mention was read; no grounded mechanism; (12) a hidden-surface algorithm visualization -- the 1974 survey was not read; a z-buffer/painter's-algorithm viz would be invented mechanism, not extracted.

## Top pick for #850

**Doug Engelbart (ENG, b. Friday 30 January 1925, Portland, Oregon; d. Tuesday 2 July 2013, Atherton, California, age 88) is the right next study.** He is the next name on the ranked HCI list after Sutherland, and the doorway carries forward directly: Sutherland thins the instrument to a dot and then to a room in which the computer controls the existence of matter -- so the next study should take up what happens when the gesture is given a whole system to live in instead, Engelbart's augmentation of human intellect, the mouse, the chorded keyset, and the Mother of All Demos, and whether the meaning then lives in the hand, the tool, or the collective that the tool makes possible. Engelbart is chosen by list order and by the doorway question, not by social adjacency. The doorway into #850, quoted verbatim: "when the hand, the instrument, and even the clock are gone, what does the gesture still mean -- and who is it for?" Verified this run: no local study file exists for him, the muse slug study/doug-engelbart.md returns an explicit HTTP 404, and the prefix ENG is free. Second pick Alan Kay (KAY, b. Friday 17 May 1940, Springfield, Massachusetts; living -- SOFT CONFLICT: Mattie Kay already carries KAY in the #806 carry-forward list; if Alan Kay takes KAY, Mattie Kay takes MKY), then Myron Krueger (KRG, b. 1942, Gary, Indiana; living; day/month 2 March 1942 astrology-only, not adopted), Jeff Hawkins (HAW, b. Saturday 1 June 1957, Huntington, New York; living), Toshio Kashio (KSH, b. Thursday 1 January 1925, Tokyo; d. Tuesday 15 May 2012, age 87), Kikuo Ibe (IBE, b. 1952, day/month not established; living), Casio DB-1000 (DBK, August 1984 -- CONFLICT: Casio sales records say 1 January 1985, a Tuesday), Casio TC-500 (TC5, 1983), Casio C-80 (CAL, February 1980 on Casio's own history page; two secondary blogs say August 1980, apparently conflating it with the August 1980 MG-880), Tissot Touch (TIS, 1999; the "world's first touchscreen watch" claim is a marketing claim, not independently verified against the Casio TC-500 of 1983). COUNT: the ranked HCI list has 9 entries remaining after Engelbart (10 after Sutherland, minus Engelbart). Note: older study-log lists place Ken Hinckley (HIN) between Tapia and MacKenzie; he has a local study file and is absent from the #839/#840 lists, consistent with already-studied removal; the 9-count is unaffected. Chevalier-network additions (unranked, carried as written): Nathalie Henry Riche (natural RIC TAKEN by #707 Gerhard Richter), Benjamin Bach (natural BAC TAKEN by #768 Luis Enriquez Bacalov), Haijun Xia (XIA proposed, not assigned), Hugo Romat (natural ROM TAKEN by #651 Juan Carlos Romero), Jean-Daniel Fekete (FEK proposed, not assigned), Pierre Dragicevic (DRA proposed, not assigned), Anastasia Bezerianos (BEZ proposed, not assigned), Nicole Sultanum (SUL proposed, not assigned), Adrien Bousseau (natural BOU TAKEN by #799 Adrian Boult), Zezhong Wang (WAN proposed, not assigned), Nobuyuki Umetani (UME proposed, not assigned). Pointers only: Eugene Fiume, Jeff Kowalski, Carl Bass, Kellogg Booth, John Senders, Karthik Mahadevan, Anthony Tang, Eitan Grinspun, Patrick Baudisch, Xiang "Anthony" Chen. Closed routes, do not re-propose: Sol LeWitt (remote study exists), Vera Molnar (remote study exists), Kiyoshi Nakauchi, Gabi Mitterer, Mathias Krissmer (local studies exist), Max Drekker (UNCLEAR provenance -- do not pick until resolved). The #808 folk-singer ranked list stands separately and is not repeated here. #809 Sam Larner remains designated and unwritten. Next: #850. [C39177]

CHAIN-BREAK NOTE -- CLOSED, DO NOT REPEAT. Sol LeWitt (remote study exists), Vera Molnar (remote study exists), Kiyoshi Nakauchi, Gabi Mitterer, Mathias Krissmer (local studies exist), Max Drekker (UNCLEAR provenance -- do not pick until resolved). [C39186]
