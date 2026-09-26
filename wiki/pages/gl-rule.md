---
title: GL rule (a Game of Life "worthy of the name")
category: Concepts
summary: Carter Bays's test for when a rule on any grid counts as a Game of Life - every touching neighbour counts equally, a glider arises naturally from random soup, and every random soup eventually settles; Conway's B3/S23 is a borderline case, and qualifying rules are known on square, triangular, hexagonal, pentagonal and 3D grids
tags: [concept, gl-rule, rule-space, glider, soup, bounded-growth, classification]
sources: [bays-1987-candidates-for-the-game-of-life-in-three-dimensions, bays-1994-cellular-automata-in-the-triangular-tessellation, bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations]
created: 2026-09-25
updated: 2026-09-25
---

# GL rule (a Game of Life "worthy of the name")

## Description

**The test.** Carter Bays calls a rule a *Game of Life*, or *GL rule*, only if it is
"worthy of the name". In its final form there are three conditions:[^1]
- **A. Plain counting.** Every touching neighbour counts, and counts the same. The rule
  sees only the cell's state and how many neighbours are live, like a
  [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] on its grid.
- **B. A glider.** At least one [[glider](pages/glider.md)] exists, and it must turn up
  naturally from random soup; Bays's probabilistic form asks for it with probability one.
- **C. Settling.** Random soups always stop growing. A finite wrapped universe filled at
  random eventually dies out or breaks into [[oscillator](pages/oscillator.md)]s.

A carefully built pattern may still grow forever, as Life's guns and breeders do; the
test only asks that random starts not do so.[^2]

**Why a natural glider.** Bays's argument: if a glider never condenses out of random
debris, there is little hope of making one by bombarding things with gliders, and a glider
gun is even less likely. The rarer the glider, the fewer interesting constructions.[^3] In
his words, "it is the relative abundance of the glider that gives Conway's rule its
allure".[^4] So the test is a proxy for having a construction kit, reached through
[[soup-search](pages/soup-search.md)].

**Life on the edge.** Conway's rule passes, but only just: it is "a borderline case, and
that contributes to its richness". Near misses show how narrow the band is.[^5]
- "3-4 Life" (B34/S34) has many oscillators, but random blobs grow without bound.
- On the hexagonal grid, B245/S3 has a period-10 glider, but large random blobs slowly
  grow forever.
- On the triangular grid, B456/S12 has a glider but grows without bound, while B3/S23 is
  bounded but has no known glider.

**Birth bounds.** Every grid has a narrow window for the lowest birth count. Too low and
two touching cells grow forever; too high and nothing can leave a convex border, so no
glider can move.[^6]

| Grid | Neighbours | Birth counts that always grow forever | Birth counts too high for a glider |
|---|---|---|---|
| Square | 8 | lowest 2 or less | lowest 4 or more |
| Hexagonal | 6 | lowest 1 | lowest 3 or more |
| Triangular | 12 | lowest 2 or less | lowest 6 or more |
| Cubic (3D) | 26 | lowest 4 or less | lowest 10 or more |
| Sphere packing (3D) | 12 | lowest 2 or less | lowest 4 or more |

That squeezes a Game of Life on the square grid to birth on 3, on the hexagonal grid to
birth on exactly 2, and on the sphere packing to birth on exactly 3.[^6]

