---
title: Cellular Automaton
category: Concepts
summary: A homogeneous lattice of identical finite-state cells, each updating in discrete time from its own state and its neighbours' states under one shared rule; introduced by von Neumann (after Ulam) as a medium for self-reproduction
tags: [concept, cellular-automata, foundations, homogeneity, lattice]
sources: [tsra-part2-ch1]
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
neighbours.[^9]

**Why a discrete model.** The crystalline and continuous (Euclidean) settings offer broadly
the same possibilities. The continuous one is much harder mathematically, and would need
nonlinear partial differential equations, but would be more satisfying if it could be
handled. Von Neumann therefore worked mainly with the crystalline setting.[^10] One cost of
removing kinematics is that moving a structure across the lattice is about as hard as
reproducing it. Structures are therefore tied to their locations, and conflicts between
them are conflicts over space.[^11]

## Appearances in Sources

- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — the derivation of the cellular model and its general properties

## Related Concepts

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
[^10]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.105-106 [synthesis] — the same general possibilities in both settings; the continuous case is mathematically much harder but more satisfactory once analytic methods exist; attention primarily on the crystalline case
[^11]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.129-130 [synthesis] — in the crystal, moving a structure is about as complex as reproducing it; structures are tied to location and conflicts are conflicts in location
