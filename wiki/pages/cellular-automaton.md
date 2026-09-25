---
title: Cellular Automaton
category: Concepts
summary: A homogeneous lattice of identical finite-state cells, each updating in discrete time from its own state and its neighbours' states under one shared rule; introduced by von Neumann (after Ulam) as a medium for self-reproduction
tags: [concept, cellular-automata, foundations, homogeneity, lattice]
sources: [tsra-part2-ch1, tsra-part2-ch2, tsra-part2-ch3, machine-models-of-self-reproduction, endomorphisms-and-automorphisms-of-the-shift-dynamical-system, statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos]
created: 2026-09-24
updated: 2026-09-24
---

# Cellular Automaton

## Description

A cellular automaton is a space divided into cells arranged in a regular lattice. Every
cell contains the same finite automaton, and every cell is connected to its neighbours in
the same way. Time is discrete. At each step every cell's new state depends only on its
own state and its neighbours' states, through a single transition rule shared by all
cells.[^1]

**Origins.** Von Neumann arrived at the cellular model by taking the physics out of his
[[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] model:[^2]

1. **No motion.** Parts don't move. Stationary cells switch between a *quiescent* state
   and one or more *active* states.
2. **A discrete medium.** Space is a granular, crystalline structure rather than a
   continuum.
3. **Growth as a change of state.** Building something means turning *unexcitable* cells
   into excitable ones. An "empty" site is just a cell in a special unexcitable state,
   which von Neumann calls the "structure of the vacuum."

Ulam suggested the cellular approach, as more amenable to logical and mathematical
treatment than the kinematic one.[^3] Von Neumann's own names for it include "crystalline
medium," "granular structure," and "cellular structure." Later authors also called it a
"tessellation model."[^3] Moore's *tessellation structure* is a formal version: the
lattice, a finite state set, a quiescent state, and one transition function, with a
quiescent cell surrounded by quiescent cells staying quiescent and all but finitely many
cells quiescent at time 0.[^4] He warns that three things can be called "machines" here: the
tessellation (the universe), a finite configuration (the machine that reproduces), and a
cell (an elementary part).[^5]

**Homogeneity and isotropy.** The medium is *functionally homogeneous*: every cell holds
the same automaton and obeys the same rules. Homogeneity and isotropy constrain the
*structure*, not the contents. Different cells can be in different states, and that is how
distinct organisms exist in a uniform medium.[^6] Von Neumann regarded achieving functional
homogeneity despite an irregular distribution of cell types as one of the main results of
the work. He also noted that self-reproduction in a homogeneous medium is a stronger
result than in an inhomogeneous one.[^7]

**Quiescence.** *Total quiescence*, with every cell in the quiescent state, is
self-perpetuating under the usual rules. It makes a natural background. Activity starts
from a finite region that differs from the background.[^8] In von Neumann's system the
blank state U plays the role of a blank square on a Turing tape. At any moment only
finitely many cells are in any other state.[^9]

**Configurations and runs.** An *initial cell assignment* is a finite list of cells with
their states, imposed at time 0, with every other cell blank. The lattice together with an
initial assignment is an *infinite cellular automaton*. After time 0 it evolves under the
transition rule alone. Self-reproduction means that a configuration occupying some region
at time 0 appears again, cell for cell, in another region at a later time.[^10]

**Dimension and lattice.** Von Neumann expected three dimensions to be usable, found that
two also suffice, and judged one unlikely to work. He used the most regular lattice: the
square lattice in two dimensions, with each cell connected to its four orthogonal
neighbours.[^11] Moore reports that von Neumann, in his 1955 Vanuxem lectures, said he had
first thought three dimensions might be needed because the wiring might be non-planar, until
he found a way for wires to cross in two. Shannon told Moore of a scheme for a limited kind
of self-reproduction in one dimension.[^12] Using the four orthogonal neighbours rather than all eight keeps the rule
simpler. A rule is then a function of five cells (the cell and its four neighbours), so
with N states there are N^(N⁵) possible rules. For von Neumann's own rule,
[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)], that is roughly 10^(59,000,000).[^13]
Moore instead takes all nine cells of the surrounding 3 × 3 block, the
[[moore-neighbourhood](pages/moore-neighbourhood.md)], which includes von Neumann's five as a
special case.[^14]

