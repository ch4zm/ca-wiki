---
title: "Bays (2005), A Note on the Game of Life in Hexagonal and Pentagonal Tessellations"
category: Sources
summary: Carter Bays's short note restating his Game of Life test (all touching neighbours count equally, a glider exists, random fills always settle) and finding qualifying rules on the hexagonal grid (B2/S35H), the pentagonal Cairo tiling (B346/S23), a second one on the square grid (B3/S245) and more on the triangular grid; none rivals Conway's
tags: [source, paper, hexagonal, pentagonal, triangular-grid, gl-rule, glider]
sources: [bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations]
created: 2026-09-25
updated: 2026-09-25
---

# Bays (2005), A Note on the Game of Life in Hexagonal and Pentagonal Tessellations

**Source:** raw/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.pdf (Bays, C., "A Note on the Game of Life in Hexagonal and Pentagonal Tessellations", *Complex Systems* 15, 245-252, 2005; https://doi.org/10.25088/ComplexSystems.15.3.245)
**Date ingested:** 2026-09-25
**Type:** paper

## Summary

This note sharpens Bays's test ([[gl-rule](pages/gl-rule.md)]) into three conditions:
every touching neighbour counts the same, at least one glider exists, and any finite
wrapped universe filled at random eventually dies out or breaks into oscillators. An
oscillator here needs an *inert* boundary, one that lets it sit in empty space
unchanged.[^1] Conway's rule is "a borderline case, and that contributes to its
richness".[^2]

The note switches to list notation, survival counts then birth counts, so Conway's Life is
2,3/3 (in B/S, B3/S23).[^2] With lists instead of ranges, a second square-grid Game of
Life appears: 2,4,5/3, which is B3/S245, with a period-7 glider.[^2] The hexagonal grid has
one: 3,5/2 (B2/S35H), with a period-5 glider. There
birth must be on exactly 2: birth on 1 is unstable and birth on 3 allows no glider.[^3] On
the Cairo pentagonal tiling, whose seven neighbours sit between the hexagon's six and the
square's eight, 2,3/3,4,6 (B346/S23) qualifies with a period-48 glider.[^4] More triangular
rules bring that grid's count to 11.[^5]

## Key Takeaways

- Games of Life exist on every regular grid Bays tried: square, triangular, hexagonal,
  pentagonal and 3D.[^3][^4][^5]
- "3-4 Life" (B34/S34) fails the test: random blobs grow without bound.[^3]
- Near misses show how narrow the test is. The hexagonal B245/S3 has a period-10 glider
  but large random blobs slowly grow forever.[^3]
- Imposing symmetry on random starts is what makes gliders findable.[^6]
- None of these rules rivals the richness of Conway's Game of Life.[^6]

## Entities & Concepts

- [[gl-rule](pages/gl-rule.md)], [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)], [[triangular-neighbourhood](pages/triangular-neighbourhood.md)], [[glider](pages/glider.md)], [[oscillator](pages/oscillator.md)], [[rulestring](pages/rulestring.md)]

## Relation to Other Wiki Pages

Completes the line begun in [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)]
and [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)].
Its E/F list notation is the old S/B order of [[rulestring](pages/rulestring.md)].

[^1]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] p.245 [synthesis] - an oscillator is "a finite shape with an inert nonliving boundary"; "A. When counting the neighbors of a cell, all touching neighbors are considered and treated the same. B. At least one glider exists. C. Start with a finite wrapped universe that is completely filled with a random pattern. Then after a finite number of generations, all such patterns eventually must either disappear, or decompose into one or more oscillators"
[^2]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] pp.246-247 [synthesis] - "The GL rule for Conway's Life is a borderline case, and that contributes to its richness"; "Conway's Life is specified by 2,3/3"; "rule 2,4,5/3 is also a GL rule"; Figure 2, "The 2,4,5/3 glider has a period of seven"
[^3]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] pp.247-248 [synthesis] - "3-4 Life ... is not a true GL rule, as random blobs exhibit unbounded growth"; "a valid hexagonal GL rule has been found. The rule 3,5/2 ... its discovered glider has a period of five"; 3/2,4,5 "supports a period 10 glider" but "sufficiently large random blobs exhibit instability by growing slowly"; "F1 must be exactly 2, for if F1 = 1, then the rule will be unstable, and if F1 = 3, then no glider is possible"
[^4]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] p.248, Fig. 6 p.250 [synthesis] - the Cairo tiling, "the neighbor count (seven) is between that for the hexagonal and square tessellations"; "one GL rule has been discovered, namely 2,3/3,4,6. This rule supports an unusual glider with a period of 48"
[^5]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] pp.248,250-251 [synthesis] - further triangular GL rules 2,7/3 (period-18 glider), 2/3, 3,5/4, 2,4/4,6 and 2,4,6/4,6, plus 2,7,8/3 with a period-80 glider in Fig. 7; "These five additional GL rules brings the total number of triangular GL rules to 11"
[^6]: [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] p.251 - "The ability to impose symmetry on these blobs greatly increases the probability of finding interesting shapes"; "none has yet been found that rivals the richness of Conway's Game of Life"
