---
title: "Bays (1987), Candidates for the Game of Life in Three Dimensions"
category: Sources
summary: Carter Bays's paper defining a "Game of Life" rule strictly (a glider that arises from random soup, and bounded growth from every soup) and finding three 3D rules that qualify - B6/S567, B5/S45 and B3/S3 on the 12-neighbour sphere packing; B6/S567 runs Conway's Life exactly on a pair of planes, so walls built from it can hold infinitely many parallel copies of Life
tags: [source, paper, three-dimensional, gl-rule, glider, soup, rule-space]
sources: [bays-1987-candidates-for-the-game-of-life-in-three-dimensions]
created: 2026-09-25
updated: 2026-09-25
---

# Bays (1987), Candidates for the Game of Life in Three Dimensions

**Source:** raw/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.pdf (Bays, C., "Candidates for the Game of Life in Three Dimensions", *Complex Systems* 1, 373-400, 1987)
**Date ingested:** 2026-09-25
**Type:** paper

## Summary

Bays asks which three-dimensional rules deserve the name "Life", and answers with a
definition. A rule is a Game of Life if a glider exists and arises naturally from random
soup, and if every soup shows bounded growth.[^1] He writes rules as four numbers
E_l E_u F_l F_u. A live cell survives with E_l to E_u live neighbours, and a dead cell is
born with F_l to F_u, so Conway's rule is 2333.[^1] In B/S form, E_l E_u F_l F_u is
B{F_l..F_u}/S{E_l..E_u}, so 2333 is B3/S23 (own reasoning, from the definitions).

On the cubic grid, with 26 neighbours, there are 123,201 such rules. Two short theorems
cut the search down: birth needing 10 or more neighbours rules out gliders, and birth on 4
or fewer gives unlimited growth. Of the rules tried, only **5766** (B6/S567) and **4555**
(B5/S45) pass.[^2] Both are described on [[three-dimensional-life](pages/three-dimensional-life.md)].

The most striking result is about 5766. A Conway pattern copied onto two adjacent planes
evolves exactly as in 2D Life, as long as no dead cell sees six live neighbours and no live
cell sees five. Flat "time-space barriers" four planes apart forbid that growth outright,
so the whole of Conway's universe, or infinitely many parallel copies, runs between
them.[^3] A last section moves to the 12-neighbour grid of densely packed spheres, where
a counting argument forces any Game of Life to have the form E_l E_u 33, and 3333 (B3/S3)
qualifies.[^4]

## Key Takeaways

- The definition turns "Life-like" from a feeling into a test: a natural glider and
  bounded growth from random soup ([[gl-rule](pages/gl-rule.md)]).[^1]
- Bays's reason for demanding a *natural* glider: if one does not condense out of soup,
  there is little hope of building one, or a glider gun, by hand.[^1]
- Three 3D rules pass: 5766 and 4555 on the cube grid, 3333 on the sphere packing.[^2][^4]
- 5766 contains Conway's Life as a two-plane subsystem; 4555 is its own universe with its
  own 10-cell glider.[^3][^5]

## Entities & Concepts

- [[gl-rule](pages/gl-rule.md)], [[three-dimensional-life](pages/three-dimensional-life.md)], [[game-of-life](pages/game-of-life.md)], [[glider](pages/glider.md)], [[soup-search](pages/soup-search.md)], [[moore-neighbourhood](pages/moore-neighbourhood.md)], [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)]

## Relation to Other Wiki Pages

The first of three Bays papers here. [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)]
carries the same test to the triangular grid, and
[[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)]
to the hexagonal and pentagonal ones.

[^1]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.373-374 [synthesis] - environment E_l ≤ E ≤ E_u keeps a live cell alive, fertility F_l ≤ F ≤ F_u gives birth, "For Conway's Life, R = (2333)"; Definition 1: "A glider must exist and must occur 'naturally' if we apply ElEuFlFu repeatedly to primordial soup configurations" and "All primordial soup configurations ... must exhibit bounded growth"; "if a glider does not condense out of some haphazard arrangement of cells, then there is little hope of creating one by bombarding some configuration with a (man-made) glider"
[^2]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] p.375 [synthesis] - 351 × 351 = 123,201 possible rules; Theorem 2, "Any rule ElEuFlFu with Fl ≥ 10 cannot support a glider"; Theorem 3, "Fl ≤ 4 leads to unlimited growth"; "Of all the rules investigated, only R = (4555) and R = (5766) satisfy definition 1"
[^3]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.382,384 [synthesis] - Theorem 7: a Conway object has an analog under 5766 iff "A non-living cell in the neighborhood of the object cannot have six living neighbors" and "A living cell cannot have five neighbors"; time-space barriers, a planar form where each live cell has seven neighbours; with barriers four planes apart "an analog to the entire Conway Life universe is contained between the barriers ... we could construct an infinite number of parallel Conway Life universes"
[^4]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.393,396 [synthesis] - the 12-neighbour "densely packed spheres" tessellation; Theorems 11 and 12 (Fl ≥ 4 no glider, Fl ≤ 2 unlimited growth); "if any Game of Life exists, it must be of the form ElEu33. The only rule that seems to exhibit gliders is (rather nicely) R = (3333) ... This rule also has bounded growth"
[^5]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.387 - "The (4555) glider contains ten elements and, like Conway's glider (and its (5766) analog), has a period of four"
