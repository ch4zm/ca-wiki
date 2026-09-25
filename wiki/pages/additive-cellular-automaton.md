---
title: Additive Cellular Automaton
category: Concepts
summary: Cellular automata obeying superposition modulo k - evolution from any start is the XOR of evolutions from single seeds; among elementary rules only 0, 90, 150, 204; exactly solvable, and a separate universality class from the non-additive complex rules
tags: [concept, additive, superposition, wolfram, exact-results, number-theory]
sources: [statistical-mechanics-of-cellular-automata, universality-and-complexity-in-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Additive Cellular Automaton

## Description

A cellular automaton is **additive** if its evolution obeys a superposition principle.
Evolving the sum (modulo 2) of two configurations gives the sum of their separate
evolutions. Any configuration is then the superposition of the patterns grown from each of
its nonzero cells alone. The addition is over a finite field, so "additive" here does not
mean linear in the real-number sense.[^1]

**Which rules.** Among the 32 legal
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] rules, only 0,
90, 150 and 204 are additive. Rules 0 (erase everything) and 204 (identity) are trivial.
[[rule-90](pages/rule-90.md)] sets each cell to the XOR (sum modulo 2) of its two
neighbours. Rule 150 sets each cell to the XOR of itself and its two neighbours.[^1] Both
90 and 150 are "complex" rules.

**Exact results.** Superposition makes these the cases that can be solved exactly, and
Wolfram uses them as benchmarks throughout:

- **Growth from a seed.** Rule 90 from one cell gives Pascal's triangle mod 2. After τ
  steps there are 2^#₁(τ) nonzero cells, where #₁(τ) is the number of 1s in the binary
  expansion of τ. Rule 150 gives the coefficients of (1 + x + x²)ⁿ mod 2.[^2] The limiting
  patterns have [[fractal-dimension](pages/fractal-dimension.md)] log₂3 ≈ 1.59 and
  log₂(2φ) ≈ 1.69 respectively.[^3]
