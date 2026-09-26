---
title: "Automata, Universality, Computation — Ch. 12: Linear Cellular Automata and Decidability"
category: Sources
summary: Sutner on where decidability ends for one-dimensional CA - every first-order property of the one-step relation is decidable by automata on the de Bruijn graph (finite, one-way and two-way infinite grids), while orbit questions are undecidable and graded - PSPACE-hard reachability, a Π⁰₁-complete fixed-point spectrum, reachability of any r.e. degree, a Σ⁰₄-complete universality test
tags: [decidability, first-order-logic, model-checking, de-bruijn, buchi-automata, reachability, arithmetic-hierarchy, rule-110, sutner]
sources: [aucm-ch12-linear-cellular-automata-and-decidability]
created: 2026-09-24
updated: 2026-09-26
---

# Automata, Universality, Computation — Ch. 12: Linear Cellular Automata and Decidability

**Source:** assets/adamatzky-2015-automata-universality-computation.pdf, printed pp. 259–276 (PDF pp. 264–281)
**Date ingested:** 2026-09-24
**Type:** book chapter (survey with proofs)
**Author:** Klaus Sutner
**Part of:** [[automata-universality-computation](pages/automata-universality-computation.md)]

> **"Linear" here means one-dimensional.** The chapter's CA live on a line, and nothing
> about their rules is assumed. This is a different sense from the wiki's
> [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] page, where
> "linear rule" means a rule that is linear over ℤ_m.

## Summary

Sutner draws the line between decidable and undecidable questions about one-dimensional
CA using model theory and computability, not classical dynamics.[^1] A rule ρ gives a
first-order structure C_ρ = ⟨C, →⟩, where C is the configuration space and x → y means y
is the image of x. Many properties are first-order sentences over this structure:
surjectivity, reversibility, being k-to-1, "there is a 5-cycle", "exactly 2 fixed
points".[^2] The method does not reach higher dimensions. Kari proved injectivity and
surjectivity undecidable in 2D, and in Lind's phrase, higher dimensions mean stepping into
"the Swamp of Undecidability".[^3]

The positive half is that **the first-order theory of every 1D CA is decidable**, for
finite grids, one-way infinite configurations and bi-infinite ones
([[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]).
C_ρ is an *automatic structure*. The one-step relation is recognized by a finite automaton
on the [[de-bruijn-graph](pages/de-bruijn-graph.md)] of the rule, and logic is compiled
into automata operations.[^4] The catch is cost. Determinization blows up exponentially,
and on infinite words it becomes very hard to implement, so in practice only simple
sentences can be checked.[^5] First-order logic also sees only a bounded number of steps.[^6]

The negative half concerns long-term behaviour, which depends on the orbit relation →*
([[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]).
Adding →* brings undecidability back, and at graded levels of the arithmetic
hierarchy.[^7]

## Key Takeaways

- **Three decidability theorems.** The first-order theory of 1D CA is decidable on finite
  grids Σⁿ (Theorem 1), on one-way infinite configurations Σ^ω (Theorem 3) and on
  bi-infinite ones Σ^ζ (Theorem 5).[^8]
- **Spectra are regular.** The spectrum of a sentence is the set of grid sizes n where it
  holds, and it is always a regular (semilinear) set. For rule 90, "every configuration
  has exactly 4 predecessors" has spectrum 2ℕ. For rule 30, "there is a 3-cycle" has
  spectrum 12ℕ.[^9]
- **Ultimately periodic configurations suffice.** These are configurations of the form
  vw^ω (one-way) or ^ωu v w^ω (bi-infinite). They form an elementary substructure, so no
  first-order sentence tells them apart from the full space. Since each is a finite
  object, orbits on them are recursively enumerable.[^10]
- **Useful extra predicates.** "Differ in only finitely many places" (E) is automatic. With
  it, surjectivity becomes an injectivity-shaped sentence through Hedlund's theorem, and
  can be tested in linear time once the automaton is built. One-sided versions of E
  express *openness* of the global map, which is not first-order in the bare language.
  They give another proof of Sutner's quadratic algorithms for injectivity, surjectivity
  and openness.[^11]
- **Graded undecidability.**[^12]

  | Question | Complexity |
  |---|---|
  | Reachability on finite grids, uniformly in n | PSPACE-hard (validity of any sentence: PSPACE-complete) |
  | Does "every orbit ends in a fixed point" (FP) hold for every n? | Π⁰₁-complete |
  | Nilpotency, ∃y ∀x (x →* y ∧ y → y) | undecidable (Kari) |
  | FP on infinite CA, over configurations with $ infinitely often both ways | Π⁰₂-complete |
  | Reachability over ultimately periodic configurations | can be any r.e. degree |
  | Does the reachability problem have degree d? | Σ⁰₃ relative to d (Σ₃^d), complete |
  | Is the CA computationally universal? | Σ⁰₄-complete |

- **Reachability and confluence are independent.** Two configurations are *confluent* if
  their orbits meet. For any two r.e. degrees d₁ and d₂ there is a CA whose reachability
  and confluence problems have exactly those degrees.[^13]
- **Rule 110.** Cook's universality proof uses ultimately periodic configurations with
  two different periodic blocks. The left block times the computation and the right one
  encodes the cyclic tag system. On configurations of finite support, reachability for
  rule 110 is trivially decidable. Neary and Woods removed the exponential slowdown of
  the original construction, so predicting the state of one cell at time t from a finite
  configuration is P-complete.[^14]

## How the Π⁰₂ proof works

The hard direction reduces INF, the set of indices of infinite r.e. sets, which is
Π⁰₂-complete. From e, build a Turing machine M_e that on input 1ⁿ dovetails the
computations m ∈ W_e for m > n and halts if one converges.[^15] A plain simulation of M_e
fails for two reasons. A CA configuration can hold many heads, even infinitely many, and a
configuration that looks like a valid instantaneous description may never occur in any
real run. So M_e is replaced by a *stable* machine, which periodically retraces its steps
to check that the current description is admissible. It keeps the claimed input with it
and halts on anything inadmissible.[^16] In the CA, every syntactically bad local pattern
is frozen, and $ can only be rewritten next to a head. So the only orbits that never
reach a fixed point simulate divergent runs, which gives e ∈ INF iff FP holds. The
argument needs $ to recur in both directions. For general ultimately periodic
configurations Sutner sees no way to organize the self-checking.[^17]

## Open problems

What is the degree of the full first-order theory of T_ρ = ⟨C, →, →*⟩, first on the
$-restricted space and then on all ultimately periodic or all configurations? Sutner
suspects every level of the arithmetic hierarchy is expressed by some orbit assertion.[^18]
He also asks whether pseudo-random rule 30 could ever carry an undecidability proof, and
suggests crowd-sourced inspection, as in Galaxy Zoo.[^19]

## Entities & Concepts

- [[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]
- [[de-bruijn-graph](pages/de-bruijn-graph.md)]
- [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)]
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]
- [[rule-110](pages/rule-110.md)]
- [[rule-90](pages/rule-90.md)]
- [[limit-set](pages/limit-set.md)]
- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)]
- [[jarkko-kari](pages/jarkko-kari.md)]

