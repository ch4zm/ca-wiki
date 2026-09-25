---
title: Endomorphisms and Automorphisms of the Shift Dynamical System
category: Sources
summary: Hedlund (1969), the founding paper on shift-commuting maps - the Curtis-Hedlund-Lyndon theorem (continuous shift-commuting maps are exactly block maps), balanced preimages and bounded multiplicity for onto maps, Welch's L·M·R = S^(n-1), Rothaus's cross-section theorem, and the rich automorphism group of the full shift
tags: [hedlund, symbolic-dynamics, shift, block-map, curtis-hedlund-lyndon, surjectivity, automorphism-group, one-dimensional]
sources: [endomorphisms-and-automorphisms-of-the-shift-dynamical-system]
created: 2026-09-24
updated: 2026-09-24
---

# Endomorphisms and Automorphisms of the Shift Dynamical System

**Source:** raw/hedlund-1969-endomorphisms-automorphisms-shift.pdf (G. A. Hedlund, *Mathematical Systems Theory* 3(4), 1969, pp. 320–375; PDF pp. 1–56; https://doi.org/10.1007/BF01691062)
**Date ingested:** 2026-09-24
**Type:** paper

> Hedlund writes about symbolic dynamics and never uses the words "cellular automaton",
> "Moore", "Myhill", or "Garden of Eden". Every link below between his results and cellular
> automata is **own reasoning**, and is labeled that way where it appears. Citations use
> the journal's printed page numbers.

## Summary

The setting is the [[shift-dynamical-system](pages/shift-dynamical-system.md)]: the space
X(S) of all two-way infinite sequences over a finite alphabet of S ≥ 2 symbols, under the
left shift σ. Hedlund studies the continuous maps of X(S) into itself that commute with σ,
which he calls endomorphisms. A *block map* reads each window of n consecutive symbols and
writes one symbol, the same way at every position. The foundational result, due to Curtis,
Hedlund and Lyndon, is that these block maps composed with powers of the shift are
*exactly* the endomorphisms
([[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)]). Every
question about endomorphisms therefore becomes a finite, combinatorial question about
block maps.[^1][^2]

Most of the paper is about onto (surjective) endomorphisms
([[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)]). A block map
of window n is onto exactly when every finite block has a preimage. It is also onto
exactly when every m-block has *exactly* S^(n−1) preimage blocks. An onto map sends at
most S^(n−1) points to any one point. A map that is not onto sends uncountably many
points to some periodic point. Distinct preimages of a point under an onto map can never
agree on both tails. Almost every point has the same number M of preimages. Welch
refines M into three multiplicative indices with L·M·R = S^(n−1). Rothaus shows that an
onto map has a continuous inverse selection exactly when it is uniformly μ-to-one. The
class of [[permutive-map](pages/permutive-map.md)]s gives the standard onto examples.[^3]

The automorphisms (invertible endomorphisms) form a group
([[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)]). One-to-one
already forces onto. Beyond shifts and symbol permutations the group is large: it
contains a copy of every finite group, and two involutions whose product has infinite
order. Hedlund presents the paper as the detailed version of results gathered over
about ten years from Curtis, Lyndon, Welch, Gleason, Rothaus, Blankenship and others, and
calls it "the work of many."[^4]

## Key Takeaways

- **Continuous + shift-commuting = block map.** Φ(S), the set of all endomorphisms, is
  exactly {σ^m f∞}: a block map f∞ composed with a power of the shift. Φ(S) is
  countable.[^2]
- **Onto ⇔ no missing block ⇔ balanced.** f∞ is onto iff each finite block has a
  preimage block. Equivalently, every m-block has exactly S^(n−1) preimage blocks.[^5]
- **Onto maps have bounded fibers.** An onto f∞ sends at most S^(n−1) points to any one
  point. A non-onto map sends an uncountable set to some periodic point.[^6]
- **One-to-one ⇒ onto.** Every injective endomorphism is surjective, and so is an
  automorphism.[^7]
- **Onto ⇒ no finite "collisions".** If two distinct points agree outside a finite
  stretch (doubly asymptotic), an onto map cannot send them to the same image.[^8]
- **Almost-everywhere constant degree.** For onto f∞ there is an integer M(f) with
  exactly M(f) preimages at every *bilaterally transitive* point (one in which every
  finite block occurs both arbitrarily far left and arbitrarily far right). Every point has at least
  M(f) preimages. M is multiplicative under composition.[^9]
- **Welch indices.** Onto f∞ also carries a left index L(f) and a right index R(f), both
  multiplicative, with L(f)·M(f)·R(f) = S^(n−1).[^10]
- **Consequences.** f∞ is permutive in the leftmost variable iff L(f) = 1. f∞ is exactly
  S^(n−1)-to-one iff it is permutive at both ends (Rothaus). When S is prime, φ^q = σ^p
  forces q | p, so σ has no continuous q-th root for any q > 1.[^11]
- **Rich automorphism group.** Every finite group embeds in A(S), and in A(S) modulo the
  shifts. A(S) also contains two involutions whose product has infinite order.[^12]

## Structure of the paper

| § | Content |
|---|---|
| 1–2 | Bisequence space, metric, shift; expansive systems are exactly subshifts (Thm 2.1) |
| 3 | Block maps; Curtis–Hedlund–Lyndon (Thm 3.4) |
| 4–5 | Window-1 maps; onto criteria, balanced preimages (Blankenship–Rothaus, Thm 5.4), multiplicity bounds, injective ⇒ onto (Thm 5.14) |
| 6 | Permutive maps; Σ ⊂ A ⊂ E ⊂ Φ with each gap infinite; finite groups inside A(S) |
| 7–8 | Recurrence classes of points; which are preserved by φ; the image of φ |
| 9–10 | Separation of preimages; Welch's theorem for recurrent points |
| 11 | Gleason–Welch: constant multiplicity M(f) on bilaterally transitive points |
| 12 | Recurrence properties pulled back through onto maps |
| 13–15 | Composition; M, L, R multiplicative; L·M·R = S^(n−1) |
| 16–17 | Rothaus: cross-sections; permutive at both ends ⇔ exactly S^(n−1)-to-one |
| 18 | Roots of shift powers (Welch); two-symbol inverse pairs |
| 19 | For prime S, every block map is a polynomial over GF(S) |
| 20 | Two involutions with product of infinite order |

## Further results

**Subshifts.** Any closed, shift-invariant subset of X(S) is a *subdynamical system*
(subshift). Theorem 2.1 says a homeomorphism of a compact, totally disconnected metric
space is expansive iff it is isomorphic to some subshift. The shift is also
topologically mixing, and its periodic points are countable and dense.[^13]

**The image of an endomorphism.** When the image of φ has more than one point, it is
a subshift. It has dense periodic points and a bilaterally transitive point, it is
topologically mixing, and it is again a Cantor set.[^14]

**Recurrence forward and backward.** Every endomorphism preserves periodicity, almost
periodicity, and recurrence. If φ is onto, the reverse also holds: every preimage of a
periodic, almost periodic, recurrent, or transitive point has the same property. For a
non-onto map this fails. "Regularly almost periodic" and "isochronous" are not pulled back
even by onto maps.[^15]

**Polynomials.** When S is prime, every block map of window n is given by a polynomial
over the finite field GF(S) with S elements, of degree at most S − 1 in each variable.[^16]

**Stated as open.** Hedlund reports that nothing has been proved about the apparent
relative sizes of these classes. The non-onto maps look "more numerous", and the
automorphisms look "relatively sparse".[^17] He also leaves open whether a single point
anywhere with S^(n−1) preimages already forces an exactly S^(n−1)-to-one map. Theorem 17.2
proves this only when the point is bilaterally transitive.[^18]

## Relation to cellular automata (own reasoning)

None of this section is in the paper.

- A one-dimensional cellular automaton on a finite alphabet, with neighbourhood of radius
  r, has a global map on X(S) that is exactly σ^(−r) f∞ for a block map f with window
  n = 2r + 1. Theorem 3.4 then says the global maps of 1D cellular automata are exactly
  the continuous, shift-commuting maps of X(S). This topological characterization is the
  form in which later literature usually cites Hedlund.
- Theorem 5.1 says f∞ is not onto iff some finite block has no preimage. A block with no
  preimage is a finite pattern that can occur only at time zero: the one-dimensional form
  of a [[garden-of-eden](pages/garden-of-eden.md)] configuration.
- Corollary 9.4 (onto ⇒ distinct points that differ on finitely many cells have
  distinct images) and Lemma 5.11 (not onto ⇒ two distinct blocks P ≠ P* with a common
  border A and f(APA) = f(AP*A)) together give both directions of "surjective ⇔ no two
  finitely-different configurations collide" in one dimension. Lemma 5.11 turns into a
  collision by placing APA and AP*A in the same surroundings. That is the one-dimensional
  shape of the Moore–Myhill relationship as the wiki's Garden-of-Eden page describes it.
  Moore's theorem gives "collide ⇒ Garden of Eden" and Myhill's converse the other
  direction ([[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]).
- Theorem 5.14 (injective ⇒ surjective) is the 1D statement that a cellular automaton
  whose global map loses no information has no Garden-of-Eden patterns.
- The [[cellular-automaton](pages/cellular-automaton.md)] page records that von Neumann
  judged one dimension unlikely to support self-reproduction. Hedlund's paper runs in the
  opposite direction: one dimension is where the global theory of these maps is sharpest.

## Entities & Concepts

- [[shift-dynamical-system](pages/shift-dynamical-system.md)] — the space X(S) and the shift σ
- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] — endomorphisms = block maps
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] — onto criteria, multiplicity, Welch indices, Rothaus's theorem
- [[permutive-map](pages/permutive-map.md)] — the standard source of onto, non-injective maps
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] — A(S) and what it contains
- [[garden-of-eden](pages/garden-of-eden.md)] — the 1D form of non-surjectivity (own reasoning)
- [[cellular-automaton](pages/cellular-automaton.md)] — 1D global maps are exactly Hedlund's endomorphisms (own reasoning)

