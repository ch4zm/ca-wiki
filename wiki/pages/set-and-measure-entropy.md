---
title: Set and Measure Entropy (cellular automata)
category: Concepts
summary: Wolfram's block entropies for cellular-automaton patterns - set (topological) entropy counts which blocks occur, measure (metric) entropy weights them by probability - taken over space, time and space-time patches, with the dimensions they converge to, the critical block length Xc, and the propagation speeds that bound them
tags: [concept, entropy, dimension, information, propagation-speed, wolfram]
sources: [universality-and-complexity-in-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Set and Measure Entropy (cellular automata)

## Description

A random configuration contains every block of X cells, each with probability k⁻ˣ, where
k is the number of cell values. Irreversible evolution breaks this randomness. Wolfram
measures the loss by looking at which blocks occur and how often.[^1] He introduces the
names "set" and "measure" entropy (and dimension) to tidy up the terminology.[^2]

**Two entropies for blocks of X cells.** Let p₁ … p_(kˣ) be the probabilities of the kˣ
possible blocks at one time step.[^1]

- **Set entropy** s⁽ˣ⁾(X) = (1/X) log_k N(X), where N(X) is the number of blocks that occur
  at all. It is also called *topological* entropy.
- **Measure entropy** s_μ⁽ˣ⁾(X) = −(1/X) Σ pⱼ log_k pⱼ. Each block is weighted by its
  probability, so the value depends on the probability distribution (the *measure*,
  hence μ). It is also called *metric* entropy. It is the average information per cell,
  allowing for correlations up to length X.[^2]

Both are in k-ary bits per cell. Always 0 ≤ s_μ⁽ˣ⁾ ≤ s⁽ˣ⁾ ≤ 1. The first bound is an
equality only if all occurring blocks are equally likely. The second is an equality if
every block occurs.[^3] For a translation-invariant distribution both entropies fall as X
grows.[^4]

**Critical block length.** Since s⁽ˣ⁾(X) falls with X, there is a *critical block length*
Xc. For X < Xc every block occurs (s⁽ˣ⁾ = 1). For X ≥ Xc some block is missing.[^5] Xc can
be computed. A procedure that builds predecessors one cell at a time (from J. Milnor's
unpublished notes, cited via Wolfram) turns the rule into a finite automaton with at most
2^(k^(2r)) states, where r is the range. It then finds Xc, or proves it infinite, in
finitely many steps.[^6] For the legal
[[totalistic-cellular-automaton](pages/totalistic-cellular-automaton.md)] rules with
k = 2, r = 2 in Wolfram's Table II (codes 2 to 60), Xc runs from 3 (codes 30, 32) to 36 (codes 10, 20). It is infinite only for
the additive code 42.[^7] A block missing at any time is already missing after one step
(Wolfram notes that if s⁽ˣ⁾(X) = 1 after one step, it stays 1).[^8] Own reasoning: so a
finite Xc means some block of length Xc has no predecessor, which is a
[[garden-of-eden](pages/garden-of-eden.md)] block.

**Always reachable.** If the rule is one-to-one in its leftmost or rightmost input, every
block of every length is reachable, and s⁽ˣ⁾ = 1 for all X. Wolfram proves this by adding
one cell at a time. He adds that the condition is sufficient but not known to be
necessary.[^9] Own reasoning: this is Hedlund's theorem that a
[[permutive-map](pages/permutive-map.md)] is onto.

**Dimensions.** Treat a configuration as a point of a Cantor set, the way a real number is
a point of [0, 1] ([[shift-dynamical-system](pages/shift-dynamical-system.md)]). The
*set dimension* is the limit d⁽ˣ⁾ = lim s⁽ˣ⁾(X) as X → ∞. For the classic middle-thirds
Cantor set this recipe gives log₃2, and in nonpathological cases it equals the Hausdorff
dimension. A random configuration has d⁽ˣ⁾ = 1 and a uniform one has d⁽ˣ⁾ = 0. The set
dimension of the configurations seen at large times is the dimension of the rule's
attractor.[^10] (This dimension of a *set of configurations* differs from the
[[fractal-dimension](pages/fractal-dimension.md)] of a single space-time pattern grown
from a seed.) Sampling is hard. Estimating s⁽ˣ⁾(X) directly needs many more than kˣ
blocks, and small samples underestimate it.[^11]

**Time and space-time.** The same definitions apply to the sequence of values one cell
takes over T steps, giving temporal entropies s⁽ᵗ⁾(T), s_μ⁽ᵗ⁾(T) and temporal dimensions.
If each cell cycles periodically, both dimensions are zero.[^12] Spatial and temporal
entropies usually differ, since a row of cells looks little like a cell's history.[^13]
For a space-time patch X cells wide and T steps long, every cell is fixed by the patch's
"rind", the top row plus 2r columns down the sides. That is X + 2r(T − 1) cells, so the
entropy per step is at most [X + 2r(T − 1)]/T. For large patches the information per cell
tends to zero. A cellular automaton therefore "can never generate random space-time
patterns".[^14] The limiting set entropy h of tall patches is the topological entropy of
the rule as a map, the rate at which the number of possible histories grows.[^15]

**Propagation speeds.** The value of a cell after T steps can depend on cells up to rT
away, so features travel at most r cells per step. The maximum speed λ₊ is the speed they
actually reach, with λ₊ ≤ r.[^16] Temporal entropy is at most 2r times spatial entropy, and
more precisely the ratio is bounded by the propagation speed.[^17] Most features travel
slower than λ₊. Let G(|x − x′|; t) be the probability that changing the cell at x changes
the cell at x′ t steps later, a kind of Green function. For large t it is almost always
zero outside a cone |x − x′| = λ̄₊t, which defines the *maximum average* speed λ̄₊. A
*minimum average* speed λ̄₋ is defined as the speed inside which G is almost always
positive. The Hamming distance H(t), the number of cells changed after t steps, is the
analogue of a Lyapunov exponent and obeys H(t)/t ≤ 2λ̄₊.[^18] If λ̄₊ = 0, finite regions
end up isolated and the temporal and mapping entropies vanish.[^19]

**Spatial and temporal chaos.** Wolfram calls behaviour *spatially chaotic* when the
spatial dimension is nonzero and *temporally chaotic* when the temporal dimension is
nonzero. Temporal chaos needs a nonzero average speed, and it means small changes have
ever-growing effects.[^20]

### Values by class

These quantities separate the [[wolfram-classes](pages/wolfram-classes.md)]:[^21]

| Class | Spatial dimension | Temporal dimension | Average speed λ̄₊ |
|---|---|---|---|
| 1 | 0 | 0 | 0 |
| 2 | not stated to vanish | 0 | 0 |
| 3 | nonzero | nonzero | nonzero (and λ̄₋ > 0) |
| 4 | no meaningful averages | - | very large fluctuations |

In class 3, spatial measure entropies drop for a few steps from a random start and then
level off at equilibrium values that do not depend on the starting distribution.[^22] For
irregular class 3 rules s_μ⁽ˣ⁾(X) stays at or above 0.9 for X < 8. For more regular ones it
falls faster, roughly as X^(−η) with η ≈ 0.1.[^23] Temporal set entropy s⁽ᵗ⁾(T) = 1 holds
for all T for any additive rule. Wolfram speculates that irregular class 3 rules have
temporal dimension 1.[^24] In the other direction, elementary rule 18 seems to allow
exactly the time sequences with no two adjacent 1s. Their count grows like the Fibonacci
numbers, giving temporal set dimension log₂φ ≈ 0.694.[^25]

## Appearances in Sources

- [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] - Sec. 4 defines the entropies, dimensions and speeds; Secs. 5-8 give their values by class; Sec. 7 gives Xc and Table II

## Related Concepts

- [[wolfram-classes](pages/wolfram-classes.md)] - what these quantities distinguish
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - the ensemble entropy of finite rings from Wolfram (1983)
- [[garden-of-eden](pages/garden-of-eden.md)] - a finite Xc means an unreachable block (own reasoning)
- [[permutive-map](pages/permutive-map.md)] - Hedlund's version of the one-to-one-at-an-end condition
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - Hedlund's theory of rules that reach every block
- [[shift-dynamical-system](pages/shift-dynamical-system.md)] - the Cantor set of configurations
- [[fractal-dimension](pages/fractal-dimension.md)] - the dimension of a single seeded pattern, a different quantity
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] - entropy and dimension 1 everywhere

