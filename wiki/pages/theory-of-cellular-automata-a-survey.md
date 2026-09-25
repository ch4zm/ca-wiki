---
title: Theory of Cellular Automata - A Survey (Kari, 2005)
category: Sources
summary: Kari's tutorial survey of cellular automata as a part of theoretical computer science - Garden-of-Eden theorems, reversibility, conservation laws, intrinsic universality, limit sets, topological dynamics, linear rules and language recognition, with the dimension-one vs dimension-two decidability split running through all of it and nine open problems
tags: [kari, survey, decidability, reversibility, garden-of-eden, limit-sets, topological-dynamics, wang-tiles, universality, linear-ca, language-recognition]
sources: [theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Cellular Automata - A Survey (Kari, 2005)

**Source:** raw/kari-2005-theory-of-cellular-automata-survey.pdf (Kari, J., *Theoretical Computer Science* 334(1-3), 3-33, 2005; https://doi.org/10.1016/j.tcs.2004.11.021)
**Date ingested:** 2026-09-24
**Type:** paper (survey)

> Locators are the journal's printed page numbers (printed page n = PDF page n + 2).
> A survey states most results without proof and credits them to other papers. Unless a
> page says otherwise, those papers (Amoroso and Patt 1972, Culik and Yu 1988, Kurka
> 1997, Ollinger 2002, Wolfram 2002 for the Cook-Wolfram rule 110 result, Hattori and Takesue 1991, Kari's own papers,
> and the rest) are cited via this survey and have not been read. Moore 1962 is
> [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)],
> Myhill 1963 is
> [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)],
> Hedlund 1969 is
> [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)],
> and Wolfram 1983 is
> [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)].

## Summary

[[jarkko-kari](pages/jarkko-kari.md)] writes a tutorial for researchers in other areas of
natural computing. He says the choice of topics follows his own research interests:
reversibility, conservation laws, decidability, universality and limit behaviour.[^1] He
fixes a single formal setting. A d-dimensional
[[cellular-automaton](pages/cellular-automaton.md)] is a triple (S, N, f): a finite state
set, a neighbourhood vector of n offsets in ℤᵈ, and a local rule f : Sⁿ → S. The global map
G acts on all configurations ℤᵈ → S. Its restrictions G_F to *finite* configurations and
G_P to *spatially periodic* ones are studied separately. He warns that the three can behave
quite differently, so experiments with periodic boundaries "may be misleading".[^2] The
physical motivation is also stated at the start: reversibility and conservation laws can be
built into a rule, and the long-term hope is "programmable matter" that runs a universal
CA directly.[^3] Physical and biological systems are commonly simulated with CA: lattice
gases for fluid flow (Hardy, Pomeau and de Pazzis 1976; Frisch, Hasslacher and Pomeau
1986), Ising spin models, and diffusion.[^4] The survey leaves out the firing squad
synchronization problem, fault tolerance (Gács 1986) and quantum CA.[^5]

Kari notes early that one-dimensional CA behave in some respects differently from
higher-dimensional ones.[^6] The difference runs through the whole survey, and in its
results it mostly takes the form **dimension one is decidable, dimension two is not** (own
reasoning, summarizing the theorems below). The [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] (G surjective iff
G_F injective) holds in every dimension, and the injectivity and surjectivity of 1D rules
can be decided. For 2D rules neither can.[^7] The 2D undecidability proofs run through
[[wang-tiles](pages/wang-tiles.md)]. In Kari's SNAKES tile set, any arrow-following path
along which the tiling is valid must pass through arbitrarily large squares. Adding an XOR
layer steered by the arrows turns tiling questions into injectivity questions.[^8] Nilpotency is the exception: it is
undecidable already in 1D, which Kari proved using NW-deterministic tiles. That result
then spreads, through a Rice-style theorem, to every non-trivial property of
[[limit-set](pages/limit-set.md)]s.[^9] The results are collected on
[[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)].

