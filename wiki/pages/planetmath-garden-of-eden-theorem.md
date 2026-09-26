---
title: Garden-of-Eden Theorem (PlanetMath)
category: Sources
summary: PlanetMath entry stating and proving the Moore and Myhill theorems for cellular automata on ℤᵈ with a radius-r neighbourhood - surjective ⇔ pre-injective - and their extension to amenable groups
tags: [garden-of-eden, moore, myhill, surjectivity, injectivity, amenable-group]
sources: [planetmath-garden-of-eden-theorem]
created: 2026-09-24
updated: 2026-09-26
---

# Garden-of-Eden Theorem (PlanetMath)

**Source:** raw/planetmath-garden-of-eden-theorem.md, cached from https://planetmath.org/gardenofedentheorem. Entry by Ziosilvio, PlanetMath, 2013. MSC 68Q80, 37B15.
**Date ingested:** 2026-09-24
**Type:** article (encyclopedia entry)

## Summary

The entry states both halves of the [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]
in modern form, for a cellular automaton 𝒜 = ⟨Q, 𝒩, f⟩ on ℤᵈ with finitely many states.
Moore's theorem says that two mutually erasable patterns
([[erasable-configuration](pages/erasable-configuration.md)]) force an *orphan pattern*,
a finite pattern with no preimage ([[garden-of-eden](pages/garden-of-eden.md)]). In other
words, surjective cellular automata are *pre-injective*. Myhill's theorem is the converse:
an orphan pattern forces two mutually erasable patterns, so pre-injective automata are
surjective. An injective automaton is therefore surjective.[^1] Moore stated his theorem in
the plane, but it holds in every dimension.[^2]

Both proofs rest on one lemma. For a > 0, d ≥ 1, r ≥ 1, k ≥ 1 and all large enough n,

(a^(k^d) − 1)^(n^d) < a^((kn − 2r)^d).

With a = |Q| and the neighbourhood the cube of radius r, a pattern of side kn has
a^((kn)^d) possible contents, and its image is a pattern of side kn − 2r. The inequality
holds for large n because log_a(a^(k^d) − 1) < k^d while (k − 2r/n)^d → k^d.[^3] Moore's
proof splits a side-kn pattern into n^d sub-patterns of side k. If two side-k patterns are
mutually erasable, each sub-pattern has at most |Q|^(k^d) − 1 effectively different
contents, so at most (|Q|^(k^d) − 1)^(n^d) side-(kn − 2r) patterns have a preimage. By the
lemma some pattern has none.[^4] Myhill's proof counts the other way. If p is an orphan of
side k, the non-orphan side-kn patterns avoid p in every sub-block, so there are at most
(|Q|^(k^d) − 1)^(n^d) of them. Fix any state q₀ and let q₁ = f(q₀, …, q₀). The lemma then
gives more configurations equal to q₀ outside a side-(kn − 2r) cube than configurations
equal to q₁ outside a slightly larger cube that are not Gardens of Eden. Since the former map
onto the latter, two of them share an image, and those two are mutually erasable.[^5] No
quiescent state is needed; any constant background works.

Both theorems extend from ℤᵈ to cellular automata on
[[amenable-group](pages/amenable-group.md)]s (Ceccherini-Silberstein, Machì and
Scarabotti, 1999). Moore's theorem characterizes amenable groups (Bartholdi, 2010).[^6]
Myhill's theorem characterizes them too (Bartholdi and Kielak, 2016).[^7]

## Key Takeaways

- Surjective ⇔ pre-injective for cellular automata on ℤᵈ, in every dimension d and for
  every neighbourhood radius r.[^1][^3]
- Injective ⇒ surjective follows as a corollary.[^1]
- A single counting lemma, (a^(k^d) − 1)^(n^d) < a^((kn − 2r)^d), gives both directions.
  It generalizes Moore's inequality (1). The roles of k and n are swapped relative to
  Moore: here k is the sub-block side and n the number of sub-blocks per side.[^3]
- Myhill's direction needs only some constant background, not a quiescent state.[^5]
- The theorem holds exactly on amenable groups.[^6][^7]

## Entities & Concepts

- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] - the theorem stated and proved
- [[garden-of-eden](pages/garden-of-eden.md)] - orphan patterns
- [[erasable-configuration](pages/erasable-configuration.md)] - mutually erasable patterns; pre-injectivity
- [[amenable-group](pages/amenable-group.md)] - the groups on which the theorem holds
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - the d = 1 case, where Hedlund's theorems give the same equivalence
- [[edward-f-moore](pages/edward-f-moore.md)], [[john-myhill](pages/john-myhill.md)] - the two authors
- [[notation-map](pages/notation-map.md)] - the k/n swap against Moore
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - Corollary 1: injective implies surjective

## Relation to Other Wiki Pages

This entry restates [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)]
(Moore, 1962) and [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)]
(Myhill, 1963) for any dimension and radius. It supplies the modern vocabulary of orphans,
surjectivity and pre-injectivity. In one dimension the same equivalence appears in
[[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)],
and the corollary injective ⇒ surjective is Hedlund's Thm 5.14 there.

[^1]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] Thms 1-2, Cor 1 [synthesis] L10-36 - Theorem 1 (Moore): two mutually erasable patterns ⇒ an orphan pattern, "surjective d-dimensional cellular automata are pre-injective"; Theorem 2 (Myhill): an orphan pattern ⇒ two mutually erasable patterns, "pre-injective d-dimensional cellular automata are surjective"; Corollary 1: "An injective d-dimensional cellular automaton is surjective."
[^2]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] intro L5-8 - "Though originally stated for cellular automata on the plane, it works in arbitrary dimension."
[^3]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] Lemma 1 [synthesis] L40-76 - inequality (1) for large n; neighbourhood (2) the cube |xᵢ| ≤ r; pattern and image counts for side kn and kn − 2r; proof via log_a(a^(k^d) − 1) < k^d and lim (k − 2r/n)^d = k^d.
[^4]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] proof of Moore's theorem [synthesis] L78-101 - erasable pair on a side-k cube; relation ρ with at most |Q|^(k^d) − 1 classes; ρₙ on side-kn patterns split into n^d sub-patterns; at most (|Q|^(k^d) − 1)^(n^d) side-(kn − 2r) patterns have a preimage; Lemma 1 gives an orphan
[^5]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] proof of Myhill's theorem [synthesis] L103-127 - orphan p of side k; νₙ ≤ (|Q|^(k^d) − 1)^(n^d); fixed q₀ and q₁ = f(q₀, …, q₀); more configurations equal to q₀ outside {0, …, kn − 2r − 1}^d than non-Garden-of-Eden configurations equal to q₁ outside {−r, …, kn − 1}^d; two with the same image are mutually erasable
[^6]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] closing paragraph and refs [synthesis] L129-150 - Theorems 1 and 2 hold on amenable groups [Ceccherini-Silberstein, Machì, Scarabotti 1999]; "Moore's theorem, in fact, characterizes amenable groups" [Bartholdi 2010]
[^7]: https://arxiv.org/abs/1605.09133 abstract (abstract read, paper not read) - Bartholdi and Kielak (2016): "A group G is amenable if and only if every cellular automaton with carrier G that has gardens of Eden also has mutually erasable patterns."
