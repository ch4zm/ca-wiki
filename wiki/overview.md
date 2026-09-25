---
title: Overview
tags: [overview, synthesis]
sources: [theory-of-self-reproducing-automata, tsra-editors-introduction, tsra-lecture-2, tsra-lecture-3, tsra-lecture-4, tsra-lecture-5, tsra-part2-ch1, tsra-part2-ch2, tsra-part2-ch3, tsra-part2-ch4, tsra-part2-ch5, endomorphisms-and-automorphisms-of-the-shift-dynamical-system, machine-models-of-self-reproduction, converse-of-moores-garden-of-eden-theorem, statistical-mechanics-of-cellular-automata, planetmath-garden-of-eden-theorem, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey, automata-universality-computation, aucm-ch5-small-universal-turing-machines, aucm-ch6-reversible-turing-machines-by-rlem, aucm-ch12-linear-cellular-automata-and-decidability, aucm-ch13-cellular-automata-with-write-access, aucm-ch14-broadcasting-automata, aucm-ch15-real-time-prime-generators, aucm-ch16-phyllosilicate-automata]
updated: 2026-09-24
---

# Cellular Automata — Overview

> Evolving synthesis of everything in the wiki. Updated by wiki-ingest when sources shift the understanding.

## Current Understanding

Cellular automata begin with von Neumann's [[theory-of-automata](pages/theory-of-automata.md)], a logical and
mathematical theory of how automata, natural and artificial, are organized. Its organizing
concept is complexity, and its two central problems are
[[self-reproduction](pages/self-reproduction.md)] and reliability.

**Foundations.** Two logical ingredients underlie everything: networks of idealized
threshold elements ([[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]) and Turing's
[[universal-turing-machine](pages/universal-turing-machine.md)]. Universality has a threshold: above a minimum complexity,
one automaton can do anything any automaton can do. The threshold is partly mapped for
program size. The smallest known universal Turing machines, many of them simulators of a
[[tag-system](pages/tag-system.md)], sit a few (states, symbols) pairs above the sizes
where halting is decidable. Machines in the gap already iterate the
[[collatz-function](pages/collatz-function.md)]. A universal automaton still cannot predict arbitrary
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
and additive [[conserved-quantity](pages/conserved-quantity.md)]s. Reversible Turing machines are universal (Bennett), and any of them can be built from a
single one-bit reversible element, the rotary element
([[reversible-logic-element-with-memory](pages/reversible-logic-element-with-memory.md)]),
realizable in the frictionless [[billiard-ball-model](pages/billiard-ball-model.md)]
([[reversible-turing-machine](pages/reversible-turing-machine.md)]). Universality splits
into the Turing kind, which Life and [[rule-110](pages/rule-110.md)] have, and the
stronger [[intrinsic-universality](pages/intrinsic-universality.md)]. Wolfram's classes
get formal, and undecidable, successors
([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]).
Topological dynamics supplies a precise vocabulary of
[[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)]. For linear rules over
ℤ_m, injectivity, surjectivity and the dynamical properties reduce to gcd tests. Variants relax the read-only cell: in a
[[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)]
active cells write to their neighbours, which suits agents and particles such as the
traffic [[rule-184](pages/rule-184.md)], without adding power at bounded radius. In a
[[broadcasting-automaton](pages/broadcasting-automaton.md)] each state sets a Euclidean
transmission radius. Its waves trace discrete discs, which generalize the von Neumann and
Moore neighbourhoods ([[neighbourhood-sequence](pages/neighbourhood-sequence.md)]). Composing
discs yields only convex shapes, and aggregating two wave trains escapes that limit. Signals, straight-line information flows limited to one cell per step, let a 1D CA act as
a clock: an 8-state rule fires its end cell at exactly the prime times
([[sequence-generation-by-cellular-automata](pages/sequence-generation-by-cellular-automata.md)]),
and 25 states suffice even when neighbours exchange only one bit per step
([[one-bit-communication-cellular-automaton](pages/one-bit-communication-cellular-automaton.md)]). Life's gliders, eaters and guns are not tied to the square grid: they reappear in
Life-like rules of the two-node-type
[[phyllosilicate-automaton](pages/phyllosilicate-automaton.md)], though most collisions
there explode. Bounded-space 1D CA also serve as
language recognizers
([[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)]).

## Open Questions

- Why exactly two universality classes? Wolfram conjectures it is because rules simulate each
  other under short encodings. Is that the whole story?
- Rule 110 is universal (Cook and Wolfram, reported by Kari). Is it intrinsically universal?
  Is rule 54 universal at all? Cook (2004), on the reading list, gives the proof.
- What is the degree of the full first-order theory of a CA with its orbit relation? Sutner
  suspects every level of the arithmetic hierarchy is expressible as an orbit assertion.
- Could pseudo-random rule 30 ever carry an undecidability proof?
- What is the fewest states a real-time prime generator can have? The record is 8 for an
  ordinary CA and 25 with one-bit links, and the source gives no lower bound.
- Do the phyllosilicate rules R65 and R68 have glider guns, and R65 and R72 still lifes?
  Adamatzky expects so. Are their few non-explosive collisions enough to build logic?
- Which of the 39 open (states, symbols) pairs admit a universal Turing machine? Machines
  of Collatz-simulator size are already at least as hard to analyse as the Collatz
  conjecture.
- Is the one remaining non-degenerate 2-state, 2-symbol reversible logic element
  universal? The other three are not, and every one with more symbols is.
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
- [[collatz-function](pages/collatz-function.md)]
- [[reversible-turing-machine](pages/reversible-turing-machine.md)]
- [[reversible-logic-element-with-memory](pages/reversible-logic-element-with-memory.md)]
- [[billiard-ball-model](pages/billiard-ball-model.md)]
- [[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]
- [[de-bruijn-graph](pages/de-bruijn-graph.md)]
- [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]
- [[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)]
- [[rule-184](pages/rule-184.md)]
- [[broadcasting-automaton](pages/broadcasting-automaton.md)]
- [[neighbourhood-sequence](pages/neighbourhood-sequence.md)]
- [[sequence-generation-by-cellular-automata](pages/sequence-generation-by-cellular-automata.md)]
- [[one-bit-communication-cellular-automaton](pages/one-bit-communication-cellular-automaton.md)]
- [[phyllosilicate-automaton](pages/phyllosilicate-automaton.md)]
