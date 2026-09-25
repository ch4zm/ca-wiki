---
title: Decidability in Cellular Automata
category: Analyses
summary: Which properties of a cellular automaton can be decided from its rule table, by dimension - a single table of the decidable, undecidable and open questions reported by Kari (2005) and Sutner (2015), with the tiling reductions that separate one dimension from two and the first-order/orbit split within one dimension
tags: [analysis, decidability, undecidability, tiling, dimension, kari]
sources: [theory-of-cellular-automata-a-survey, aucm-ch12-linear-cellular-automata-and-decidability]
created: 2026-09-24
updated: 2026-09-24
---

# Decidability in Cellular Automata

The input is always a finite description (S, N, f) of a CA
([[cellular-automaton](pages/cellular-automaton.md)]). The question is whether some
algorithm answers yes or no for every input.[^1] The rows come from
[[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)]
(Kari) and, for the first-order and reachability rows,
[[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] (Sutner).

## The table

| Question | 1D | 2D | Page |
|---|---|---|---|
| Are two CA equal? Are they inverses? | decidable | decidable | [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] |
| Injective (= reversible = bijective)? | decidable (Amoroso and Patt) | **undecidable** (Kari) | [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] |
| Surjective (no Garden of Eden)? | decidable (Amoroso and Patt) | **undecidable** (Kari) | [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] |
| Is a given additive quantity conserved? Find all with a given neighbourhood | decidable (Hattori and Takesue) | decidable | [[conserved-quantity](pages/conserved-quantity.md)] |
| Any non-trivial conserved quantity at all? | **open** | undecidable | [[conserved-quantity](pages/conserved-quantity.md)] |
| Nilpotent? | **undecidable** (Kari) | undecidable (Culik, Pachl and Yu) | [[limit-set](pages/limit-set.md)] |
| Any non-trivial property of the limit set (state set may vary) | undecidable (Kari) | undecidable | [[limit-set](pages/limit-set.md)] |
| Topological entropy | uncomputable (dimension not stated) | | [[limit-set](pages/limit-set.md)] |
| Culik-Yu class | undecidable | | [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] |
| Kurka class K1, K2 or K3 | undecidable | | [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] |
| Positively expansive (K4)? | **open** | trivially no: none exist in 2D or higher | [[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)] |
| Any first-order property of the one-step relation (injective, surjective, k-to-1, has a k-cycle, number of fixed points) | decidable on finite, one-way and bi-infinite configurations (Sutner) | undecidable in general (injectivity, surjectivity) | [[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)] |
| Reachability (is Y in the orbit of X?) | finite grids: PSPACE-hard; ultimately periodic configurations: any chosen r.e. degree | | [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)] |
| Does every orbit end in a fixed point, on every finite grid? | Π⁰₁-complete | | [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)] |
| Is the CA computationally universal? | Σ⁰₄-complete | | [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)] |
| Does a finite Life configuration die? | | undecidable (Berlekamp, Conway and Guy) | [[game-of-life](pages/game-of-life.md)] |
| Surjective, injective, equicontinuous, sensitive, transitive, positively expansive, for **linear** rules over ℤ_m | decidable (gcd tests; injectivity by a prime-factor test) | decidable, same tests (positive expansivity impossible) | [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] |

Sources for the rows: equality and inverses,[^2] injectivity and surjectivity,[^3]
conservation,[^4] nilpotency, limit sets and entropy,[^5] classifications,[^6] Life,[^7]
linear rules,[^8] first-order properties and reachability.[^9] Blank cells are cases the survey does not state. Over a fixed state set,
surjectivity is a limit-set property that is decidable in 1D, and whether it is the only
one is open ([[limit-set](pages/limit-set.md)]).[^5] Several results hold in all dimensions
d ≥ 1 (nilpotency, limit sets) or all d ≥ 2 (no positively expansive rules). The 2D
undecidability of injectivity, surjectivity and conserved quantities is stated only for
two dimensions. (Own reasoning:
properties undecidable in 1D stay undecidable in higher dimensions whenever a 1D rule can
be embedded by ignoring the extra coordinates, which is how Kari extends XOR and
CONTROLLED-XOR to higher dimensions.)[^10]

## Why the split falls between one and two dimensions

