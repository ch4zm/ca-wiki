---
title: Garden-of-Eden Theorem (Moore-Myhill)
category: Concepts
summary: A tessellation structure has Garden-of-Eden configurations if and only if it has two distinct configurations that no environment can tell apart; Moore (1962) proved "if", Myhill (1963) "only if"
tags: [concept, garden-of-eden, theorem, moore, myhill, surjectivity, injectivity]
sources: [machine-models-of-self-reproduction, converse-of-moores-garden-of-eden-theorem]
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
equivalent to injectivity on finite patterns. This framing, and the name "Moore-Myhill
theorem" often used for it, are the wiki's own summary of later usage rather than wording
from either paper.

**Why it works.** Both directions rest on one counting inequality. Take a kn × kn block
divided into k² sub-blocks of side n, with A states per cell. Moore's inequality (1) says
that for large k,

(A^(n²) − 1)^(k²) < A^((kn−2)²).

On the left is the number of kn × kn blocks when each sub-block has only A^(n²) − 1
effectively different contents. On the right is the number of patterns of the interior block one step later,
which is only two cells narrower because the neighbourhood has radius 1
([[moore-neighbourhood](pages/moore-neighbourhood.md)]).[^4]

- **Moore (2 ⇒ 1).** If an n × n pair is mutually erasable, each sub-block has at most
  A^(n²) − 1 effectively different contents. So at most the left side's number of
  successors occur in the interior, which is fewer than its A^((kn−2)²) possible
  patterns. Some interior pattern has no predecessor.[^4]
- **Myhill (1 ⇒ 2).** Suppose instead every pair is distinguishable and G is an n × n
  Garden-of-Eden pattern. Every (kn − 2) × (kn − 2) pattern placed in a quiescent plane
  then gives a different kn × kn successor, so at least A^((kn−2)²) kn × kn patterns are
  not Garden-of-Eden. Any block containing G is Garden-of-Eden, so at most
  (A^(n²) − 1)^(k²) blocks are not. For large k this contradicts the inequality.[^5]

**Assumptions.** Moore's proof assumes a homogeneous universe, discrete space and time,
local action, Euclidean space, deterministic laws, and the possibility of erasing. He calls
erasing vital.[^6]

**Consequence for self-reproduction.** No self-reproducing configuration can contain a
Garden-of-Eden pattern.[^7] In any structure with erasure, then, some describable machines
can never be built or reproduced.

## Appearances in Sources

- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - Theorem 2, the sufficient direction, and inequality (1)
- [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] - the necessary direction

## Related Concepts

- [[garden-of-eden](pages/garden-of-eden.md)] - the configurations the theorem is about
- [[erasable-configuration](pages/erasable-configuration.md)] - the equivalent condition
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the radius-1 neighbourhood behind the boundary count
- [[self-reproduction](pages/self-reproduction.md)] - what the theorem limits
- [[cellular-automaton](pages/cellular-automaton.md)] - the setting

[^1]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.26 - "THEOREM 2. For a tessellation structure for which there exist erasable configurations, there exist Garden-of-Eden configurations."
[^2]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.686 - "Thus we have proved that the existence of two indistinguishable configurations is a necessary as well as a sufficient condition for the existence of Garden-of-Eden configurations."
[^3]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.685 n.2 [synthesis] - the referee pointed out that two mutually erasable configurations in Moore's sense is equivalent to two configurations which cannot be distinguished
[^4]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.26-28 [synthesis] - k² sub-arrays of an n × n erasable size; relation R* has at most (A^(n²) − 1)^(k²) classes, each leading to one configuration at T + 1; the (kn − 2) × (kn − 2) interior has A^((kn−2)²) configurations; inequality (1) holds for large k; the unreachable state is Garden-of-Eden
[^5]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] pp.685-686 [synthesis] - under the assumption that every pair is distinguishable, at least A^((kn−2)²) kn × kn configurations are sequents and not Garden-of-Eden; at most (A^(n²) − 1)^(k²) avoid a copy of G; contradiction with Moore's inequality for large k
[^6]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.28-29 [synthesis] - the six assumptions (homogeneous, discrete, local, Euclidean, deterministic, erasing possible); assumption (6) is vital
[^7]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23-24 - "no self-reproducing configuration can contain a copy of a Garden-of-Eden configuration."
