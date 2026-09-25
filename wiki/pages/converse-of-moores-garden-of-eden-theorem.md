---
title: "The Converse of Moore's Garden-of-Eden Theorem (Myhill, 1963)"
category: Sources
summary: Myhill's two-page note proving that two indistinguishable (mutually erasable) configurations are necessary as well as sufficient for Garden-of-Eden configurations, completing the Garden-of-Eden theorem
tags: [myhill, moore, garden-of-eden, erasable-configuration, surjectivity, injectivity]
sources: [converse-of-moores-garden-of-eden-theorem]
created: 2026-09-24
updated: 2026-09-24
---

# The Converse of Moore's Garden-of-Eden Theorem (Myhill, 1963)

**Source:** raw/myhill-converse-of-moore-garden-of-eden-theorem.pdf. Myhill, J. (1963). The converse of Moore's Garden-of-Eden theorem. *Proceedings of the American Mathematical Society, 14*(4), 685-686. http://www.jstor.org/stable/2034301
**Date ingested:** 2026-09-24
**Type:** paper (shorter note)

## Summary

Myhill, at Stanford, builds directly on
[[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] and
uses its terminology. Moore had shown that two mutually erasable configurations are a
*sufficient* condition for [[garden-of-eden](pages/garden-of-eden.md)] configurations.
Myhill shows the condition is also *necessary*.[^1] Together the two papers give the
[[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]: a tessellation structure has
Garden-of-Eden configurations exactly when it has two configurations that no surrounding
can tell apart.[^2]

He restates the condition in terms of **environments**. An environment fixes the state of
every cell except one square hole. Inserting a configuration C into environment E gives
E(C), and the *sequent* E(C)′ is the state of the whole universe one step later. Two
configurations of the same size are *distinguished* by E if their sequents differ.[^3] The
referee pointed out that having two mutually erasable configurations in Moore's sense is
equivalent to having two configurations that no environment distinguishes
([[erasable-configuration](pages/erasable-configuration.md)]).[^4]

The proof reuses Moore's counting. Assume every pair of configurations can be
distinguished and that a Garden-of-Eden configuration G of side n exists. A lemma shows
that any two configurations are then distinguished by the all-passive environment. So each
of the A^((kn−2)²) configurations of a (kn − 2) × (kn − 2) block, placed in a quiescent
plane, gives a different kn × kn successor, and none of those successors is
Garden-of-Eden. But any block containing a copy of G is Garden-of-Eden, and at most
(A^(n²) − 1)^(k²) kn × kn blocks avoid G. For large k that is fewer than
A^((kn−2)²), which contradicts Moore's inequality.[^5]

## Key Takeaways

- **Necessary and sufficient.** "the existence of two indistinguishable configurations is a
  necessary as well as a sufficient condition for the existence of Garden-of-Eden
  configurations."[^2]
- **Moore's direction is sufficiency.** Moore proved that erasability *implies*
  Garden-of-Eden configurations; Myhill supplies the reverse implication.[^1]
- **The lemma.** If some two configurations have identical sequents in the all-passive
  environment, surrounding each with a passive border of width 2 gives two configurations
  with identical sequents in *every* environment.[^6]
- **Same inequality, used backwards.** Moore's inequality (A^(n²) − 1)^(k²) < A^((kn−2)²)
  drives both directions.[^5]
- **A convention on configurations.** Myhill identifies configurations that differ only by
  a translation, but does not identify a configuration with the same configuration
  surrounded by blank cells. The lemma depends on this.[^7]
- **A stronger lemma.** The referee's equivalence rests on a strengthening: if every pair of
  distinct configurations is distinguished by *some* environment, every pair is
  distinguished by *every* environment of the right size.[^4]

## Entities & Concepts

- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]
- [[garden-of-eden](pages/garden-of-eden.md)]
- [[erasable-configuration](pages/erasable-configuration.md)]
- [[john-myhill](pages/john-myhill.md)]
- [[edward-f-moore](pages/edward-f-moore.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]

## Relation to Other Wiki Pages

This note answers the converse question left open by
[[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] and
reuses its inequality (1). Burks's footnote in [[tsra-part2-ch5](pages/tsra-part2-ch5.md)]
relates non-constructibility in von Neumann's structure to this pair of results.

[^1]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.685 - "Moore proves that the existence of two mutually erasable configurations in a tessellation universe is a sufficient condition for the existence of Garden-of-Eden configurations therein. We shall show that this condition is both necessary and sufficient."
[^2]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.686 - "Thus we have proved that the existence of two indistinguishable configurations is a necessary as well as a sufficient condition for the existence of Garden-of-Eden configurations."
[^3]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.685 [synthesis] - definitions of environment (all cells specified except a square piece), insertion E(C), sequent E(C)′ as the state at t = 1, and configurations distinguished by E when their sequents differ
[^4]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.685 n.2 [synthesis] - the referee pointed out that two mutually erasable configurations in Moore's sense is equivalent to two configurations which cannot be distinguished; the proof uses a strengthening of the Lemma: if every pair of distinct configurations is distinguished by some environment, every pair is distinguished by every environment of appropriate size
[^5]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] pp.685-686 [synthesis] - suppose every pair distinguishable and a Garden-of-Eden G of side n exists; at least A^((kn−2)²) sequent (non-Garden-of-Eden) kn × kn configurations; at most (A^(n²) − 1)^(k²) kn × kn configurations avoid G, and every configuration containing G is Garden-of-Eden; for large k this contradicts Moore's inequality (A^(n²) − 1)^(k²) < A^((kn−2)²)
[^6]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.686 - "LEMMA. Any two configurations have distinct sequents in the environment E₀ consisting entirely of passive cells. For if the configurations C₁ and C₂ had identical sequents in E₀, the configurations C₁* and C₂*, obtained by adjoining to C₁ and C₂ a border of passive cells of width 2, would have identical sequents in every environment."
[^7]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.685 n.3 [synthesis] - two copies of a configuration related by translation are identified; a configuration is not identified with itself surrounded by one or more layers of blank cells, which is essential to the Lemma
