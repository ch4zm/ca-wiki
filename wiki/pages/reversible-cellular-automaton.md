---
title: Reversible Cellular Automaton
category: Concepts
summary: A cellular automaton whose global map has an inverse that is again a cellular automaton - equivalent to bijective and to injective in every dimension; decidable in 1D, undecidable in 2D; universal reversible rules exist, and in 1D and 2D every reversible rule is a block permutation plus a translation
tags: [concept, reversibility, injectivity, bijectivity, decidability, physics, margolus, kari]
sources: [theory-of-cellular-automata-a-survey, endomorphisms-and-automorphisms-of-the-shift-dynamical-system, statistical-mechanics-of-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Reversible Cellular Automaton

## Description

Two CA G₁ and G₂ are **reversible**, and inverses of each other, if G₁ ∘ G₂ = G₂ ∘ G₁ =
id. Whether two given rules are inverses is decidable, because composition can be computed
and equivalence of two CA can be checked.[^1]

**Three equivalent conditions.** A CA is reversible iff its global map is a bijection. The
inverse of a bijective CA commutes with the shifts, and it is continuous because the
configuration space is compact, so by the
[[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] it is itself a
CA.[^2] Injectivity alone is enough: an injective CA is surjective (a consequence of the
[[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]), so injectivity, bijectivity
and reversibility coincide.[^3] Hedlund and Richardson proved this independently.[^4] In
symbolic dynamics, reversible CA are the automorphisms of the shift
([[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)]).[^5]

**Why physics cares.** Microscopic physics is reversible, so CA that model it should be.
A parallel computer that makes the best use of physics must be reversible too, because
irreversibility always costs energy, in practice as heat.[^6] Wolfram makes the same point
from the ensemble side: ordinary rules lose information and their entropy can fall, while
reversible rules keep Liouville's theorem
([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]).[^7]

**Universal reversible rules.** It was once unclear whether interesting reversible CA
existed. Toffoli (1977) showed that any d-dimensional CA can be simulated by a
(d + 1)-dimensional reversible one, which gives universal 2D reversible CA. Morita and
Harao (1989) simulated reversible Turing machines on 1D reversible CA. Since reversible
Turing machines can be universal (Bennett 1973), universal 1D reversible CA exist. Margolus's
billiard-ball computer is a particularly elegant 2D example
([[margolus-neighbourhood](pages/margolus-neighbourhood.md)]).[^8]

**Deciding reversibility.** For 1D rules, Amoroso and Patt (1972) gave algorithms for both
injectivity and surjectivity. Sutner later gave cleaner ones using de Bruijn graphs. For
2D rules neither is decidable (Kari).[^9] The injectivity proof reduces the tiling problem.
Given a tile set T, build a CA with a control layer that holds a T-tile and a SNAKES tile
([[wang-tiles](pages/wang-tiles.md)]), and an XOR layer. A cell is active when both tilings
are valid there. An active cell adds, mod 2, the XOR bit of the neighbour its arrow points
to. If T tiles the plane, two configurations with the same valid control layer and
complementary XOR layers have the same image. If two configurations collide, the
plane-filling property forces valid tilings of arbitrarily large squares. So the CA is
injective iff T does not tile the plane.[^10]

The two problems fail in opposite directions. Injectivity of G is semi-decidable: search
for an inverse. Non-injectivity of G_F on finite configurations is semi-decidable: search
for two finite configurations with the same image.[^11]

**How big the inverse is.** Because 2D injectivity is undecidable, the neighbourhood of
the inverse CA has no computable bound. Otherwise one could test every candidate inverse
up to that size. In 1D the inverse is small: for a radius-½ rule with s states it needs at
most s − 1 consecutive cells, and that bound is tight.[^12]

**Reversible local rules.** A reversible global map still has a many-to-one local rule
f, which cannot be built from reversible logic. Toffoli and Margolus asked whether every
reversible CA can be built from reversible local rules instead. Kari showed that in 1D and
2D every reversible CA is a generalized-Margolus (block-permutation) rule composed with a
"translation-type" rule, and that a d-dimensional block rule needs a clock cycle of at most
d + 1. The translation part cannot be dropped: the left shift is not a block-permutation
rule.[^13] In three or more dimensions, extra states always make such a representation
possible (Durand-Lose), but whether it exists without them is open. So is whether any
block rule really needs a cycle as long as d + 1.[^14]

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.4 definition, Corollary 1, §4 in full
- [[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)] - 1D: injective endomorphisms are automorphisms (Thm 5.14)
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - reversible second-order rules and entropy

## Related Concepts

- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] - the reversible 1D rules as a group
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - reversible by construction
- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] - why injective implies surjective
- [[garden-of-eden](pages/garden-of-eden.md)] - reversible rules have none
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - what reversibility rules out
- [[wang-tiles](pages/wang-tiles.md)] - the 2D undecidability proof
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - reversibility among the other decision problems
- [[conserved-quantity](pages/conserved-quantity.md)] - reversible rules conserve information; other conservation laws
- [[curtis-hedlund-lyndon-theorem](pages/curtis-hedlund-lyndon-theorem.md)] - why the inverse is a CA

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.7-8 [synthesis] - G₁ ∘ G₂ = G₂ ∘ G₁ = id defines reversible and inverse automata; "One can effectively decide whether two given CA are inverses of each other", from the effectiveness of composition and decidability of equivalence
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.12-13 [synthesis] - the inverse of a bijective CA commutes with the shift and is continuous because C is compact, "and therefore it is a CA function"; Corollary 1 (Hedlund): "A CA G is reversible if and only if it is a bijection."
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.15 - "Corollary 3. Injective CA are also surjective. Hence injectivity, bijectivity and reversibility are equivalent."
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 - "Hedlund [33] and Richardson [57] independently proved that all one-to-one CA are reversible"
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.13 - "In symbolic dynamics literature it is therefore customary to call reversible CA automorphisms of the shift dynamical system."
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.17 [synthesis] - reversibility "implied by the laws of quantum mechanics"; "a massively parallel computer that optimally uses physics to compute must itself be reversible. Non-reversibility always implies energy dissipation, in practice in the form of heat."
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.622-625 [synthesis] - in a reversible system the number of configurations stays constant (Liouville's theorem); for irreversible cellular automata the entropy may decrease
[^8]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 [synthesis] - "At that point of time it was not know whether interesting reversible CA exist"; Toffoli [65]: d-dimensional CA simulated by (d + 1)-dimensional reversible CA; Morita and Harao [54] reversible Turing machines on 1D reversible CA; Bennett [4]; Theorem 8; "An especially elegant two-dimensional solution is the billiard-ball computer by Margolus"
[^9]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.19 [synthesis] - Theorem 9 (Amoroso and Patt, 1972); "Elegant decision algorithms based on de Bruijn graphs were later designed by Sutner"; Theorem 10 (Kari): "There are no algorithms to determine if a given two-dimensional CA is injective or surjective."
[^10]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.19-20 [synthesis] - control layer with tiles T and SNAKES, xor layer; active iff valid on both components; the arrow selects the second bit; plane-filling property; "the CA we constructed is injective if and only if T does not admit a valid tiling"
[^11]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.20 [synthesis] - "a semi-algorithm exists for the injectivity of G (based on an exhaustive search for the inverse CA) and for the non-injectivity of G_F (based on looking for two finite configurations with the same image)"
[^12]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.20 [synthesis] - no computable upper bound on the inverse neighbourhood, "as otherwise we could test all candidate inverses one-by-one"; 1D radius-½: at most s − 1 consecutive cells [20], "this bound is tight [39]"
[^13]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.20 [synthesis] - the local rule f of a reversible G "is not one-to-one ... useless if we want to implement G in reversible logic"; question of [67]; Theorem 11 (Kari [43,45]); "left shift σ cannot be implemented as a GMN-CA alone"
[^14]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.20 [synthesis] - in higher dimensions new states can be added so that the extended reversible CA uses the generalized Margolus neighbourhood [24]; Open problem 3
