---
title: Garden-of-Eden Configuration
category: Concepts
summary: A cellular-automaton configuration with no predecessor, which can occur only at time zero; Moore (1962) proved they exist in any structure with erasable configurations
tags: [concept, garden-of-eden, moore, myhill, surjectivity]
sources: [machine-models-of-self-reproduction, tsra-part2-ch5, endomorphisms-and-automorphisms-of-the-shift-dynamical-system]
created: 2026-09-24
updated: 2026-09-24
---

# Garden-of-Eden Configuration

## Description

A **Garden-of-Eden configuration** is a pattern that no configuration at time T − 1 can
turn into at time T. It can therefore occur only at time 0, where initial conditions are
set by hand. Moore named it in 1962, on a suggestion from John W. Tukey, after the account
in Genesis.[^1]

**Moore's theorem.** Moore's Theorem 2: "For a tessellation structure for which there
exist erasable configurations, there exist Garden-of-Eden configurations."[^2] An
[[erasable-configuration](pages/erasable-configuration.md)] is a pair of distinct patterns
with the same surroundings that become identical after one step.

**The proof.** Suppose an n × n block can hold an erasable configuration. Divide a
kn × kn block into k² such sub-blocks. Patterns that agree up to erasure in every sub-block
lead to the same next state, so at most (A^(n²) − 1)^(k²) distinct successors can appear
in the (kn − 2) × (kn − 2) interior, where A is the number of cell states. The interior has
A^((kn−2)²) possible patterns. The loss from erasure grows with k², while the loss from the
boundary layer grows only with k, so for large k the first count is smaller. Some interior
pattern is then unreachable, and it is a Garden-of-Eden configuration.[^3]

**Assumptions.** Moore lists six: the universe is homogeneous, space and time are
discrete, action is local, space is Euclidean N-space, the laws are deterministic, and
erasing is possible. Local action plays the role of a finite speed of light, confining
outside influence to a thin boundary. Euclidean space supplies regions whose interior is
arbitrarily large relative to their boundary. Erasing is vital: a structure from earlier in
his paper satisfies the other five and has no Garden-of-Eden configurations.[^4] He
suggests that a similar result in a model of modern physics would mean some states of the
universe "are describable but not attainable".[^5]

**Relation to self-reproduction and constructibility.** Since nothing produces a
Garden-of-Eden configuration, no self-reproducing configuration can contain one.[^6] Moore
reads it as a machine "which cannot be built out of the available parts, but whose
physical structure can be described as an arrangement of those parts".[^7] Every
Garden-of-Eden configuration is non-constructible, but not every non-constructible pattern
is Garden-of-Eden. Burks gives a pattern in
[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] that has predecessors yet
cannot be built: a 3 × 3 block of sensitized S₀ in C₀₀
([[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)]).[^8][^9]

**Size.** Moore's proof gives very large Garden-of-Eden patterns. In every structure he
examined in detail, one of size 5 × 5 or smaller existed.[^10]

**The converse.** Burks, in a footnote to TSRA Ch. 5, says Myhill proved the converse
condition, and that the condition amounts to the structure not being "backwards
deterministic" in the sense of Burks and Wang.[^8] Myhill (1963), "The converse of Moore's
Garden-of-Eden theorem", has not been ingested yet.

**One dimension (own reasoning, from Hedlund's theorems).** Hedlund (1969) studies the
global maps of 1D cellular automata as continuous shift-commuting maps of the space of
all infinite configurations. He never says "Garden of Eden", but several of his results
translate directly:

- A 1D global map fails to be onto iff some *finite* block has no preimage block
  (Thm 5.1). A 1D Garden-of-Eden configuration therefore always contains a finite
  Garden-of-Eden pattern, which cannot occur in any configuration that has a
  predecessor.[^11]
- If the map is onto, two distinct configurations that differ on only finitely many
  cells never have the same image (Cor 9.4). If the map is not onto, the proof of
  Thm 5.12 builds two distinct blocks P ≠ P* with a common border A that give the same
  image (Lemma 5.11). Placed in the same surroundings, they become two configurations
  differing on finitely many cells with the same image. Together these give "a
  Garden-of-Eden configuration exists iff two finitely-different configurations
  collide" for 1D rules. Two colliding finitely-different configurations are an
  [[erasable-configuration](pages/erasable-configuration.md)], so one direction is the 1D
  case of Moore's theorem (own reasoning). The other direction is presumably Myhill's
  converse, not yet checked against his paper.[^12][^13]
- A one-to-one global map is onto (Thm 5.14), so an invertible rule has no
  Garden-of-Eden configurations.[^14]
- For a rule that is not onto, some *periodic* configuration has uncountably many
  predecessors (Thm 5.12). This is the opposite extreme: too many predecessors rather
  than none.[^13]
- For onto rules the count is tightly controlled: every length-m pattern has exactly
  S^(n−1) predecessor patterns (Thm 5.4). See
  [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)].[^15]

