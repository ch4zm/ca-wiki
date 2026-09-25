---
title: Cellular Automaton
category: Concepts
summary: A homogeneous lattice of identical finite-state cells, each updating in discrete time from its own state and its neighbours' states under one shared rule; introduced by von Neumann (after Ulam) as a medium for self-reproduction
tags: [concept, cellular-automata, foundations, homogeneity, lattice]
sources: [tsra-part2-ch1, tsra-part2-ch2, tsra-part2-ch3, machine-models-of-self-reproduction, endomorphisms-and-automorphisms-of-the-shift-dynamical-system, statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey, aucm-ch13-cellular-automata-with-write-access, aucm-ch14-broadcasting-automata, aucm-ch15-real-time-prime-generators]
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
it to bound self-reproduction to at most quadratic growth in two dimensions.[^17] In
one dimension the same bound caps *signals*, information drawn as straight lines in the
space-time diagram, at one cell per step. Signal timing is how CA are programmed to fire a
cell at the prime times
([[sequence-generation-by-cellular-automata](pages/sequence-generation-by-cellular-automata.md)]).[^18] The same
locality, together with the possibility of erasure, forces
[[garden-of-eden](pages/garden-of-eden.md)] configurations to exist
([[erasable-configuration](pages/erasable-configuration.md)]).[^19]

**Parallel medium, serial machines.** A cellular automaton updates every cell at once, so
it allows unlimited parallelism. Von Neumann's self-reproducing machine nonetheless works
like a serial computer, with most of its organs dormant at any moment.[^20] Moore lists parallel reproduction as an
open problem.[^21] Two
dimensions also force a problem that three do not: signal lines must sometimes cross,
which von Neumann solves by coding ([[coded-channel](pages/coded-channel.md)]).[^22]