**1D is tamed by finite graphs.** In 1D a rule's behaviour on finite windows can be
tracked with finite structures. Sutner makes this precise: the one-step relation is
recognized by an automaton on the [[de-bruijn-graph](pages/de-bruijn-graph.md)], so every
first-order property of it is decidable
([[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]).[^{n+1}]
What stays undecidable in 1D is long-term behaviour, which needs the orbit relation
([[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]). The
examples are Sutner's de Bruijn graph algorithms for injectivity and surjectivity, and
the s − 1 bound on the inverse neighbourhood of a reversible rule.[^11]

**2D inherits the tiling problem.** The undecidable tiling problem
([[wang-tiles](pages/wang-tiles.md)]) reduces to 2D questions directly. A CA that keeps a
tile when the tiling is correct around it and otherwise erases it is nilpotent iff no
tiling exists. A control layer holding both a T-tile and a SNAKES tile, under an XOR layer,
gives a CA that is injective iff T admits no tiling. The finite tiling problem does the same for surjectivity and for
conserved quantities.[^12]

**Nilpotency breaks the pattern.** It is undecidable even in 1D. Any NW-deterministic tile set T
becomes a 1D CA with neighbourhood (0, 1) and states T ∪ {q}. A valid tiling by T is a
space-time diagram that never produces q, so the CA is nilpotent iff T admits no tiling,
and tiling stays undecidable for those sets. Kari's Rice theorem then spreads that one undecidable problem to every
non-trivial property of limit sets.[^5]

**Semi-decidability goes in opposite directions.** Injectivity of G is semi-decidable
(search for an inverse). Non-injectivity on finite configurations, which by the
[[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] is non-surjectivity, is
semi-decidable (search for two finite configurations with the same image). The two tiling
problems split the same way.[^13]

## Related Concepts

- [[jarkko-kari](pages/jarkko-kari.md)] - author of several of the undecidability results
- [[universal-turing-machine](pages/universal-turing-machine.md)] - the halting problem behind the finite tiling problem and Life's undecidable death
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - Hedlund's finite characterizations of 1D surjectivity
- [[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)] - why the short-term 1D properties are decidable
- [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)] - the orbit problem behind the undecidable long-term properties
- [[de-bruijn-graph](pages/de-bruijn-graph.md)] - the 1D decision procedures

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.5 - "In algorithmic questions G is, however, always specified using the three finite items S, N and f."
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.7-8 [synthesis] - "The equivalence of two given CA G₁ and G₂ is decidable"; "One can effectively decide whether two given CA are inverses of each other"
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.19 [synthesis] - Theorem 9 (Amoroso and Patt), Theorem 10 (Kari)
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.22 [synthesis] - Theorem 12 (Hattori and Takesue); the conservation test is stated for d-dimensional quantities; Open problem 4 (1D); 2D "easily seen undecidable"
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.24-25 [synthesis] - Theorem 15 (Culik et al. [19], Kari [40]), with the 2D and 1D proofs; topological entropy uncomputable [35]; Theorem 16 for every d ≥ 1 with arbitrary input state sets; with S fixed, 1D surjectivity is a decidable limit-set property (Open problem 6)
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.8, 26 [synthesis] - Culik-Yu classification undecidable for 1D CA; K1-K3 undecidable for 1D [23]; K4 open (Open problem 7) and empty in 2D and higher
[^7]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 - "Theorem 1 (Berlekamp et al. [6]). Game of Life is computationally universal. It is undecidable whether a given finite configuration dies."
[^8]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.28-29 [synthesis] - Theorem 17 (Sato, p.28), Corollary 4 (injectivity: every prime factor of m divides all but exactly one coefficient), Theorem 18; "all the given conditions are fast to test"; "Higher dimensional positively expansive CA do not exist"
[^9]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.265-271 [synthesis] — Theorems 1, 3, 5 (first-order logic decidable for finite, infinite and bi-infinite 1D CA); Theorem 6 (Reachability PSPACE-hard uniformly in n); Theorem 7 (FP spectrum universality Π⁰₁-complete); Theorem 8 (Reachability over C_up any r.e. degree); universality Σ⁰₄-complete; 2D injectivity and surjectivity undecidable (Kari), p.260
[^10]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.17 - "In higher-dimensional spaces the rules are applied in one of the dimensions only."
[^11]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.19-20 [synthesis] - Sutner's de Bruijn graph algorithms; "in the one-dimensional space the inverse automaton can only have a relatively small neighborhood", at most s − 1 cells for radius-½ rules
[^12]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.19-20, 22, 24 [synthesis] - nilpotency via T ∪ {q}; injectivity via control layers T and SNAKES plus an xor layer; surjectivity by "an analogous reduction from the finite tiling problem"; conserved quantities via the finite tiling problem
[^13]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.14, 20 [synthesis] - semi-algorithms for injectivity of G and non-injectivity of G_F; for tiling, a semi-algorithm detects a finite tiling, while non-existence of a tiling is semi-decidable
[^14]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.262-264 [synthesis] — A_ρ(x, y) is a subautomaton of the de Bruijn automaton; the first-order theory captures temporally local properties and is decidable, but is "too weak to deal with aspects of the long-term behavior"
