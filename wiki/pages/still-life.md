---
title: Still life
category: Patterns
summary: A Life pattern that never changes from one generation to the next (a finite fixed point of the rule); strict vs pseudo still lifes and their counts (known to 34 cells), still-life grammar and induction coils, and the commonest in random ash (block, tub, boat, ship, beehive, loaf, pond)
tags: [pattern-class, life, still-life, stable, enumeration]
sources: [cgol-ch1-early-life, cgol-ch2-still-lifes, fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Still life

## Description

A still life is a pattern that remains unchanged from one generation to the next: every
live cell survives and no dead cell is born.[^1] Formally, a finite configuration c with
G(c) = c, a fixed point of the global map.[^2] Still lifes, [[oscillator](pages/oscillator.md)]s
and [[spaceship](pages/spaceship.md)]s are the three basic object types in
[[game-of-life](pages/game-of-life.md)], the building blocks of everything larger.[^3]
Most starting patterns end as still lifes or oscillators.[^4] "Stable" sometimes means
still lifes only and sometimes includes oscillators.[^5]

**The smallest.** Every still life with 7 or fewer live cells:[^6]
- 4 cells: [[block](pages/block.md)], tub;
- 5 cells: boat;
- 6 cells: snake, ship, [[beehive](pages/beehive.md)], aircraft carrier, barge;
- 7 cells: long snake, long boat, loaf, and eater 1 ([[eater](pages/eater.md)]).

The commonest in the ash of random soups are the block, tub, boat, ship, beehive, loaf and
pond ([[soup-search](pages/soup-search.md)]).[^7]

**Strict and pseudo.** Two far-apart blocks form a still life too, so counting needs a
notion of which still lifes are non-trivial.[^8]
- A **strict** still life is connected, or disconnected but not splittable into separately
  stable parts. The aircraft carrier is strict: its two halves are unstable alone.
- A **pseudo** still life splits into two or more separately stable parts, and some dead
  cell has more than 3 live neighbours in the whole but fewer than 3 in the parts. The
  bi-block, two blocks almost touching, is one.
- A group of non-interacting still lifes, such as the honey farm, is neither
  ([[familiar-fours](pages/familiar-fours.md)]).

Every pseudo still life can be split into at most 4 still lifes. The proof colours the
half-cell margins around its strict components with the four-colour theorem. Some need
exactly 3 parts and some exactly 4, and the smallest examples of each are known.[^9]

**Counts.**[^10]

| Cells | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Strict | 2 | 1 | 5 | 4 | 9 | 10 | 25 | 46 | 121 | 240 | 619 | 1,353 | 3,286 |
| Pseudo | 0 | 0 | 0 | 0 | 1 | 1 | 7 | 16 | 55 | 110 | 279 | 620 | 1,645 |

At 23 cells there are 1,646,147 strict and 1,184,882 pseudo still lifes. Counts are
known up to 34 cells, and Simon Ekström's program has catalogued every still life, strict
and pseudo, up to 30 cells. Greedy searches miss some strict still lifes, the smallest
with 16 cells, which is part of why enumerating larger ones is hard.[^11]

**Still-life grammar.**[^12]
- Many still lifes come in families extended two cells at a time. The tub, barge and long
  barge form one; the boat and long boat another; the ship and long ship a third. The
  snake and canoe families extend one cell at a time. The "long" prefix counts the
  extensions.
- The repeating middle is capped by stabilizing end pieces, usually a pre-block or a tail
  ("tub with tail"; "cis-" and "trans-" tell two tail orientations apart).
- If a 2 × 2 square is all alive, it must be an isolated block, since any further neighbour
  overcrowds it. So still lifes have no thick parts. They are one-cell-thick paths that
  branch, curve and loop, plus isolated blocks.
- A one-cell-thick path can often, though not always, be made stable by adding junk that
  suppresses nearby births. Rules of thumb: put pre-blocks or tails on the ends, thicken
  diagonal runs, and support orthogonal runs.
- Objects that stabilize without touching are **induction coils**. A tub, loaf, eater 1 or
  any "pointy" still life stabilizes a run of orthogonal cells. Blocks and snakes can line
  up to support a row of any length.

**Eating.** A still life can destroy another object and survive: a block eats a
beehive in 7 generations. Still lifes built for this are [[eater](pages/eater.md)]s.[^13]
Packing limits are on [[still-life-density](pages/still-life-density.md)].

## Appearances in Sources

- [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] - the full chapter: small still lifes, strict and pseudo, counts, grammar, eaters, density
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - definition, common ash still lifes, eating
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - the term
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: the fixed-point definition

## Related Concepts

- [[oscillator](pages/oscillator.md)] - the periodic generalization; a still life is period 1
- [[spaceship](pages/spaceship.md)] - periodic up to a translation
- [[eater](pages/eater.md)] - still lifes that delete other objects
- [[still-life-density](pages/still-life-density.md)] - how densely they can pack
- [[block](pages/block.md)], [[beehive](pages/beehive.md)] - examples
- [[familiar-fours](pages/familiar-fours.md)] - stable groups of four

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.4 - "A pattern like this that remains unchanged from one generation to the next is called a still life"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - still life defined as a finite configuration c with G(c) = c
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7 - "Still lifes, oscillators, and spaceships are the three most basic types of objects that we will study in Life, and they form the building blocks of all of the more complicated patterns"
[^4]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 - "Most starting patterns either reach stable figures--Conway calls them 'still lifes'--that cannot change or patterns that oscillate forever"
[^5]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.38, n.9 - "The term stable is sometimes used to refer to still lifes, and it is sometimes used to refer to both still lifes and oscillators"
[^6]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.33, Fig. 2.1 - "All still lifes with 7 or fewer live cells, arranged by their cell count ... (4 cells) block, tub, (5 cells) boat, (6 cells), snake, ship, beehive, aircraft carrier, barge, (7 cells) long snake, long boat, loaf, and eater 1"
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7, Fig. 1.6 - "seven still lifes, called the block, tub, boat, ship, beehive, loaf and pond ... All of these objects frequently appear in the ash left behind by chaotic patterns"
[^8]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.34 [synthesis] - "two blocks far away from each other ... (trivial) 8-cell still lifes"; strict still life definition; aircraft carrier; pseudo still life definition with the overcrowded dead cell; Fig. 2.2 bi-block and honey farm "not strict still lifes"
[^9]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.36-37,50 [synthesis] - Fig. 2.4 pseudo still lifes needing 3 and 4 parts; "there does not exist a pseudo still life that can only be partitioned into 5 or more still lifes"; Theorem 2.1 proof with regions extending 1/2 cell and the four color theorem; Ekström's program showed the Fig. 2.4 examples are the smallest possible
[^10]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.35, Table 2.1 - numbers of strict and pseudo still lifes with 4 to 23 cells
[^11]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.34,49-50 [synthesis] - "they have been computed up to 34 cells"; Ekström's January 2017 program has "catalog[ed] all still lifes (both strict and pseudo) with 30 or fewer cells, count[ed] all still lifes with 34 or fewer cells"; Fig. 2.33: the smallest strict still life missed by a greedy search has 16 cells
[^12]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] §2.2, pp.37-39 [synthesis] - Fig. 2.6 and 2.7 families; n.7 "long" prefix; pre-block and tail end pieces; n.8 cis and trans; "if every cell in a 2 × 2 square is alive, then every cell that is an immediate neighbor ... must be dead"; "still lifes never have 'thick' sections"; paths stabilized "often" (n.10 "But not always"); rules of thumb; induction coils (Figs. 2.12-2.13)
[^13]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.10-11 [synthesis] - "a block being placed next to a beehive results in the beehive being destroyed and the block surviving unharmed"; Fig. 1.16: 7 generations
