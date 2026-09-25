---
title: De Bruijn Graph
category: Concepts
summary: The finite graph whose vertices are the length-(w-1) words of a 1D rule of width w and whose edges are the length-w windows - labelled by the rule, it becomes an automaton recognizing "y is the image of x", the basis of the quadratic 1D algorithms for injectivity, surjectivity and openness
tags: [concept, de-bruijn, automata, decidability, one-dimensional, sutner]
sources: [aucm-ch12-linear-cellular-automata-and-decidability, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-24
---

# De Bruijn Graph

## Description

For a 1D rule ρ of odd width w = 2r + 1, the automaton A_ρ(x, y) reads two configurations
at once, as a word over the two-track alphabet Σ². It accepts iff y is obtained from x by
applying ρ to every window. Its states hold the last 2r symbols of x and the last r symbols
of y. A transition on the letter a:b appends a to the x-part and b to the y-part. It is
allowed only when ρ applied to the old x-part followed by a gives the oldest symbol of the
y-part, which is then dropped. So A_ρ is the complete de Bruijn automaton of order 2r over
Σ², with every edge that does not agree with ρ removed.[^1] For an additive rule such as
rule 150, every edge survives and the automaton is the full de Bruijn graph.[^2]

**Boundary conditions.** On bi-infinite configurations every state is both initial and
final, so A_ρ accepts exactly when a bi-infinite path exists, and no boundary cases
arise.[^3] On finite grids, extra initial and final states stand for the phantom cells
outside the grid.[^4]

**Algorithms built on it.** Combining copies of A_ρ decides first-order properties of the
rule ([[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]).
For injectivity on finite grids, two copies test x → z and y → z, and a third part checks
x ≠ y. Emptiness can then be tested in time linear in the automaton, whose size is
quadratic in the rule table.[^5] On bi-infinite configurations the same idea gives
Sutner's quadratic algorithms for injectivity, surjectivity and openness of the global
map.[^3] Kari cites these as the cleaner successors of Amoroso and Patt's 1972 decision
procedures ([[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]).[^6]

(Own reasoning: this is why such questions are decidable in one dimension. A rule's
behaviour on a line is captured by paths in one finite graph. No such graph exists in 2D,
where the same questions are undecidable
([[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)]).)

## Appearances in Sources

- [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] - the construction of A_ρ, the rule-150 example, boundary conditions
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - Sutner's de Bruijn algorithms for 1D injectivity and surjectivity

## Related Concepts

- [[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)] - built from products of this automaton
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the 1D decision procedures
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - 1D injectivity decided on the graph
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - 1D surjectivity
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] - additive rules keep every edge

[^1]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.263 [synthesis] — two-track words X:Y ∈ (Σ²)ⁿ ("convolution"); width w = 2r + 1; A_ρ(x, y) has state set Σ^{2r} × Σ^r with transitions ⟨a1 … a2r ; b1 … br⟩ —a:b→ ⟨a2 … a2r a ; b2 … br b⟩ "provided that ρ(a1, …, a2r, a) = b1"; "a subautomaton of the complete de Bruijn automaton over Σ² of order 2r: we remove all the directed edges ... that do not conform to ρ"
[^2]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.263-264 (Fig. 12.1) — "Note that the underlying CA is the additive rule 150, as a consequence the automaton uses the full de Bruijn graph."
[^3]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.268 [synthesis] — bi-infinite case: "in the basic de Bruijn automata all states are initial and final, so that A_ρ(x, y) accepts its input if there is a bi-infinite computation: no complications arise from boundary conditions ... This was used in [44] to give simple quadratic algorithms to test for injectivity, surjectivity and openness of the global map."
[^4]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.263 [synthesis] — fixed boundary conditions: initial states of indegree 0 and final states of outdegree 0 representing the phantom cells
[^5]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.263-264 [synthesis] — injectivity via the 3-track product of A_ρ(x, z), A_ρ(y, z) and an inequality test; "this last step can be handled in time linear in the size of A, which size is quadratic in the size of the lookup table for the local map"
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.19-20 [synthesis] - Sutner's de Bruijn graph algorithms for injectivity and surjectivity of 1D CA, after Amoroso and Patt
