---
title: Fractal Dimension (self-similar CA patterns)
category: Concepts
summary: The Hausdorff-Besicovitch dimension of the self-similar patterns cellular automata grow from simple seeds - log₂3 ≈ 1.59 for almost every complex elementary rule, log₂(2φ) ≈ 1.69 for rule 150, with values for modulo-k and higher-dimensional rules
tags: [concept, fractal, self-similarity, scale-invariance, wolfram]
sources: [statistical-mechanics-of-cellular-automata]
created: 2026-09-24
updated: 2026-09-25
---

# Fractal Dimension (self-similar CA patterns)

## Description

**Definition.** Cover a figure with squares of side a, and let N(a) be the smallest number
of squares that covers every nonzero cell. The figure is *self-similar* (scale-invariant)
if rescaling a changes N(a) by a constant factor, whatever the absolute size of a. In
that case N(a) ~ a^(−D), and D is the Hausdorff-Besicovitch or *fractal* dimension. A
figure that fills the plane has D = 2 and a line has D = 1. Values in between indicate
clustering or intermittency.[^1]

**Why cellular automata give fractals.** A local rule has no length scale except one cell
and no time scale except one step. A single-cell seed has no scale either. So the pattern
grown from a seed should have no intrinsic scale, at least in the long run. Simple rules
reach this trivially by becoming uniform. Complex rules reach it nontrivially, as
self-similar fractals.[^2]

**Elementary rules.** In the space-time pattern grown from one cell:

| Rule(s) | Recurrence for triangle density T | Dimension |
|---|---|---|
| [[rule-90](pages/rule-90.md)] and every other complex rule that grows a non-trivial pattern from a seed, except 150 | T(n/2) = 3T(n) | log₂3 ≈ 1.59 |
| rule 150 | two-term, Fibonacci-like | log₂(2φ) = 1 + log₂φ ≈ 1.69, φ the golden ratio |

At each stage of the rule-90 construction the triangles halve in size and triple in
number, which gives the power law. For rule 150 the largest root of the recurrence
dominates, the way the golden ratio dominates the Fibonacci numbers.[^3] A single row (one
time step) of these patterns has dimension D − 1, for example 0.59 for rule 90, except at
a measure-zero set of times such as τ = 2ᵏ.[^4]

**Robust to the seed.** If the seed is any finite pattern of size n₀, the pattern depends
on the seed only at scales up to about n₀. Above that it takes the same self-similar form,
with dimension log₂3 for every complex rule that grows a non-trivial pattern from a seed,
except 150.[^5] Random, infinite starts are
different. They give structure at all scales, but the pattern is *not* self-similar,
because it depends on the absolute scale of the cell spacing
([[self-organization](pages/self-organization.md)]).[^6]

**Other rules** (all from a single seed):[^7]

- **Modulo-k rules, k prime.** The dimension is D_k = 1 + log_k((k+1)/2): about 1.63 for
  k = 3 and about 1.68 for k = 5. For composite k the pattern depends on the seed's value.
  As k → ∞ the dimension approaches 2, since every binomial coefficient becomes nonzero.
- **Two dimensions** (stacking the time steps into a 3D pyramid). The modulo-two sum of the
  four orthogonal neighbours gives log₂5 ≈ 2.32. Including the cell itself gives
  1 + log₂(1 + √3) ≈ 2.45. In d dimensions the first case gives log₂(2d + 1).
- Reversible second-order rules also give self-similar patterns, but these are symmetric
  in time ([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]).

**Conjecture.** Because self-similarity is generic for complex rules grown from simple
seeds, Wolfram conjectures that many natural systems with self-similar structure get it
"through local processes which follow cellular automaton rules". He offers this as a
possible explanation of how common self-similarity is in nature.[^8]

## Appearances in Sources

- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — the definition, the elementary-rule values, the seed-independence argument, the modulo-k and 2D values, and the conjecture about nature

## Related Concepts

- [[rule-90](pages/rule-90.md)] — the canonical log₂3 pattern
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] — where the dimensions can be derived exactly
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] — the simple/complex split that decides whether a fractal appears
- [[self-organization](pages/self-organization.md)] — the random-start counterpart: structure on all scales but not self-similar

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.616 [synthesis] — minimum number N(a) of squares of side a covering the figure; self-similar if rescaling a changes N(a) by a constant factor independent of a; D the Hausdorff-Besicovitch or fractal dimension; plane D = 2, line D = 1, intermediate values "indicate clustering or intermittency"
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.604 [synthesis] — rules define no intrinsic length or time scale beyond a site and a step; the single-site initial state has no intrinsic scale; simple rules give a uniform, manifestly scale-invariant state; the scale invariance of complex-rule configurations "is nontrivial"
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.616 [synthesis] — base lengths halved and number multiplied by 3 at each stage, T(n/2) = 3T(n), D = log₂3 ≈ 1.59; rule 150 two-term recurrence solved "in analogy with the Fibonacci series", D = log₂(2φ) = 1 + log₂φ ≈ 1.69; footnote: a p-term recurrence is dominated by its largest root
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.616-617 [synthesis] — "the fractal dimension of almost all the individual configurations is D − 1"; time steps of the form 2ᵏ form "an exceptional set of measure zero"; D = log₂3 − 1 ≈ 0.59
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.617 [synthesis] — the initial state determines triangles with n ≲ n₀ but not n ≫ n₀; patterns from any simple initial state under complex rules (except 150) share self-similarity with dimension log₂3
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.617 — "Triangles of all sizes are nevertheless obtained, so that structure is generated on all scales ... However, the pattern is not self-similar, but depends on the absolute scale defined by the spacing between sites."
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.626 n.12, 630, 637 [synthesis] — modulo-k with k prime: D_k = 1 + log_k((k+1)/2), D₃ ≈ 1.63, D₅ ≈ 1.68; composite k depends on the seed value; D → 2 as k → ∞; 2D type-I modulo-two rules log₂5 ≈ 2.32 and 1 + log₂(1+√3) ≈ 2.45; d dimensions log₂(2d+1); reversible rules give self-similar patterns "symmetrical in time"
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.617, 641 [synthesis] — conjecture that many self-similar systems "attain this structure through local processes which follow cellular automaton rules"; "This result may provide some explanation for the widespread occurrence of self-similarity in natural systems."