**The topological view in one dimension.** Hedlund (1969) never uses the words
"cellular automaton". Read as a 1D CA (own reasoning), a configuration is a point of the
[[shift-dynamical-system](pages/shift-dynamical-system.md)] X(S): an infinite row of
cells with no finiteness condition. Translating by one cell is the shift σ, and a rule of
radius r is a block map on windows of 2r + 1 cells. The
[[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] says the
continuous, shift-commuting maps of X(S) are exactly these block maps composed with
shifts.[^23] This gives a definition of the global map with no mention of neighbourhoods,
and a global theory of all rules at once. That theory covers which rules are onto
([[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)]), which are
invertible ([[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)]),
and how many predecessors a configuration has.[^24]

**A physicist's view.** Wolfram describes cellular automata as idealized physical systems
in which space, time and the physical quantities are all discrete. The lattice is regular
and usually infinite. All cells update together ("synchronously") from their neighbourhoods
at the previous step.[^25] He counts "cellular spaces" (von Neumann and Ulam's term),
"tessellation automata", "homogeneous structures", "cellular structures", "tessellation
structures" and "iterative arrays" as names for the same idea. He proposes cellular
automata as models for spin systems, reaction-diffusion chemistry, crystal growth,
turbulence, biological pattern formation, and parallel computers. Finite differences turn
any differential equation into one, and nontrivial behaviour needs nonlinearity, such as
"growth inhibition".[^26] The simplest case, a line of two-state cells with nearest
neighbours, is the [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)].

**Neighbourhoods in d dimensions.** A *type-I* neighbourhood has the cell plus its 2d
orthogonal neighbours, which is von Neumann's five-cell neighbourhood when d = 2. A *type-II*
neighbourhood has all 3ᵈ cells within one step, orthogonal or diagonal, which is the
nine-cell Moore neighbourhood when d = 2. In one dimension the two coincide. Requiring
quiescence and the lattice's rotation and reflection symmetries, there are 2¹¹ = 2048
legal two-state type-I rules in 2D and 2⁵⁹ ≈ 6 × 10¹⁷ type-II rules.[^27] A rule is
*totalistic* if it depends only on the sum of the neighbourhood values. The
[[game-of-life](pages/game-of-life.md)] is a type-II totalistic rule.[^28]

**Computers or universes.** Langton distinguishes two ways to see computation in a
cellular automaton. The CA can *be* a computer, with the initial configuration as data
and the rule as algorithm. Or the initial configuration can *contain* a computer, with
the rule as the physics its parts obey, as in von Neumann's construction. With K states
and N neighbours there are K^(K^N) rules, and Langton orders this space with the
[[lambda-parameter](pages/lambda-parameter.md)] to ask which rules can support the second view
([[edge-of-chaos](pages/edge-of-chaos.md)]).[^29]

**The computer-science formalization.** Kari (2005) fixes the setting used in theoretical
computer science. A d-dimensional CA is a triple (S, N, f): a finite state set S, a
neighbourhood vector N of n distinct offsets in ℤᵈ, and a local rule f : Sⁿ → S. The
global map G sends a configuration c : ℤᵈ → S to the configuration whose value at x is f
applied to the states at x + x₁, …, x + xₙ. A CA is usually identified with G, but in
algorithmic questions it is always given by the three finite items S, N and f.[^30] A
quiescent state q must satisfy f(q, …, q) = q. A configuration is *finite* if only finitely
many cells are not quiescent, and *spatially periodic* if d independent translations fix
it. Both kinds are preserved by G, giving restrictions G_F and G_P. The three maps can
behave differently, so simulations with periodic boundary conditions "may be
misleading".[^31] Temporal notions are kept separate: c is *temporally periodic* if Gᵏ(c) =
c for some k ≥ 1, and every CA has a homogeneous temporally periodic configuration. It is
*eventually periodic* if its forward orbit is finite, and every spatially periodic
configuration is eventually periodic. The *phase space* is the infinite directed graph with
an edge from c to G(c). A CA is
*nilpotent* if all configurations end at one configuration after some fixed number of
steps ([[limit-set](pages/limit-set.md)]).[^32] Composing two CA gives a CA, and whether two
CA are equal is decidable.[^33] Which other properties can be decided is the subject of
[[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)].

**Read-only cells, and a write-access variant.** In the standard model a cell reads its
neighbours but only ever changes itself, so no two updates can conflict. Hoffmann's
[[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)]
drops this restriction to make moving agents easier to describe. A radius-1 version can
still be emulated by an ordinary CA of radius 2. In a
[[broadcasting-automaton](pages/broadcasting-automaton.md)], each cell's state sets how far
its messages reach, so neighbourhoods change from step to step. A CA extended with variable
neighbourhoods can simulate it.[^34][^35]

## Appearances in Sources

- [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] - signals and their speed limit; the 1-bit communication subclass
- [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] - broadcasting automata as a variable-neighbourhood relative
- [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] - the read-only principle, and the write-access variant that relaxes it
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - two views of computation; the size of rule space and an ordering for it
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - the formal triple (S, N, f); finite and periodic configurations; composition, equivalence, nilpotency
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
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - rules whose global map is invertible
- [[limit-set](pages/limit-set.md)] - what a rule can still produce after arbitrarily many steps
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - which properties of a rule are decidable, by dimension
- [[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)] - CA as topological dynamical systems
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Wolfram, Culik-Yu and Kurka classes
- [[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)] - a variant in which cells may write to neighbours
- [[broadcasting-automaton](pages/broadcasting-automaton.md)] - state-dependent transmission radii
- [[sequence-generation-by-cellular-automata](pages/sequence-generation-by-cellular-automata.md)] - programming with signals
- [[one-bit-communication-cellular-automaton](pages/one-bit-communication-cellular-automaton.md)] - a bandwidth-restricted subclass

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
[^18]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.343 — "A signal (wave) is an information flow that is described as a straight line in the space-time diagram. Note that any signal cannot propagate at speed more than one cell per one step."
[^19]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.26, 28-29 [synthesis] - Theorem 2 and its assumptions, including local action and the possibility of erasing
[^20]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.157-158 [synthesis] — editor: the cellular structure allows an indefinite amount of parallelism, but the self-reproducing automaton works like a serial digital computer with most organs normally quiescent
[^21]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.30 [synthesis] - how the steps of reproduction could go on in parallel rather than serially, as in the machines of Penrose, von Neumann, and Jacobson
[^22]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.190-191 [synthesis] — in 2D, communication channels must sometimes intersect; solved by the coded channel
[^23]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.323-325 [synthesis] — block maps f∞ with [f∞(x)]_i = f(x_i ⋯ x_(i+n−1)); Thm 3.1 (continuous, commute with σ); Thm 3.4 (Curtis, Hedlund, Lyndon): every continuous shift-commuting map is σ^m f∞
[^24]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.321, 326-334, 351 [synthesis] — the paper's program: onto maps E(S), automorphisms A(S), multiplicities of preimages
[^25]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.602 [synthesis] — "mathematical idealizations of physical systems in which space and time are discrete, and physical quantities take on a finite set of discrete values"; regular uniform lattice, usually infinite; variables "updated simultaneously ('synchronously')" from neighbourhood values at the preceding step
[^26]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.602-603 [synthesis] — introduced by von Neumann and Ulam as "cellular spaces"; also called tessellation automata, homogeneous structures, cellular structures, tessellation structures, iterative arrays; any system of differential equations may be approximated by finite differences and discrete variables; nontrivial cellular automata arise with nonlinearity such as "growth inhibition"; applications to Ising-type spin systems, chemical reaction-diffusion, dendritic crystal growth, turbulence, biology, parallel computation
[^27]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 and n.14 [synthesis] — type-I neighbourhood of 2d+1 sites, type-II of 3ᵈ sites; identical when d = 1; for d = 2 "known as von Neumann and Moore neighborhoods"; legality includes rotation and reflection invariance; 2¹¹ = 2048 type-I rules for k = 2; 2⁵⁹ ≈ 6 × 10¹⁷ type-II rules
[^28]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] — "totalistic" cellular automata depend only on the sum of neighbourhood values; Life is a type-II example
[^29]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.13-16 [synthesis] - Sec. 1.4: K^N neighbourhood states and K^(K^N) transition functions; Sec. 2.5: CAs "can be viewed either as computers themselves or as logical universes within which computers may be embedded"; on the second view "the transition function is seen as the 'physics' obeyed by the parts of this embedded computer"; "when is it possible - even necessary - to adopt the second point of view"
[^30]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.4-5 [synthesis] - configurations c : ℤᵈ → S; neighbourhood vector N = (x₁, …, xₙ); local rule f : Sⁿ → S; global transition function G; "A d-dimensional CA is specified by a triple (S, N, f)"; "In algorithmic questions G is, however, always specified using the three finite items S, N and f"
[^31]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.6-7 [synthesis] - quiescent state stable, f(q, q, …, q) = q; finite configurations C_F and G_F; periodic configurations invariant under d linearly independent translations, C_P and G_P; "experiments done with periodic boundary conditions may be misleading"
[^32]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.7 [synthesis] - temporally periodic configurations; every CA has a homogeneous temporally periodic configuration; eventually periodic iff the forward orbit is finite; "Every spatially periodic configuration is eventually periodic"; phase space as a directed graph; nilpotent if Gⁿ(C) is a singleton
[^33]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.7 [synthesis] - "The composition G₁ ∘ G₂ is also a CA function, and the composition can be formed effectively"; "The equivalence of two given CA G₁ and G₂ is decidable"
[^34]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.301, 306 [synthesis] — transmission radius dictated by the state, connectivity graph changes each step; variable-neighbourhood CA can simulate Broadcasting Automata, "it is only possible to say that BA ⊆ CA"
[^35]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.278, 283 [synthesis] — "CA and GCA do not allow to modify the state of a neighbor. Therefore no write-conflict can occur"; CA-w allows a cell to write to its neighbours; "the CA-w model with radius 1 can be emulated by a CA model with radius 2"
