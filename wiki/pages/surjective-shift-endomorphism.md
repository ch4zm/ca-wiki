---
title: Surjective Shift Endomorphism
category: Concepts
summary: Onto block maps of the full shift - onto iff no finite block is missing iff every block has exactly S^(n-1) preimages; bounded fibers, no finite collisions, a constant degree M on transitive points, Welch's L·M·R = S^(n-1), and Rothaus's cross-section theorem
tags: [concept, surjectivity, block-map, preimage, welch-indices, symbolic-dynamics, one-dimensional]
sources: [endomorphisms-and-automorphisms-of-the-shift-dynamical-system]
created: 2026-09-24
updated: 2026-09-24
---

# Surjective Shift Endomorphism

## Description

E(S) is the set of onto endomorphisms of the
[[shift-dynamical-system](pages/shift-dynamical-system.md)]. By the
[[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)], each is σ^m f∞
for a block map f of some window n. Such a map is onto iff f∞ is, so everything below is
stated for f∞.[^1] Hedlund's picture is a sharp split: onto maps are finite-to-one and
behave uniformly, and non-onto maps collapse uncountable sets.[^2]

### Deciding surjectivity

- **No missing block.** f∞ is onto iff every finite block has at least one preimage
  block (Thm 5.1).[^3]
- **Balanced.** f∞ is onto iff every m-block has *exactly* S^(n−1) preimage blocks, for
  every m (Thm 5.4, Blankenship and Rothaus).[^4]
- **Bounded.** f∞ is onto iff the number of preimage blocks is bounded over all block
  lengths (Thm 5.9). A non-onto map has blocks with arbitrarily many preimages.[^5]
- **Composition.** φψ is onto iff both φ and ψ are (Thm 13.3).[^6]

### Fibers

- An onto f∞ sends at most S^(n−1) points to any one point (Thm 5.5).[^7] This does not
  make it exactly k-to-one. For every n ≥ 3 there are onto f∞ whose fiber size varies from
  point to point.[^8]
- A non-onto f∞ has a *periodic* point with uncountably many preimages (Thm 5.12).[^9]
- **Injective ⇒ onto.** A one-to-one endomorphism is onto, and so is an automorphism
  (Thm 5.14).[^10]

### How preimages are separated

Two points y ≠ z with the same image under an onto map cannot agree on both tails. If
they agree far left and far right, the map is not onto (Cor 9.4). For onto f∞ with
window n ≥ 2, exactly one of the following holds: y and z agree on the right tail and
their (n − 1)-windows differ everywhere far left; the mirror case; or their (n − 1)-windows
differ everywhere far out on both sides (Thm 9.5).[^11] If the image point is recurrent,
distinct preimages have different (n − 1)-windows at *every* position: they are *totally
(n − 1)-separated* (Thm 10.5, Welch).[^12]

### The degree M(f)

For onto f∞ there is an integer M(f), found independently by Gleason and Welch. Every
bilaterally transitive point has exactly M(f) preimages, and every point has at least
M(f) (Thms 11.1-11.2).[^13] M can be read off finite blocks: it is the least, over all
blocks B, of the largest (n − 1)-separated set of preimages of B (Thm 11.4). M is
multiplicative: M(φψ) = M(φ)M(ψ).[^14]

### Welch's indices L and R

L. R. Welch attached two more integers to an onto f∞. R(f) is the largest number of right
extensions of a block that f cannot tell apart, meaning they all have the same image.
L(f) is the same count for left extensions. Both are independent of the block chosen, as
long as it has length at least n − 1.[^15] The central identity is

  L(f) · M(f) · R(f) = S^(n−1)  (Thm 14.9),

and L and R are multiplicative under composition, like M (Thm 15.1).[^16] Consequences:

- f is permutive in its leftmost variable iff L(f) = 1, and in its rightmost iff
  R(f) = 1 ([[permutive-map](pages/permutive-map.md)]).[^17]
- **Roots of the shift.** If S is prime and φ^q = σ^p for an endomorphism φ, then q divides
  p. The reason is that σ^p as a block map has L = S^p, so L(f)^q = S^p, and a prime S
  forces L(f) to be a power of S.[^18] In particular σ itself has no continuous q-th root
  for q > 1.[^19]

### Cross-sections (Rothaus)

A. Nerode asked when an onto f∞ has a continuous right inverse, a *cross-section*.
O. S. Rothaus answered for window n ≥ 2. The following are equivalent (Thm 16.1):[^20]

1. f∞ is exactly μ-to-one for some μ. Then μ = M(f).
2. f∞ is an open map.
3. f∞ has a cross-section.
4. Distinct preimages of every point are totally (n − 1)-separated.

Step (2) ⇒ (3) uses E. A. Michael's selection theorem.[^21] The same equivalence holds for
every φ ∈ E(S), with "totally (n − 1)-separated" replaced by "separated" (Thm 16.11).[^22]

### Pulling properties back

Onto maps pull back dynamical properties that arbitrary endomorphisms only push forward.
Every preimage of a periodic, almost periodic, recurrent, or transitive point under an
onto φ has the same property.[^23] This lets Hedlund show that a closed invariant
Y ⊂ X(S) with φ(Y) = X(S) must be all of X(S) (Thm 13.2).[^24]

### Cellular-automaton reading (own reasoning)

