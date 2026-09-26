---
title: Garden-of-Eden Configuration
category: Concepts
summary: A cellular-automaton configuration with no predecessor, which can occur only at time zero; they exist exactly when erasable configurations do (Moore 1962, Myhill 1963)
tags: [concept, garden-of-eden, moore, myhill, surjectivity]
sources: [cgol-ch5-glider-synthesis, cgol-ch1-early-life, machine-models-of-self-reproduction, tsra-part2-ch5, converse-of-moores-garden-of-eden-theorem, endomorphisms-and-automorphisms-of-the-shift-dynamical-system, statistical-mechanics-of-cellular-automata, planetmath-garden-of-eden-theorem, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-25
---

# Garden-of-Eden Configuration

## Description

A **Garden-of-Eden configuration** is a pattern that no configuration at time T − 1 can
turn into at time T. It can therefore occur only at time 0, where initial conditions are
set by hand. [[edward-f-moore](pages/edward-f-moore.md)] named it in 1962, on a suggestion from John W. Tukey, after the account
in Genesis.[^1] A finite pattern that cannot occur in any successor is also called an
*orphan*; a configuration containing one is a Garden of Eden.[^2]

**Moore's theorem.** Moore's Theorem 2: "For a tessellation structure for which there
exist erasable configurations, there exist Garden-of-Eden configurations."[^3] An
[[erasable-configuration](pages/erasable-configuration.md)] is a pair of distinct patterns
with the same surroundings that become identical after one step.

**The proof.** Suppose an n × n block can hold an erasable configuration. Divide a
kn × kn block into k² such sub-blocks. Patterns that agree up to erasure in every sub-block
lead to the same next state, so at most (A^(n²) − 1)^(k²) distinct successors can appear
in the (kn − 2) × (kn − 2) interior, where A is the number of cell states. The interior has
A^((kn−2)²) possible patterns. The loss from erasure grows with k², while the loss from the
boundary layer grows only with k, so for large k the first count is smaller. Some interior
pattern is then unreachable, and it is a Garden-of-Eden configuration.[^4]

**Assumptions.** Moore lists six: the universe is homogeneous, space and time are
discrete, action is local, space is Euclidean N-space, the laws are deterministic, and
erasing is possible. Local action plays the role of a finite speed of light, confining
outside influence to a thin boundary. Euclidean space supplies regions whose interior is
arbitrarily large relative to their boundary. Erasing is vital: a structure from earlier in
his paper satisfies the other five and has no Garden-of-Eden configurations.[^5] He
suggests that a similar result in a model of modern physics would mean some states of the
universe "are describable but not attainable".[^6]

**Relation to self-reproduction and constructibility.** Since nothing produces a
Garden-of-Eden configuration, no self-reproducing configuration can contain one.[^7] Moore
reads it as a machine "which cannot be built out of the available parts, but whose
physical structure can be described as an arrangement of those parts".[^8] Every
Garden-of-Eden configuration is non-constructible, but not every non-constructible pattern
is Garden-of-Eden. Burks gives a pattern in
[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] that has predecessors yet
cannot be built: a 3 × 3 block of sensitized S₀ in C₀₀
([[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)]).[^9][^10]

**Size.** Moore's proof gives very large Garden-of-Eden patterns. In every structure he
examined in detail, one of size 5 × 5 or smaller existed.[^11]

**The converse.** [[john-myhill](pages/john-myhill.md)] proved that the condition is also
necessary: if a structure has Garden-of-Eden configurations, it has two configurations that
no environment can tell apart, which is equivalent to Moore's mutual erasability.[^12]
Together the two results are the [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]. Burks, in a footnote to
TSRA Ch. 5, says the condition amounts to the structure not being "backwards
deterministic" in the sense of Burks and Wang.[^9]

**One dimension (own reasoning, from Hedlund's theorems).** Hedlund (1969) studies the
global maps of 1D cellular automata as continuous shift-commuting maps of the space of
all infinite configurations. He never says "Garden of Eden", but several of his results
translate directly:

- A 1D global map fails to be onto iff some *finite* block has no preimage block
  (Thm 5.1). A 1D Garden-of-Eden configuration therefore always contains a finite
  Garden-of-Eden pattern, which cannot occur in any configuration that has a
  predecessor.[^13]
- If the map is onto, two distinct configurations that differ on only finitely many
  cells never have the same image (Cor 9.4). If the map is not onto, the proof of
  Thm 5.12 builds two distinct blocks P ≠ P* with a common border A that give the same
  image (Lemma 5.11). Placed in the same surroundings, they become two configurations
  differing on finitely many cells with the same image. Together these give "a
  Garden-of-Eden configuration exists iff two finitely-different configurations
  collide" for 1D rules. Two colliding finitely-different configurations are an
  [[erasable-configuration](pages/erasable-configuration.md)], so one direction is the 1D
  case of Moore's theorem, and the other is the 1D case of Myhill's converse (own
  reasoning).[^14][^15]
- A one-to-one global map is onto (Thm 5.14), so an invertible rule has no
  Garden-of-Eden configurations.[^16]
- For a rule that is not onto, some *periodic* configuration has uncountably many
  predecessors (Thm 5.12). This is the opposite extreme: too many predecessors rather
  than none.[^15]
- For onto rules the count is tightly controlled: every length-m pattern has exactly
  S^(n−1) predecessor patterns (Thm 5.4). See
  [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)].[^17]

**How common they are.** Wolfram links Garden-of-Eden configurations to irreversibility.
When a rule sends several configurations to the same one, some configurations have no
predecessor at all. He cites Moore (1962, [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)]) and Aggarwal (1973) as giving criteria for their
existence, which he calls "equivalent to irreversibility".[^18] On a finite ring of N
cells they are the typical case. There the non-additive rule 126 leaves a fraction of
configurations unreachable that tends to 1 as N grows (about 1 − 0.88ᴺ). The additive
[[rule-90](pages/rule-90.md)] leaves exactly half or three quarters of the ring's
configurations unreachable, and only the identity rule 204 reaches everything.[^19] These
counts hold only on the ring. On the infinite line rule 90 is a
[[permutive-map](pages/permutive-map.md)], hence onto, and has no Garden-of-Eden
configurations at all (own reasoning, from the 1D section above). See
[[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)].