## Appearances in Sources

- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - the definition, the name, Theorem 2 and its proof, the six assumptions
- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] - footnote 12 to §5.3.1, relating non-constructibility to Moore and Myhill
- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] - the 1D theory of onto and non-onto global maps, without the term (connection is own reasoning)

## Related Concepts

- [[erasable-configuration](pages/erasable-configuration.md)] - the condition that forces Garden-of-Eden configurations
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the radius-1 neighbourhood behind the boundary-layer count
- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] - the class a constructor can build; Garden-of-Eden patterns lie wholly outside it
- [[universal-constructor](pages/universal-constructor.md)] - no constructor can build a Garden-of-Eden pattern
- [[self-reproduction](pages/self-reproduction.md)] - no self-reproducer contains one
- [[cellular-automaton](pages/cellular-automaton.md)] - the general setting
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - a 1D rule has no Garden-of-Eden configuration exactly when its global map is onto
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] - invertible 1D rules, which have none

[^1]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.23 [synthesis] - configurations that "cannot occur except at time T = 0"; no configuration at T − 1 gives rise to them; "Such a configuration will be called a Garden-of Eden configuration. This term, from the Biblical account in the second and third chapters of Genesis, was suggested by John W. Tukey."
[^2]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.26 - "THEOREM 2. For a tessellation structure for which there exist erasable configurations, there exist Garden-of-Eden configurations."
[^3]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.26-28 [synthesis] - kn × kn array of k² n × n sub-arrays; relation R* has at most (A^(n²) − 1)^(k²) classes, each leading to one configuration at T + 1; inequality (1) against A^((kn−2)²); erasure loss grows with k², boundary loss with k; the unreachable state p is the Garden-of-Eden configuration
[^4]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.28-29 [synthesis] - the six assumptions and how each is used; local action corresponds to information not travelling faster than light; Euclidean space gives interiors arbitrarily large relative to boundaries; assumption (6) is vital, with one of the paper's structures as counterexample
[^5]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.29 - "it might have some cosmological interest in indicating that certain states of the physical universe are describable but not attainable."
[^6]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23-24 - "Since a Garden-of-Eden configuration cannot be produced by any other configuration, no self-reproducing configuration can contain a copy of a Garden-of-Eden configuration."
[^7]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.28 - "This also corresponds to a machine which cannot be built out of the available parts, but whose physical structure can be described as an arrangement of those parts."
[^8]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 n.12 [synthesis] - every Garden-of-Eden configuration is non-constructible, not conversely; Moore established a condition for their existence where information needs at least 1 unit of time to pass between neighbours; Myhill showed the converse; the condition is essentially non-backwards-determinism (Burks and Wang)
[^9]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 [synthesis] - the 3 × 3 configuration of sensitized S₀ surrounded by C₀₀ is not constructible
[^10]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.30 [synthesis] - the proof of Theorem 2 gives a very large array; 5 × 5 or smaller sufficed in every structure Moore examined in detail
[^11]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.326-327 [synthesis] — Thm 5.1: f∞ is onto iff every f_m: 𝔅_(m+n−1)(S) → 𝔅_m(S) is onto
[^12]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.346 [synthesis] — Cor 9.4: if distinct doubly asymptotic y, z have f∞(y) = f∞(z), then f∞ is not onto
[^13]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.330-331 [synthesis] — Lemma 5.11: blocks P ≠ P* and an (n − 1)-block A with f(APA) = f(AP*A); Thm 5.12: if f∞ is not onto, some periodic x has uncountable preimage
[^14]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.331-332 [synthesis] — Thm 5.14: A(S) = H(S); a one-to-one endomorphism is onto
[^15]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.327-328 [synthesis] — Thm 5.4: f∞ onto iff card f_m⁻¹(B) = S^(n−1) for every m-block B