**Known GL rules.** In B/S form (translated from Bays's notations):[^7]
- **Square grid:** B3/S23 (Conway's Life) and B3/S245, with a period-7 glider.
- **Hexagonal grid:** B2/S35H, with a period-5 glider
  ([[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)]).
- **Pentagonal (Cairo) tiling, 7 neighbours:** B346/S23, with a period-48 glider.
- **Triangular grid, 12 neighbours:** eleven rules
  ([[triangular-neighbourhood](pages/triangular-neighbourhood.md)]).
- **3D:** B6/S567 and B5/S45 on the cubic grid, and B3/S3 on the sphere packing
  ([[three-dimensional-life](pages/three-dimensional-life.md)]).

None of these, Bays concludes, rivals the richness of Conway's Game of Life.[^8]

**What the test leaves out (own reasoning).** It is a necessary condition for Life-like
richness. It says nothing about guns, glider synthesis or universality, and Bays's
triangular results suggest a rule can pass while settling too fast for guns to appear.
It also makes "natural" depend on soup experiments, so a rule can move into the list when
a glider is found. Its two halves echo two yes/no questions used to classify Life-like
rules: can a pattern escape its bounding box, and can a pattern die out
([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]).

## Appearances in Sources

- [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] - Definition 1, and the 3D search
- [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] - the probabilistic form; six triangular rules
- [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] - conditions A-C; hexagonal, pentagonal and square-grid rules

## Related Concepts

- [[game-of-life](pages/game-of-life.md)] - the rule the test is modelled on
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the square-grid rule family it screens
- [[glider](pages/glider.md)], [[soup-search](pages/soup-search.md)] - the natural glider it demands
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - other ways of sorting rules

[^1]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] p.245 - "A. When counting the neighbors of a cell, all touching neighbors are considered and treated the same. B. At least one glider exists. C. Start with a finite wrapped universe that is completely filled with a random pattern. Then after a finite number of generations, all such patterns eventually must either disappear, or decompose into one or more oscillators"; [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] p.374 - "A glider must exist and must occur 'naturally' if we apply ElEuFlFu repeatedly to primordial soup configurations"; [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] p.127 - a glider "discoverable with probability one by starting with finite random initial configurations"
[^2]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] p.127 - "this second condition does not eliminate the possibility that some unusual highly organized configuration can be constructed where the growth is unbounded"; [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] p.246 - "it is possible to construct quadratic growth patterns under Conway's Life rather easily. But Condition C eliminates the possibility that they could persist"
[^3]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] p.374 - "if a glider does not condense out of some haphazard arrangement of cells, then there is little hope of creating one by bombarding some configuration with a (man-made) glider. Thus, the 'rarer' a glider is, the less likely that interesting configurations (e.g. a 'glider gun' ...) may exist"
[^4]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] p.145 - "it is the relative abundance of the glider that gives Conway's rule its allure"
[^5]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] pp.246-248 [synthesis] - "The GL rule for Conway's Life is a borderline case, and that contributes to its richness"; 3-4 Life "is not a true GL rule, as random blobs exhibit unbounded growth"; hex 3/2,4,5 "supports a period 10 glider" but large blobs grow slowly; [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] pp.130,145 - "Rule 1246 also sports a glider ... but unfortunately leads to unbounded growth"; rule 2333 bounded, "no glider has been discovered"
[^6]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] p.128 [synthesis] - triangular Theorems 1 and 2 (Fl ≤ 2 unbounded, Fl ≥ 6 bounded); "Similar theorems for □ yield values of Fl ≤ 2 causing unbounded growth and Fl ≥ 4 causing bounded growth; for the hexagonal tessellation the values are 1 and 3"; [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.375,396 - cubic Theorems 2 and 3 (Fl ≥ 10 no glider, Fl ≤ 4 unlimited growth); sphere packing Theorems 11 and 12 (Fl ≥ 4 no glider, Fl ≤ 2 unlimited growth), "if any Game of Life exists, it must be of the form ElEu33"; [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] p.248 - hexagonal "F1 must be exactly 2"
[^7]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] pp.246-251 [synthesis] - square 2,3/3 and 2,4,5/3 (period-7 glider); hexagonal 3,5/2 (period-5 glider); Cairo 2,3/3,4,6 (period-48 glider); triangular total "to 11"; [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.375,396 - 4555, 5766 and 3333; B/S translations are own reasoning from Bays's definitions (E is survival, F is birth)
[^8]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] p.251 - "none has yet been found that rivals the richness of Conway's Game of Life"
