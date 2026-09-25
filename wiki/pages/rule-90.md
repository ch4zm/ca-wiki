---
title: Rule 90
category: Rules
summary: The elementary "modulo-two" rule - each cell becomes the XOR of its two neighbours; grows Pascal's triangle mod 2 (a Sierpinski pattern of dimension log₂3) from one cell, is additive and exactly solvable, and copies any finite pattern
tags: [rule, elementary-ca, additive, wolfram, sierpinski, pascal-triangle]
sources: [statistical-mechanics-of-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Rule 90

## Description

**Rule 90** is the [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)]
with rule table 01011010. Each cell's new value is the sum modulo 2 of its two neighbours'
old values:

  s_{n+1}(m) = s_n(m−1) ⊕ s_n(m+1).

The cell's own value is ignored, so the rule is *peripheral*.[^1] Wolfram calls it the
"modulo-two rule" and uses it as the running example of his 1983 paper.[^2]

**From a single cell.** The rows are Pascal's triangle mod 2. The value of a cell is a
binomial coefficient mod 2, that is, a coefficient of (1 + x)ⁿ mod 2.[^3] At large times
the pattern approaches a recursive construction of nested triangles (Sierpinski's), which
is self-similar with [[fractal-dimension](pages/fractal-dimension.md)] log₂3 ≈ 1.59. A
single row has dimension log₂3 − 1 ≈ 0.59.[^4] After τ steps the number of 1s is
2^#₁(τ), where #₁(τ) counts the 1s in the binary expansion of τ.[^5] This is an irregular
function of τ. At τ = 2^j only two cells are nonzero, at ±2^j.[^5]

**Additivity.** Rule 90 is one of the two nontrivial
[[additive-cellular-automaton](pages/additive-cellular-automaton.md)] rules, so evolution
from any start is the XOR of the patterns grown from each of its 1s. That makes its
density, correlations, damage spreading, cycle lengths and reachable configurations all
exactly computable. Details are on the additive page.[^6]

**Self-reproduction.** Since the pattern from one cell is two cells after 2^j steps,
superposition gives two exact copies of *any* finite starting pattern after τ = 2^j
steps, once j is large enough. After a further 2^(j−1) steps there are four copies. After
another 2^(j−1) the inner pair meet and annihilate, leaving two copies again at
τ = 2^(j+1). Wolfram names this purely geometrical "overcrowding" as what stops the copies
from multiplying exponentially.[^7] See [[self-reproduction](pages/self-reproduction.md)].

**Relatives.** Rule 150 adds the centre cell (s₋ ⊕ s ⊕ s₊) and gives dimension
log₂(2φ) ≈ 1.69.[^8] The modulo-k rules generalize rule 90 to k values per cell. The
two-dimensional sum of the four orthogonal neighbours gives self-similar pyramids of
dimension log₂5 ≈ 2.32.[^9] The non-additive rule 18 ends up evolving like rule 90 on
alternate cells.[^10]

## Appearances in Sources

- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — the running example: Pascal's triangle mod 2, exact density and cycle results, and the self-reproduction example

## Related Concepts

- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] — the property that makes it exactly solvable
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] — its family
- [[fractal-dimension](pages/fractal-dimension.md)] — log₂3 from a single seed
- [[self-reproduction](pages/self-reproduction.md)] — trivial replication by superposition
- [[self-organization](pages/self-organization.md)] — additive rules form their own statistical class
- [[permutive-map](pages/permutive-map.md)] - XOR of the end cells, permutive at both ends
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - onto on the infinite line

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.603-604 [synthesis] — Fig. 1 rule table; Eq. 2.1 s_{n+1}(m) = s_n(m−1) ⊕ s_n(m+1); rules 0, 90, 160, 250 are peripheral
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.603 [synthesis] — "As a first example consider the 'modulo-two' rule 90 (also used as the example for Fig. 1)"
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.605 [synthesis] — the configurations are the lines of Pascal's triangle modulo two; site values are binomial coefficients, equivalently coefficients in the expansion of (1+x)ⁿ, modulo two (Fig. 4)
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.605-607, 616-617 [synthesis] — recursive geometrical construction (cf. Sierpinski 1916) in Fig. 5, "a self-similar figure with fractal dimension log₂3"; individual configurations have dimension log₂3 − 1 ≈ 0.59
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.613 [synthesis] — N_τ⁽¹⁾ = 2^#₁(τ) (Eq. 3.2), #₁ shown to be highly irregular (Fig. 11); after τ = 2^j steps a single site evolves to exactly two nonzero sites at n ± τ
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.604, 613-615, 621, 623, 627-628 [synthesis] — additive superposition and its consequences for density (Eq. 3.3), correlations, Hamming distance, reachability, and cycle periods
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] — Fig. 33: two exact copies after τ = 2^j; four after a further 2^(j−1); the innermost pair annihilate, leaving two at τ = 2^(j+1); "Purely geometrical 'overcrowding' thus prevents exponential multiplication of copies by self-reproduction in this case"
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.604, 607 [synthesis] — rule 150 is s₋ ⊕ s ⊕ s₊; Fig. 6 dimension log₂2φ ≈ 1.69
[^9]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.630, 637 [synthesis] — modulo-k rules generalize the modulo-two rule 90; 2D type-I case (a), the sum of four neighbours "in analogy with one-dimensional cellular automaton rule 90", fractal dimension log₂5 ≈ 2.32
[^10]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.614 [synthesis] — Grassberger (1982), cited via this paper: after kinks annihilate, alternate sites of rule 18 evolve according to rule 90
