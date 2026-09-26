---
title: First-Order Theory of Cellular Automata
category: Concepts
summary: Treating a 1D cellular automaton as the logical structure (configurations, one-step relation) - every first-order sentence about it (injective, surjective, k-to-1, has a 5-cycle, ...) is decidable by compiling it into word, Büchi or bi-infinite automata, though the cost explodes and long-term orbit properties stay out of reach
tags: [concept, decidability, first-order-logic, model-checking, automatic-structures, buchi-automata, sutner]
sources: [aucm-ch12-linear-cellular-automata-and-decidability]
created: 2026-09-24
updated: 2026-09-26
---

# First-Order Theory of Cellular Automata

## Description

**The structure.** A one-dimensional CA with local rule ρ: Σ^w → Σ gives the relational
structure C_ρ = ⟨C, →⟩. Here C is a configuration space and x → y means one step of ρ
takes x to y. There are three natural choices of C: finite grids Σⁿ, one-way infinite
configurations Σ^ω, and bi-infinite configurations Σ^ζ.[^1] Deciding whether a sentence φ
holds, C_ρ ⊨ φ, is *model checking*. In *expression* model checking the rule is fixed and
many sentences are tested, for example to study rule 30 or
[[rule-110](pages/rule-110.md)]. In *data* model checking the sentence is fixed and many
rules are tested.[^2]

**What it can express.** Injectivity is ∀x, y, z (x → z ∧ y → z ⇒ x = y). Surjectivity,
being k-to-1, having a k-cycle, the number of fixed points, and whether some finite
directed graph occurs inside C_ρ are all first-order. They are *temporally local*: each
looks at a bounded number of steps.[^3]

**Why it is decidable.** C_ρ is an *automatic structure*. A finite automaton reading two
tracks at once recognizes x → y. It is a subautomaton of the
[[de-bruijn-graph](pages/de-bruijn-graph.md)] of the rule. Since regular languages form an
effective Boolean algebra, a sentence compiles into an automaton by induction on its
structure. Connectives become product machines and determinization. An existential
quantifier erases a track. A sentence is true iff the final automaton accepts
something.[^4] The theory is decidable for all three kinds of configuration
space:[^5]

| Space | Automata | Theorem |
|---|---|---|
| finite grids Σⁿ | ordinary word automata (Rabin-Scott) | 1 |
| one-way infinite Σ^ω | Büchi automata | 3 |
| bi-infinite Σ^ζ | ζ-automata, handled as finite unions of pairs of Büchi automata | 5 |

(A Büchi automaton accepts an infinite word if some run passes through an accepting state
infinitely often.)[^6] Finite grids need extra states for the boundary cells.[^7] The
language can be extended with "there exist infinitely many" and "there exist r mod k
many" without losing decidability (Finkel), so one can ask, for example, whether a rule
has infinitely many fixed points.[^8]

**Spectra.** On finite grids the natural question is the *spectrum* of a sentence, the set
of n for which it holds. It is always regular.[^9] Rule 90 has exactly 4 predecessors for
every configuration on the sizes 2ℕ. Rule 30 has a 3-cycle on the sizes 12ℕ.[^9]

**Ultimately periodic configurations.** In the infinite cases, the configurations of the
forms vw^ω and ^ωuvw^ω form an *elementary substructure*. No first-order sentence tells
them apart from the full uncountable space. They are the smallest such class that contains
the finite-support configurations, and each has a finite description, so orbits on them
are recursively enumerable.[^10]

**Extra predicates.** Adding automatic predicates extends what can be said. "Equal except
in finitely many places" turns surjectivity into an injectivity-shaped sentence, using
Hedlund's theorem. One-sided versions express openness of the global map, which is not
first-order in → alone.[^11]