**Why a discrete model.** The crystalline and continuous (Euclidean) settings offer broadly
the same possibilities. The continuous one is much harder mathematically, and would need
nonlinear partial differential equations, but would be more satisfying if it could be
handled. Von Neumann therefore worked mainly with the crystalline setting.[^15] One cost of
removing kinematics is that moving a structure across the lattice is about as hard as
reproducing it. Structures are therefore tied to their locations, and conflicts between
them are conflicts over space.[^16]

**Finite speed.** With a radius-1 neighbourhood, the non-quiescent region grows by at most
one cell per step in each direction. Moore likens this to a finite velocity of light and uses
it to bound self-reproduction to at most quadratic growth in two dimensions.[^17] The same
locality, together with the possibility of erasure, forces
[[garden-of-eden](pages/garden-of-eden.md)] configurations to exist
([[erasable-configuration](pages/erasable-configuration.md)]).[^18]

**Parallel medium, serial machines.** A cellular automaton updates every cell at once, so
it allows unlimited parallelism. Von Neumann's self-reproducing machine nonetheless works
like a serial computer, with most of its organs dormant at any moment.[^19] Moore lists parallel reproduction as an
open problem.[^20] Two
dimensions also force a problem that three do not: signal lines must sometimes cross,
which von Neumann solves by coding ([[coded-channel](pages/coded-channel.md)]).[^21]

**The topological view in one dimension.** Hedlund (1969) never uses the words
"cellular automaton". Read as a 1D CA (own reasoning), a configuration is a point of the
[[shift-dynamical-system](pages/shift-dynamical-system.md)] X(S): an infinite row of
cells with no finiteness condition. Translating by one cell is the shift σ, and a rule of
radius r is a block map on windows of 2r + 1 cells. The
[[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] says the
continuous, shift-commuting maps of X(S) are exactly these block maps composed with
shifts.[^22] This gives a definition of the global map with no mention of neighbourhoods,
and a global theory of all rules at once. That theory covers which rules are onto
([[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)]), which are
invertible ([[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)]),
and how many predecessors a configuration has.[^23]

**A physicist's view.** Wolfram describes cellular automata as idealized physical systems
in which space, time and the physical quantities are all discrete. The lattice is regular
and usually infinite. All cells update together ("synchronously") from their neighbourhoods
at the previous step.[^24] He counts "cellular spaces" (von Neumann and Ulam's term),
"tessellation automata", "homogeneous structures", "cellular structures", "tessellation
structures" and "iterative arrays" as names for the same idea. He proposes cellular
automata as models for spin systems, reaction-diffusion chemistry, crystal growth,
turbulence, biological pattern formation, and parallel computers. Finite differences turn
any differential equation into one, and nontrivial behaviour needs nonlinearity, such as
"growth inhibition".[^25] The simplest case, a line of two-state cells with nearest
neighbours, is the [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)].

**Neighbourhoods in d dimensions.** A *type-I* neighbourhood has the cell plus its 2d
orthogonal neighbours, which is von Neumann's five-cell neighbourhood when d = 2. A *type-II*
neighbourhood has all 3ᵈ cells within one step, orthogonal or diagonal, which is the
nine-cell Moore neighbourhood when d = 2. In one dimension the two coincide. Requiring
quiescence and the lattice's rotation and reflection symmetries, there are 2¹¹ = 2048
legal two-state type-I rules in 2D and 2⁵⁹ ≈ 6 × 10¹⁷ type-II rules.[^26] A rule is
*totalistic* if it depends only on the sum of the neighbourhood values. The
[[game-of-life](pages/game-of-life.md)] is a type-II totalistic rule.[^27]

**Computers or universes.** Langton distinguishes two ways to see computation in a
cellular automaton. The CA can *be* a computer, with the initial configuration as data
and the rule as algorithm. Or the initial configuration can *contain* a computer, with
the rule as the physics its parts obey, as in von Neumann's construction. With K states
and N neighbours there are K^(K^N) rules, and Langton orders this space with the
[[lambda-parameter](pages/lambda-parameter.md)] to ask which rules can support the second view
([[edge-of-chaos](pages/edge-of-chaos.md)]).[^28]

## Appearances in Sources

- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - two views of computation; the size of rule space and an ordering for it
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — the physicist's view, alternative names, applications, type-I/type-II neighbourhoods, rule counts
- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] — the tessellation structure, the nine-cell neighbourhood, finite speed
- [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] — serial operation and wire-crossing in 2D
- [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] — the neighbourhood and the size of the rule space
- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — the derivation of the cellular model and its general properties
- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] — 1D global maps as continuous shift-commuting maps (the CA reading is own reasoning)