**In the Game of Life.** In [[game-of-life](pages/game-of-life.md)], the existence proof
needs only that a [[block](pages/block.md)] and a pre-block evolve the same way. Split a
6n × 6n square into n² tiles of 6 × 6. A tile holding a centred block can always be
swapped for one holding a pre-block without changing the next generation, so at most
(2^36 − 1)^(n²) patterns can appear in the central (6n − 2) × (6n − 2) square after one
step, out of 2^((6n−2)²) possible. For large n the first number is smaller, so some
central pattern has no parent.[^20] The ratio of the two counts tends to 0, so almost all
large patterns are Gardens of Eden. The argument proves more: it gives *orphans*,
patterns that stay parentless whatever surrounds them. Every pattern containing an
orphan is a Garden of Eden, and every Garden of Eden contains an orphan.[^21]

- **Construction.** An orphan can be built one cell at a time along a spiral, choosing
  each new cell's state to minimize the count of parents; this reaches zero parents after
  266 cells.[^22]
- **Smallest known orphans.** 45 live cells (Beluchenko, 2009); 88 specified live and
  dead cells, and a bounding box of area 96 = 8 × 12 (both Eker).[^23] None fits in a
  6 × 7 box.[^24]
- **Thin patterns.** Every pattern of height 1 has a parent, with an explicit
  construction. No orphan has height 2 or 3, one of height 5 exists, and height 4 is
  open.[^24]
- **Only-from-itself patterns.** Some configurations, if present at any generation,
  must have been present unchanged at every earlier one. A 306-cell still life contains
  one, so it cannot be constructed ([[object-synthesis](pages/object-synthesis.md)]).[^25]
- **Deeper ancestry.** Some patterns have parents but no grandparents: one has 17,920
  parents, all Gardens of Eden. For every n ≥ 1 there are patterns with a
  great^n-grandparent but no great^(n+1)-grandparent (Törmä and Salo, 2022).[^26]

