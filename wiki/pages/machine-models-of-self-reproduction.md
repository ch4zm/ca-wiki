---
title: "Machine Models of Self-Reproduction (Moore, 1962)"
category: Sources
summary: Moore's survey and formalization of self-reproducing machines - Penrose's and Jacobson's kinematic models, "tessellation structures" with a 9-cell neighbourhood, a formal definition of self-reproduction, the kT² bound on offspring, and the Garden-of-Eden theorem (erasable configurations imply Garden-of-Eden configurations)
tags: [moore, self-reproduction, garden-of-eden, erasable-configuration, tessellation, kinematic-model, penrose]
sources: [machine-models-of-self-reproduction]
created: 2026-09-24
updated: 2026-09-24
---

# Machine Models of Self-Reproduction (Moore, 1962)

**Source:** raw/bellman-mathematical-problems-biological-sciences.pdf, printed pp. 17-33 (PDF pp. 26-42). Moore, E. F. (1962). Machine models of self-reproduction. In R. E. Bellman (Ed.), *Mathematical problems in the biological sciences* (Proc. Symp. Appl. Math., Vol. 14, pp. 17-33). American Mathematical Society. http://dx.doi.org/10.1090/psapm/014/9961
**Date ingested:** 2026-09-24
**Type:** paper (symposium proceedings chapter)

## Summary

[[edward-f-moore](pages/edward-f-moore.md)], at Bell Telephone Laboratories, writes before von Neumann's cellular manuscript was
published. He knows it from one lecture series he attended, from reading, and from
hearsay.[^1] He first surveys *kinematic* models that had actually been built. Jacobson
built a model railroad whose trains assemble copies of themselves from cars. Penrose made
rigid A and B units that, shaken in a box with an AB "seed", hook together into more AB
machines ([[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)]).[^2]

He then formalizes von Neumann's cellular model
([[tsra-part2-ch1](pages/tsra-part2-ch1.md)]) under the name **tessellation structure**:
a lattice of identical, deterministic, synchronous finite-state cells with a quiescent
state and finitely many non-quiescent cells ([[cellular-automaton](pages/cellular-automaton.md)]).[^3]
His neighbourhood is the nine-cell square around a cell, now called the
[[moore-neighbourhood](pages/moore-neighbourhood.md)].[^4] On this base he defines
*copy*, *contains n copies*, and *self-reproducing configuration*: a configuration that,
started alone at time 0, eventually yields any number of disjoint copies of itself
([[self-reproduction](pages/self-reproduction.md)]).[^5] The definition admits trivial
cases, and he shows that the number of offspring can grow at most quadratically in time
(Theorem 1).[^6]

The main result is Theorem 2. If a tessellation structure has an
[[erasable-configuration](pages/erasable-configuration.md)], meaning two different
patterns that become indistinguishable after one step, then it has
[[garden-of-eden](pages/garden-of-eden.md)] configurations, which have no predecessor and
can occur only at time 0. The proof is a counting argument. Erasures lose states in
proportion to the area of a large block, while information leaking across the boundary
grows only with its perimeter, so some pattern of the block can never be reached.[^7] No
self-reproducing configuration can contain a Garden-of-Eden pattern, so the theorem is a
limit on what machines can build.[^8] [[john-myhill](pages/john-myhill.md)] later proved the
converse, completing the [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]
([[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)]).

## Key Takeaways

- **Three kinds of "machine".** The tessellation is the universe, a configuration is the
  machine that reproduces, and a cell is an elementary part. Moore traces Rosen's claimed
  paradox of self-reproduction to confusing the tessellation with the configuration.[^9]
- **A formal definition.** A configuration c is self-reproducing if for every n there is a
  time by which the non-quiescent region contains at least n disjoint copies of c.[^5]
- **Trivial reproducers exist.** In a two-state rule where a cell turns X when any
  neighbour is X, a single X cell counts as self-reproducing. Moore calls this "more nearly
  a model of crystal growth". Von Neumann avoided triviality by requiring a universal Turing
  machine in each configuration.[^10]
- **No exponential growth (Theorem 1).** Offspring by time T are fewer than kT². The
  non-quiescent region grows by at most one cell per step in each direction, a finite
  "velocity of light". In N dimensions the bound is kT^N.[^6]
- **Garden-of-Eden theorem (Theorem 2).** Erasable configurations imply Garden-of-Eden
  configurations. The name was suggested by John W. Tukey, and the statement and proof idea
  by Shannon.[^7][^11]
- **Six assumptions.** Homogeneity, discrete space and time, local action, Euclidean
  space, determinism, and the possibility of erasing. Erasing is essential. Moore notes that
  erasing violates Newtonian mechanics but not quantum mechanics, and determinism the
  reverse.[^12]
- **Open problems.** How small a Garden-of-Eden pattern can be (every structure Moore
  examined had one of size 5 × 5 or less); whether self-reproduction is possible without
  erasability; how simple a structure can support non-trivial self-reproduction
  ([[complexity-threshold](pages/complexity-threshold.md)]); and how
  reproduction could run in parallel rather than one part at a time.[^13]

