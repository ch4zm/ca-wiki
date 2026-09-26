---
title: Reachability in Cellular Automata
category: Concepts
summary: The orbit problem - does configuration Y appear in the orbit of X? - which carries every long-term question about a CA into undecidability; PSPACE-hard on finite grids, of any chosen r.e. degree on ultimately periodic configurations, with universality testing Σ⁰₄-complete
tags: [concept, reachability, orbit, undecidability, arithmetic-hierarchy, re-degrees, sutner]
sources: [aucm-ch12-linear-cellular-automata-and-decidability]
created: 2026-09-24
updated: 2026-09-26
---

# Reachability in Cellular Automata

## Description

**The problem.** Write x →* y when y is in the orbit of x, that is, some number of steps
(possibly zero) takes x to y. The *Reachability Problem* asks, for two configurations with
finite descriptions, whether X →* Y.[^1] Adding →* to the one-step structure gives
T_ρ = ⟨C, →, →*⟩. Its first-order theory is not decidable in general, in contrast with the
decidable [[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]
of → alone.[^2] Sutner argues that undecidability and hardness for 1D CA are "closely
related to the full orbit problem".[^3]

**On finite grids.** Reachability on finite grids, uniformly in the length n, is PSPACE-hard, because a CA can
simulate a linear bounded automaton. Any single sentence on a single grid is still
decidable in polynomial space.[^4] Things change once all grid sizes are asked about
together. The sentence FP ≡ ∀x ∃y (x →* y ∧ y → y) says every orbit ends in a fixed point,
a formal version of Wolfram class I. Whether FP holds for every n is Π⁰₁-complete.[^5]

**On infinite configurations.** Here Sutner restricts to ultimately periodic
configurations, which have finite descriptions. Cook's universality proof for
[[rule-110](pages/rule-110.md)] lives in this space too.[^6] Reachability there is
undecidable in general. More precisely, it can be made to have **any** recursively
enumerable degree.[^7] Two obstacles have to be overcome. Most CA configurations mean
nothing to the simulated Turing machine, and the construction must not allow unintended
simulations that push the degree higher.[^8] Restricted to configurations in which a
marker $ recurs in both directions, FP becomes Π⁰₂-complete, by a reduction from INF using
a self-verifying Turing machine.[^9]

**Classifying by reachability degree.** Sutner suggests classifying CA by the degree of
their reachability problem when computation is the interest. This classification is
itself highly undecidable. Deciding whether the degree is d is Σ₃^d-complete, and deciding
computational universality is Σ⁰₄-complete. *Confluence* (two orbits meet) is independent of reachability:
any pair of r.e. degrees can be realized as a CA's reachability and confluence degrees.[^10]
The r.e. degrees themselves have a complicated structure. They are dense (Sacks), and
their first-order theory is highly undecidable, so a classification by degree inherits
that complexity.[^11]

**A contrast.** For rule 110 on configurations of finite support, reachability is
trivially decidable. Its universality needs periodic backgrounds on both sides.[^6]
Nilpotency, ∃y ∀x (x →* y ∧ y → y), is FP with the quantifiers swapped, and is undecidable
(Kari) ([[limit-set](pages/limit-set.md)]).[^12]

## Appearances in Sources

- [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] - Theorems 6-9, degree classification, confluence, rule 110

## Related Concepts

- [[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)] - decidable until →* is added
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the table of decidable and undecidable questions
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - FP as Wolfram class I; Culik-Yu's CY3 is decidable reachability for finite configurations
- [[limit-set](pages/limit-set.md)] - nilpotency, the quantifier swap of FP
- [[rule-110](pages/rule-110.md)] - universal, yet trivially decidable on finite support
- [[jarkko-kari](pages/jarkko-kari.md)] - proved nilpotency undecidable

[^1]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.269 — "one can expect hardness results for the plain Reachability Problem: for two configurations X and Y that have finitary descriptions, is X →* Y?"
[^2]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.262 [synthesis] — T_ρ = ⟨C, →, →*⟩ with →* "the transitive reflexive closure of →, the reachability or orbit relation"; "the first-order theory of T_ρ is not decidable in general"
[^3]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.259 (Abstract) — "Undecidability and hardness, on the other hand, are closely related to the full orbit problem: does a given configuration appear in the orbit of another?"
[^4]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.269-270 [synthesis] — Theorem 6: "Reachability over Tⁿ_ρ, uniformly in n, is PSPACE-hard", since CA "are easily capable of simulating linear bounded automata"; validity of any first-order sentence over Tⁿ_ρ is decidable in polynomial space, so PSPACE-complete
[^5]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.270 [synthesis] — FP ≡ ∀x ∃y (x →* y ∧ y → y), "every orbit ends in a fixed point"; "We can construe FP as a formalization of the first Wolfram class"; Theorem 7: universality of its spectrum is "Π⁰₁-complete"
[^6]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.270 [synthesis] — ultimately periodic configurations as the natural space; "Cook's proof of computational universality uses ultimately periodic configurations"; "Reachability for rule 110 is trivially decidable for configurations of finite support"
[^7]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.270-271 [synthesis] — over ultimately periodic configurations Reachability is "undecidable in general"; Theorem 8: "The Reachability problem of an infinite or bi-infinite cellular automaton over C_up can be chosen to be any r.e. degree."
[^8]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.271 [synthesis] — "we have to deal with all configurations of the cellular automaton, most of which are meaningless from the perspective of the Turing machine. Second, we need to make sure that there are no unintended simulations that could drive the degree of Reachability up"
[^9]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.271-273 [synthesis] — C_$: ultimately periodic configurations containing $ infinitely often in both directions; Theorem 9: "Deciding FP for an infinite cellular automaton is Π⁰₂-complete on C_$"; reduction from INF via a stable, self-verifying Turing machine
[^10]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.271 [synthesis] — "testing whether a cellular automaton has Reachability problem of degree d is Σ₃^d-complete. In particular, testing for computational universality is Σ⁰₄-complete"; confluence: "given arbitrary r.e. degrees d1 and d2 there is a cellular automaton whose Reachability and Confluence problems have exactly those two chosen degrees"
[^11]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.271 — "by a famous theorem of Sacks, the partial order of the r.e. degrees is dense: whenever A <_T B for two r.e. sets A and B there is a third r.e. set such that A <_T C <_T B"; "The first order theory of this semi-lattice is highly undecidable"
[^12]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.271 [synthesis] — "the nilpotency statement ∃y ∀x (x →* y ∧ y → y) is undecidable according to [21]. By interchanging quantifiers we obtain the 'fixed point' sentence FP"; [21] = Kari (1992)
