---
title: Curtis–Hedlund–Lyndon Theorem
category: Concepts
summary: The continuous maps of the full shift that commute with the shift are exactly the sliding block maps (composed with shift powers) - equivalently, the global maps of one-dimensional cellular automata are exactly the continuous shift-commuting maps
tags: [concept, theorem, curtis-hedlund-lyndon, block-map, sliding-block-code, symbolic-dynamics, one-dimensional]
sources: [endomorphisms-and-automorphisms-of-the-shift-dynamical-system]
created: 2026-09-24
updated: 2026-09-24
---

# Curtis–Hedlund–Lyndon Theorem

## Description

**Block maps.** Take a window length n ≥ 1 and any function f from n-blocks over S to
single symbols. There are S^(S^n) such functions. f induces a map f∞ on the
[[shift-dynamical-system](pages/shift-dynamical-system.md)] X(S) by sliding the window
along the sequence:

  [f∞(x)]_i = f(x_i x_(i+1) ⋯ x_(i+n−1))  for every i.

f also acts on finite blocks. f_m sends an (m + n − 1)-block to an m-block.[^1]

Every f∞ is continuous and commutes with σ: output symbol i depends only on a bounded
window around position i, and the same f is applied at every position.[^2] A shift σ^k
is itself a block map of window n exactly when 0 ≤ k ≤ n − 1. Negative shifts need an
explicit factor σ^m because Hedlund's window starts at position i.[^3]

**The theorem.** Let Φ(S) be the set of *all* continuous maps X(S) → X(S) that commute
with σ. Then

  Φ(S) = { σ^m f∞ : m ∈ ℤ, f a block map }.

Hedlund credits the result to M. L. Curtis, G. A. Hedlund and R. C. Lyndon.[^4]

**Proof idea.** Given φ ∈ Φ(S), split X(S) into the clopen sets U_i = {x : x₀ = i}, and
pull them back: V_i = φ⁻¹(U_i). By compactness there is a k such that points in
different V_i differ within the central (2k + 1)-block. Therefore the central
(2k + 1)-block of x determines [φ(x)]₀. Commuting with σ spreads this local rule to every
coordinate, and φ = σ^(−k) f∞ for a block map f of window 2k + 1.[^5]

**Consequences in the paper.** Φ(S) is countable, since each window size contributes
finitely many block maps.[^6] More importantly, every result proved for block maps f∞
transfers directly to all endomorphisms. Hedlund proves each theorem for f∞, then
restates it for φ ∈ Φ(S) "by Theorem 3.4".[^7] The composite of block maps is a block
map: (fg)∞ = f∞ g∞, with window m + n − 1.[^8]

**Cellular-automaton reading (own reasoning).** A 1D
[[cellular-automaton](pages/cellular-automaton.md)] with radius-r neighbourhood has
global map σ^(−r) f∞, where f is its local rule on windows of 2r + 1 cells. The theorem
therefore says that the global maps of 1D cellular automata on S states are *exactly* the
continuous, translation-commuting self-maps of X(S). Later literature usually cites
Hedlund for this topological definition of a cellular automaton.

## Appearances in Sources

- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] — §3, Thm 3.4, proved in full

## Related Concepts

- [[shift-dynamical-system](pages/shift-dynamical-system.md)] — the space and the shift
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] — the onto members of Φ(S)
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] — the invertible members of Φ(S)
- [[permutive-map](pages/permutive-map.md)] — a class of block maps with easily computed behaviour
- [[cellular-automaton](pages/cellular-automaton.md)] — 1D global maps are exactly Φ(S) (own reasoning)
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - block maps with S = 2, window 3
- [[notation-map](pages/notation-map.md)] - Hedlund's symbols

[^1]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.323-324 [synthesis] — n-blocks, F(S, n) as maps 𝔅_n(S) → S with card F(S, n) = S^(S^n); f_m: 𝔅_(m+n−1)(S) → 𝔅_m(S); f∞(x) = y with y_i = f(x_i x_(i+1) ⋯ x_(i+n−1))
[^2]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.324 [synthesis] — Thm 3.1: f∞ is continuous and commutes with σ
[^3]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.324 [synthesis] — Lemma 3.3: σ^k ∈ F∞(S, n) iff 0 ≤ k ≤ n − 1; σ^k ∉ F∞(S) for k < 0 when card S > 1
[^4]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.324 — "The basic result that the last two sets are identical is due to M. L. Curtis, G. A. Hedlund and R. C. Lyndon. 3.4 THEOREM. F*(S) = Φ(S)."
[^5]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.324-325 [synthesis] — proof of Thm 3.4: clopen U_i and V_i = φ⁻¹(U_i); k with d ≥ (1 + k)⁻¹ between different V_i; classes 𝔅_i of central (2k + 1)-blocks; f(B) = i for B ∈ 𝔅_i; φ = σ^(−k) f∞
[^6]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.325 [synthesis] — card Φ(S) = ℵ₀, since card F(S, n) = S^(S^n) and the powers of σ are distinct
[^7]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.328-329, 331, 347, 350, 352 [synthesis] — e.g. Thm 5.6, 5.13, Cor 9.6, Cor 10.6, Thm 11.5: results for f∞ transferred to Φ(S) or E(S) via Thm 3.4
[^8]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.357 [synthesis] — for f ∈ F(S, m), g ∈ F(S, n), fg maps (m + n − 1)-blocks to symbols; Remark 13.1 (fg)∞ = f∞ g∞
