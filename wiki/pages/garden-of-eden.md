---
title: Garden-of-Eden Configuration
category: Concepts
summary: A cellular-automaton configuration that has no predecessor and so can only occur at time zero (Moore); stub pending the Moore and Myhill ingests
tags: [concept, garden-of-eden, moore, myhill, surjectivity]
sources: [tsra-part2-ch5, endomorphisms-and-automorphisms-of-the-shift-dynamical-system]
created: 2026-09-24
updated: 2026-09-24
---

# Garden-of-Eden Configuration

> **Stub.** The definition and the Moore/Myhill attribution come from a footnote in Burks's
> Ch. 5 of [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)].
> Moore (1962) and Myhill (1963) are cited via that footnote and have not been read yet.
> The one-dimensional section below rests on Hedlund (1969), which does not use the term;
> its connection to Garden-of-Eden configurations is own reasoning.

## Description

Moore called a configuration that can exist only at time zero a "Garden-of-Eden"
configuration. It cannot arise from any earlier configuration.[^1]

**Relation to constructibility.** Every Garden-of-Eden configuration is non-constructible,
since nothing can build a pattern that has no predecessor. The converse fails: a
configuration can have predecessors and still be unbuildable by any constructor. Burks
gives an example in [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] (a 3 × 3
block of sensitized S₀ in C₀₀; see
[[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)]).[^1][^2]

**Existence.** In Burks's words, Moore "established a necessary condition" for
Garden-of-Eden configurations to exist in a cellular structure where information takes at
least one time step to pass from a cell to its neighbors, and Myhill showed the condition is
also sufficient. Burks says the condition amounts to the structure not being "backwards
deterministic", in the sense of Burks and Wang. Which direction each paper proves is to be
checked against Moore and Myhill directly.[^1]

**One dimension (own reasoning, from Hedlund's theorems).** Hedlund (1969) studies the
global maps of 1D cellular automata as continuous shift-commuting maps of the space of
all infinite configurations. He never says "Garden of Eden", but several of his results
translate directly:

- A 1D global map fails to be onto iff some *finite* block has no preimage block
  (Thm 5.1). A 1D Garden-of-Eden configuration therefore always contains a finite
  Garden-of-Eden pattern, which cannot occur in any configuration that has a
  predecessor.[^3]
- If the map is onto, two distinct configurations that differ on only finitely many
  cells never have the same image (Cor 9.4). If the map is not onto, the proof of
  Thm 5.12 builds two distinct blocks P ≠ P* with a common border A that give the same
  image (Lemma 5.11). Placed in the same surroundings, they become two configurations
  differing on finitely many cells with the same image. Together these give "a
  Garden-of-Eden configuration exists iff two finitely-different configurations
  collide" for 1D rules. That is presumably the equivalence Burks attributes to Moore
  and Myhill, but it is not checked against their papers.[^4][^5]
- A one-to-one global map is onto (Thm 5.14), so an invertible rule has no
  Garden-of-Eden configurations.[^6]
- For a rule that is not onto, some *periodic* configuration has uncountably many
  predecessors (Thm 5.12). This is the opposite extreme: too many predecessors rather
  than none.[^5]
- For onto rules the count is tightly controlled: every length-m pattern has exactly
  S^(n−1) predecessor patterns (Thm 5.4). See
  [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)].[^7]

## Appearances in Sources

- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] — footnote 12 to §5.3.1, relating non-constructibility to Moore and Myhill
- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] — the 1D theory of onto and non-onto global maps, without the term (connection is own reasoning)

## Related Concepts

- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] — the class a constructor can build; Garden-of-Eden patterns lie wholly outside it
- [[universal-constructor](pages/universal-constructor.md)] — no constructor can build a Garden-of-Eden pattern
- [[cellular-automaton](pages/cellular-automaton.md)] — the general setting
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] — a 1D rule has no Garden-of-Eden configuration exactly when its global map is onto
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] — invertible 1D rules, which have none

[^1]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 n.12 [synthesis] — Moore called a configuration that can exist only at time zero a "Garden-of-Eden" configuration; every such configuration is non-constructible, not conversely; Moore established a necessary condition for their existence where information needs at least 1 unit of time to pass between neighbors; Myhill showed it is also sufficient; the condition is essentially non-backwards-determinism (Burks and Wang)
[^2]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 [synthesis] — the 3 × 3 configuration of sensitized S₀ surrounded by C₀₀ is not constructible
[^3]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.326-327 [synthesis] — Thm 5.1: f∞ is onto iff every f_m: 𝔅_(m+n−1)(S) → 𝔅_m(S) is onto
[^4]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.346 [synthesis] — Cor 9.4: if distinct doubly asymptotic y, z have f∞(y) = f∞(z), then f∞ is not onto
[^5]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.330-331 [synthesis] — Lemma 5.11: blocks P ≠ P* and an (n − 1)-block A with f(APA) = f(AP*A); Thm 5.12: if f∞ is not onto, some periodic x has uncountable preimage
[^6]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.331-332 [synthesis] — Thm 5.14: A(S) = H(S); a one-to-one endomorphism is onto
[^7]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.327-328 [synthesis] — Thm 5.4: f∞ onto iff card f_m⁻¹(B) = S^(n−1) for every m-block B
