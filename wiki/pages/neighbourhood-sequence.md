---
title: Neighbourhood Sequence
category: Concepts
summary: Digital geometry's repeated application of neighbourhoods to a lattice - von Neumann (L1 diamond) and Moore (L∞ square) mixtures approximate Euclidean distance; broadcasting sequences extend them to any Euclidean radius, whose discrete discs have chain-code-characterized sides, compose by merging sides in gradient order, and can never produce certain gradients or any non-convex shape without aggregation
tags: [concept, neighbourhood-sequences, digital-geometry, discrete-discs, chain-codes, metrics, minkowski-sum]
sources: [aucm-ch14-broadcasting-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Neighbourhood Sequence

## Description

**Neighbourhood sequences.** Points p, q ∈ ℤⁿ are *M-neighbours* if every coordinate
differs by at most 1 and the coordinates differ by at most M in total. A neighbourhood
sequence A = (a(1), a(2), …) says which M-neighbourhood to use at each step. The
A-distance d(p, q; A) is the length of the shortest path that follows the sequence, and
A_k is the set of points within A-distance k of the origin.[^1] In 2D, M = 1 is the von
Neumann neighbourhood, whose unit ball is the L1 diamond ("city block"), and M = 2 is the
[[moore-neighbourhood](pages/moore-neighbourhood.md)], whose unit ball is the L∞ square
("chessboard").[^2] Each deviates badly from Euclidean distance on its own. Periodic
mixtures of the two, such as the octagonal distance, do better, and approximating the
Euclidean circle is a central topic of the field.[^3]

**Broadcasting sequences.** Points are *r-neighbours* if their Euclidean distance is at most
r. A *broadcasting sequence* R = (r₁, …, r_l) applies these radii periodically, as a
[[broadcasting-automaton](pages/broadcasting-automaton.md)] does when it relays a wave.
The first two distinct *discrete discs* {(x, y) | x² + y² ≤ r²} are radius² 1 and 2, the
von Neumann and Moore neighbourhoods. The distinct discs are indexed by the values of r²
that are sums of two squares.[^4]

**Chain codes of discs.** A disc's boundary can be encoded as a chain code, a word of moves
in 8 directions (Freeman). In the first octant only the moves 0 (along x) and 1 (a
diagonal step) occur. The code breaks into *chain code segments* 0^k and 10^k, and those
group into *line segments*, the polygon's sides, whose gradients increase along the
octant.[^5] Every side has the form (10ⁿ)*, (10ⁿ)(10ⁿ⁺¹)*, or (10ⁿ)*(10ⁿ⁺¹).[^6]

**Composition.** Following disc u with disc v covers the Minkowski sum
{a + b | a ∈ ζ_u, b ∈ ζ_v}. Its chain code merges the sides of u and v in order of gradient,
as the Minkowski sum of convex polygons does. The merge takes linear time and is
commutative.[^7] The authors suggest that composition might form an Abelian group, with the
radius-0 disc as identity, but closure is unknown.[^8] Given a finite set of radii and a
convex polygon P, whether some composition is similar to P is decidable, through linear
Diophantine equations over the counts of each gradient.[^9]

**What composition cannot do.** Side gradients have the reduced forms 1/n, a/(a(n+1) − 1)
or a/(an + 1). So infinitely many rational gradients, 5/8 for example, never occur.[^10]
Composition adds no new sides, and every shape it produces is convex. So no mixture of von
Neumann and Moore steps can approximate a concave L_p shape such as the astroid (p = 2/3).[^11]

**Aggregation.** Two broadcasting sequences from the same source give every cell a pair of
arrival labels mod m. A combining table (*moiré*, or *anti-moiré*, which is addition mod 4)
turns the pair into one colour. The boundaries between colours have new gradients,
(w₀m₁ ∓ w₁m₀)/(w₀ ∓ w₁), which change with the widths wᵢ of the wave fronts. Non-convex
shapes appear, and moiré aggregation of radius² 2 and 5 approximates the astroid in
experiments.[^12]

## Appearances in Sources

- [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] - M-neighbours, broadcasting sequences, chain-code theorems, composition, aggregation, the astroid

## Related Concepts

- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the von Neumann and Moore neighbourhoods as the first two discrete discs
- [[broadcasting-automaton](pages/broadcasting-automaton.md)] - the model whose waves these sequences describe
- [[cellular-automaton](pages/cellular-automaton.md)] - repeated neighbourhoods bound how far a cell's influence spreads

[^1]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.308-309 [synthesis] — Definition 11 (M-neighbours: |Pr_i(p) − Pr_i(q)| ≤ 1 for all i and Σ|Pr_i(p) − Pr_i(q)| ≤ M); neighbourhood sequence A = (a(i)); Definition 12 (A-distance, shortest A-path); Definition 13 (A_k = {p : d(0, p; A) ≤ k})
[^2]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.298, 307, 328 [synthesis] — "The cityblock motion allows movements only in horizontal and vertical directions, while the chessboard allows to move in diagonal directions"; diamond wave (von Neumann), square wave (Moore) in Fig. 14.4; "the Moore neighbourhood, L∞, the von Neumann neighbourhood, L1"
[^3]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.298, 328 [synthesis] — "In 2D the distances based on cityblock and chessboard neighbourhood sequences deviate quite substantially from the ideal Euclidian distances, so instead their combination that form 'the octagon' was more often employed"; approximating the Euclidean metric "has been one of the main studies with regards to neighbourhood sequences"
[^4]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.307-310 [synthesis] — Definition 16 (r-neighbours); broadcasting sequences R = (r₁, r₂, …, r_l); von Neumann and Moore as "the first two radii in the set of distinct discrete discs, r² = 1 and r² = 2"; Definition 23 (discrete disc); distinct discs from n = x² + y²
[^5]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.310-315 [synthesis] — chain coding from Freeman [10]; Definition 17; Lemma 1: first-octant code in {0, 1}*; Definition 19 (chain code segment 0^{|s₀|} or 10^{|s_i|−1}); Definition 20 (gradient #₁(u)/|u|); Definition 21 (line segment, increasing gradient)
[^6]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] p.316 — "Theorem 1. Any line segments on the discrete circle with non-negative gradients should be in one of the following forms (10ⁿ)*, (10ⁿ)(10ⁿ⁺¹)*, (10ⁿ)*(10ⁿ⁺¹)."
[^7]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.317-322 [synthesis] — Definition 24 (ζ ∘ ζ′ = {a + b | a ∈ ζ, b ∈ ζ′}); Lemma 3; Theorem 2 (commutative); Theorem 3 (Composition Theorem: order the line segments by gradient; "a similar result about the Minkowski sum [25] of convex polygons"); Proposition 4 (linear time)
[^8]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] p.320 — "it may be possible that it is an Abelian group, where the identity element is simply the circle of radius 0 ... However, it is currently unknown whether or not the operation is closed."
[^9]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] p.322 [synthesis] — Theorem 4: decidable whether a composition of given radii is similar to a convex polygon P; gradient-count vectors and "a system of linear Diophantine equation over positive integers"
[^10]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.322-323 [synthesis] — Proposition 5: reduced forms 1/n, a/(a(n+1) − 1), a/(an + 1); Proposition 6: "It is impossible to express any such rational of the form 5/8"
[^11]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.323, 328 [synthesis] — Corollary 2: line segments closed under composition; "a large barrier to the extension of this body of work in the approximation of the more general L_p metrics due to the impossibility of constructing any non-convex polygon from the composition of the two convex polygons which represent the Moore and von Neumann neighbourhoods"; astroid as L_{2/3}
[^12]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.324-334 [synthesis] — two labellings mod m; moiré and anti-moiré tables (Definitions 26-27); Propositions 7-9: gradients (w₀m₁ − w₁m₀)/(w₀ − w₁) and (w₀m₁ + w₁m₀)/(w₀ + w₁) varying with the widths; non-convex polygons; best astroid approximation with discs of squared radius 2 and 5 (Table 14.1)