[^1]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.8 [synthesis] - a disordered initial state is statistically random; "In a random sequence, all k^X possible subsequences ('blocks') of length X must occur with equal probabilities"; spatial set entropy (4.1) and spatial measure entropy (4.2) defined from the block probabilities p_j⁽ˣ⁾
[^2]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.15 [synthesis] - set entropy determined by the number N⁽ˣ⁾(X) of blocks generated (4.3); measure entropy weights blocks by probability and depends on the measure μ; "Set entropy is often called 'topological entropy'; measure entropy is sometimes referred to as 'metric entropy'"; footnote: "The terms 'set' and 'measure' entropy, together with 'set' and 'measure' dimension, are introduced here to rationalize nomenclature"; average "information content" per site; units of k-ary bits per unit distance
[^3]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.15 [synthesis] - s_μ⁽ˣ⁾(X) ≤ s⁽ˣ⁾(X) ≤ 1 (4.4); first saturated only for "equidistributed" systems, second if all possible length-X blocks occur; 0 ≤ s_μ ≤ s (4.5)
[^4]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.15-16 [synthesis] - subadditivity (4.6); for translationally invariant systems the set and measure entropies "decrease monotonically with the block size X" (4.11); X s(X) convex (4.12)
[^5]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.16 [synthesis] - critical block size Xc with s⁽ˣ⁾(X) = 1 for X < Xc and < 1 for X ≥ Xc (4.13)
[^6]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.23, 27 [synthesis] - predecessor construction as a finite automaton with at most 2^(k^(2r)) states; the progressive construction "provides a more efficient procedure [21]"; Xc found from the state transition graph, infinite if the graph is closed cycles not including ψ = 0; "a finite algorithm for determining whether all possible arbitrarily long sequences of site values may be generated"
[^7]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.28 [synthesis] - Table II, Xc for the legal totalistic k = 2, r = 2 rules with codes 2 to 60: 3 for codes 30 and 32; 36 for codes 10 and 20; ∞ for code 42; all others between 5 and 22
[^8]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.27 - "Notice that if s⁽ˣ⁾(X) = 1 after one time step, then s⁽ˣ⁾(X) = 1 at any time."
[^9]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.28 [synthesis] - s⁽ˣ⁾(X) = 1 for all X, so d⁽ˣ⁾ = 1, "if F is an injective (one-to-one) function of either its first or last argument (or can be obtained by composition of functions with such a property)", proved by induction; "it is apparently not necessary. A necessary condition is not known."
[^10]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.16-17 [synthesis] - configurations as elements of a Cantor set; the limit of s⁽ˣ⁾(X) as X → ∞ gives the set dimension; bins of width k⁻ᵇ; classic Cantor set dimension log₃2; except in pathological examples equal to the Hausdorff dimension; d⁽ˣ⁾ = lim s⁽ˣ⁾(X) (4.15); disordered configuration d⁽ˣ⁾ = 1, null configuration 0; the set dimension of the attractors given by (4.15)
[^11]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.17 [synthesis] - accurate direct evaluation "typically requires sampling of many more than k^X length X blocks. Inadequate samples yield systematic underestimates"; the error estimate (4.16)
[^12]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.19 [synthesis] - temporal measure entropy (4.21); temporal set and measure dimensions (4.22)-(4.23); if each site takes a fixed cycle of values, d⁽ᵗ⁾ = d_μ⁽ᵗ⁾ = 0 (4.24); units of k-ary bits per unit time
[^13]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.19 [synthesis] - configurations "typically have little similarity with the 'time series' of values attained by a particular site"; spatial and temporal entropies "in general quite different"; spatial entropy is the temporal entropy of a pure shift
[^14]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.19-20 [synthesis] - space-time patch entropies (4.25)-(4.26); values in a T × X patch determined by the "rind" of X + 2r(T − 1) sites (4.29); information per site tends to zero; "The evolution of cellular automata can therefore never generate random space-time patterns."
[^15]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.20 [synthesis] - limiting set entropy h (4.33) "equivalent to the set (or topological) entropy of the cellular automaton mapping in symbolic dynamics"; "the asymptotic rate at which the number of possible histories for the cellular automaton increases with time"
[^16]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.20 [synthesis] - after T steps a site may depend on sites up to rT away, features propagate at speeds up to r; maximum propagation speed λ₊ (4.37); λ₊ ≤ r (4.38)
[^17]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.20-21 [synthesis] - s⁽ᵗ⁾(T) ≤ 2r s⁽ˣ⁾(2rT) (4.40), Fig. 8; "The ratio of temporal to spatial entropy is thus bounded by the maximum propagation speed in the cellular automaton" (4.41)
[^18]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.21 [synthesis] - G(|x − x′|; t) the probability that a site at x′ changes when x is changed t steps before, "a Green function"; vanishes outside a cone |x − x′| = λ̄₊t; minimum average speed λ̄₋ with G > 0 for almost any |x − x′| < λ̄₋t; Hamming distance H(t) "analogous to Lyapunov exponents"; H(t)/t ≤ 2λ̄₊ (4.44)
[^19]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.21 [synthesis] - when λ₊ = 0 finite regions become isolated, d_μ⁽ᵗ⁾ = h_μ = 0 (4.39); mapping and temporal entropies vanish for zero maximum average propagation speed; class 2 has this property
[^20]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.21 [synthesis] - "Spatial chaos" when the spatial measure dimension is nonzero, "temporal chaos" when the temporal one is; temporal chaos requires a nonzero maximum average propagation speed and "implies that small changes in initial conditions lead to effects ever-increasing with time"
[^21]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.22, 26, 33-34 [synthesis] - class 1: spatial and temporal dimensions zero; class 2: λ̄₊ = 0, temporal and mapping but not spatial dimensions vanish; class 3: nonzero λ̄₋, spatial and temporal dimensions nonzero; class 4: "very large fluctuations in the propagation speed, and no meaningful averages may be obtained"
[^22]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.26-27 [synthesis] - Fig. 10, code 12: entropies decrease for a few steps then reach "equilibrium" values, typically independent of the initial measure for smooth measures
[^23]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.27 [synthesis] - reliable estimates only for 0 < X < 8; for irregular rules the equilibrium s_μ⁽ˣ⁾(X) "typically remains ≳ 0.9 for X < 8"; for more regular rules it decreases roughly as X^(−η) with η ≈ 0.1
[^24]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.29 [synthesis] - equilibrium temporal set entropy s⁽ᵗ⁾(T) = 1 for all T < 8 for irregular class 3 rules in Fig. 1; "s⁽ᵗ⁾(T) = 1 holds for all T for any additive cellular automaton rule"; speculation that irregular class 3 rules "form a special subclass, characterized by temporal dimension d⁽ᵗ⁾ = 1"
[^25]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.29 [synthesis] - rule 18: "some evidence [21] that all possible temporal sequences which contain no 11 subsequences may appear", N⁽ᵗ⁾(T) = F_T, F_T ~ φ^T with φ ≈ 1.618, "suggesting a temporal set dimension d⁽ᵗ⁾ = log₂φ ≈ 0.694"
