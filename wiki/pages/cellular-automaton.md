---
title: Cellular Automaton
category: Concepts
summary: A homogeneous lattice of identical finite-state cells, each updating in discrete time from its own state and its neighbours' states under one shared rule; introduced by von Neumann (after Ulam) as a medium for self-reproduction
tags: [concept, cellular-automata, foundations, homogeneity, lattice]
sources: [tsra-part2-ch1, tsra-part2-ch2, tsra-part2-ch3, endomorphisms-and-automorphisms-of-the-shift-dynamical-system]
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
"tessellation model."[^3]

**Homogeneity and isotropy.** The medium is *functionally homogeneous*: every cell holds
the same automaton and obeys the same rules. Homogeneity and isotropy constrain the
*structure*, not the contents. Different cells can be in different states, and that is how
distinct organisms exist in a uniform medium.[^4] Von Neumann regarded achieving functional
homogeneity despite an irregular distribution of cell types as one of the main results of
the work. He also noted that self-reproduction in a homogeneous medium is a stronger
result than in an inhomogeneous one.[^5]

**Quiescence.** *Total quiescence*, with every cell in the quiescent state, is
self-perpetuating under the usual rules. It makes a natural background. Activity starts
from a finite region that differs from the background.[^6] In von Neumann's system the
blank state U plays the role of a blank square on a Turing tape. At any moment only
finitely many cells are in any other state.[^7]

**Configurations and runs.** An *initial cell assignment* is a finite list of cells with
their states, imposed at time 0, with every other cell blank. The lattice together with an
initial assignment is an *infinite cellular automaton*. After time 0 it evolves under the
transition rule alone. Self-reproduction means that a configuration occupying some region
at time 0 appears again, cell for cell, in another region at a later time.[^8]

**Dimension and lattice.** Von Neumann expected three dimensions to be usable, found that
two also suffice, and judged one unlikely to work. He used the most regular lattice: the
square lattice in two dimensions, with each cell connected to its four orthogonal
neighbours.[^9] Using the four orthogonal neighbours rather than all eight keeps the rule
simpler. A rule is then a function of five cells (the cell and its four neighbours), so
with N states there are N^(N⁵) possible rules. For von Neumann's own rule,
[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)], that is roughly 10^(59,000,000).[^10]

**Why a discrete model.** The crystalline and continuous (Euclidean) settings offer broadly
the same possibilities. The continuous one is much harder mathematically, and would need
nonlinear partial differential equations, but would be more satisfying if it could be
handled. Von Neumann therefore worked mainly with the crystalline setting.[^11] One cost of
removing kinematics is that moving a structure across the lattice is about as hard as
reproducing it. Structures are therefore tied to their locations, and conflicts between
them are conflicts over space.[^12]

**Parallel medium, serial machines.** A cellular automaton updates every cell at once, so
it allows unlimited parallelism. Von Neumann's self-reproducing machine nonetheless works
like a serial computer, with most of its organs dormant at any moment.[^13] Two
dimensions also force a problem that three do not: signal lines must sometimes cross,
which von Neumann solves by coding ([[coded-channel](pages/coded-channel.md)]).[^14]

**The topological view in one dimension.** Hedlund (1969) never uses the words
"cellular automaton". Read as a 1D CA (own reasoning), a configuration is a point of the
[[shift-dynamical-system](pages/shift-dynamical-system.md)] X(S): an infinite row of
cells with no finiteness condition. Translating by one cell is the shift σ, and a rule of
radius r is a block map on windows of 2r + 1 cells. The
[[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] says the
continuous, shift-commuting maps of X(S) are exactly these block maps composed with
shifts.[^15] This gives a definition of the global map with no mention of neighbourhoods,
and a global theory of all rules at once. That theory covers which rules are onto
([[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)]), which are
invertible ([[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)]),
and how many predecessors a configuration has.[^16]

## Appearances in Sources

- [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] — serial operation and wire-crossing in 2D
- [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] — the neighbourhood and the size of the rule space
- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — the derivation of the cellular model and its general properties
- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] — 1D global maps as continuous shift-commuting maps (the CA reading is own reasoning)

## Related Concepts

- [[garden-of-eden](pages/garden-of-eden.md)] — configurations with no predecessor
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
[^4]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.103, 106 [synthesis] — homogeneity of the medium is distinguished from homogeneity of the population of objects; functional homogeneity and isotropy apply to structure, not content
[^5]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.103-104 [synthesis] — self-reproduction in a homogeneous medium is the stronger result; achieving functional homogeneity despite irregularly distributed neuron species is "one of the main results"
[^6]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.104 [synthesis] — total quiescence is self-perpetuating under the usual rules; start from total quiescence plus a minimal injection of external stimulation
[^7]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.107 [synthesis] — editor: the unexcitable state U is utterly quiescent; only finitely many cells are ever in another state; U is analogous to a blank square on a Turing tape
[^8]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.108 [synthesis] — editor: initial cell assignment; "infinite cellular automaton"; self-reproduction as a later copy of an embedded automaton in another area
[^9]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.105-106 [synthesis] — questions of dimensionality, isotropy, and crystal class; 2D usable, 1D unlikely; maximum regularity chosen; editor: square cells with four neighbours
[^10]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.133-134, 149 [synthesis] — nearest four neighbours chosen over eight as simpler; the transition rule is a function of five states; N^(N⁵) possible rules, 29^(29⁵) ≈ 10^(59,000,000) for N = 29
[^11]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.105-106 [synthesis] — the same general possibilities in both settings; the continuous case is mathematically much harder but more satisfactory once analytic methods exist; attention primarily on the crystalline case
[^12]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.129-130 [synthesis] — in the crystal, moving a structure is about as complex as reproducing it; structures are tied to location and conflicts are conflicts in location
[^13]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.157-158 [synthesis] — editor: the cellular structure allows an indefinite amount of parallelism, but the self-reproducing automaton works like a serial digital computer with most organs normally quiescent
[^14]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.190-191 [synthesis] — in 2D, communication channels must sometimes intersect; solved by the coded channel
[^15]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.323-325 [synthesis] — block maps f∞ with [f∞(x)]_i = f(x_i ⋯ x_(i+n−1)); Thm 3.1 (continuous, commute with σ); Thm 3.4 (Curtis, Hedlund, Lyndon): every continuous shift-commuting map is σ^m f∞
[^16]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.321, 326-334, 351 [synthesis] — the paper's program: onto maps E(S), automorphisms A(S), multiplicities of preimages
