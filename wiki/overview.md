---
title: Overview
tags: [overview, synthesis]
sources: [eppstein-2010-growth-and-decay-in-life-like-ca, eppstein-gliders-in-life-like-cellular-automata, eppstein-2002-searching-for-spaceships, bays-1987-candidates-for-the-game-of-life-in-three-dimensions, bays-1994-cellular-automata-in-the-triangular-tessellation, bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations, lifewiki-brians-brain, lifewiki-star-trek, lifewiki-wireworld, lifewiki-seeds, lifewiki-rulestring, lifewiki-life-like-cellular-automaton, lifewiki-von-neumann-neighbourhood, lifewiki-hexagonal-neighbourhood, lifewiki-larger-than-life, lifewiki-higher-range-outer-totalistic-rule, lifewiki-higher-range-isotropic-non-totalistic-rule, lifewiki-ruleloader, lifewiki-unit-cell, lifewiki-apgsearch, lifewiki-catagolue, cgol-ch7-stable-circuitry, cgol-ch8-guns-and-glider-streams, cgol-ch9-universal-computation, cgol-ch10-self-supporting-spaceships, cgol-ch11-universal-construction, lifewiki-generations, lifewiki-star-wars, lifewiki-list-of-generations-rules, golly-help-generations, cgol-ch12-0e0p-metacell, cgol-ch6-periodic-circuitry, cgol-ch5-glider-synthesis, cgol-ch4-spaceships-and-moving-objects, cgol-ch3-oscillators, cgol-ch2-still-lifes, conways-game-of-life-mathematics-and-construction, cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, theory-of-self-reproducing-automata, tsra-editors-introduction, tsra-lecture-2, tsra-lecture-3, tsra-lecture-4, tsra-lecture-5, tsra-part2-ch1, tsra-part2-ch2, tsra-part2-ch3, tsra-part2-ch4, tsra-part2-ch5, endomorphisms-and-automorphisms-of-the-shift-dynamical-system, machine-models-of-self-reproduction, converse-of-moores-garden-of-eden-theorem, statistical-mechanics-of-cellular-automata, planetmath-garden-of-eden-theorem, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey, automata-universality-computation, aucm-ch12-linear-cellular-automata-and-decidability]
updated: 2026-09-25
---

# Cellular Automata — Overview

> Evolving synthesis of everything in the wiki. Updated by wiki-ingest when sources shift the understanding.

## Current Understanding

Cellular automata begin with von Neumann's [[theory-of-automata](pages/theory-of-automata.md)], a logical and
mathematical theory of how automata, natural and artificial, are organized. Its organizing
concept is complexity, and its two central problems are
[[self-reproduction](pages/self-reproduction.md)] and reliability.