## Related Concepts

- [[lambda-parameter](pages/lambda-parameter.md)] - an ordering of rule space by one number
- [[edge-of-chaos](pages/edge-of-chaos.md)] - where in rule space computation is possible
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] — the simplest one-dimensional family
- [[game-of-life](pages/game-of-life.md)] — the best-known two-dimensional rule
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — the ensemble, statistical-mechanics view
- [[garden-of-eden](pages/garden-of-eden.md)] — configurations with no predecessor
- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] — Garden-of-Eden patterns exist exactly when erasure does
- [[erasable-configuration](pages/erasable-configuration.md)] — local information loss, which forces Garden-of-Eden patterns
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] — the nine-cell neighbourhood
- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] — 1D global maps = continuous shift-commuting maps
- [[shift-dynamical-system](pages/shift-dynamical-system.md)] — the configuration space of a 1D automaton
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] — 1D rules whose global map is onto
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] — invertible 1D rules
- [[permutive-map](pages/permutive-map.md)] — a class of 1D rules that are always onto
- [[coded-channel](pages/coded-channel.md)] — the 2D wire-crossing problem and its solution
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] — the first concrete rule
- [[construction-arm](pages/construction-arm.md)] — how construction works without moving parts
- [[self-reproduction](pages/self-reproduction.md)] — the problem the cellular model was built to solve
- [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] — the physical model it abstracts
- [[universal-constructor](pages/universal-constructor.md)] — realized inside a cellular automaton in Part II
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the blank cellular background is analogous to blank tape
- [[theory-of-automata](pages/theory-of-automata.md)] — the program within which the cellular automaton appears

