---
title: Triangular neighbourhood
category: Concepts
summary: The 12 cells touching a cell on the grid of equilateral triangles (three across its edges, nine at its corners); 8,464 two-state count-based rules live there, and eleven of them pass Carter Bays's Game of Life test, more than on any other grid, though none rivals Conway's
tags: [concept, neighbourhood, triangular-grid, lattice, gl-rule, glider]
sources: [bays-1994-cellular-automata-in-the-triangular-tessellation, bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations]
created: 2026-09-25
updated: 2026-09-25
---

# Triangular neighbourhood

## Description

On the grid of equilateral triangles, each cell touches 12 others: three that share an
edge and nine that share only a corner. Cells come in two orientations, pointing up and
pointing down.[^1] Counting all 12 gives Bays's count-based rules. Their survival and
birth ranges can each be any of 91 intervals or none, so there are 92 × 92 = 8,464 of
them.[^2]

**Growth bounds.** Birth on 2 or fewer neighbours always grows without bound, since two
touching cells keep spreading. Birth needing 6 or more is always bounded, since no cell
outside a straight or convex border can touch more than five live cells.[^2] Bounded rules
with wide ranges keep their interiors churning for so long that the period is effectively
never reached: with n cells in turmoil and k generations, the chance of repeating a pattern
is about k²/2^(n+1).[^3]

**Games of Life here.** Eleven rules pass Bays's test ([[gl-rule](pages/gl-rule.md)]),
more than on any other grid he studied. In B/S form (translated from his notation, own
reasoning):[^4]

| Rule | Glider period | Notes |
|---|---|---|
| B4/S456 | 3 | glider easiest to find; one of the richest in oscillators |
| B45/S34 | 7 | no other known GL oscillator has period 7 |
| B456/S45 | 8 | the most prolific in oscillators |
| B456/S23 | 5 | shares its glider and many oscillators with B45/S23 |
| B456/S34 | 12 | glider moves two cells per period |
| B45/S23 | 5 | same glider as B456/S23 |
| B3/S27 | 18 | glider shrinks to four cells in some phases; few other oscillators |
| B3/S2 | 36 | a huge glider |
| B4/S35 | 3 | |
| B46/S24 | 8 | |
| B46/S246 | 10 | its glider moves along the triangles' bases |

The same note's figure also shows B3/S278, which it calls a GL rule, with a period-80
glider that throws off debris as it goes and which also carries the B3/S27 glider; its text
counts eleven rules in all.[^5]

All six rules found first settle random soups faster, and leave far less debris, than
Conway's rule does on the square grid. Bays reads that as a sign that glider guns will be
hard to find here.[^6]

**Conway's numbers on triangles.** B3/S23 on this grid is bounded and settles even more
slowly than Life does, going through wild swings in population, but no glider has been
found and it has no period-2 oscillators. Among B3/S01, B3/S12, B3/S23 and B3/S34 it is the
only bounded one.[^7]

**Simulating it.** Up and down triangles map onto a square array, with a 12-cell template
for each orientation chosen by the parity of the coordinates. Swapping templates runs the
square, hexagonal, Cairo-pentagonal and mixed tilings in the same program.[^8] Golly's
higher-range rules also offer a triangular neighbourhood
([[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)], code
NL).[^9]

## Appearances in Sources

- [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] - the whole paper
- [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] - five more triangular GL rules
- [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] - the NL code

## Related Concepts

- [[gl-rule](pages/gl-rule.md)] - the test
- [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)] - the dual grid, with six neighbours
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the square grid's eight
- [[three-dimensional-life](pages/three-dimensional-life.md)] - Bays's other grids

[^1]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] pp.127-128 - "each cell has 12 touching neighbors: three on the edges and nine on the vertices"; Figure 1, "There are two types of cells: E and O cells"
[^2]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] p.128 [synthesis] - 91 environment values "plus the rule 'no cell remains alive'"; "92 × 92 = 8464 LFR rules"; Theorem 1 (Fl ≤ 2 unbounded) and Theorem 2 (Fl ≥ 6 bounded, "no currently dead cell can possibly touch more than 5 cells")
[^3]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] pp.128-130 [synthesis] - bounded rules "evolve into extremely high-period oscillators that are usually contained within convex enclosures"; the probability of having met a previous pattern "is simply k²/2^(n+1)"
[^4]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] pp.130-134,138 [synthesis] - Life 4644, 3445, 4546, 2346, 3446, 2345; 4644 glider period 3, "the most easily discovered"; 3445 glider period 7, "No other oscillator for any GL rule has been discovered whose period is seven"; 4546 period 8; 2345 and 2346 share a period-5 glider; 3446 period 12, "moves two cells per cycle"; "The richest rules in terms of easily discoverable oscillators appear to be Life 4644 and 4546"; "The most prolific GL rule appears to be Life 4546"; [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] pp.248,250-251 - 2,7/3 (period 18, "several states containing only four or five cells", "a paucity of other simple oscillators"), 2/3 (period 36, "huge"), 3,5/4 (period 3), 2,4/4,6 (period 8), 2,4,6/4,6 (period 10, "movement is parallel to the bases of the triangles"); total of 11
[^5]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] p.250, Fig. 7 - "An even more remarkable GL rule is 2,7,8/3. The illustrated glider has a period of 80 ... spewing off much material as it moves along"; p.251 - "These five additional GL rules brings the total number of triangular GL rules to 11"
[^6]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] pp.130,142 [synthesis] - "experiments under Conway's rule yield much more residue than any of the GL rules. Furthermore, Life 2333 requires more time to settle ... devices such as 'glider guns' ... will be hard to discover"; Figure 15 orders the six by rate of stabilization
[^7]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] pp.144-146 [synthesis] - rule 2333 "appears to have bounded growth and stabilizes even more slowly than Life 2333. So far no glider has been discovered"; "Growth for this rule decays very slowly, going through wild gyrations"; "no period-two oscillators"; "among rules 0133, 1233, 2333, and 3433, rule 2333 is the only rule where growth is bounded"
[^8]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] pp.148-149 [synthesis] - even and odd cells in a two-dimensional array, "We determine whether a cell is even or odd by finding (I + J) mod 2"; the same program explores "the hexagonal tessellation, the Cairo tessellation ... or the square tessellation"; templates for mixed tilings
[^9]: [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] L13,L32 - "except for the Triangular neighbourhood where r is from 1 to 250"; "NL for Triangular"