**Life.** The wiki's center is Conway's [[game-of-life](pages/game-of-life.md)], B3/S23 in the rulestring
notation of the [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] family: two states, eight neighbours,
birth on three, survival on two or three. Its objects fall into three basic classes: the
[[still-life](pages/still-life.md)] ([[block](pages/block.md)], [[beehive](pages/beehive.md)]), the [[oscillator](pages/oscillator.md)]
([[blinker](pages/blinker.md)], [[pulsar](pages/pulsar.md)], [[pentadecathlon](pages/pentadecathlon.md)]), and the [[spaceship](pages/spaceship.md)]
(the [[glider](pages/glider.md)] at c/4 and the [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)] at c/2,
against a "speed of light" of one cell per generation). Random soups, catalogued at scale
by [[soup-search](pages/soup-search.md)], show which objects arise naturally and in what formations
([[familiar-fours](pages/familiar-fours.md)]). Unstable objects such as the [[queen-bee](pages/queen-bee.md)],
[[twin-bees](pages/twin-bees.md)] and [[switch-engine](pages/switch-engine.md)] can be stabilized into shuttles, guns
([[gosper-glider-gun](pages/gosper-glider-gun.md)]; [[gun](pages/gun.md)]s of every period from 14, including slow ones like the [[caber-tosser](pages/caber-tosser.md)]) and puffers, so finite patterns can grow forever; most modern
Life patterns are engineered this way. Still lifes are well understood: counted to 34 cells, built by a known grammar, used as [[eater](pages/eater.md)]s to delete gliders, and packed at most at density 1/2 ([[still-life-density](pages/still-life-density.md)]). Oscillators exist of every period ([[omniperiodicity](pages/omniperiodicity.md)]), built from sparks ([[sparker](pages/sparker.md)]), hasslers ([[hassler](pages/hassler.md)]), glider loops around reflectors ([[reflector](pages/reflector.md)]) and [[herschel](pages/herschel.md)] tracks; no phoenix, an oscillator whose live cells all die every generation, has period 3 or 5 ([[phoenix](pages/phoenix.md)]). Moving objects are capped at c/4 diagonally and c/2 orthogonally but have no lower speed limit; switch engines combine into c/12 [[cordership](pages/cordership.md)]s, a [[self-supporting-spaceship](pages/self-supporting-spaceship.md)] builds the track for its moving reaction ahead of itself (a [[caterloopillar](pages/caterloopillar.md)] for every rational speed below c/4), [[self-constructing-spaceship](pages/self-constructing-spaceship.md)]s rebuild themselves by [[single-channel-construction](pages/single-channel-construction.md)], xWSS-based [[puffer](pages/puffer.md)]s become rakes (moving guns), and [[signal-wire](pages/signal-wire.md)]s carry information up to c through non-empty patterns. Colliding gliders builds almost anything ([[object-synthesis](pages/object-synthesis.md)]): every still life up to 23 cells, anything constructible from just 15 gliders, and anything at all from a one-direction [[slow-salvo](pages/slow-salvo.md)]; rakes that build guns make a quadratically growing [[breeder](pages/breeder.md)]. Oscillator-based circuitry at periods 30 and 46 routes and processes glider streams: [[inverter](pages/inverter.md)]s and duplicators, [[memory-cell](pages/memory-cell.md)]s, [[heisenburp](pages/heisenburp.md)]s that copy a glider without touching it, [[regulator](pages/regulator.md)]s that re-time gliders, and a [[primer](pages/primer.md)] that outputs the primes. Stable Herschel [[conduit](pages/conduit.md)]s and [[period-multiplier](pages/period-multiplier.md)]s do the same without oscillators, and Life hosts explicit programmable computers ([[apgsembly](pages/apgsembly.md)], [[sliding-block-register](pages/sliding-block-register.md)]). Small patterns can also take very long to settle
([[methuselah](pages/methuselah.md)], [[r-pentomino](pages/r-pentomino.md)]), and almost all large patterns are Gardens of
Eden. The theory sections below are background to this.

**Beyond B3/S23.** Life is one of 2^18 [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] rules, which
sit inside 2^102 [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s (Hensel notation), which sit inside
2^512 [[non-isotropic-rule](pages/non-isotropic-rule.md)]s (MAP rulestrings) on the same eight-cell neighbourhood.
Other rules have patterns Life lacks: [[highlife](pages/highlife.md)]'s 12-cell [[replicator](pages/replicator.md)],
looping oscillators and spaceships made of spaceships in isotropic rules, and single-cell
spaceships in non-isotropic ones. [[generations-rule](pages/generations-rule.md)]s add dying ("refractory") states: a live cell that fails to survive ages through states that neither count as live nor allow birth, which makes small lightspeed spaceships abundant. [[brians-brain](pages/brians-brain.md)] (B2/S/C3) is almost all motion; [[star-wars-rule](pages/star-wars-rule.md)] (B2/S345/C4) adds survival, and gains still lifes, oscillators of every period from 4, guns and a photon logic technology able to emulate Rule 110. Life can host all of them. A [[metacell](pages/metacell.md)] is a Life
pattern that acts as one cell of another rule; the 0E0P metacell runs any two-state Moore
rule where empty stays empty, by emulating an 8-state von Neumann rule and building its
own neighbours. Rule 110 unit cells are the standard way to prove a rule universal, which is how
[[seeds-rule](pages/seeds-rule.md)] (B2/S), where every pattern is a phoenix, and Brian's Brain were both shown
Turing-complete. [[wireworld](pages/wireworld.md)] confines all activity to fixed wires and runs a whole computer that prints
the primes; [[star-trek-rule](pages/star-trek-rule.md)] (B3/S0248) shares only a name with Star Wars.

**Writing and widening rules.** A [[rulestring](pages/rulestring.md)] names a rule (B3/S23, /C for Generations, V and H
suffixes for the [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)] and [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)]). A Life-like rule's lowest birth count
largely fixes its character: B1 fills the plane at lightspeed, B2 explodes, under B4 and up no pattern leaves its bounding box,
so chaos lives at B3 or B0. [[larger-than-life](pages/larger-than-life.md)] and [[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)]s count
neighbours out to range 500, and Golly's [[ruleloader](pages/ruleloader.md)] runs any rule written as a table or tree.

