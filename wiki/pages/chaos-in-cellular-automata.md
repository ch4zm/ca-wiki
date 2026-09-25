---
title: Chaos in Cellular Automata
category: Concepts
summary: Cellular automata as topological dynamical systems on the Cantor space - equicontinuity, sensitivity, positive expansivity, transitivity, mixing, and Devaney chaos; in CA transitivity already implies sensitivity and surjectivity, positively expansive rules exist only in 1D, and whether surjectivity gives dense periodic points is open
tags: [concept, topological-dynamics, chaos, equicontinuity, sensitivity, expansivity, transitivity, devaney, kurka]
sources: [theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-24
---

# Chaos in Cellular Automata

> Kurka (1997), Blanchard and Maass (1997), Devaney (1989) and the other papers named
> here are cited via
> [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)]
> and have not been read.

## Description

**The setting.** A CA's global map G is a continuous map of the compact metric space of
configurations, with the Cantor topology in which two configurations are close when they
agree on a large region around the origin
([[shift-dynamical-system](pages/shift-dynamical-system.md)]). So a CA is a topological
dynamical system, and the notions of chaos theory apply. Most of them are about what
iterating G does to configurations that start close together.[^1]

**Equicontinuity.** A configuration c is an *equicontinuity point* if configurations
close enough to c stay as close as desired to c's orbit for all time. G is
*equicontinuous* if every configuration is one. G is equicontinuous iff Gⁿ = Gᵐ for some
n ≠ m, meaning the rule is eventually periodic as a map (Kurka).[^2]

**Sensitivity.** G is *sensitive to initial conditions* if there is one ε > 0 such that
every configuration has arbitrarily close neighbours whose orbits eventually differ from
its own by more than ε. For CA, having no equicontinuity points already implies
sensitivity.[^3]

**Positive expansivity.** Stronger still: there is an ε such that *any* two different
configurations, however close, eventually separate by more than ε.[^4] Positively
expansive CA exist only in one dimension. There are none in two or more.[^5] Every
positively expansive CA is mixing (Blanchard and Maass).[^6]

**Kurka's classes** sort every CA into exactly one of K1 equicontinuous, K2 some
equicontinuity points, K3 sensitive but not positively expansive, and K4 positively
expansive ([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]).
Membership in K1-K3 is undecidable for 1D CA. Whether positive expansivity is decidable is
open.[^5]

**Transitivity and mixing.** G is *transitive* if for any two open sets U and V some Gᵗ(U)
meets V. It is *mixing* if Gᵗ(U) meets V for *all* large enough t. Transitivity is
equivalent to some configuration having a dense orbit, by the Baire category theorem.
Mixing implies transitive, and in CA transitive implies surjective and sensitive
(Kurka).[^6]

**Devaney chaos.** Devaney calls a system chaotic if it is (1) transitive, (2) has dense
temporally periodic points, and (3) is sensitive. In CA (1) implies (3), so only (1) and
(2) are needed. Kari asks whether temporally periodic configurations are dense in every
surjective CA. If they are, then (since transitive implies surjective) chaos in CA is the
same as transitivity.[^7]

**Linear rules.** For linear CA over ℤ_m, equicontinuity, sensitivity, transitivity and
positive expansivity each reduce to a gcd test on the coefficients
([[additive-cellular-automaton](pages/additive-cellular-automaton.md)]).[^8]

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.7 (topology), §8 (dynamical systems approach), §9 (linear rules)

## Related Concepts

- [[shift-dynamical-system](pages/shift-dynamical-system.md)] - the Cantor space and its topology
- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] - CA are exactly the continuous shift-commuting maps
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Kurka's classes among the others
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - transitive CA are surjective
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] - the linear case, decided by gcd tests
- [[self-organization](pages/self-organization.md)] - Wolfram's statistical counterpart (damage spreading, strange-attractor behaviour)
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the dynamical properties among the other decision problems

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.12, 25 [synthesis] - Cantor topology, compact, metric; "two configurations are close to each other if they agree with each other within a large region around the origin"; "CA G is a continuous function on the compact metric space ... an example of a dynamical system studied by topological dynamics and chaos theory"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.25 [synthesis] - definition of equicontinuity point and Eq(G); equicontinuous if all configurations are equicontinuity points; "It was proved in [48] that G is equicontinuous if and only if Gⁿ = Gᵐ for some n ≠ m"
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.25 [synthesis] - sensitivity with ε chosen uniformly; "CA have the property that if there are no equicontinuity points then the CA is sensitive [48]"
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.25 [synthesis] - positive expansivity: ε > 0 with d(Gᵗ(c), Gᵗ(e)) > ε for some t for any two different c and e
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.26 [synthesis] - "In two- and higher-dimensional cases class (K4) is empty: there are no positively expansive two-dimensional CA [26,60]"; undecidable for 1D whether K1, K2 or K3 [23]; Open problem 7
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.26 [synthesis] - definitions of transitive and mixing; dense orbit equivalence via the Baire category theorem; "Trivially all mixing CA are also transitive"; positively expansive ⇒ mixing (Blanchard and Maass [7]); transitive ⇒ surjective and sensitive (Kurka [48])
[^7]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.26 [synthesis] - Devaney's three conditions [21]; "In CA transitivity implies sensitivity so only conditions (1) and (2) remain"; Open problem 8: "Are the temporally periodic configurations dense when G is surjective?"; "If the answer is affirmative then chaos in CA becomes equivalent to transitivity"
[^8]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.28-29 [synthesis] - Theorem 18 (Cattaneo et al. and Manzini and Margara): gcd conditions for equicontinuity, sensitivity, transitivity and positive expansivity over ℤ_m
