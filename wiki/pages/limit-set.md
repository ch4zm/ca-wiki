---
title: Limit Set
category: Concepts
summary: The configurations a cellular automaton can still reach after arbitrarily many steps - compact, non-empty, the largest set G maps onto itself, finite exactly when the rule is nilpotent; nilpotency is undecidable in every dimension, and so is every non-trivial property of limit sets (Kari's Rice theorem)
tags: [concept, limit-set, attractor, nilpotency, undecidability, rice-theorem, kari]
sources: [theory-of-cellular-automata-a-survey, aucm-ch12-linear-cellular-automata-and-decidability]
created: 2026-09-24
updated: 2026-09-24
---

# Limit Set

## Description

**Definition.** Some configurations are *transient*: they can appear only early in the
evolution. [[garden-of-eden](pages/garden-of-eden.md)] configurations, for instance,
cannot appear after the first step. The **limit set** Λ of a CA G keeps the configurations
that matter in the long run, those that can occur after arbitrarily many steps.
Equivalently, Λ is the set of configurations that are not Garden-of-Eden for any power
Gⁿ. With Λ⁽ⁿ⁾ = Gⁿ(C), the images form a decreasing chain Λ⁽¹⁾ ⊇ Λ⁽²⁾ ⊇ ⋯ and

  Λ = ⋂ₙ Λ⁽ⁿ⁾.[^1]

**Basic properties** (credited in the survey to "Culik et al." and Hurd):[^2]

- Λ is **compact**, as an intersection of compact images of the compact configuration
  space.
- Λ is **non-empty**: it always contains a homogeneous configuration, since every CA has a
  temporally periodic homogeneous configuration.
- **G(Λ) = Λ**, and Λ is the largest set with that property. Every configuration in Λ has a
  predecessor in Λ, and hence an infinite chain of predecessors. The proof is a
  compactness argument on the nested closed sets G⁻¹(c) ∩ Λ⁽ⁿ⁾.
- Λ is either a single configuration or infinite, and if infinite it contains
  non-periodic configurations. It is a single configuration **iff the CA is nilpotent**,
  and then Λ = Λ⁽ⁿ⁾ for some n.

**Nilpotency.** A CA is *nilpotent* if, after some number of steps n, every configuration
has become the same configuration c. That c must be homogeneous and a fixed point.[^3]
Whether a given CA is nilpotent is **undecidable in every dimension**. The survey credits
Culik, Pachl and Yu and Kari, and sketches the 2D proof from the first and the 1D proof
from the second.[^4]

- *2D.* Given a Wang tile set T, take states T ∪ {q}. A cell keeps its tile if the tiling
  is correct around it and otherwise becomes q. The CA is nilpotent iff T does not tile the
  plane, and tiling is undecidable.[^5]
- *1D.* Take an NW-deterministic tile set T
  ([[wang-tiles](pages/wang-tiles.md)]) and the neighbourhood (0, 1). Set f(a, b) to the
  unique tile that fits with a on its west and b on its north, and to q if there is none. A
  valid tiling is then a space-time diagram, read along diagonals, that never produces q,
  so the CA is not nilpotent. If there is no valid tiling, q appears at bounded intervals
  from any start and spreads over the whole line in finitely many steps. NW-deterministic
  tiling is undecidable, so 1D nilpotency is too.[^6]

In logic, nilpotency is the sentence ∃y ∀x (x →* y ∧ y → y). Swapping the quantifiers
gives "every orbit ends in a fixed point", a version of Wolfram class I
([[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]).
By compactness a nilpotent rule has a fixed bound on the number of steps. Even with that
bound n written out, the first-order sentence compiles to an automaton exponential in n,
so checking it directly is hopeless except for tiny n.[^7]

Nilpotency is stronger than class CY1 of Culik and Yu, where only *finite*
configurations must die. Rule 128, where the quiescent 0 spreads and kills every 1, is in
CY1 without being nilpotent
([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]).[^8]

**Rice's theorem for limit sets.** A *property of limit sets* is any family of CA such
that two CA with the same limit set are either both in it or both out, whatever their
state sets. It is non-trivial if some CA have it and some do not. Kari reduced nilpotency
to every such property. **In every dimension, every non-trivial property of limit sets is
undecidable.**[^9] Before this, Culik, Pachl and Yu had already shown several particular
properties of limit sets undecidable. Theorem 15 also gives the uncomputability of
topological entropy (Hurd, Kari and Culik).[^10]

**Fixed state set.** The theorem allows the state set of the input to vary. If S is fixed,
surjectivity becomes a limit-set property, since G is surjective iff Λ contains every
configuration over S. Surjectivity is decidable in 1D, so at least one property of limit
sets is decidable over a fixed S. Kari asks whether it is the only one.[^11]

## Appearances in Sources

- [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] - nilpotency as a sentence; its quantifier swap FP
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.4 (nilpotency), §7 (limit sets, Theorems 14-16, Open problem 6)

## Related Concepts

- [[garden-of-eden](pages/garden-of-eden.md)] - the configurations Λ leaves out first
- [[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)] - a surjective rule has the whole space as its limit set
- [[wang-tiles](pages/wang-tiles.md)] - the reductions behind undecidable nilpotency
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the other decision problems
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Culik-Yu class 1 vs nilpotency
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - Wolfram's statistical view of the same shrinking of reachable configurations
- [[jarkko-kari](pages/jarkko-kari.md)] - 1D nilpotency and Rice's theorem
- [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)] - nilpotency and FP as orbit sentences

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.23 [synthesis] - transient configurations; "Garden of Eden configurations cannot appear after the first update"; Λ consists of configurations "that are not Garden-of-Eden configurations for any Gⁿ"; Λ⁽ⁿ⁾ = Gⁿ(C), Λ = ⋂ Λ⁽ⁿ⁾, decreasing chain
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.23-24 [synthesis] - compactness; non-empty via temporally periodic homogeneous configurations; singleton or infinite with non-periodic configurations; singleton implies Λ = Λ⁽ⁿ⁾ and nilpotency [19]; the compactness proof that G(Λ) = Λ; infinite pre-image sequence; Theorem 14 (Culik et al. [20] and Hurd [34]); the survey's [20] is Czeizler and Kari, so the reference number looks like a misprint (own reasoning)
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.7 [synthesis] - "CA G is called nilpotent if Gⁿ(C) is a singleton set for sufficiently large n"; the configuration "has to be homogeneous and a fixed point"
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.24 - "Theorem 15 (Culik et al. [19] and Kari [40]). For every d ⩾ 1, it is undecidable whether a given d-dimensional CA is nilpotent."
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.24 [synthesis] - 2D construction with state set T ∪ {q}; "This CA is nilpotent if and only if T does not admit a valid tiling of the plane"; Theorem 4
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.24 [synthesis] - 1D construction with NW-deterministic T, neighbourhood (0, 1), f(a, b) = c for the matching tile, else q; valid tiling as space-time diagram on SW/NE diagonals; otherwise q's appear at bounded intervals and spread; contradiction with Theorem 5
[^7]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.267, 271 [synthesis] — "A standard compactness argument shows that there has to be a fixed bound n, the nilpotency index"; the matrix converts to a de Bruijn product automaton whose "size ... is exponential in n"; "the nilpotency statement ∃y ∀x (x →* y ∧ y → y) is undecidable according to [21]. By interchanging quantifiers we obtain the 'fixed point' sentence FP"
[^8]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.9 - "every nilpotent CA belongs to class (1) but it has also non-nilpotent members, e.g. rule 128 in which the quiescent state 0 spreads killing all 1's."
[^9]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.24-25 [synthesis] - definition of a property of limit sets "regardless of their state set" and of non-triviality; "the nilpotency problem was successfully reduced to all non-trivial properties of limit sets"; Theorem 16 (Rice's theorem for limit sets, Kari [42])
[^10]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.24 - "Using Theorem 15 one can show that the topological entropy of a given CA is uncomputable [35]. In [19] several properties of the limit sets were proved undecidable."
[^11]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.25 [synthesis] - with S fixed, "a CA is surjective if and only if its limit set contains all configurations over the state set S"; decidable in dimension one by Theorem 9; Open problem 6