For a 1D [[cellular-automaton](pages/cellular-automaton.md)], "onto" means every
configuration has a predecessor. Thm 5.1 then says a non-surjective 1D rule always has a
*finite* orphan pattern, the 1D [[garden-of-eden](pages/garden-of-eden.md)]. Cor 9.4,
read with Lemma 5.11, says a 1D rule is surjective iff no two configurations that differ
on finitely many cells have the same successor, the 1D form of the
[[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] (surjective ⇔ pre-injective, stated for every dimension in
[[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)]). Thm 5.4 also gives a finite test:
count preimages of blocks. The balanced-preimage property is special to onto maps, since
non-onto maps have blocks with no preimage at all.

## Appearances in Sources

- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] — §§5, 9-18 develop the theory of onto maps

## Related Concepts

- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] — reduces every endomorphism to a block map
- [[permutive-map](pages/permutive-map.md)] — the simplest onto maps; L = 1 or R = 1
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] — the onto maps with exactly one preimage at every point
- [[garden-of-eden](pages/garden-of-eden.md)] — non-surjectivity seen from the configuration that has no predecessor (own reasoning)
- [[shift-dynamical-system](pages/shift-dynamical-system.md)] — the space the maps act on
- [[rule-90](pages/rule-90.md)] - onto on the infinite line
- [[notation-map](pages/notation-map.md)] - Hedlund's symbols

[^1]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.328-329 [synthesis] — E(S) defined as the onto members of Φ(S); proof of Thm 5.6: φ = σ^p f∞ is onto iff f∞ is onto, since σ is a bijection
[^2]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.321 [synthesis] — "There are sharp differences in behavior with respect to multiplicities between the members of E(S) and the members of Φ(S) − E(S)": uncountable preimages of a periodic point versus uniformly bounded preimage counts
[^3]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.326-327 [synthesis] — Thm 5.1: f∞ onto iff each f_m: 𝔅_(m+n−1)(S) → 𝔅_m(S) is onto, for all m
[^4]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.327-328 [synthesis] — Blankenship and Rothaus credited on p.327; Thm 5.4: f∞ onto iff card f_m⁻¹(B) = S^(n−1) for all B ∈ 𝔅_m(S) and all m
[^5]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.329-330 [synthesis] — Lemma 5.8 (not onto: blocks with more than k preimages for every k); Thm 5.9 (onto iff preimage counts are uniformly bounded)
[^6]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.357-358 [synthesis] — Thm 13.3: φψ is onto iff both φ and ψ are onto
[^7]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.328 [synthesis] — Thm 5.5: card f∞⁻¹(x) ≤ S^(n−1) for all x when f∞ is onto
[^8]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.328 — "Examples to be constructed subsequently show that for any n ∈ I₃, there exists f ∈ F(S, n) such that f∞ is onto but not an exactly k-to-1 map"
[^9]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.331 [synthesis] — Thm 5.12: if f∞ is not onto, some periodic x has uncountable f∞⁻¹(x); Thm 5.13 extends this to Φ(S)
[^10]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.331-332 [synthesis] — Thm 5.14: A(S) = H(S); a one-to-one φ is onto by Thm 5.13, hence a homeomorphism
[^11]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.345-346 [synthesis] — definitions of asymptotic and m-separated; Thm 9.3; Cor 9.4 (doubly asymptotic y ≠ z with equal images imply not onto); Thm 9.5 trichotomy
[^12]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.348-350 [synthesis] — "The following theorem is due to L. R. Welch"; Thm 10.5: f∞ onto, x recurrent, y ≠ z preimages of x imply y and z totally (n − 1)-separated
[^13]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.351 [synthesis] — "It has been proved by A. M. Gleason and L. R. Welch, using quite dissimilar methods"; Thm 11.1 and 11.2
[^14]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.351-352, 358 [synthesis] — Thm 11.4: M(f) = inf over blocks B of M(B, f), the largest (n − 1)-separated subset of f⁻¹(B); Thm 13.5 M(φψ) = M(φ)M(ψ)
[^15]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.358-359 [synthesis] — compatible right/left extensions; R(A, f) and L(A, f) as maximum cardinalities; "first defined by L. R. Welch"; Remark 14.3: R(A, f) is the same for every block A of length ≥ n − 1
[^16]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.362-363 [synthesis] — Thm 14.9 L(f)M(f)R(f) = S^(n−1); Thm 15.1 L(fg) = L(f)L(g), R(fg) = R(f)R(g)
[^17]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.370 [synthesis] — Lemma 17.1: for onto f∞, f is permutive in x₁ [x_n] iff L(f) = 1 [R(f) = 1]
[^18]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.371 [synthesis] — Thm 18.1: g = f^q with g∞ = σ^p; "It is easily verified that L(g) = S^p"; [L(f)]^q = S^p; S prime gives L(f) = S^λ and p = λq; Cor 18.2 extends to Φ(S)
[^19]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.321 — "the shift transformation σ has no continuous roots if card S is a prime"
[^20]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.364 [synthesis] — "A. Nerode raised the question as to conditions on f∞ … which are equivalent to the existence of a cross-section. O. S. Rothaus has given a definitive answer"; Thm 16.1 (1)-(4); Thm 16.3 (2) gives μ = M(f)
[^21]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.369 — "A continuous open map of a complete metric space onto a zero-dimensional paracompact space always has a cross-section." (E. A. Michael)
[^22]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.369-370 [synthesis] — Thm 16.11 for φ ∈ E(S), condition (4) "any two distinct members of φ⁻¹(x) are separated"
[^23]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.345, 355-357 [synthesis] — Thm 9.1 (periodic), Cor 12.5 (almost periodic), Cor 12.8 (recurrent), Cor 12.11 (transitive, one-sided and bilateral)
[^24]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.357 [synthesis] — Thm 13.2: if φ(Y) = X(S) for closed invariant Y, then Y = X(S), via a transitive point's transitive preimage