**Limits.** Decidable in principle is not the same as feasible. Determinization can blow
up exponentially. Safra's determinization of Büchi automata has a tight O(nⁿ) bound, and
the bi-infinite case also has to make its unions disjoint first. Even nilpotency with a
fixed index n leads to an automaton exponential in n.[^12] Long-term behaviour needs the
orbit relation →*, and adding it makes the theory undecidable in general
([[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]).[^13]
The method also stops at one dimension. In 2D, even injectivity and surjectivity are
undecidable (Kari).[^14]

## Appearances in Sources

- [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] - the structures, Theorems 1-5, spectra, ultimately periodic configurations, efficiency

## Related Concepts

- [[de-bruijn-graph](pages/de-bruijn-graph.md)] - the automaton that recognizes the one-step relation
- [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)] - what first-order logic in → cannot reach
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the decidable 1D properties this method covers
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - Hedlund's characterizations of 1D surjectivity
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - injectivity as a first-order sentence
- [[jarkko-kari](pages/jarkko-kari.md)] - 2D injectivity and surjectivity are undecidable by his theorem

[^1]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.260-261 [synthesis] — local map ρ: Σ^w → Σ, structure C_ρ = ⟨C, →⟩; "three natural choices of the configuration space C: the bi-infinite case Σ^ζ, the one-way infinite case Σ^ω and the finite case Σⁿ"
[^2]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.261 [synthesis] — "Given a first-order sentence φ, we want to determine whether φ is valid over C_ρ ... model checking"; expression model checking (structure fixed, e.g. "rule 30 or rule 110") vs data model checking (sentence fixed, many structures)
[^3]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.262-263 [synthesis] — first-order theory "easily captures elementary properties such as injectivity, surjectivity, k-to-1-ness, the existence of k-cycles"; a finite directed graph having an isomorphic copy in C_ρ; "temporally local properties"; injectivity φ ≡ ∀x, y, z (x → z ∧ y → z ⇒ x = y)
[^4]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.261, 263-265 [synthesis] — C_ρ is automatic (Khoussainov and Nerode); A_ρ(x, y) on two-track words is a subautomaton of the de Bruijn automaton; "regular languages form an effective Boolean algebra"; induction on subformulae; product machines and determinization for connectives; existential quantifiers "we can simply erase the corresponding track"; sentences decided by emptiness testing
[^5]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.261, 265, 267-268 [synthesis] — "ordinary word automata in the finite case, Büchi automata in the infinite case and ζ-automata in the bi-infinite case"; Theorems 1, 3, 5; ζ-regular languages as finite unions ∪ U_i^op V_i handled by pairs of Büchi automata
[^6]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.266 — "a Büchi automaton B = ⟨Q, Σ, τ; I, F⟩ is said to accept a word X ∈ Σ^ω if there is a computation B on X that starts at a state in I and touches F infinitely often"
[^7]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.263 [synthesis] — fixed boundary conditions: add initial and final states representing phantom cells; periodic boundary conditions associate these states appropriately
[^8]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.267 — "It was pointed out by O. Finkel that we can extend our language slightly by quantifiers for 'there exist infinitely many' and 'there exist r mod k many' without affecting decidability ... we can check, say, whether there are infinitely many fixed points."
[^9]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.265 [synthesis] — spec(φ) = {0ⁿ | Cⁿ_ρ ⊨ φ}; Lemma 1: regular spectrum; rule 90 "every configuration has exactly 4 predecessors" spectrum 2N; rule 30 "there is a 3-cycle" spectrum 12N
[^10]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.266, 268 [synthesis] — Theorem 2 and Theorem 4: ultimately periodic configurations form an elementary substructure; "the least class of configurations that contain configurations of finite support and form an elementary subspace"; finite description (v, w), "orbits on C_up are recursively enumerable"
[^11]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.269 [synthesis] — predicate E ("equal except for finitely many places") and Hedlund's result give a sentence for surjectivity tested by path existence; openness is "equivalent to the map being k-to-1 for some k" and "cannot be formalized in first-order", but is expressible with =_L and =_R
[^12]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.265, 267-268 [synthesis] — exponential blow-up from products and determinization; nilpotency with index n gives an automaton "exponential in n"; Safra's algorithm, "the upper bound of O(n^n) is known to be tight"; bi-infinite determinization first makes the U_i and V_i pairwise disjoint, with a possible exponential blow-up of the index set
[^13]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.262 — "the first-order theory of T_ρ is not decidable in general"
[^14]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.260 [synthesis] — higher-dimensional analogues "are not amenable to these techniques", as shown by "Kari's theorem concerning the undecidability of injectivity and surjectivity of the global map in dimension 2"
