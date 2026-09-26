---
title: "Bays (1994), Cellular Automata in the Triangular Tessellation"
category: Sources
summary: Carter Bays's paper on two-state count-based rules on the triangular grid, where each cell touches 12 others; it finds six rules meeting his Game of Life test (natural glider, bounded growth), more than the square grid's two, and notes that the triangular analogue of B3/S23 settles slowly but has no known glider
tags: [source, paper, triangular-grid, gl-rule, glider, soup, rule-space]
sources: [bays-1994-cellular-automata-in-the-triangular-tessellation]
created: 2026-09-25
updated: 2026-09-25
---

# Bays (1994), Cellular Automata in the Triangular Tessellation

**Source:** raw/bays-1994-cellular-automata-in-the-triangular-tessellation.pdf (Bays, C., "Cellular Automata in the Triangular Tessellation", *Complex Systems* 8, 127-150, 1994)
**Date ingested:** 2026-09-25
**Type:** paper

## Summary

Bays takes his Game of Life test ([[gl-rule](pages/gl-rule.md)]) to the grid of
equilateral triangles. Here each cell touches 12 others: three along its edges and nine
at its corners. He states the test in probability terms: a glider must turn up with
probability one from finite random soups, and unbounded growth from such soups must have
probability zero.[^1]

There are 92 × 92 = 8,464 count-based two-state rules on this grid. Birth on 2 or fewer
neighbours always grows without bound, and birth needing 6 or more can never leave a
convex border, since no outside cell can touch more than five live ones. Bounded rules of
that kind tend to lock into oscillators with astronomically long periods inside convex
enclosures.[^2]

Six rules pass the test, each with its own glider and small oscillators found from random
starts, so the triangular grid holds more Games of Life than the square grid, which has
two ([[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)]). They also settle faster and leave less debris than Conway's rule,
which Bays takes as a sign that glider guns will be hard to find there.[^3] The details are
on [[triangular-neighbourhood](pages/triangular-neighbourhood.md)].

## Key Takeaways

- Six triangular Games of Life: 4644, 3445, 4546, 2346, 3446 and 2345 in Bays's notation.[^3]
- The triangular analogue of Conway's numbers, rule 2333, is bounded and slow to settle
  but has no known glider and no period-2 oscillator.[^4]
- Bays: "it is the relative abundance of the glider that gives Conway's rule its
  allure".[^4]
- One program with swappable neighbour templates runs square, hexagonal, triangular,
  Cairo-pentagonal and mixed tilings.[^5]

## Entities & Concepts

- [[triangular-neighbourhood](pages/triangular-neighbourhood.md)], [[gl-rule](pages/gl-rule.md)], [[glider](pages/glider.md)], [[oscillator](pages/oscillator.md)], [[soup-search](pages/soup-search.md)], [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)]

## Relation to Other Wiki Pages

Follows [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)];
[[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)]
adds more triangular rules and finds Games of Life on the hexagonal and pentagonal grids
and a second one on the square grid. Its square-grid growth bounds match those on
[[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] (birth on 4 or more
cannot leave the bounding box).

[^1]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] p.127 [synthesis] - "A lifelike rule (LFR rule) is a semitotalistic CA rule where (1) cells have exactly two states"; GL conditions "(A) there must exist at least one glider ... that is discoverable with probability one by starting with finite random initial configurations ... and (B) the probability is zero that a finite random initial configuration leads to unbounded growth"; "each cell has 12 touching neighbors: three on the edges and nine on the vertices"
[^2]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] pp.128-130 [synthesis] - "a possible total of 92 × 92 = 8464 LFR rules"; Theorem 1, "Any LFR rule where Fl ≤ 2 leads to unbounded growth"; Theorem 2, "Any LFR rule where Fl ≥ 6 cannot grow without bounds ... no currently dead cell can possibly touch more than 5 cells"; bounded rules "evolve into extremely high-period oscillators that are usually contained within convex enclosures"
[^3]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] p.130 [synthesis] - "there are (at least) six GL rules ... Life 4644, 3445, 4546, 2346, 3446, and 2345"; "With one exception each sports at least one glider unique to the rule"; the square-grid count of two is from [[bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations](pages/bays-2005-game-of-life-in-hexagonal-and-pentagonal-tessellations.md)] pp.246-247; "experiments under Conway's rule yield much more residue than any of the GL rules. Furthermore, Life 2333 requires more time to settle ... devices such as 'glider guns' ... will be hard to discover"
[^4]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] p.145 [synthesis] - rule 2333 "appears to have bounded growth and stabilizes even more slowly than Life 2333. So far no glider has been discovered"; "no period-two oscillators have yet been discovered"; "it is the relative abundance of the glider that gives Conway's rule its allure"
[^5]: [[bays-1994-cellular-automata-in-the-triangular-tessellation](pages/bays-1994-cellular-automata-in-the-triangular-tessellation.md)] pp.148-149 [synthesis] - even and odd cells mapped onto a square array with neighbour templates; "we can thus utilize the same program to explore cellular automata in many regular tessellations - for example, the hexagonal tessellation, the Cairo tessellation ... or the square tessellation"; templates for mixed tilings