**The computer-science view.** Kari (2005) defines Garden-of-Eden configurations as
configurations without a pre-image, which exist exactly when G is not surjective.[^27]
They are the first configurations to drop out of the [[limit-set](pages/limit-set.md)],
since none can appear after the first step.[^28] Whether a rule has any can be decided for
1D rules (Amoroso and Patt, 1972) but not for 2D rules (Kari).[^29]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - §1.7: the Life existence proof, orphans, smallest known orphans, thin patterns, grandparentless patterns
- [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] - orphan patterns; the theorem in d dimensions and on amenable groups
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - the definition via non-surjectivity; decidable in 1D, undecidable in 2D; transient configurations and limit sets
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Garden-of-Eden configurations as a consequence of irreversibility, and how common they are in 1D rules and Life
- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - the definition, the name, Theorem 2 and its proof, the six assumptions
- [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] - the converse: Garden-of-Eden configurations require indistinguishable pairs
- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] - footnote 12 to §5.3.1, relating non-constructibility to Moore and Myhill
- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] - the 1D theory of onto and non-onto global maps, without the term (connection is own reasoning)

## Related Concepts

- [[amenable-group](pages/amenable-group.md)] - the groups on which Garden-of-Eden configurations exist exactly when erasable ones do
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - the many-to-one evolution that produces them
- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] - the if-and-only-if result
- [[erasable-configuration](pages/erasable-configuration.md)] - the condition equivalent to Garden-of-Eden configurations existing
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the radius-1 neighbourhood behind the boundary-layer count
- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] - the class a constructor can build; Garden-of-Eden patterns lie wholly outside it
- [[universal-constructor](pages/universal-constructor.md)] - no constructor can build a Garden-of-Eden pattern
- [[self-reproduction](pages/self-reproduction.md)] - no self-reproducer contains one
- [[cellular-automaton](pages/cellular-automaton.md)] - the general setting
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - a 1D rule has no Garden-of-Eden configuration exactly when its global map is onto
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] - invertible 1D rules, which have none
- [[limit-set](pages/limit-set.md)] - configurations that survive every number of steps
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - whether a rule has any is decidable only in 1D
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - reversible rules, which have none

