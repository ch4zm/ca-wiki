---
title: Garden-of-Eden Theorem (Moore-Myhill)
category: Concepts
summary: A tessellation structure has Garden-of-Eden configurations if and only if it has two distinct configurations that no environment can tell apart; Moore (1962) proved "if", Myhill (1963) "only if"
tags: [concept, garden-of-eden, theorem, moore, myhill, surjectivity, injectivity]
sources: [machine-models-of-self-reproduction, converse-of-moores-garden-of-eden-theorem, planetmath-garden-of-eden-theorem, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-24
---

# Garden-of-Eden Theorem (Moore-Myhill)

## Description

**Statement.** In a tessellation structure (a
[[cellular-automaton](pages/cellular-automaton.md)] with a quiescent state), the following
are equivalent:[^1][^2]

1. There are [[garden-of-eden](pages/garden-of-eden.md)] configurations, patterns that no
   earlier state can produce.
2. There are two mutually erasable configurations
   ([[erasable-configuration](pages/erasable-configuration.md)]), or equivalently two
   different configurations that no environment distinguishes.

[[edward-f-moore](pages/edward-f-moore.md)] proved that 2 implies 1 in 1962.[^1]
[[john-myhill](pages/john-myhill.md)] proved that 1 implies 2 in 1963.[^2] The equivalence
of the two forms of condition 2 was pointed out by Myhill's referee.[^3]

**Modern reading.** Condition 1 says the global map from configurations to their successors
is not surjective. Condition 2 says it is not injective on finite patterns: two finite
patterns that differ get sent to the same successor. The theorem thus says surjectivity is
equivalent to injectivity on finite patterns. In current terms a Garden-of-Eden pattern is
an *orphan*, and injectivity on finite patterns is *pre-injectivity*: surjective ⇔
pre-injective. Injective automata are therefore surjective.[^4] Kari (2005) states it the same way, as
"G_F injective iff G surjective" (below). Neither Moore's nor Myhill's paper uses this
wording.

**Any dimension.** The theorem holds for cellular automata on ℤᵈ in every dimension d, with
a cubic neighbourhood of any radius r. The counting inequality becomes
(a^(k^d) − 1)^(n^d) < a^((kn − 2r)^d), with k now the sub-block side and n the number of
sub-blocks per side, the reverse of Moore's letters ([[notation-map](pages/notation-map.md)]).
Myhill's direction needs only a constant background state, not a quiescent one.[^5]

**Beyond grids.** On a general group the theorem holds exactly when the group is an
[[amenable-group](pages/amenable-group.md)]. Both directions hold on every amenable group,
and each direction separately fails on some cellular automaton over every non-amenable
group.[^6][^7]

**Why it works.** Both directions rest on one counting inequality. Take a kn × kn block
divided into k² sub-blocks of side n, with A states per cell. Moore's inequality (1) says
that for large k,

(A^(n²) − 1)^(k²) < A^((kn−2)²).

On the left is the number of kn × kn blocks when each sub-block has only A^(n²) − 1
effectively different contents. On the right is the number of patterns of the interior block one step later,
which is only two cells narrower because the neighbourhood has radius 1
([[moore-neighbourhood](pages/moore-neighbourhood.md)]).[^8]

- **Moore (2 ⇒ 1).** If an n × n pair is mutually erasable, each sub-block has at most
  A^(n²) − 1 effectively different contents. So at most the left side's number of
  successors occur in the interior, which is fewer than its A^((kn−2)²) possible
  patterns. Some interior pattern has no predecessor.[^8]
- **Myhill (1 ⇒ 2).** Suppose instead every pair is distinguishable and G is an n × n
  Garden-of-Eden pattern. Every (kn − 2) × (kn − 2) pattern placed in a quiescent plane
  then gives a different kn × kn successor, so at least A^((kn−2)²) kn × kn patterns are
  not Garden-of-Eden. Any block containing G is Garden-of-Eden, so at most
  (A^(n²) − 1)^(k²) blocks are not. For large k this contradicts the inequality.[^9]

**Assumptions.** Moore's proof assumes a homogeneous universe, discrete space and time,
local action, Euclidean space, deterministic laws, and the possibility of erasing. He calls
erasing vital.[^10]

**Consequence for self-reproduction.** No self-reproducing configuration can contain a
Garden-of-Eden pattern.[^11] In any structure with erasure, then, some describable machines
can never be built or reproduced.

**Finite, periodic and all configurations.** Kari (2005) states the theorem as "G_F is
injective if and only if G is surjective", in every dimension, and adds the restriction
G_P to spatially periodic configurations.[^12] In every dimension: G injective implies G_P
and G_F injective; G_P or G_F surjective implies G surjective; G_P injective implies G_P
surjective; and G injective implies G_F surjective. In 1D two more hold: G_P injective
implies G injective, and G surjective implies G_P surjective.[^13] Three small rules show
that the other implications fail:[^14]

- **XOR**, the two-state rule f(x, y) = x + y mod 2 on neighbourhood (0, 1). It is
  injective on finite configurations but not surjective on them: a single 1 has two
  infinite predecessors and no finite one.
- **CONTROLLED-XOR**, with four states ab. The bit a never changes. When a = 1 the cell
  applies XOR to its second bit, and when a = 0 it does nothing. It is surjective on finite
  configurations but not injective, since two all-active configurations with complementary
  second bits have the same image.
- **SNAKE-XOR**, a 2D rule whose control layer holds SNAKES tiles
  ([[wang-tiles](pages/wang-tiles.md)]). It is injective on periodic configurations but
  not injective. On a periodic configuration every infinite arrow path must reach an
  inactive cell.

In two or more dimensions three implications are open: does G_P injective imply G_F
surjective, does G_F surjective imply G_P surjective, and does G surjective imply G_P
surjective?[^15] Both sides of the theorem can be decided for 1D rules (Amoroso and Patt,
1972) and neither can for 2D rules (Kari)
([[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)]).[^16]

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - Theorem 6 in the G / G_F form; Theorem 7 and the XOR counterexamples; open implications in 2D
- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - Theorem 2, the sufficient direction, and inequality (1)
- [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] - the necessary direction
- [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] - the modern statement in d dimensions, both proofs, amenable groups

## Related Concepts

- [[garden-of-eden](pages/garden-of-eden.md)] - the configurations the theorem is about
- [[erasable-configuration](pages/erasable-configuration.md)] - the equivalent condition
- [[amenable-group](pages/amenable-group.md)] - the groups on which the theorem holds
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the radius-1 neighbourhood behind the boundary count
- [[self-reproduction](pages/self-reproduction.md)] - what the theorem limits
- [[cellular-automaton](pages/cellular-automaton.md)] - the setting
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - Hedlund's 1D form of the theorem
- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] - Hedlund's paper, where the 1D form appears
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - injective CA are surjective, hence reversible
- [[wang-tiles](pages/wang-tiles.md)] - the SNAKES tile set behind SNAKE-XOR and 2D undecidability
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - decidable in 1D, undecidable in 2D
[^1]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.26 - "THEOREM 2. For a tessellation structure for which there exist erasable configurations, there exist Garden-of-Eden configurations."
[^2]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.686 - "Thus we have proved that the existence of two indistinguishable configurations is a necessary as well as a sufficient condition for the existence of Garden-of-Eden configurations."
[^3]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.685 n.2 [synthesis] - the referee pointed out that two mutually erasable configurations in Moore's sense is equivalent to two configurations which cannot be distinguished
[^4]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] Thms 1-2, Cor 1 [synthesis] L10-36 - "surjective d-dimensional cellular automata are pre-injective"; "pre-injective d-dimensional cellular automata are surjective"; "An injective d-dimensional cellular automaton is surjective."
[^5]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] Lemma 1 and proofs [synthesis] L5-8,L40-127 - arbitrary dimension; neighbourhood the cube of radius r; (a^(k^d) − 1)^(n^d) < a^((kn − 2r)^d); side-kn patterns split into n^d sub-patterns of side k; Myhill's proof uses a fixed q₀ and q₁ = f(q₀, …, q₀)
[^6]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] closing paragraph [synthesis] L129-133 - Theorems 1 and 2 hold on amenable groups; "Moore's theorem, in fact, characterizes amenable groups"
[^7]: https://arxiv.org/abs/1605.09133 abstract (abstract read, paper not read) - "A group G is amenable if and only if every cellular automaton with carrier G that has gardens of Eden also has mutually erasable patterns."
[^8]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.26-28 [synthesis] - k² sub-arrays of an n × n erasable size; relation R* has at most (A^(n²) − 1)^(k²) classes, each leading to one configuration at T + 1; the (kn − 2) × (kn − 2) interior has A^((kn−2)²) configurations; inequality (1) holds for large k; the unreachable state is Garden-of-Eden
[^9]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] pp.685-686 [synthesis] - under the assumption that every pair is distinguishable, at least A^((kn−2)²) kn × kn configurations are sequents and not Garden-of-Eden; at most (A^(n²) − 1)^(k²) avoid a copy of G; contradiction with Moore's inequality for large k
[^10]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.28-29 [synthesis] - the six assumptions (homogeneous, discrete, local, Euclidean, deterministic, erasing possible); assumption (6) is vital
[^11]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23-24 - "no self-reproducing configuration can contain a copy of a Garden-of-Eden configuration."
[^12]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.15 - "Theorem 6 (Garden-of-Eden theorem, Moore [53] and Myhill [55]). G_F is injective if and only if G is surjective."
[^13]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.15 [synthesis] - Theorem 7: implications in every dimension d and additional implications for one-dimensional CA; Figs. 6 and 7
[^14]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.16-17 [synthesis] - XOR f(x, y) = x + y (mod 2), injective on finite configurations, a single 1 has two infinite predecessors but no finite ones; CONTROLLED-XOR surjective on finite configurations, not injective; SNAKE-XOR not injective but injective on periodic configurations by the plane-filling property
[^15]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.17 [synthesis] - "Fig. 7 contains three implications whose status is unknown"; Open problem 2
[^16]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.19 [synthesis] - Theorem 9 (Amoroso and Patt); Theorem 10 (Kari): no algorithms for 2D injectivity or surjectivity