[^1]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.94, 103, 106 [synthesis] — each cell contains the same finite automaton; functional homogeneity means every cell is connected to its neighbours in the same way and obeys the same rules
[^2]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.102-103, 109 [synthesis] — avoidance of geometry and kinematics; stationarity with quiescent vs. active states; discrete medium; growth as the transformation of unexcitable cells into excitable ones; the "structure of the vacuum"
[^3]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.94 [synthesis] — editor: Ulam suggested the cellular model; von Neumann's terms "crystalline regularity," "crystalline medium," "granular structure," "cellular structure"; Moore's "tessellation model"
[^4]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.17-18, 21 [synthesis] - the tessellation structure as the system of space, states, quiescent state, and transition rules; formally a quintuple (N, T, S, q₀, f); quiescent neighbourhood stays quiescent; all but finitely many cells quiescent at T = 0
[^5]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.20 [synthesis] - the tessellation, the configuration, and the cell can each be called a machine; the tessellation is the environment, the configuration reproduces, the cell is an elementary part
[^6]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.103, 106 [synthesis] — homogeneity of the medium is distinguished from homogeneity of the population of objects; functional homogeneity and isotropy apply to structure, not content
[^7]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.103-104 [synthesis] — self-reproduction in a homogeneous medium is the stronger result; achieving functional homogeneity despite irregularly distributed neuron species is "one of the main results"
[^8]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.104 [synthesis] — total quiescence is self-perpetuating under the usual rules; start from total quiescence plus a minimal injection of external stimulation
[^9]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.107 [synthesis] — editor: the unexcitable state U is utterly quiescent; only finitely many cells are ever in another state; U is analogous to a blank square on a Turing tape
[^10]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.108 [synthesis] — editor: initial cell assignment; "infinite cellular automaton"; self-reproduction as a later copy of an embedded automaton in another area
[^11]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.105-106 [synthesis] — questions of dimensionality, isotropy, and crystal class; 2D usable, 1D unlikely; maximum regularity chosen; editor: square cells with four neighbours
[^12]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.20 [synthesis] - Vanuxem lectures (Princeton, March 2-5, 1955): 3 dimensions first thought necessary since the wiring diagram might be non-planar, then a method for wires to cross in 2 dimensions; Shannon's unpublished scheme for a limited kind of self-reproduction in a 1-dimensional tessellation structure
[^13]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.133-134, 149 [synthesis] — nearest four neighbours chosen over eight as simpler; the transition rule is a function of five states; N^(N⁵) possible rules, 29^(29⁵) ≈ 10^(59,000,000) for N = 29
[^14]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.21 [synthesis] - neighbours are the nine cells whose coordinates differ by at most 1; von Neumann's five-cell definition is included as a special case
[^15]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.105-106 [synthesis] — the same general possibilities in both settings; the continuous case is mathematically much harder but more satisfactory once analytic methods exist; attention primarily on the crystalline case
[^16]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.129-130 [synthesis] — in the crystal, moving a structure is about as complex as reproducing it; structures are tied to location and conflicts are conflicts in location
[^17]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.23 [synthesis] - Theorem 1, f(T) < kT²; each unit of time lets the non-quiescent region grow one cell in each direction; "a physical limitation such as a finite velocity of light"
[^18]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.26, 28-29 [synthesis] - Theorem 2 and its assumptions, including local action and the possibility of erasing
[^19]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.157-158 [synthesis] — editor: the cellular structure allows an indefinite amount of parallelism, but the self-reproducing automaton works like a serial digital computer with most organs normally quiescent
[^20]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.30 [synthesis] - how the steps of reproduction could go on in parallel rather than serially, as in the machines of Penrose, von Neumann, and Jacobson
[^21]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.190-191 [synthesis] — in 2D, communication channels must sometimes intersect; solved by the coded channel
[^22]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.323-325 [synthesis] — block maps f∞ with [f∞(x)]_i = f(x_i ⋯ x_(i+n−1)); Thm 3.1 (continuous, commute with σ); Thm 3.4 (Curtis, Hedlund, Lyndon): every continuous shift-commuting map is σ^m f∞
[^23]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.321, 326-334, 351 [synthesis] — the paper's program: onto maps E(S), automorphisms A(S), multiplicities of preimages
[^24]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.602 [synthesis] — "mathematical idealizations of physical systems in which space and time are discrete, and physical quantities take on a finite set of discrete values"; regular uniform lattice, usually infinite; variables "updated simultaneously ('synchronously')" from neighbourhood values at the preceding step
[^25]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.602-603 [synthesis] — introduced by von Neumann and Ulam as "cellular spaces"; also called tessellation automata, homogeneous structures, cellular structures, tessellation structures, iterative arrays; any system of differential equations may be approximated by finite differences and discrete variables; nontrivial cellular automata arise with nonlinearity such as "growth inhibition"; applications to Ising-type spin systems, chemical reaction-diffusion, dendritic crystal growth, turbulence, biology, parallel computation
[^26]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 and n.14 [synthesis] — type-I neighbourhood of 2d+1 sites, type-II of 3ᵈ sites; identical when d = 1; for d = 2 "known as von Neumann and Moore neighborhoods"; legality includes rotation and reflection invariance; 2¹¹ = 2048 type-I rules for k = 2; 2⁵⁹ ≈ 6 × 10¹⁷ type-II rules
[^27]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] — "totalistic" cellular automata depend only on the sum of neighbourhood values; Life is a type-II example
[^28]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.13-16 [synthesis] - Sec. 1.4: K^N neighbourhood states and K^(K^N) transition functions; Sec. 2.5: CAs "can be viewed either as computers themselves or as logical universes within which computers may be embedded"; on the second view "the transition function is seen as the 'physics' obeyed by the parts of this embedded computer"; "when is it possible - even necessary - to adopt the second point of view"