## Relation to Other Wiki Pages

This chapter explains why the 1D column of
[[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] is so
full. Every property on that page that is first-order in → falls under Theorems 1-5. The
undecidable 1D entries (nilpotency, the Culik-Yu class, limit-set properties) are all
about long-term behaviour, not a bounded number of steps (own reasoning, following
Sutner's split between temporally local and long-term properties). Sutner's FP sentence formalizes Wolfram class I in the same spirit as Culik
and Yu's classes ([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]).
His opening picture, a CA as a shift-invariant continuous map with a finite lookup table,
is the [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)].[^20]

[^1]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.260 — "In this paper we will focus on one-dimensional cellular automata and discuss an approach to classification that is based on model theory and computability rather than classical dynamics."
[^2]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.260 [synthesis] — "Using first-order logic one can easily formalize assertions such as 'the global map is surjective,' 'the system is reversible', 'the global map is k-to-1' where k is fixed, 'there exists a 5-cycle' or 'there are exactly 2 fixed points.'"; the structure C_ρ = ⟨C, →⟩ with Σ the alphabet and w the width
[^3]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.260 — "their higher-dimensional analogues are not amenable to these techniques as can be seen for example from Kari's theorem concerning the undecidability of injectivity and surjectivity of the global map in dimension 2, see [20]. As Douglas Lind pointed out, the study of higher-dimensional cellular automata requires one to step into 'the Swamp of Undecidability,' see [29]."
[^4]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.261, 263-264 [synthesis] — "C_ρ is an automatic structure in the sense of Khoussainov and Nerode"; the automaton A_ρ(x, y) "is a subautomaton of the complete de Bruijn automaton over Σ² of order 2r"; "regular languages form an effective Boolean algebra"; construction by induction on subformulae
[^5]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.265, 267-268 [synthesis] — "the use of product automata and determinization has the potential effect of exponential blow-up ... only relatively simple formulae can be handled"; Safra's determinization "is notoriously difficult to implement well; the upper bound of O(n^n) is known to be tight"; bi-infinite case: "typically unfeasible to handle first-order sentences of all but the most limited complexity"
[^6]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.262 — "Of course, the first-order theory of C_ρ is too weak to deal with aspects of the long-term behavior of the cellular automaton, but it easily captures elementary properties such as injectivity, surjectivity, k-to-1-ness, the existence of k-cycles and so on."
[^7]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.262 [synthesis] — augmented structures T_ρ = ⟨C, →, →*⟩ with →* the reachability or orbit relation; "Pace Lind, this leads back into the undecidability swamp: the first-order theory of T_ρ is not decidable in general"
[^8]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.265, 267, 268 — Theorem 1: "First-order logic for finite one-dimensional cellular automata is decidable."; Theorem 3: "First-order logic for infinite one-dimensional cellular automata is decidable."; Theorem 5: "First-order logic for bi-infinite one-dimensional cellular automata is decidable."
[^9]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.265 [synthesis] — Lemma 1: "Any sentence in first-order logic has regular spectrum over the structures C^n_ρ"; semi-linear as a set of naturals; rule 90: "The property 'every configuration has exactly 4 predecessors' here has spectrum 2N. Likewise, elementary cellular automaton number 30 has spectrum 12N for the property 'there is a 3-cycle.'"
[^10]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.266, 268 [synthesis] — ultimately periodic configurations vw^ω; Theorem 2: "The space C_up of ultimately periodic configurations is an elementary substructure of the full space"; "ultimately periodic configurations are finitary objects but are indistinguishable from arbitrary configurations from the perspective of first-order logic"; "the orbits on C_up are recursively enumerable"; bi-infinite ^ωuvw^ω, Theorem 4
[^11]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.261-262, 269 [synthesis] — "differ in only finitely many places" predicate E is automatic; Hedlund's characterization of surjectivity by injectivity on finite-support configurations gives ∀x, y, z (x → z ∧ y → z ∧ x E y ⇒ x = y), testable by path existence "in linear time and space"; openness "cannot be formalized in first-order" but is expressible with =_L, =_R; "an alternative proof for the quadratic algorithms from [44]"
[^12]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.269-271 [synthesis] — Theorem 6: Reachability over T^n_ρ uniformly in n is PSPACE-hard, validity PSPACE-complete; Theorem 7: universality of the spectrum of FP ≡ ∀x ∃y (x →* y ∧ y → y) is Π⁰₁-complete; nilpotency statement "undecidable according to [21]"; Theorem 9: FP Π⁰₂-complete on C_$; Theorem 8: Reachability over C_up can be any r.e. degree; "testing whether a cellular automaton has Reachability problem of degree d is Σ⁰₃^d-complete. In particular, testing for computational universality is Σ⁰₄-complete."
[^13]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.271 — "two configurations are confluent if their orbits overlap ... given arbitrary r.e. degrees d1 and d2 there is a cellular automaton whose Reachability and Confluence problems have exactly those two chosen degrees as their complexity."
[^14]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.270 [synthesis] — Cook's proof "uses ultimately periodic configurations ... the left block serves to time the computation whereas the right block encodes the cyclic tag-system that is essential for universality. By contrast, Reachability for rule 110 is trivially decidable for configurations of finite support"; Neary and Woods avoid the exponential slow-down, so "it is P-complete to determine the state of a particular cell at time t of the evolution of a finite configuration under rule 110"
[^15]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.272 [synthesis] — INF is Π⁰₂-complete; e ∈ INF ⟺ ∀n ∃m (n < m ∧ m ∈ W_e); M_e on input 1ⁿ dovetails computations m ∈ W_e for m > n, halting if any converges
[^16]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.272 [synthesis] — configurations may carry several (even infinitely many) head cells, or look like instantaneous descriptions that occur in no computation; convert M_e into a stable machine "that ultimately halts on all inadmissible descriptions"; it "becomes self-verifying: retraces its steps every so often", keeping "a copy of the alleged original input"
[^17]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.272-273 [synthesis] — syntactically incorrect local configurations are fixed points; $ convertible only in the presence of the state head; "the only situation where a configuration can not evolve to a fixed point is when we are in fact simulating a divergent computation"; "e ∈ INF if, and only if, the sentence FP holds"; "for general ultimately periodic configurations there appears to be no way to organize the self-testing mechanism"
[^18]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.274 — "One natural challenge is to determine the degree of the full first-order theory of T_ρ, perhaps first over some specialized configuration space such as C_$. One suspects that any level in the arithmetic hierarchy can be represented by a suitable assertion about orbits of a cellular automaton."
[^19]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.274 [synthesis] — crowd-sourcing as in Galaxy Zoo; "the pseudo-random behavior of elementary cellular automaton rule 30 seems to make it a hopeless undertaking to encode any kind of undecidability proof. Perhaps many eyes could find enough structure to support such an argument."
[^20]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.259 [synthesis] — discretizing space and the evolution operators gives maps G: Σ^ℤ → Σ^ℤ continuous and shift-invariant, "expressed in the classical Curtis-Hedlund-Lyndon theorem"; G is represented by a finite lookup table ρ: Σ^w → Σ
