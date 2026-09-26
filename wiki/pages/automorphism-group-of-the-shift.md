---
title: Automorphism Group of the Shift
category: Concepts
summary: A(S), the group of invertible shift-commuting maps of the full shift (the reversible 1D cellular automata, own reasoning); one-to-one already implies onto; contains every finite group and two involutions with product of infinite order, though no continuous roots of σ exist for prime S
tags: [concept, automorphism, group, reversibility, block-map, symbolic-dynamics, one-dimensional]
sources: [endomorphisms-and-automorphisms-of-the-shift-dynamical-system, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-26
---

# Automorphism Group of the Shift

## Description

An *automorphism* of the [[shift-dynamical-system](pages/shift-dynamical-system.md)] is a
homeomorphism of X(S) onto itself that commutes with σ. A(S) is the set of all of them,
and it is a group under composition.[^1] Invertibility comes free with injectivity: every
one-to-one endomorphism is onto, and its inverse is again continuous and shift-commuting
(Thm 5.14).[^2]

Hedlund's chain of classes is

  Σ(S) ⊂ A(S) ⊂ E(S) ⊂ Φ(S),

where Σ(S) = {σ^n} is the powers of the shift, E(S) the onto endomorphisms, and Φ(S) all
endomorphisms. Each difference Φ − E, E − A, and A − Σ is infinite.[^3]

**The easy automorphisms.** Permuting the symbols is an automorphism with window 1. A
window-1 map is onto, one-to-one, and a homeomorphism exactly when it permutes the
alphabet (Thm 4.1).[^4]

**A nontrivial example on three symbols.** On {0, 1, 2}, take the window-2 map

| f(ab) | b = 0 | b = 1 | b = 2 |
|---|---|---|---|
| a = 0 | 0 | 2 | 0 |
| a = 1 | 1 | 1 | 1 |
| a = 2 | 2 | 0 | 2 |

It swaps 0 and 2 at every position whose right neighbour is 1. Hedlund proves f∞ is
one-to-one, so it is an automorphism. It is not a power of σ, and no window-1 map equals
it.[^5] Hedlund also notes that f∞ composed with itself is the identity.[^6] That checks
directly (own reasoning): the swap never changes a 1, so a second pass swaps the same
positions back. On two symbols this cannot happen. There, f∞g∞ = identity forces both
maps to be the identity or both the complement (Thm 18.3, Curtis, Hedlund and
Lyndon).[^7]

**Every finite group embeds (Curtis, Hedlund, Lyndon).** A(S) contains a subgroup
isomorphic to any finite group G (Thm 6.13). The construction starts from a family 𝒞 of
*marker blocks* A 0 c₁⋯c_n 0 B, where A = 1^(n+1) and B is alternating 10⋯. No two blocks
of 𝒞 overlap one another (Lemma 6.12). Each permutation π of the n-blocks then gives a
map φ_π: wherever a marker block occurs, rewrite its middle c₁⋯c_n as π(c₁⋯c_n), and
leave everything else alone. Because markers cannot overlap, φ_π is well defined and
invertible, and π ↦ φ_π is a group homomorphism. That embeds the full symmetric group on
n-blocks, and with it any finite group, once n is large enough.[^8] The same holds
modulo the shifts, in A(S)/Σ(S) (Cor 6.15). So A(S) has elements of every finite order.[^9]

**Infinite order from two involutions.** Let α swap the symbols 0 and 1. Let β change the
symbol at i whenever x_(i−1) = 1, x_(i+1) = 0 and x_(i+2) = 1, so the window
x_(i−1) x_i x_(i+1) x_(i+2) switches between 1001 and 1101. Both are automorphisms of
order two. Their product αβ has infinite order, even modulo the shifts (Thms 20.1-20.2). The
proof exhibits a point x whose images under (αβ)^k never return to a translate of x.[^10]

**Roots.** When p = qk with q ≥ 2, σ^p has q-th roots that are not powers of σ: take an
automorphism ψ of order q and set φ = σ^k ψ.[^11] For prime S, Welch's index argument shows φ^q = σ^p forces q | p. So σ
has no continuous square root, cube root, and so on
([[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)]).[^12]

**Size.** Hedlund reports the impression that A(S) is "relatively sparse" among the
endomorphisms, and notes that nothing had been proved in that direction.[^13]

**The later name.** Kari (2005) confirms the cellular-automaton reading below as standard usage. Because a CA
is reversible iff it is bijective, symbolic dynamics calls reversible CA the automorphisms
of the shift, and CA its endomorphisms.[^14] The survey adds facts about this group that
Hedlund did not have. Universal computation is possible inside it: Morita and Harao (1989)
built computationally universal 1D reversible CA. The inverse of a 1D radius-½
automorphism with s states needs at most s − 1 consecutive cells, and the bound is tight.
Every element is a block-permutation rule composed with a translation, and the shift σ
itself needs the translation part
([[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)],
[[margolus-neighbourhood](pages/margolus-neighbourhood.md)]).[^15]

**Cellular-automaton reading (own reasoning).** A(S) is the group of 1D
[[cellular-automaton](pages/cellular-automaton.md)] global maps that are invertible, whose
inverse is again a cellular automaton, over the full space of infinite configurations.
Thm 5.14 is the 1D statement that a rule which loses no information has no
[[garden-of-eden](pages/garden-of-eden.md)] patterns and can be run backwards by another
local rule.

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - reversible CA are called automorphisms of the shift; universal reversible 1D CA; inverse neighbourhood bound; block representation
- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] — §§5-6 (definition, existence), §18 (inverse pairs, roots), §20 (infinite order)