Physics motivates the chapters on the
[[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] and the
[[conserved-quantity](pages/conserved-quantity.md)]. A reversible rule's inverse is again a
CA, but in 2D its neighbourhood has no computable bound. The
[[margolus-neighbourhood](pages/margolus-neighbourhood.md)] (block permutations on
alternating partitions) makes a rule reversible by construction. In 1D and 2D every
reversible rule is a composition of a block-permutation rule and a translation.[^10] On the
computation side, [[intrinsic-universality](pages/intrinsic-universality.md)] (simulating
every CA, including on infinite configurations) is set apart from Turing universality, as
shown by the [[game-of-life](pages/game-of-life.md)] and [[rule-110](pages/rule-110.md)].[^11]
[[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)] covers the
topological-dynamics notions (equicontinuity, sensitivity, expansivity, transitivity) and
Kurka's classification ([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]).
For linear (additive) rules over ℤ_m
([[additive-cellular-automaton](pages/additive-cellular-automaton.md)]), these properties
reduce to gcd tests, and injectivity to a test on the prime factors of m.[^12]
The survey closes with
[[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)],
where the real-time vs linear-time question has been open since 1972.[^13]

## Key Takeaways

- **Three spaces, three maps.** G on all configurations, G_F on finite ones, G_P on
  periodic ones. The Garden-of-Eden theorem is a statement linking G and G_F. Two
  implications between the injectivity and surjectivity of the three are proved only in
  1D. One of them fails in 2D, and three implications are open there.[^7][^14]
- **Reversible = bijective = injective**, in every dimension (Hedlund, Richardson; Moore
  and Myhill). Injectivity is decidable in 1D (Amoroso and Patt 1972) and undecidable in 2D
  (Kari 1990, 1994).[^15]
- **Nilpotency is undecidable in every dimension** (Culik, Pachl and Yu 1989; Kari 1992),
  and so is every non-trivial property of limit sets when the state set may vary (Kari
  1994).[^9]
- **Universality comes in two strengths.** Life and rule 110 are Turing-universal (Theorems
  1-2). An intrinsically universal CA simulates every CA of its dimension. The smallest
  known 1D example has 6 states and the nearest-neighbour neighbourhood (Ollinger).[^11]
- **The Wolfram classes are informal**, and Culik and Yu's formal version is undecidable.
  Kurka's equicontinuity classes are undecidable except for the positively expansive
  class, whose status is open.[^16]
- **Linear rules are the tractable case.** Over ℤ_m, surjectivity, equicontinuity,
  sensitivity, transitivity and positive expansivity reduce to gcd conditions on the
  coefficients, and injectivity to a condition on the prime factors of m.[^12]

## Kari's open problems

The survey poses nine, numbered in order:[^17]

1. Is elementary rule 54 computationally universal? ([[rule-110](pages/rule-110.md)])
2. In two or more dimensions, does G_P injective imply G_F surjective? Does G_F
   surjective imply G_P surjective? Does G surjective imply G_P surjective?
   ([[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)])
3. Is every reversible CA in three or more dimensions a composition of a
   generalized-Margolus rule and a translation? Do some d-dimensional block-permutation
   rules need a clock cycle as long as d + 1?
   ([[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)])
4. Can one decide whether a 1D CA has any non-trivial conserved quantity, or find them
   all? ([[conserved-quantity](pages/conserved-quantity.md)])
5. Is rule 110 intrinsically universal?
   ([[intrinsic-universality](pages/intrinsic-universality.md)])
6. Over a fixed state set, is surjectivity of 1D CA the only decidable property of limit
   sets? ([[limit-set](pages/limit-set.md)])
7. Is positive expansivity of 1D CA decidable?
   ([[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)])
8. Are the temporally periodic configurations dense when G is surjective? If so, chaos in
   CA is just transitivity. ([[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)])
9. (Smith 1972) Is real-time CA recognition as strong as linear-time recognition,
   equivalently, is it closed under reversal?
   ([[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)])

## Entities & Concepts

- [[jarkko-kari](pages/jarkko-kari.md)] - author
- [[cellular-automaton](pages/cellular-automaton.md)] - the formal triple (S, N, f), finite and periodic configurations
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - von Neumann and Moore neighbourhoods, radius r, one-way (radius-½) rules
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - Wolfram numbers, 88 essentially different rules
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Wolfram, Culik-Yu and Kurka classes
- [[game-of-life](pages/game-of-life.md)] - object categories, universality, undecidable death
- [[rule-110](pages/rule-110.md)] - universal; intrinsic universality open
- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] - CA = continuous shift-commuting maps in any dimension
- [[shift-dynamical-system](pages/shift-dynamical-system.md)] - the Cantor topology on configurations
- [[wang-tiles](pages/wang-tiles.md)] - the tiling problem, aperiodic sets, NW-determinism, SNAKES
- [[garden-of-eden](pages/garden-of-eden.md)] and [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] - surjectivity vs injectivity on finite configurations
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - reversibility, inverse neighbourhoods, block representation
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - block partitioning and the billiard-ball computer
- [[conserved-quantity](pages/conserved-quantity.md)] - additive invariants
- [[intrinsic-universality](pages/intrinsic-universality.md)] - simulating every CA
- [[limit-set](pages/limit-set.md)] - nilpotency and Rice's theorem for limit sets
- [[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)] - topological dynamics
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] - linear rules over rings, Laurent polynomials
- [[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)] - real-time and linear-time recognition
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the decidability results in one table

## Relation to Other Wiki Pages