## Relation to Other Wiki Pages

Von Neumann's program builds one particular two-dimensional rule for self-reproduction.
This paper asks global questions about *every* rule in one dimension: which rules are
onto, which are invertible, how many predecessors a configuration has. It supplies the
one-dimensional theory behind [[garden-of-eden](pages/garden-of-eden.md)], whose general
form is Moore's theorem
([[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)]) and
Myhill's converse
([[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)]).
It also adds a topological definition of the global map to
[[cellular-automaton](pages/cellular-automaton.md)]. Its notation is mapped in
[[notation-map](pages/notation-map.md)].

[^1]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.320-321 [synthesis] — X(S) is the set of bisequences over S, 1 < card S < ∞, with the shift σ; continuous shift-commuting maps are the endomorphisms; block maps; "It has been shown by Curtis, Hedlund and Lyndon that these mappings, composed with powers of the shift, constitute the entire class of continuous transformations which commute with the shift"
[^2]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.323-325 [synthesis] — definition of F(S, n) and f∞ by y_i = f(x_i ⋯ x_{i+n−1}); Thm 3.1 (continuous, commutes with σ); Thm 3.4 F*(S) = Φ(S), credited to Curtis, Hedlund and Lyndon; card Φ(S) = ℵ₀
[^3]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.321, 326-334, 345-346, 351, 362, 364 [synthesis] — Thm 5.1 (onto iff every f_m onto); Thm 5.4 (exactly S^(n−1) preimage blocks); Thm 5.5 (≤ S^(n−1) preimages); Thm 5.12 (non-onto: uncountable preimage of a periodic point); Thm 9.3-9.5 (preimage separation); Thm 11.2 (M(f)); Thm 14.9 (L·M·R = S^(n−1)); Thm 16.1 (Rothaus); Thm 6.6-6.7 (permutive maps)
[^4]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.321-322 — "results obtained over a period of some ten years, and which have not appeared in print … it should be clear that this paper is the work of many"; intro credits Curtis, Lyndon, Gleason, Welch, Rothaus, and (p.327) Blankenship
[^5]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.326-328 [synthesis] — Thm 5.1: f∞ onto iff each f_m: 𝔅_{m+n−1}(S) → 𝔅_m(S) is onto; Thm 5.4 (Blankenship and Rothaus): f∞ onto iff card f_m⁻¹(B) = S^(n−1) for every m-block B and every m
[^6]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.328, 331 [synthesis] — Thm 5.5: f∞ onto implies card f∞⁻¹(x) ≤ S^(n−1) for all x; Thm 5.12-5.13: if not onto, there is a periodic x with uncountable preimage
[^7]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.331-332 [synthesis] — H(S), the one-to-one members of Φ(S); Thm 5.14: A(S) = H(S), since by Thm 5.13 a one-to-one φ is onto and hence a homeomorphism
[^8]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.346 [synthesis] — Cor 9.4: if distinct doubly asymptotic y, z have f∞(y) = f∞(z), then f∞ is not onto
[^9]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.351-352, 358 [synthesis] — Gleason and Welch by different methods; Thm 11.1 (every point has ≥ M(x) preimages for bilaterally transitive x); Thm 11.2 (constant M(f) on BT(S)); Thm 11.5; Thm 13.5 M(φψ) = M(φ)M(ψ)
[^10]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.358-359, 362-363 [synthesis] — R(f), L(f) "first defined by L. R. Welch" via maximal compatible extensions; Thm 14.9 L(f)M(f)R(f) = S^(n−1); Thm 15.1 L and R multiplicative
[^11]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.370-371 [synthesis] — Lemma 17.1 (permutive in x₁ iff L(f) = 1, in x_n iff R(f) = 1); Thm 17.2 (Rothaus: permutive in both ⇔ exactly S^(n−1)-to-one); Thm 18.1-18.2 (Welch: S prime and φ^q = σ^p imply q divides p); intro p.321: "the shift transformation σ has no continuous roots if card S is a prime"
[^12]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.336-338, 373-374 [synthesis] — Thm 6.13 (Curtis, Hedlund, Lyndon): every finite group is isomorphic to a subgroup of A(S); Cor 6.15 (same for A(S)/Σ(S)); Thm 20.1-20.2: two elements of order two whose product has infinite order, in A(S) and in A(S)/Σ(S)
[^13]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.322-323, 339, 341 [synthesis] — subdynamical systems; Thm 2.1 (expansive ⇔ isomorphic to a subshift); Remark 7.6 (periodic points invariant, countable, dense); Remark 7.17 (topologically mixing)
[^14]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.342 [synthesis] — Thm 8.2: if card φ(X(S)) > 1, the image is a closed invariant set with dense periodic points, bilaterally transitive points, topologically mixing, homeomorphic to the Cantor discontinuum
[^15]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.341-343, 345, 352, 355-357 [synthesis] — Thm 8.1 (forward invariance); p.343 counterexample for non-onto maps; Thm 9.1 (periodic), Cor 12.5 (almost periodic), Cor 12.8 (recurrent), Cor 12.11 (transitive) pulled back when φ is onto; Remark 12.1 (regularly almost periodic and isochronous not pulled back)
[^16]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.372-373 [synthesis] — Thm 19.1: S prime implies F_P(S, n) = F(S, n), polynomials of degree at most S − 1 in each variable over GF(S)
[^17]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.321 — "It appears that the set Φ(S) − E(S) is in some sense more numerous than the set E(S) and that the set A(S) is relatively sparse, but nothing has been proved in this direction."
[^18]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.370-371 — "It is not known whether the same conclusion can be reached if it is assumed that card f∞⁻¹(x) = S^(n−1) for some x ∈ X(S)."
