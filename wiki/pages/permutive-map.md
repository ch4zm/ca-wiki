---
title: Permutive Map
category: Concepts
summary: A block map that permutes the alphabet in its leftmost (or rightmost) variable whatever the other variables are; permutive at one end implies onto, and at both ends exactly S^(n-1)-to-one (Hedlund; converse by Rothaus)
tags: [concept, permutive, block-map, surjectivity, symbolic-dynamics, one-dimensional]
sources: [endomorphisms-and-automorphisms-of-the-shift-dynamical-system, universality-and-complexity-in-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Permutive Map

## Description

Let f be a block map of window n ≥ 2 over an alphabet of S symbols
([[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)]). f is
*permutive in x₁* if, for every fixed choice of x₂ ⋯ x_n, the map x₁ ↦ f(x₁ x₂ ⋯ x_n) is
a permutation of the alphabet. *Permutive in x_n* is defined the same way for the last
variable. For n = 1, permutive just means f is a permutation.[^1] A map permutive in a
variable depends on that variable.[^2]

**Example.** Let π be the cyclic permutation s ↦ s + 1 (mod S), and set f(ts) = π^t(s),
which is s + t (mod S). This f is permutive in both variables. Padding it to window n,
g(x₁ ⋯ x_n) = f(x₁ x_n), gives a map permutive at both ends for every n ≥ 2.[^3] For
S = 2 the example is the exclusive-or (XOR) of the two end cells (own reasoning, from the definition).

**Permutive ⇒ onto.** If f is permutive in x₁ or in x_n, f∞ is onto. Given a target
block and any choice of the last n − 1 preimage symbols, permutivity in x₁ lets the
preimage be filled in one symbol at a time from right to left.[^4]

**Permutive at both ends ⇒ exactly S^(n−1)-to-one.** The fill-in then runs in both
directions from any seed of n − 1 symbols. Each point therefore has at least S^(n−1)
preimages, and since S^(n−1) is also the upper bound for onto maps, it has exactly
S^(n−1) (Thm 6.7).[^5] Since this count differs for each n ≥ 2, these maps show that
E(S) − A(S), the onto maps that are not invertible, is infinite (Thm 6.8).[^6]

**Characterization through Welch's indices.** For onto f∞, f is permutive in x₁ iff
L(f) = 1, and in x_n iff R(f) = 1 (Lemma 17.1;
[[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)]).[^7] Rothaus
proves the converse of Thm 6.7. The following are equivalent: f is permutive at both
ends; f∞ is onto with S^(n−1) preimages at some bilaterally transitive point; every point
has exactly S^(n−1) preimages (Thm 17.2).[^8] Hedlund leaves open whether S^(n−1)
preimages at a single arbitrary point is enough.[^9]

**Permutive automorphisms are trivial on two symbols.** For S = 2, a one-to-one f∞ that is
permutive in x₁ equals a window-1 map. It is either the identity or the complement
0 ↔ 1 (Thm 6.9). This fails for S = 3. Hedlund's window-2 map on {0, 1, 2} is permutive in
x₁, depends on x₂, and is still one-to-one.[^10]

**Wolfram's version.** Wolfram (1984) proves the permutive ⇒ onto direction for cellular
automata in his own terms: if the rule is one-to-one in its first or last argument, every
block of every length can be produced, so the configurations keep full spatial set
dimension 1. His proof also adds one cell at a time. He extends it to compositions of such
rules and remarks that the condition is not necessary. He does not cite Hedlund, and the
identification with permutivity is own reasoning
([[set-and-measure-entropy](pages/set-and-measure-entropy.md)]).[^11] The XOR rules, such as
[[additive-cellular-automaton](pages/additive-cellular-automaton.md)] rule 90, are
permutive at both ends (own reasoning).

## Appearances in Sources

- [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] - the same one-to-one-at-an-end condition, proved in cellular-automaton terms (identification is own reasoning)
- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] — §6 (definition, onto and S^(n−1)-to-one results), §17 (Rothaus's converse)

## Related Concepts

- [[set-and-measure-entropy](pages/set-and-measure-entropy.md)] - Wolfram's form of the result
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] — permutive maps are the standard onto examples; L = 1 / R = 1
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] — the S = 3 permutive automorphism
- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] — block maps in general

[^1]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.332-333 [synthesis] — Definition 6.3: g(x₁) = f(x₁ x̄₂ ⋯ x̄_n) a permutation for every choice of x̄₂, …, x̄_n; likewise for x_n; for n = 1, permutive means f is a permutation of S
[^2]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.333 [synthesis] — Remark 6.4: permutive in x₁ [x_n] implies f depends on x₁ [x_n]
[^3]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.333 [synthesis] — Remark 6.5: π the cyclic permutation s ↦ s + 1, π(S − 1) = 0; f(ts) = π^t(s) permutive in both variables; g(x₁ ⋯ x_n) = f(x₁ x_n)
[^4]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.333 [synthesis] — Thm 6.6 and its proof: choose y_(m+1) ⋯ y_(m+n−1) arbitrarily, then solve for y_m, y_(m−1), … by permutivity in x₁
[^5]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.333-334 [synthesis] — Thm 6.7: permutive in both x₁ and x_n implies f∞ is exactly S^(n−1)-to-one; proof extends a free (n − 1)-block both ways and uses Thm 5.5's upper bound
[^6]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.334 [synthesis] — Thm 6.8: E(S) − A(S) is infinite, via the maps f^(n) of Remark 6.5 for each n ≥ 2
[^7]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.370 [synthesis] — Lemma 17.1
[^8]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] p.370 [synthesis] — "The converse of this has been proved by O. S. Rothaus"; Thm 17.2 (1)-(3)
[^9]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.370-371 — "It is not known whether the same conclusion can be reached if it is assumed that card f∞⁻¹(x) = S^(n−1) for some x ∈ X(S)."
[^10]: [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] pp.334-335 [synthesis] — Thm 6.9: card S = 2, f permutive in x₁ and f∞ one-to-one implies f∞ = g∞ with g ∈ F(S, 1), i.e. the identity or the complement; "the preceding theorem is no longer true if card S > 2", with the S = {0, 1, 2} example
[^11]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.28 [synthesis] - "cellular automata evolving according to eq. (2.1) yield s⁽ˣ⁾(X) = 1 for all X, so that d⁽ˣ⁾ = 1, if F is an injective (one-to-one) function of either its first or last argument (or can be obtained by composition of functions with such a property)"; induction by adding a site at one end; "it is apparently not necessary"
