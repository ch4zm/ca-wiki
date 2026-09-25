---
title: "Automata, Universality, Computation — Ch. 14: Broadcasting Automata and Patterns on Z²"
category: Sources
summary: Nickson and Potapov's broadcasting automata - finite machines on the square lattice whose state sets a Euclidean transmission radius - and the geometry of their waves - discrete discs as generalized von Neumann/Moore neighbourhoods, chain-code characterization and linear-time composition of discs, the gradients that can never appear, and moiré aggregation of two wave trains that yields non-convex shapes and an approximate astroid
tags: [broadcasting-automata, neighbourhood-sequences, digital-geometry, discrete-discs, chain-codes, waves, moire, nickson, potapov]
sources: [aucm-ch14-broadcasting-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Automata, Universality, Computation — Ch. 14: Broadcasting Automata and Patterns on Z²

**Source:** assets/adamatzky-2015-automata-universality-computation.pdf, printed pp. 297–339 (PDF pp. 301–343)
**Date ingested:** 2026-09-24
**Type:** book chapter (model and results)
**Authors:** Thomas Nickson and Igor Potapov
**Part of:** [[automata-universality-computation](pages/automata-universality-computation.md)]

## Summary

A [[broadcasting-automaton](pages/broadcasting-automaton.md)] is a finite-state machine
placed at a point of a metric space, here the square lattice ℤ². Its current state sets a
transmission radius, and each message it sends reaches every automaton within that
Euclidean distance, as in an ad-hoc radio network. The communication graph can therefore
change at every step.[^1] Computation proceeds by *waves*: messages relayed outward from a
source, with each automaton labelling itself by the step at which the wave arrived.[^2]

The chapter studies the shapes these waves make. A single broadcast of radius r reaches a
*discrete disc*. Radius² = 1 gives the von Neumann neighbourhood and radius² = 2 the
[[moore-neighbourhood](pages/moore-neighbourhood.md)], so broadcasting sequences
generalize the neighbourhood sequences of digital geometry
([[neighbourhood-sequence](pages/neighbourhood-sequence.md)]).[^3] Using chain codes, the
authors characterize the sides of discrete discs and give a linear-time algorithm for
composing them. They show that repeated broadcasting can never produce certain side
gradients, and that it only ever produces convex shapes.[^4] Aggregating two broadcast
sequences through a combining table gets around both limits. It produces new gradients and
non-convex polygons, including an approximation of the astroid, a concave L_p shape that
neighbourhood sequences cannot reach.[^5]

## Key Takeaways

- **Model.** BA = ((M, d), A, C₀). A extends a Moore machine with final states and a radius
  function τ: Q → ℝ. The messages received at u are Γ_u = {Δ(c(v)) | d(u, v) ≤ τ(c(v))}.
  Messages arrive as a set, so multiplicities are lost.[^6] Synchronous and asynchronous
  versions can simulate each other (Proposition 1).[^7]
- **Relation to CA.** A CA whose neighbourhoods can vary in size can simulate a
  broadcasting automaton, so the authors claim BA ⊆ CA but not the reverse.[^8]
- **Discrete discs.** The distinct discs on ℤ² come from the values of r² that are sums of
  two squares (OEIS A001481).[^9] Discs of radius² 1 and 2 are the diamond and square waves
  of the von Neumann and Moore neighbourhoods.[^10]
- **Sides of a disc.** In the first octant, a disc's boundary is a word over {0, 1}. Every
  side (line segment) has one of the forms (10ⁿ)*, (10ⁿ)(10ⁿ⁺¹)*, or (10ⁿ)*(10ⁿ⁺¹)
  (Theorem 1).[^11]
- **Composition.** Broadcasting disc u and then disc v covers the Minkowski sum of the two
  discs. Its chain code is obtained by merging the sides of u and v in order of gradient
  (Theorem 3). This is commutative and takes linear time.[^12] It is decidable whether a
  finite sequence of radii composes to a shape similar to a given convex polygon, by
  solving linear Diophantine equations (Theorem 4).[^13]
- **Missing gradients.** Every side gradient has the reduced form 1/n, a/(a(n+1) − 1) or
  a/(an + 1). So there are infinitely many rational gradients that never appear, 5/8 for
  example (Propositions 5-6).[^14] Composition makes no new gradients, so the set of sides
  is closed under it (Corollary 2).[^15]
- **Aggregation.** Label each cell by its arrival step mod 4 in two broadcast sequences.
  Then combine the two labels with a table: *moiré* (which depends on the difference of the
  labels) or *anti-moiré* (addition mod 4). The new lines have gradients
  (w₀m₁ − w₁m₀)/(w₀ − w₁) and (w₀m₁ + w₁m₀)/(w₀ + w₁), where the mᵢ are the gradients and
  the wᵢ the widths of the original wave fronts. Varying the widths varies the gradient,
  and the resulting polygons can be non-convex.[^16]
- **Astroid.** The astroid x^(2/3) + y^(2/3) = r^(2/3) (the L_(2/3) shape) cannot come from
  von Neumann and Moore sequences, since those produce only convex shapes. Moiré
  aggregation of discs of radius² 2 and 5 gave the best experimental approximation, and the
  fit worsens as k grows. The evidence is experimental only.[^17]

## Patterns

Aggregation tables can themselves be pictures. With two sources broadcasting radius² 8, a
table shaped like the radius²-5 disc is reproduced exactly in parts of the lattice. With
radii² 26 and 36 the same table appears skewed. Changing the table, the colours or the
radii reshapes the pattern while keeping its overall form. The authors suggest uses in
pattern formation for swarm robotics.[^18] Earlier work by the same group used such
standing-wave patterns to partition a cluster of robots and to find the centre of a digital
disc.[^19]

## Entities & Concepts

- [[broadcasting-automaton](pages/broadcasting-automaton.md)]
- [[neighbourhood-sequence](pages/neighbourhood-sequence.md)]
- [[moore-neighbourhood](pages/moore-neighbourhood.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]

## Relation to Other Wiki Pages

The von Neumann and Moore neighbourhoods of
[[moore-neighbourhood](pages/moore-neighbourhood.md)] are the first two discrete discs
here. They are the unit balls of the L1 and L∞ distances, which the chapter calls city
block and chessboard.[^20] The region a single cell can influence after t steps of a CA is the
t-fold sum of its neighbourhood. For the von Neumann and Moore neighbourhoods, that is the
same diamond and square that the waves here trace (own reasoning, extending the
finite-speed bound on [[cellular-automaton](pages/cellular-automaton.md)]).

[^1]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.300-301 [synthesis] — "we introduced in [19] a new model of Broadcasting Automata, which can be seen as a network of finite automata with a dynamic network topology"; connectivity depends on the distances between points and the transmission strengths, as in ad-hoc radio networks; "the topology, or connectivity graph, of the network of automata is able to change at each time step based on the states of the automata"
[^2]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.298, 310 [synthesis] — wave algorithms: "messages passed from automata to automata throughout the topology, to construct computations"; points reached at successive applications of the sequence are labelled 0, 1, …, modulo m
[^3]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.307, 309 [synthesis] — radius 1 reaches four of the eight neighbours, radius √2 all eight: "Such structures are identical to the well studied neighbourhoods von Neumann and Moore"; von Neumann and Moore "can be described as the first two radii in the set of distinct discrete discs, r² = 1 and r² = 2"; discrete discs as "a natural extension to the basic notion of neighbourhood sequences"
[^4]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.299, 322-323 [synthesis] — characterization of the shapes of polygons produced by broadcasting sequences, a linear-time composition algorithm, "an infinite number of gradients ... that cannot be produced by Broadcasting Sequences"; shapes "limited by their convexity as well as by the gradients of the lines that compose them"
[^5]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.299, 326-328 [synthesis] — aggregation of two broadcasting sequences with moiré and anti-moiré functions produces new gradients and non-convex polygons; approximation of "astroids, a previously unachievable concave metric"
[^6]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.300-302 [synthesis] — Definition 4: A = (Q, Σ, Λ, δ, Δ, τ, q₀, F) with τ: Q → ℝ the radius of transmission; Definition 5: BA = ((M, d), A, C₀); Definition 7: Γ_u = {Δ(c(v)) | v ∈ M ∧ d(u, v) ≤ τ(c(v))}; "all transitions must operate upon a set of distinct symbols"
[^7]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.305-306 — "Proposition 1. [20] Both the synchronous and asynchronous models are able to simulate the other."
[^8]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] p.306 [synthesis] — with variable-radius neighbourhoods "the Cellular Automata (CA) model may also be used to simulate the Broadcasting Automata model"; "This does not mean however that there is an exact translation of Cellular Automata in to Broadcasting Automata and as such it is only possible to say that BA ⊆ CA."
[^9]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.307-308 [synthesis] — distinct discs defined by "the numbers n such that n = x² + y² has a solution in non-negative integers x, y [26]"; [26] = OEIS A001481, numbers that are the sum of 2 nonnegative squares
[^10]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] p.307 (Fig. 14.4) — "Diagram a) represents the propagation pattern for a diamond wave (Von Neumann neighbourhood) and diagram b) shows the propagation pattern for a square wave (Moore neighbourhood)."
[^11]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.313, 316 [synthesis] — Lemma 1: a chain coding for the circle in the first octant is a word in {0, 1}*; Lemma 2: no line segment of the form 10ⁿ10ⁿ⁺¹10ⁿ⁺²…; Theorem 1: "Any line segments on the discrete circle with non-negative gradients should be in one of the following forms (10ⁿ)*, (10ⁿ)(10ⁿ⁺¹)*, (10ⁿ)*(10ⁿ⁺¹)"
[^12]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.317-322 [synthesis] — Definition 24: ζ ∘ ζ′ = {a + b | a ∈ ζ, b ∈ ζ′}; Theorem 2: composition is commutative; Theorem 3 (Composition Theorem): combine the line segments of u and v "and ordering them by increasing gradient", related to the Minkowski sum of convex polygons; Proposition 4: linear time; Example 2: ζ45 = 0001, ζ9 = 01, ζ45 ∘ ζ9 = 000101
[^13]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] p.322 [synthesis] — Theorem 4: given a finite broadcasting sequence and a convex polygon P, "it is decidable whether there are radii such that the chain coding of the composition of is similar to P"; proof by representing discs as gradient-count vectors and solving "a system of linear Diophantine equation over positive integers"
[^14]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.322-323 [synthesis] — gradients G1 = 1/n, G2 = (m+1)/(n + m(n+1)), G3 = (m+1)/(nm + n + 1); Proposition 5: reduced forms 1/n, a/(a(n+1) − 1), a/(an + 1); Proposition 6: "It is impossible to express any such rational of the form 5/8"
[^15]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] p.323 — "Corollary 2. The set of line segments, and as such gradients, that compose any discrete circle are closed under composition."
[^16]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.324-326 [synthesis] — two labellings mod m from the same point; Definition 26 (moiré table) and Definition 27 (anti-moiré, "addition over modulo 4"); Proposition 7: gradient (w₀·m₁ − w₁·m₀)/(w₀ − w₁); Proposition 8: (w₀·m₁ + w₁·m₀)/(w₀ + w₁); Proposition 9: varying the widths changes the gradient; "new polygons may now be formed with this technique such that they are non-convex"
[^17]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.328-334 [synthesis] — barrier: "the impossibility of constructing any non-convex polygon from the composition of the two convex polygons which represent the Moore and von Neumann neighbourhoods"; astroid x^{2/3} + y^{2/3} = r^{2/3}, L_{2/3}; moiré aggregation f(A_i, B_j) = |i − j|; "only experimental data shall be given here"; best approximation with B the disc of squared radius 5 (A of squared radius 2); "the approximation weakens as it increases"
[^18]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.334-337 [synthesis] — aggregation functions shaped like the radius²-5 disc; two sources of radius² 8 give "in some sections of the lattice, a perfect reproduction of the shape given in the aggregating function"; radii 26 and 36 skew and deform it "whilst retaining the gestalt representation"; possible use in "pattern recognition and detection methods that are part of the Swarm Robotics cannon"
[^19]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.298-299 [synthesis] — the standing wave as "a powerful tool for partitioning a cluster of robots on a non-oriented grid"; distributed algorithms "for the problem of finding the centre of a digital disk of broadcasting automata" [19]
[^20]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.298, 328 [synthesis] — cityblock motion: horizontal and vertical moves only; chessboard: diagonal moves allowed (footnote 1); "the Moore neighbourhood, L∞, the von Neumann neighbourhood, L1, and the Euclidean metric, L2"