- **Density.** Under rule 90, starting from random density ρ₀, the density is
  ρ_τ = ½[1 − (1 − 2ρ₀)^(2^#₁(τ))]. It tends to ½ for almost all τ, but it dips sharply at
  τ = 2^j, when each cell depends on only two initial cells. Non-additive complex rules
  instead approach their limit smoothly.[^4]
- **Correlations.** From a random start the additive rules never build two-point
  correlations, because the result is a convolution of the uncorrelated initial state.[^5]
- **Damage spreading.** A one-cell change spreads exactly like the single-seed pattern.
  Its Hamming distance is about τ^0.59 averaged over time, compared with linear growth under
  non-additive rules.[^6]
- **Cycles.** On a ring of N cells, every cycle period divides the period Π_N of the
  single-seed evolution, and every transient length divides its transient. Π_N is the same
  for rules 90 and 150 and depends on number-theoretic properties of N. It is 1 when N is a
  power of 2, it relates to the multiplicative order of 2 mod N, and it is bounded by about
  2^((N−1)/2), roughly the square root of the 2ᴺ maximum. The transient configurations
  form balanced quaternary trees rooted on the cycles. These results are due to Martin,
  Odlyzko and Wolfram (1983), cited via this paper and not read.[^7]
- **Reachability.** With N odd, rule 90 reaches exactly half of all configurations, the
  ones with an even number of 1s. With N even it reaches a quarter. A fixed fraction
  therefore stays reachable as N → ∞, while for non-additive rules the reachable fraction
  goes to 0 ([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]).[^8]
- **Every block reachable.** In Wolfram (1984), with k values and range r, every block
  of every length can be produced, and each has exactly k^(2r) predecessor blocks. So the
  spatial set and measure dimensions are both 1, and the temporal set entropy is 1 for all
  block lengths. Wolfram calls additive rules "maximally chaotic"
  ([[set-and-measure-entropy](pages/set-and-measure-entropy.md)]).[^12] Own reasoning: the
  k^(2r) count is Hedlund's balanced-preimage count S^(n−1) with window n = 2r + 1
  ([[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)]). In the
  four-class scheme they are class 3 ([[wolfram-classes](pages/wolfram-classes.md)]). The
  k = 2, r = 2 totalistic code 42, the XOR of five cells, is the example.[^12]

**A separate universality class.** From random starts, the density of triangles of base n
falls off as λ⁻ⁿ, with λ ≈ 2 for rules 90 and 150 and λ ≈ 4/3 for every non-additive
complex rule ([[self-organization](pages/self-organization.md)]).[^9]

**Hidden additivity.** Some non-additive rules contain additive behaviour. Under rule 18,
a configuration with all even cells 0 evolves like rule 90 on alternate cells. A general
configuration splits into such domains separated by "kinks". The kinks random-walk and
annihilate in pairs, and what is left evolves by rule 90 (Grassberger 1982, cited via this
paper and not read).[^10]

**Beyond two states.** The *modulo-k* rules, where each cell becomes the sum mod k of its
two neighbours, are also additive and grow self-similar figures from a seed. In two
dimensions the modulo-two sums over the four orthogonal neighbours, with or without the
cell itself, are additive as well.[^11]

## Appearances in Sources

- [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] - additive rules reach every block, with dimension 1; code 42 as a class 3 example
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — defines additivity, identifies the additive elementary rules, and derives their exact density, damage-spreading, cycle and reachability results

## Related Concepts

- [[set-and-measure-entropy](pages/set-and-measure-entropy.md)] - additive rules have entropy and dimension 1
- [[wolfram-classes](pages/wolfram-classes.md)] - additive rules are the most chaotic class 3 rules
- [[rule-90](pages/rule-90.md)] — the main additive rule
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] — the family in which they are identified
- [[fractal-dimension](pages/fractal-dimension.md)] — the dimensions of their seed patterns
- [[self-organization](pages/self-organization.md)] — additive rules form their own statistical class
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — additive rules keep a finite reachable fraction
- [[self-reproduction](pages/self-reproduction.md)] — superposition makes rule 90 copy any pattern

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.604 [synthesis] — superposition principle (Eq. 2.2); "such additivity does not imply linearity in the real number sense ... since the addition is over a finite field"; "Only rules 0, 90, 150, and 204 are of this form"; 0 erases, 204 is the identity; rule 90 sums two neighbours mod 2, rule 150 also includes the site's own value
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.605-606, 613 [synthesis] — rule 90 from one site: binomial coefficients mod 2 (Fig. 4); N_τ⁽¹⁾ = 2^#₁(τ) (Eq. 3.2); rule 150: coefficients of (x² + x + 1)ⁿ mod 2
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.607, 616 [synthesis] — Fig. 5 dimension log₂3; Fig. 6 dimension log₂2φ ≈ 1.69
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.613-614 [synthesis] — ρ_τ = ½[1 − (1 − 2ρ₀)^(2^#₁(τ))] (Eq. 3.3); ρ_τ → ½ for almost all τ; at τ = 2^j, ρ = 2ρ₀(1 − ρ₀); Fig. 12 irregularities occur when each site depends on few initial sites, while nonadditive 18 and 182 tend smoothly to a limit
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.615 — "With these rules, the correlation function obtained by evolution from a disordered initial configuration thus always remains zero."
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.621-622 [synthesis] — for additive rules the Hamming distance is the number of nonzero sites grown from a single site, smoothed ~ τ^0.59; nonadditive rule 126 gives linear growth
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.627-628 [synthesis] — cycle periods divide Π_N and transients divide the single-site transient; Π_N identical for rules 90 and 150; Π_N = 1 for N a power of 2; multiplicative order of 2 mod N; Π_N ≤ 2^((N−1)/2) − 1, "approximately the square root of the maximum possible length"; "an irregular function of N"; balanced quaternary trees; derivations in Martin et al. (1983)
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.623 [synthesis] — with N odd, rule 90 generates only configurations with an even number of ones, "exactly half"; for even N, ¼; "A finite fraction of all the configurations are thus reached in the limit N → ∞"
[^9]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.617, 619 [synthesis] — T(n) ~ λ⁻ⁿ, λ ~ 4/3 for nonadditive rules, λ ~ 2 for additive rules; Fig. 16
[^10]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.614 [synthesis] — Grassberger (1982): rule 18 configurations with even sites zero evolve as rule 90; domains separated by kinks that random-walk (⟨x²⟩ = t) and annihilate, density ~ (4πt)^(−1/2); alternate sites ultimately follow rule 90
[^11]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.630, 637 [synthesis] — modulo-k rules obey additive superposition and tend to self-similar figures; 2D type-I modulo-two rules in analogy with rules 90 and 150 (Fig. 32)
[^12]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.27-29 [synthesis] - for additive rules (such as code 42) "all possible blocks of any length X may be reached, and have exactly k^(2r) predecessors of length X + 2r"; d⁽ˣ⁾ = d_μ⁽ˣ⁾ = 1 (7.1); "maximally chaotic"; "s⁽ᵗ⁾(T) = 1 holds for all T for any additive cellular automaton rule"