## Related Concepts

- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] — why every automorphism and its inverse are block maps
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] — the larger class E(S) and Welch's indices
- [[permutive-map](pages/permutive-map.md)] — on two symbols, permutive automorphisms are only the trivial ones
- [[garden-of-eden](pages/garden-of-eden.md)] — invertible rules have none (own reasoning)
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - invertible rules restore Liouville's theorem
- [[notation-map](pages/notation-map.md)] - Hedlund's symbols
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - the same maps in any dimension
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - every 1D automorphism is a block permutation plus a translation
- [[jarkko-kari](pages/jarkko-kari.md)] - the inverse-neighbourhood bound and block representation are his results

[^1]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.321, 331 [synthesis] — automorphisms are homeomorphisms of X(S) onto X(S) commuting with σ; "the set A(S) is a group and is of some complexity"
[^2]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.331-332 [synthesis] — H(S) the one-to-one members of Φ(S); Thm 5.14 A(S) = H(S)
[^3]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.332-334, 337 [synthesis] — Σ(S) = {σⁿ}; Σ ⊂ A ⊂ E ⊂ Φ; Thm 6.2 (Φ − E infinite), Thm 6.8 (E − A infinite), Cor 6.14 (A − Σ infinite)
[^4]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.325 [synthesis] — Thm 4.1: for f ∈ F(S, 1), f a permutation ⇔ f∞ onto ⇔ f∞ a homeomorphism
[^5]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.335 [synthesis] — the table of f on {0, 1, 2}; f permutive in x₁, depends on x₂, f∞ one-to-one; "an example of a member of A(S) − Σ(S), card S = 3"; Remark 6.1 rules out a window-1 equivalent
[^6]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.372 [synthesis] — the §6 example cited as showing the S > 2 analogue of Thm 18.3 fails; f∞ composed with itself is the identity, yet no f′ ∈ F(S, 1) has f∞ = f′∞
[^7]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.371-372 [synthesis] — Thm 18.3 (Curtis, Hedlund, Lyndon): card S = 2, (fg)∞ = identity implies f∞ = g∞ = identity or f∞ = g∞ = complement β
[^8]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.336-337 [synthesis] — Lemma 6.12 (𝒞 = A0𝔅_n(S)0B, no two members overlap); Thm 6.13 construction of φ_π, its continuity, commuting with σ, invertibility, φ_π φ_ρ = φ_πρ
[^9]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.337-338 [synthesis] — "given any k ∈ I₁, there exists an element of A(S) of order k"; Cor 6.15 every finite group is isomorphic to a subgroup of A(S)/Σ(S)
[^10]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.373-374 [synthesis] — α swaps 0 and 1; β changes x_i when x_(i−1)x_i x_(i+1)x_(i+2) = 1001 or 1101; α² = β² = identity; φ = αβ with φ^(2p)(x) = x^(2p) ≠ x; Thm 20.1 and 20.2 (Curtis, Hedlund, Lyndon)
[^11]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.371 [synthesis] — for p = qk with q ≥ 2, take ψ of order q from Thm 6.13 and φ = σ^k ψ; then φ^q = σ^p and φ is not a power of σ
[^12]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.371 [synthesis] — Thm 18.1 and Cor 18.2 (Welch): S prime and φ^q = σ^p imply q divides p
[^13]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.321 — "the set A(S) is relatively sparse, but nothing has been proved in this direction"
[^14]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.13 - "In symbolic dynamics literature it is therefore customary to call reversible CA automorphisms of the shift dynamical system. CA are termed endomorphisms."
[^15]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.18, 20 [synthesis] - Theorem 8 (Morita and Harao): one-dimensional reversible CA exist that are computationally universal; 1D radius-½ inverse neighbourhood at most s − 1 consecutive cells, tight; Theorem 11; "left shift σ cannot be implemented as a GMN-CA alone"