## Entities & Concepts

- [[garden-of-eden](pages/garden-of-eden.md)]
- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]
- [[edward-f-moore](pages/edward-f-moore.md)]
- [[erasable-configuration](pages/erasable-configuration.md)]
- [[moore-neighbourhood](pages/moore-neighbourhood.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]
- [[self-reproduction](pages/self-reproduction.md)]
- [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]

## Relation to Other Wiki Pages

Moore's reference [16], "The theory of automata: Construction, reproduction, and
homogeneity", is the manuscript Burks later published as Part II of
[[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)], and
his [15], the five lectures of December 1949, became Part I.[^14][^15]
Moore notes that von Neumann's rule uses only the five orthogonal cells, which fits inside
his nine-cell scheme ([[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]).[^4]
The Garden-of-Eden theorem sharpens the non-constructibility discussed in
[[tsra-part2-ch5](pages/tsra-part2-ch5.md)] and
[[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)]. Moore's call for
parallel reproduction matches the serial character of von Neumann's design noted on
[[cellular-automaton](pages/cellular-automaton.md)].[^13]

[^1]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.17 - "I heard only one series of the later lectures, but by reading and by hearsay I am acquainted with the ideas of some of the others."
[^2]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.18-20 [synthesis] - Jacobson's model railroad, with relay logic on the cars; Penrose's basic model of A and B units that, shaken with an AB or BA seed, build more copies of it; no "spontaneous generation" without a seed except under unusual force; Morowitz's proposed electromagnet model, not built
[^3]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.17-18, 21 [synthesis] - square cells each holding one copy of a deterministic, synchronous finite-state machine; a quiescent state that persists when all neighbours are quiescent; all but finitely many cells quiescent; the whole system "will be called a tessellation structure"; formally a quintuple (N, T, S, q₀, f)
[^4]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.21 [synthesis] - neighbours are all cells (including the cell itself) whose coordinates differ by at most 1, nine cells in Fig. 2; von Neumann's construction uses only the five cells V and X, which is included by making f independent of the D cells
[^5]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.22 [synthesis] - definitions of copy (a translate with the same states), containing n copies (n disjoint subsets that are copies), capable of reproducing n offspring by time T, and self-reproducing configuration (for each n some T)
[^6]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.23 [synthesis] - Theorem 1, f(T) < kT²; the non-quiescent region is at most (2T + D)² cells; the bound rests on a finite velocity of propagation, "roughly to a physical limitation such as a finite velocity of light"; kT^N in N dimensions
[^7]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23, 26-28 [synthesis] - Garden-of-Eden configuration defined, term suggested by John W. Tukey; Theorem 2, "For a tessellation structure for which there exist erasable configurations, there exist Garden-of-Eden configurations"; kn × kn block argument with loss due to erasure growing with k² and boundary loss with k
[^8]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23-24 - "no self-reproducing configuration can contain a copy of a Garden-of-Eden configuration. Hence an investigation of the conditions under which they can occur throws light on the limitations of the ability of machines to reproduce themselves."
[^9]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.20 [synthesis] - three things can be called machines: the tessellation (environment), the configuration (the self-reproducer), the cell (elementary part); Rosen's alleged paradox arises from failing to distinguish tessellation and configuration
[^10]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.22-23 [synthesis] - two-state X/0 rule where a cell becomes X if any neighbour was X; one X cell is self-reproducing, "more nearly a model of crystal growth than of self-reproduction"; von Neumann required each configuration to contain a universal Turing machine
[^11]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.31 [synthesis] - acknowledgement to Shannon, "whose suggestions led to the statement of Theorem 2 and the basic idea for the method of proving it"; Pollak, Gilbert, and Kruskal simplified inequality (1)
[^12]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.28-29 [synthesis] - the six assumptions and the role of each; (6) is vital and one of the paper's structures is a counterexample without it; "Assumption (6) violates Newtonian mechanics but not quantum mechanics. However, assumption (5) violates quantum mechanics but not Newtonian mechanics."
[^13]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.29-30 [synthesis] - further problems: a partial order of triviality; complexity needed for the origin of life; smallest Garden-of-Eden array (5 × 5 or smaller in every structure examined); simplest structure with non-trivial self-reproduction; self-reproduction without erasability; fraction of n-state structures with erasable configurations; one-cell inner arrays; parallel rather than serial reproduction
[^14]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.18, 32 [synthesis] - von Neumann's tessellation work unfinished at his death, publication planned [16]; bibliography entry 15, typescript of five lectures delivered in December 1949, and entry 16, uncompleted typescript of three chapters (circa 1952), to be published by the Univ. of Illinois Press
[^15]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xv [synthesis] - the Illinois lectures of December 1949 are Part I and the manuscript begun in fall 1952 is Part II
