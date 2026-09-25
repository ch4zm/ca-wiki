---
title: λ Parameter (Langton)
category: Concepts
summary: Langton's one-number ordering of cellular-automaton rule space - the fraction of rule-table entries that do not map to a chosen quiescent state, from 0 (all quiescent, most ordered) to 1 - 1/K (all states equally represented, most disordered); sweeping it reveals an order-chaos phase transition
tags: [concept, langton, lambda-parameter, rule-space, phase-transition]
sources: [computation-at-the-edge-of-chaos]
created: 2026-09-24
updated: 2026-09-24
---

# λ Parameter (Langton)

Not to be confused with Wolfram's λ, the decay constant of triangle spectra on
[[self-organization](pages/self-organization.md)] (see
[[notation-map](pages/notation-map.md)]).

## Description

**The problem it solves.** With K states per cell and a neighbourhood of N cells, a rule
table has K^N entries and there are K^(K^N) rules. For K = 8, N = 5 that is about
10^30,000. The space has no built-in order. Langton wants an ordering under which nearby
rules behave alike, so that he can see where different kinds of behaviour live.[^1]

**Definition.** Pick one state and call it the quiescent state s_q. Suppose n of the K^N
entries in the rule table map to s_q, and the rest map to other states chosen uniformly
at random. Then

λ = (K^N - n) / K^N,

the fraction of entries that do not lead to s_q. If every entry maps to s_q, λ = 0. If
all K states are equally represented, λ = 1 - 1/K. These are the most homogeneous and
most heterogeneous tables, and Langton works between them.[^2]

**Sampling rule space.** Langton builds tables for a given λ in two ways:[^3]

- **Random table.** For each entry, with probability 1 - λ map it to s_q, otherwise to a
  random other state. Every table is new.
- **Table walk-through.** Start with every entry mapping to s_q. Raise λ by replacing a
  few such entries with other states, or lower it by the reverse. This perturbs "the same
  table" step by step and shows where that table changes behaviour.

Two restrictions apply throughout. *Strong quiescence*: a neighbourhood entirely in one
state s maps to s, so uniform arrays stay uniform. *Isotropy*: all planar rotations of a
neighbourhood map to the same state. Because of strong quiescence, λ = 0 exactly is not
possible.[^4]

**What λ shows.** Sweeping λ runs from rules that freeze at once to fully chaotic rules,
with a phase transition in between. Near it, transients are long and structures are complex
([[edge-of-chaos](pages/edge-of-chaos.md)]).[^5] Different walk-throughs cross the
transition at different λ values, spread around a mean.[^6] The
[[game-of-life](pages/game-of-life.md)] has λ = 0.273, inside the transition region for
2-state, 9-neighbour rules.[^7]

**Limits.** Langton calls λ "not necessarily the best parameter". Gutowitz's hierarchy of
parameterizations has λ as its simplest level and mean field theory as the next (cited via
Langton, not read). λ is still useful for finding a promising region before looking at
finer detail, because it is one-dimensional.[^8] It separates behaviours well when K and N
are large and poorly when they are small. For the 2-state, 3-neighbour
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] rules it is only
roughly correlated with behaviour. Langton suggests this is why earlier classification
work on small rule spaces missed the transition. His surveys use K ≥ 4 and N ≥ 5, so
tables have at least 1024 entries.[^9]

**As a density.** Langton treats λ as a dynamical analogue of the occupation probability in
site percolation. In the 2D survey the lowest-entropy rules stop at λ ≈ 0.6 for the
five-cell neighbourhood (site-percolation threshold 0.59) and at λ ≈ 0.4 for the nine-cell
one (threshold 0.402).[^10]

## Appearances in Sources

- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - defines λ, the two sampling methods, and its limits

## Related Concepts

- [[edge-of-chaos](pages/edge-of-chaos.md)] - the phase transition found by sweeping λ
- [[cellular-automaton](pages/cellular-automaton.md)] - the rule space being ordered
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - a rule space too small for λ to work well
- [[game-of-life](pages/game-of-life.md)] - a well-known rule with λ in the transition region
- [[chris-langton](pages/chris-langton.md)] - introduced it

[^1]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.13-14 [synthesis] - K^N neighbourhood states, K^(K^N) transition functions; K = 8, N = 5 gives about 10^30 000; "there is no intrinsic order"; "The ideal ordering scheme would partition the space of CA rules in such a manner that rules from the same partition would support similar dynamics"
[^2]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.14 [synthesis] - Sec. 2.1, Eq. 1: λ = (K^N - n)/K^N; n = K^N gives λ = 0.0; all states equally represented gives λ = 1.0 - 1/K; "the most homogeneous and the most heterogeneous rule tables"
[^3]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.15 [synthesis] - Sec. 2.2: "random-table method", λ-biased coin for each neighbourhood state; "table-walk-through" method, perturbing "the same table" up or down in λ
[^4]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.15, 17 [synthesis] - Sec. 2.3: strong quiescence and isotropy conditions, "the physics cannot tell which way is up"; p.17: "under the strong quiescence condition mentioned above we cannot have λ = 0.00 exactly"
[^5]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.24 [synthesis] - "we progress from CAs exhibiting the maximal possible order to CAs exhibiting the maximal possible disorder. At intermediate values of λ, we encounter a phase transition between periodic and chaotic dynamics"
[^6]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.26, 28 [synthesis] - different table walk-throughs make the transition at different λ, with a distribution around a mean; Fig. 7 shows four transitions at different λ values
[^7]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.25 - "The λ value for the Game of Life (λ_Life = 0.273) lies within the transition region for K = 2, N = 9 2D CAs."
[^8]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.15 [synthesis] - Sec. 2.4: "λ is not necessarily the best parameter"; Gutowitz's hierarchy with λ simplest and mean field theory next; λ "helps restrict the area of search to a particularly promising 'spot'"; higher-order parameterizations map rule space onto many dimensions
[^9]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.15 [synthesis] - λ discriminates well for large K and N, poorly for small; for K = 2, N = 3 "λ is only roughly correlated with dynamical behavior"; may explain why earlier classification work with minimal K and N did not see the relationships; K ≥ 4 and N ≥ 5, tables of size 4⁵ = 1024 or larger
[^10]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.27 [synthesis] - λ as "a dynamical analog of the site occupation probability"; cutoff at λ = 0.6 vs p_c ≈ 0.59; 9-neighbour cutoff at λ = 0.4 vs p_c = 0.402