Kari's survey takes the computer-science view of the field. Von Neumann and Moore
([[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)],
[[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)]) each
designed or analysed particular structures. Hedlund took the topological view of all 1D
rules and Wolfram the statistical one. Kari asks which properties of a rule can be
*decided* from its table. Kari cites the earlier sources for their theorems: the
Garden-of-Eden theorem (Moore, Myhill), the
[[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] and "reversible
iff bijective" (Hedlund), and the Wolfram numbering. It also states two readings that other pages
make. The first is that Hedlund's endomorphisms and automorphisms are the CA and
reversible CA of later usage: "In symbolic dynamics literature it is therefore customary
to call reversible CA automorphisms of the shift dynamical system". The second is that the
Garden-of-Eden theorem is usually stated as surjectivity iff injectivity on finite
configurations.[^18][^19]

Wolfram (1983) judged the elementary rules too simple for universal computation,[^20]
while Kari reports rule 110 proved universal by Cook and Wolfram, citing Wolfram
(2002).[^21] Rule 110 is not among Wolfram's 32 "legal"
rules, so the two statements do not strictly conflict ([[rule-110](pages/rule-110.md)]).
[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.3-4 [synthesis] - abstract: "a tutorial of CA theory to researchers in other branches of natural computing"; "The selection of topics ... reflects the research interests of the author"; topics: reversibility, conservation laws, decidability questions, computational universality and limit behavior
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.4-7 [synthesis] - §2.1: a d-dimensional CA is a triple (S, N, f), global transition function G; §2.3: finite configurations C_F and G_F, periodic configurations C_P and G_P; "the behavior of a CA can be quite different on finite, periodic and general configurations, so experiments done with periodic boundary conditions may be misleading"
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.4 [synthesis] - reversibility and conservation laws "can be programmed by choosing the local update rule properly"; using physics to run a universal CA; "While such truly programmable matter may be decades away, its potential is great"
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.4 [synthesis] - "Discrete simulation of fluid flows using CA has even become a field of its own in which CA models are called lattice gases"; refs [27, 31] (Frisch, Hasslacher, Pomeau 1986; Hardy, Pomeau, de Pazzis 1976); "Ising spin models [68] and diffusion phenomena"
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.30 - "Examples of omissions include the firing squad synchronization problem [52], results on fault tolerance [28] and quantum CA [71]."
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.4 - "one-dimensional CA behave in some respects differently from the higher-dimensional ones"
[^7]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.15-19 [synthesis] - Theorem 6 (G_F injective iff G surjective, Moore and Myhill); Theorem 7 implications in every dimension and in 1D; Theorem 9 (Amoroso and Patt: 1D injectivity and surjectivity decidable); Theorem 10 (Kari: undecidable in 2D)
[^8]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.14-15, 17, 19-20 [synthesis] - SNAKES tile set and its plane-filling property; SNAKE-XOR; the injectivity proof reduces the tiling problem using a control layer of T and SNAKES tiles and an xor layer
[^9]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.24-25 [synthesis] - Theorem 15 (Culik et al. [19], Kari [40]): nilpotency undecidable for every d ≥ 1; Theorem 16 holds for input CA with arbitrary state sets, and over a fixed state set 1D surjectivity is a decidable limit-set property (Open problem 6); 1D proof via NW-deterministic tiles; Theorem 16 (Rice's theorem for limit sets, Kari): all non-trivial properties of d-dimensional limit sets are undecidable
[^10]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.18-20 [synthesis] - Margolus neighbourhood; no computable bound on the inverse neighbourhood in 2D; Theorem 11 (Kari): all 1D and 2D reversible CA are a composition of a GMN-CA and a "translation-type" CA
[^11]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.11, 22-23 [synthesis] - Theorem 1 (Berlekamp et al.: Life universal), Theorem 2 (Cook and Wolfram: rule 110 universal); §6 intrinsic universality; Theorem 13 (Ollinger: 6 states, neighbourhood (−1, 0, 1))
[^12]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.28-29 [synthesis] - Corollary 4 (Ito et al.): a gcd condition for surjectivity and a prime-factor condition for injectivity over ℤ_m; Theorem 18 (Cattaneo et al., Manzini and Margara) gcd conditions for equicontinuity, sensitivity, transitivity and positive expansivity; "all the given conditions are fast to test"
[^13]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.30 [synthesis] - closure of L(RCA) under reversal holds iff L(RCA) = L(LCA); "This is an intriguing open problem, already posed in 1972"
[^14]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.15-17 [synthesis] - Theorem 7 (two implications stated for 1D only); SNAKE-XOR shows G_P injective does not imply G injective in 2D; Figs. 6 and 7; "Fig. 7 contains three implications whose status is unknown"
[^15]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.12-13, 15, 18-19 [synthesis] - Corollary 1 (reversible iff bijection); Corollary 3 (injectivity, bijectivity and reversibility equivalent); Hedlund and Richardson independently; Theorems 9 and 10
[^16]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.8, 25-26 [synthesis] - "The classification due to Wolfram is vague"; Culik and Yu proved their classification undecidable; Durand, Formenti and Varouchas: membership in K1, K2, K3 undecidable for 1D; "The membership problem for class (K4) remains an open problem"
[^17]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.12, 17, 20, 22-23, 25-26, 30 [synthesis] - Open problems 1-9 as stated in §§2.6, 3, 4, 5, 6, 7, 8 and 10
[^18]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.13 - "In symbolic dynamics literature it is therefore customary to call reversible CA automorphisms of the shift dynamical system. CA are termed endomorphisms."
[^19]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.15 - "Theorem 6 (Garden-of-Eden theorem, Moore [53] and Myhill [55]). G_F is injective if and only if G is surjective."
[^20]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.630 - "the elementary cellular automata considered here and in Secs. II and III are not of sufficient complexity to be capable of universal computation."
[^21]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 - "Theorem 2 (M. Cook, S.Wolfram [76]). Rule 110 is computationally universal."