**The census.** [[apgsearch](pages/apgsearch.md)] evolves random soups by the trillion and uploads what they leave to
[[catagolue](pages/catagolue.md)], a peer-reviewed natural history of Life and some twenty thousand other rules.

**Mapping rule space.** Two yes/no questions sort the Life-like rules: can some finite pattern escape every bounding box,
and can some pattern die out completely? Rules where both hold are where spaceships and Life-style engineering live
([[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)]). Every object also has a [[rule-range](pages/rule-range.md)], the interval
of rules it works in unchanged: Life's glider flies in 256 of them, while much engineered machinery works in Life alone.
Spaceships in any of these rules are found by [[row-by-row-search](pages/row-by-row-search.md)], which turns the hunt into a
path search through a de Bruijn-style graph. Other grids ask the same question, what counts as a Game of Life, with their own answers
([[gl-rule](pages/gl-rule.md)]): the [[triangular-neighbourhood](pages/triangular-neighbourhood.md)] has many qualifying rules, and
[[three-dimensional-life](pages/three-dimensional-life.md)] has rules with their own gliders.

**Foundations.** Two logical ingredients underlie everything: networks of idealized
threshold elements ([[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]) and Turing's
[[universal-turing-machine](pages/universal-turing-machine.md)]. Universality has a threshold: above a minimum complexity,
one automaton can do anything any automaton can do. A universal automaton still cannot predict arbitrary
behavior, which suggests that complex automata may be simpler than any description of what
they do ([[description-vs-object-complexity](pages/description-vs-object-complexity.md)]).

**Self-reproduction.** Below a [[complexity-threshold](pages/complexity-threshold.md)], automata can only build simpler
automata. Above it, self-reproduction works through the [[universal-constructor](pages/universal-constructor.md)]
scheme: build from a description, copy the description, attach the copy. Von Neumann first
set this out in a [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] model. He then abstracted it into a
[[cellular-automaton](pages/cellular-automaton.md)], a homogeneous lattice of identical finite-state cells where
construction means changing cell states. The key move is to copy a quiescent description
rather than the live automaton ([[descriptions-vs-originals](pages/descriptions-vs-originals.md)]).

**The cellular machine.** The concrete medium is [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]. Ordinary
stimuli do logic, special stimuli build and destroy, and a [[construction-arm](pages/construction-arm.md)] places
cells at a distance. From the rule von Neumann builds a library of organs:
[[signal-coding-organs](pages/signal-coding-organs.md)] for timed bit patterns and one-bit memory, and a
[[coded-channel](pages/coded-channel.md)] that gets around wire-crossing in 2D. These are assembled into a
[[cellular-tape](pages/cellular-tape.md)]: unbounded memory reached by an extendible wire loop, with position and timing
both measured relative to the tape. Controller plus tape is a Turing machine inside the CA.

**The completed machine.** Burks finishes the design. A two-path [[construction-arm](pages/construction-arm.md)] makes
every construction step a fixed pulse sequence, and a [[crossing-organ](pages/crossing-organ.md)] lets signals truly
cross. Every buildable machine has to be an [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)], laid down
inert and switched on afterwards. Within that constraint the 29-state rule holds a universal
Turing machine, a universal constructor, and a self-reproducer, which may carry a Turing
machine as payload. Construction and computation turn out to be the same kind of activity.
Some patterns can never be built, the extreme case being [[garden-of-eden](pages/garden-of-eden.md)]
configurations, which have no predecessor.

