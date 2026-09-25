---
title: Conserved Quantity (cellular automata)
category: Concepts
summary: An additive invariant of a cellular automaton - a sum over all cells of a locally computed number that the rule never changes; checking one is decidable and all of a given neighbourhood can be found (Hattori and Takesue), but whether a 1D rule has any non-trivial one is open, and in 2D undecidable
tags: [concept, conservation-law, additive-invariant, number-conservation, physics, decidability]
sources: [theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-24
---

# Conserved Quantity (cellular automata)

## Description

Reversible CA conserve information
([[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]). Physics has
other conservation laws, such as energy and momentum, that CA may obey. The [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] makes
such laws easy to build in.[^1] For example, if the block permutations never change the
number of black cells in a block, the number of black cells in every finite configuration
is conserved.[^2]

**Additive quantities.** Hattori and Takesue (1991) introduced additive conserved
quantities: invariants that are sums of numbers computed locally. Others found the same
ideas independently, and *number conservation* is a later special case (Boccara and
Fukś).[^3]

- *Range one.* Give each state a real weight μ(s), with μ(q) = 0 for the quiescent state.
  The value of a finite configuration is the sum of the weights of its cells. G conserves μ
  if every finite configuration has the same value as its image.[^4]
- *General.* Use a neighbourhood vector of its own, which need not be the CA's, and a
  density function μ : Sⁿ → ℝ with μ(q, …, q) = 0. Apply μ at every cell and sum.[^5]

The reals can be replaced by any abelian group, and quantities conserved only by some
power Gᵗ can also be considered. The definition works equally with periodic
configurations, summing over one period. The finite and periodic definitions are
equivalent.[^6]

**Testing is decidable.** It is enough to check that changing a single cell changes the
total by the same amount before and after G is applied, since any finite configuration can
be reached from any other by single-cell changes. Only a finite region around the changed
cell matters, so finitely many checks suffice. For a fixed neighbourhood, the conserved
density functions form a vector space that can be computed. So: **one can decide whether a
given quantity is conserved, and find every conserved quantity with a given neighbourhood**
(Hattori and Takesue).[^7] This matters for modelling. A model that conserves the wrong
quantities obeys the wrong conservation laws, and the results can be wrong.[^8]

**Trivial quantities.** Some quantities are conserved by every CA because every finite
configuration has value 0. In 1D with two states and neighbourhood (0, 1), the density
μ(01) = 1, μ(10) = −1, μ(00) = μ(11) = 0 is one: along a finite configuration, 01 and 10
boundaries alternate and cancel.[^9] A quantity is *trivial* if it gives every finite
configuration the value zero.

**Open in 1D, undecidable in 2D.** With the neighbourhood unrestricted, Kari asks whether
it is decidable if a 1D CA has *any* non-trivial conserved quantity, and whether all of
them can be found.[^10] In 2D the question is undecidable, by reduction from the finite
tiling problem ([[wang-tiles](pages/wang-tiles.md)]). Build the CA that keeps a cell's
tile when the tiling is valid there and otherwise sets it blank. It has a non-trivial
conserved quantity iff a non-trivial valid finite tiling exists.[^11]

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §5, Theorem 12, Open problem 4

## Related Concepts

- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - conservation of information
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - conservation built into block permutations
- [[wang-tiles](pages/wang-tiles.md)] - the 2D undecidability
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the other decision problems
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - the statistical-physics side of CA modelling
- [[rule-184](pages/rule-184.md)] - the traffic rule conserves the number of particles

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.21 [synthesis] - "Reversible CA preserve information. There are also other conservation laws in physics that CA may obey, e.g. conservation of energy, momentum, etc. The Margolus neighborhood is a particularly useful tool in programming conservation laws into CA."
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 [synthesis] - "the number of black cells in finite configurations is automatically preserved if the permutations are such that they conserve black states"
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.21 [synthesis] - Hattori and Takesue [32] introduced additive conserved quantities, "invariants of the CA evolution that are obtained as sums of locally computed numerical values"; discovered independently, e.g. [9]; number conservation introduced in [8]
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.21 [synthesis] - range-one additive quantity μ : S → ℝ with μ(q) = 0, extended by summing over all cells; G conserves μ if μ̂(G(c)) = μ̂(c) for all finite c
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.21 [synthesis] - general additive quantity: a neighbourhood vector N and density function μ : Sⁿ → ℝ; "the neighborhood vector is not the same as the neighborhood vector of the CA under consideration"; μ(q, …, q) = 0
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.21 [synthesis] - replace ℝ by any abelian group; conserved quantities of Gᵗ; staggered invariants [63]; periodic definition summing over one period; "Definitions using finite and periodic configurations are equivalent."
[^7]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.21-22 [synthesis] - the single-cell-change test; finitely many configurations suffice; conserved density functions form a vector space whose orthogonal complement is easily found; Theorem 12 (Hattori and Takesue)
[^8]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.22 - "incorrect conserved quantities in the model mean that the model obeys incorrect conservation laws that may affect the simulation results."
[^9]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.22 [synthesis] - d = 1, N = (0, 1), S = {0, 1}, μ(01) = 1, μ(10) = −1, μ(00) = μ(11) = 0 "assigns value 0 to all finite configurations and is therefore conserved by every CA"; definition of trivial. The alternation of boundaries is own reasoning
[^10]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.22 - "Open problem 4. Is there an algorithm to determine if a given one-dimensional CA has any non-trivial conserved quantities? Is there an effective method to find all conserved quantities of a given one-dimensional CA?"
[^11]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.22 [synthesis] - 2D undecidable by reduction from the finite tiling problem: keep the state if the tiling is valid at the cell, otherwise alter it to B; "a non-trivial conserved quantity exists if and only if a non-trivial valid finite tiling exists"