[^1]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.23 [synthesis] - configurations that "cannot occur except at time T = 0"; no configuration at T − 1 gives rise to them; "Such a configuration will be called a Garden-of Eden configuration. This term, from the Biblical account in the second and third chapters of Genesis, was suggested by John W. Tukey."
[^2]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] Thms 1-2 [synthesis] L10-32 - Theorem 1 concludes that the automaton "has an orphan pattern"; the proof of Myhill's theorem counts configurations that "are not Gardens of Eden" by the orphan patterns they avoid (L103-122)
[^3]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.26 - "THEOREM 2. For a tessellation structure for which there exist erasable configurations, there exist Garden-of-Eden configurations."
[^4]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.26-28 [synthesis] - kn × kn array of k² n × n sub-arrays; relation R* has at most (A^(n²) − 1)^(k²) classes, each leading to one configuration at T + 1; inequality (1) against A^((kn−2)²); erasure loss grows with k², boundary loss with k; the unreachable state p is the Garden-of-Eden configuration
[^5]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.28-29 [synthesis] - the six assumptions and how each is used; local action corresponds to information not travelling faster than light; Euclidean space gives interiors arbitrarily large relative to boundaries; assumption (6) is vital, with one of the paper's structures as counterexample
[^6]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.29 - "it might have some cosmological interest in indicating that certain states of the physical universe are describable but not attainable."
[^7]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23-24 - "Since a Garden-of-Eden configuration cannot be produced by any other configuration, no self-reproducing configuration can contain a copy of a Garden-of-Eden configuration."
[^8]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.28 - "This also corresponds to a machine which cannot be built out of the available parts, but whose physical structure can be described as an arrangement of those parts."
[^9]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 n.12 [synthesis] - every Garden-of-Eden configuration is non-constructible, not conversely; Moore established a condition for their existence where information needs at least 1 unit of time to pass between neighbours; Myhill showed the converse; the condition is essentially non-backwards-determinism (Burks and Wang)
[^10]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 [synthesis] - the 3 × 3 configuration of sensitized S₀ surrounded by C₀₀ is not constructible
[^11]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.30 [synthesis] - the proof of Theorem 2 gives a very large array; 5 × 5 or smaller sufficed in every structure Moore examined in detail
[^12]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.686 - "the existence of two indistinguishable configurations is a necessary as well as a sufficient condition for the existence of Garden-of-Eden configurations."
[^13]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.326-327 [synthesis] — Thm 5.1: f∞ is onto iff every f_m: 𝔅_(m+n−1)(S) → 𝔅_m(S) is onto
[^14]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.346 [synthesis] — Cor 9.4: if distinct doubly asymptotic y, z have f∞(y) = f∞(z), then f∞ is not onto
[^15]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.330-331 [synthesis] — Lemma 5.11: blocks P ≠ P* and an (n − 1)-block A with f(APA) = f(AP*A); Thm 5.12: if f∞ is not onto, some periodic x has uncountable preimage
[^16]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.331-332 [synthesis] — Thm 5.14: A(S) = H(S); a one-to-one endomorphism is onto
[^17]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.327-328 [synthesis] — Thm 5.4: f∞ onto iff card f_m⁻¹(B) = S^(n−1) for every m-block B
[^18]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.623 n.10 — "The existence of unreachable or 'garden-of-Eden' configurations in cellular automata is discussed in Moore (1962) and Aggarwal (1973), where criteria (equivalent to irreversibility) for their occurrence are given."
[^19]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.623 [synthesis] — rule 204 is unique in allowing all configurations to be reached; rule 90 reaches half (N odd) or ¼ (N even); rule 126 unreachable fraction tends to one, behaving as 1 − λᴺ with λ ≈ 0.88 (Martin et al. 1983, cited via this paper)
[^20]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.20-21 [synthesis] - Theorem 1.1 (Existence of Gardens of Eden); proof with 6 × 6 tiles, block vs pre-block (Fig. 1.33); at most (2^36 − 1)^(n²) children against 2^((6n−2)²) central patterns
[^21]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.22-23 [synthesis] - n.30 the ratio "can be made as small as we like ... almost all large patterns are Gardens of Eden"; "Patterns like this one that cannot be any part of the evolution of another pattern ... are called orphans"; "Every pattern containing an orphan is (by definition) a Garden of Eden, and remarkably the converse is also true"; n.35 the proof "actually demonstrates the existence of orphans"
[^22]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.22 [synthesis] - cells added "in a clockwise spiral", each chosen alive or dead to give fewer parents; "after 266 cells the pattern has no parents at all"
[^23]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.23, Fig. 1.36 - "(a) An orphan with 45 live cells, found by Nicolay Beluchenko in 2009. (b) An orphan with 88 specified cells, found by Steven Eker in 2017. (c) An orphan in a bounding box with area 96 = 8 × 12, found by Steven Eker in 2016"
[^24]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.23-25 [synthesis] - "there does not exist an orphan that fits within a 6 × 7 bounding box"; Theorem 1.2 (No Thin Gardens of Eden) with constructive proof; no orphans 2 or 3 cells high; "there does exist an orphan ... with height 5"; "whether or not there exists an orphan whose bounding box is 4 cells high remains open"
[^25]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.147 - "a configuration of live and dead cells with the property that, if it occurs at any generation, then it must occur at the same location in all previous generations. There is a 306-cell still life that contains this configuration"
[^26]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.25-26 [synthesis] - a pattern with "17 920 distinct parents, every single one of which is a Garden of Eden"; n.42: Törmä and Salo (January 2022), for every n ≥ 1 a pattern with a great^n-grandparent but no great^(n+1)-grandparent
[^27]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.15 - "If G is not surjective then there exist Garden-of-Eden configurations, that is, configurations without a pre-image."
[^28]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.23 - "For example, Garden of Eden configurations cannot appear after the first update."
[^29]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.19 [synthesis] - Theorem 9 (Amoroso and Patt): 1D surjectivity decidable; Theorem 10 (Kari): 2D surjectivity undecidable