**Moore's formalization.** Moore recasts the cellular model as a *tessellation structure*
on the nine-cell [[moore-neighbourhood](pages/moore-neighbourhood.md)] and gives
self-reproduction a formal definition, which admits trivial crystal-like cases. Locality
caps offspring at quadratic growth in time. His Garden-of-Eden theorem says that wherever
an [[erasable-configuration](pages/erasable-configuration.md)] exists, so do patterns with
no predecessor, and no self-reproducer can contain one. Myhill proved the converse, so the
[[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] is an equivalence: Garden-of-Eden patterns exist exactly
when two different patterns can be indistinguishable after one step. The theorem holds in every dimension and, on general groups, exactly on an
[[amenable-group](pages/amenable-group.md)]; in modern terms, surjective ⇔ pre-injective. He also surveys working kinematic
reproducers (Penrose's shaken blocks, Jacobson's model trains).

**One dimension, all rules at once.** Hedlund's symbolic dynamics takes the opposite
approach to von Neumann's. It builds no single machine and asks global questions about
every 1D rule. Configurations are points of the
[[shift-dynamical-system](pages/shift-dynamical-system.md)], and the
[[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] identifies the
global maps with the continuous shift-commuting maps. The main results concern
[[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)]s. A 1D rule is
onto iff no finite pattern is orphaned, iff every pattern has exactly S^(n−1)
predecessors, iff no two finitely-different configurations collide. Onto rules are
finite-to-one, with a constant degree at almost every point. Injective rules are always
onto. [[permutive-map](pages/permutive-map.md)]s are the standard onto examples. The
invertible rules form the [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)],
which contains every finite group. Hedlund does not use the words, so reading these as
statements about cellular automata and [[garden-of-eden](pages/garden-of-eden.md)]
configurations is the wiki's own step.

**Reliability.** Von Neumann proposed a [[probabilistic-logic](pages/probabilistic-logic.md)] in which failure is part
of the axioms, bringing the theory closer to analysis and thermodynamics, via the
entropy–information link illustrated by [[maxwells-demon](pages/maxwells-demon.md)]. Natural automata survive
unreliable parts through [[self-repair](pages/self-repair.md)]: they operate across errors instead of halting
on the first one.

**The statistical turn.** Wolfram (1983) reverses von Neumann's approach. Instead of
designing one huge rule for a purpose, he surveys every rule in the smallest family, the
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)], and asks what
the rules do statistically, as models of [[self-organization](pages/self-organization.md)].
The rules split into simple and complex. From a single seed, complex rules grow
self-similar patterns ([[fractal-dimension](pages/fractal-dimension.md)] log₂3 ≈ 1.59,
with [[rule-90](pages/rule-90.md)] the canonical case). From random noise they reach
equilibria whose densities and structure spectra do not depend on the start. These fall
into two universality classes: the
[[additive-cellular-automaton](pages/additive-cellular-automaton.md)] rules, which are
exactly solvable, and all the others. The mechanism is
[[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]. Trajectories
merge, entropy falls, and [[garden-of-eden](pages/garden-of-eden.md)] configurations
become the typical case. Von Neumann's expectation that a theory of automata would
resemble thermodynamics becomes something measurable. The
[[game-of-life](pages/game-of-life.md)] enters as a universal two-state rule built from
glider-stream circuits.

**The edge of chaos.** Langton (1990) asks where in rule space computation is possible at
all. He orders rules by the [[lambda-parameter](pages/lambda-parameter.md)], the fraction
of rule-table entries that do not lead to the quiescent state, and finds a phase
transition between frozen and chaotic dynamics ([[edge-of-chaos](pages/edge-of-chaos.md)]).
Near it, transients grow long and size-dependent, glider-like particles appear, and mutual
information between cells peaks. Wolfram's class IV sits there, as does the
[[game-of-life](pages/game-of-life.md)]. Langton pairs the "freezing problem" with the
halting problem and gives von Neumann's [[complexity-threshold](pages/complexity-threshold.md)]
an upper bound: too much disorder is as degenerative as too little. Where Wolfram (1983)
found no phase transition as noise increased, Langton finds one as the rule itself
changes.

**The decidability turn.** Kari (2005) surveys the field as theoretical computer
science. A rule is a finite triple (S, N, f), and the main question is which properties of
its global map can be *decided* from that triple
([[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)]). The
[[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] reads "surjective iff
injective on finite configurations" in this setting, and injective, bijective and
[[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] all coincide.
Hedlund's automorphisms are exactly the reversible CA. The dividing line is
dimension. 1D injectivity and surjectivity are decidable. In 2D both are undecidable,
because [[wang-tiles](pages/wang-tiles.md)] and the tiling problem can be encoded in them.
Within 1D the line falls between short and long term. Every first-order property of the
one-step relation is decidable by automata on the
[[de-bruijn-graph](pages/de-bruijn-graph.md)]
([[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]),
while orbit questions are undecidable at graded levels
([[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]).
Nilpotency is undecidable even in 1D, and so is every non-trivial property of the
[[limit-set](pages/limit-set.md)] when the state set may vary. Physics motivates block-permutation rules that are
reversible by construction ([[margolus-neighbourhood](pages/margolus-neighbourhood.md)])
and additive [[conserved-quantity](pages/conserved-quantity.md)]s. Reversible Turing machines are universal (Bennett)
([[reversible-turing-machine](pages/reversible-turing-machine.md)]). Universality splits
into the Turing kind, which Life and [[rule-110](pages/rule-110.md)] have, and the
stronger [[intrinsic-universality](pages/intrinsic-universality.md)]. Wolfram's classes
get formal, and undecidable, successors
([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]).
Topological dynamics supplies a precise vocabulary of
[[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)]. For linear rules over
ℤ_m, injectivity, surjectivity and the dynamical properties reduce to gcd tests. Bounded-space 1D CA also serve as
language recognizers
([[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)]).

## Open Questions

- What is the maximum average density of an oscillator? Still lifes top out at 1/2; oscillators are only bounded by 8/13 ([[still-life-density](pages/still-life-density.md)]).
- Does an orphan of height 4 exist? Heights 1-3 are ruled out and height 5 is achieved ([[garden-of-eden](pages/garden-of-eden.md)]).
- Which methuselahs above 9 cells are optimal? Records are proved only up to 9 ([[methuselah](pages/methuselah.md)]).
- Why exactly two universality classes? Wolfram conjectures it is because rules simulate each
  other under short encodings. Is that the whole story?
- Rule 110 is universal (Cook and Wolfram, reported by Kari). Is it intrinsically universal?
  Is rule 54 universal at all? Cook (2004), on the reading list, gives the proof.
- What is the degree of the full first-order theory of a CA with its orbit relation? Sutner
  suspects every level of the arithmetic hierarchy is expressible as an orbit assertion.
- Could pseudo-random rule 30 ever carry an undecidability proof?
- In two or more dimensions, which of the three open Garden-of-Eden implications between
  G, G_F and G_P hold?
- Is positive expansivity of 1D rules decidable? Can one decide whether a 1D rule has any
  non-trivial conserved quantity?
- Are temporally periodic configurations dense in every surjective rule? If so, chaos in
  CA is just transitivity.
- Is real-time CA language recognition as strong as linear-time (Smith, 1972)?
- What exactly is von Neumann's complexity threshold, and does the 29-state construction
  make it precise? Von Neumann guessed millions of parts for the kinematic model.
- How do the kinematic (Part I) and cellular (Part II) models of self-reproduction differ
  in what they assume?
- Von Neumann's design is serial and ignores the medium's parallelism. How much smaller could
  a parallel self-reproducer be?
- How small can the smallest Garden-of-Eden pattern be? Moore always found one within
  5 × 5, while the Moore-Myhill counting argument gives enormous ones.
- Can self-reproduction happen in a structure with no erasable configurations?
- How can "less trivial" self-reproduction be made precise?
- Hedlund reports that onto maps look rare and automorphisms "relatively sparse" among all
  1D rules, but nothing was proved. Can that be made precise?
- Is Langton's freezing problem undecidable, as he conjectures, and is the halting problem
  really a special case of it?
- λ works poorly for 2-state, 3-neighbour rules. Where do elementary rules such as rule 110
  sit relative to the transition, and what finer parameter would place them?

## Key Entities / Concepts

- [[theory-of-automata](pages/theory-of-automata.md)]
- [[self-reproduction](pages/self-reproduction.md)]
- [[complexity-threshold](pages/complexity-threshold.md)]
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[description-vs-object-complexity](pages/description-vs-object-complexity.md)]
- [[probabilistic-logic](pages/probabilistic-logic.md)]
- [[maxwells-demon](pages/maxwells-demon.md)]
- [[self-repair](pages/self-repair.md)]
- [[universal-constructor](pages/universal-constructor.md)]
- [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]
- [[descriptions-vs-originals](pages/descriptions-vs-originals.md)]
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]
- [[construction-arm](pages/construction-arm.md)]
- [[signal-coding-organs](pages/signal-coding-organs.md)]
- [[coded-channel](pages/coded-channel.md)]
- [[cellular-tape](pages/cellular-tape.md)]
- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)]
- [[crossing-organ](pages/crossing-organ.md)]
- [[garden-of-eden](pages/garden-of-eden.md)]
- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]
- [[amenable-group](pages/amenable-group.md)]
- [[edward-f-moore](pages/edward-f-moore.md)]
- [[john-myhill](pages/john-myhill.md)]
- [[erasable-configuration](pages/erasable-configuration.md)]
- [[moore-neighbourhood](pages/moore-neighbourhood.md)]
- [[shift-dynamical-system](pages/shift-dynamical-system.md)]
- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)]
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)]
- [[permutive-map](pages/permutive-map.md)]
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)]
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)]
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)]
- [[rule-90](pages/rule-90.md)]
- [[fractal-dimension](pages/fractal-dimension.md)]
- [[self-organization](pages/self-organization.md)]
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]
- [[game-of-life](pages/game-of-life.md)]
- [[still-life](pages/still-life.md)]
- [[oscillator](pages/oscillator.md)]
- [[spaceship](pages/spaceship.md)]
- [[glider](pages/glider.md)]
- [[block](pages/block.md)]
- [[beehive](pages/beehive.md)]
- [[blinker](pages/blinker.md)]
- [[r-pentomino](pages/r-pentomino.md)]
- [[pulsar](pages/pulsar.md)]
- [[pentadecathlon](pages/pentadecathlon.md)]
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]
- [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)]
- [[gosper-glider-gun](pages/gosper-glider-gun.md)]
- [[queen-bee](pages/queen-bee.md)]
- [[twin-bees](pages/twin-bees.md)]
- [[switch-engine](pages/switch-engine.md)]
- [[familiar-fours](pages/familiar-fours.md)]
- [[methuselah](pages/methuselah.md)]
- [[soup-search](pages/soup-search.md)]
- [[eater](pages/eater.md)]
- [[still-life-density](pages/still-life-density.md)]
- [[sparker](pages/sparker.md)]
- [[hassler](pages/hassler.md)]
- [[reflector](pages/reflector.md)]
- [[herschel](pages/herschel.md)]
- [[omniperiodicity](pages/omniperiodicity.md)]
- [[phoenix](pages/phoenix.md)]
- [[cordership](pages/cordership.md)]
- [[puffer](pages/puffer.md)]
- [[signal-wire](pages/signal-wire.md)]
- [[object-synthesis](pages/object-synthesis.md)]
- [[slow-salvo](pages/slow-salvo.md)]
- [[breeder](pages/breeder.md)]
- [[inverter](pages/inverter.md)]
- [[primer](pages/primer.md)]
- [[memory-cell](pages/memory-cell.md)]
- [[heisenburp](pages/heisenburp.md)]
- [[regulator](pages/regulator.md)]
- [[conduit](pages/conduit.md)]
- [[period-multiplier](pages/period-multiplier.md)]
- [[gun](pages/gun.md)]
- [[caber-tosser](pages/caber-tosser.md)]
- [[apgsembly](pages/apgsembly.md)]
- [[sliding-block-register](pages/sliding-block-register.md)]
- [[self-supporting-spaceship](pages/self-supporting-spaceship.md)]
- [[caterloopillar](pages/caterloopillar.md)]
- [[single-channel-construction](pages/single-channel-construction.md)]
- [[self-constructing-spaceship](pages/self-constructing-spaceship.md)]
- [[metacell](pages/metacell.md)]
- [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]
- [[non-isotropic-rule](pages/non-isotropic-rule.md)]
- [[highlife](pages/highlife.md)]
- [[replicator](pages/replicator.md)]
- [[generations-rule](pages/generations-rule.md)]
- [[star-wars-rule](pages/star-wars-rule.md)]
- [[brians-brain](pages/brians-brain.md)]
- [[lambda-parameter](pages/lambda-parameter.md)]
- [[edge-of-chaos](pages/edge-of-chaos.md)]
- [[chris-langton](pages/chris-langton.md)]
- [[jarkko-kari](pages/jarkko-kari.md)]
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)]
- [[wang-tiles](pages/wang-tiles.md)]
- [[limit-set](pages/limit-set.md)]
- [[conserved-quantity](pages/conserved-quantity.md)]
- [[intrinsic-universality](pages/intrinsic-universality.md)]
- [[rule-110](pages/rule-110.md)]
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]
- [[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)]
- [[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)]
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)]
- [[tag-system](pages/tag-system.md)]
- [[reversible-turing-machine](pages/reversible-turing-machine.md)]
- [[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]
- [[de-bruijn-graph](pages/de-bruijn-graph.md)]
- [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]
