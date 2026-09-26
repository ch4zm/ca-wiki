---
title: Spaceship
category: Patterns
summary: A finite Life pattern that returns to its original phase shifted across the plane; speeds are fractions of the "speed of light" c, capped at c/4 diagonally and c/2 orthogonally with no lower limit; elementary ships reach ten orthogonal and five diagonal speeds, and engineered ones cover every rational speed below c/4 and every slope
tags: [pattern-class, life, spaceship, speed-of-light, speed-limit, oblique, tagalong, flotilla]
sources: [cgol-ch4-spaceships-and-moving-objects, cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Spaceship

## Description

A spaceship is a pattern that returns to its initial phase after some number of
generations, but in a different location. The least such number is its period.[^1]
Formally, a finite configuration c such that Gᵏ(c) is a translate of c.[^2]

**Speed.** A spaceship's speed is the average number of cells it moves per generation.
It is written as a fraction of the "speed of light" *c*, one cell per generation, since
nothing can move faster. The [[glider](pages/glider.md)] moves 1 cell diagonally every 4
generations, c/4; the [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)]
move 2 cells every 4, c/2.[^3] When the period matters, the fraction is left unreduced:
the xWSSes travel at 2c/4.[^4]

**Speed limits (Theorem 4.1, Conway).** No finite object crosses empty space faster than
c/4 diagonally or c/2 orthogonally.[^5]
- *Proof.* Suppose a cell X just beyond the pattern's diagonal edge were alive at
  generation 2. Then three cells next to it must be born at generation 1, which needs a
  cell B to have at least four live neighbours at generation 0. B then dies, a
  contradiction.
- So a diagonal front advances at most one cell per 4 generations. Two diagonal fronts
  together give the c/2 orthogonal limit.
- There is no lower limit: engineered spaceships can be made as slow as desired.
- The limits hold only in empty space; signals through wires can reach c
  ([[signal-wire](pages/signal-wire.md)]).

**Periods.** A spaceship of speed c/n needs period at least n. Period 1 would mean moving
at c, so period 2 is the minimum, and period-2 spaceships exist. Adjustable designs give
spaceships and rakes of arbitrarily large period ([[puffer](pages/puffer.md)]).[^6]

**Natural spaceships.** Ordinary random soups produce the glider, LWSS, MWSS and HWSS
([[soup-search](pages/soup-search.md)]).[^7]

**Building on spaceships.**[^8]
- A *tagalong* is an object a spaceship drags along, usually held by a spark. A
  *pushalong* rides in front. Chains of c/4 tagalongs give a grammar of diagonal
  spaceships.
- A *flotilla* is a group of spaceships whose sparks interact. In a *pseudo spaceship* the
  components are unchanged but some dead cell is overcrowded.
- Some tagalongs, such as the crab tubstretcher, lengthen a single object forever.
- Unstable objects can be made into moving objects: the
  [[switch-engine](pages/switch-engine.md)] into the c/12 [[cordership](pages/cordership.md)],
  and the B-heptomino into c/2 puffers and rakes ([[puffer](pages/puffer.md)]).

**Known speeds.** An *elementary* spaceship acts as a whole, found by search; an
*engineered* one repeats simple reactions and usually has thousands or millions of
cells.[^9] Oblique spaceships move at a slope other than 0 or ±1; their speed (x, y)c/n
is at most (2, 1)c/6.[^10]

| Direction | Elementary speeds | Engineered |
|---|---|---|
| orthogonal | c/2 (xWSS), c/3, c/4, c/5 (spider), 2c/5, c/6, c/7 (loafer), 2c/7 (weekender), 3c/7, c/10 (copperhead) | 17c/45 (caterpillar), 31c/240 (silverfish), every rational speed below c/4 (caterloopillar) |
| diagonal | c/4 (glider), c/5, c/6, c/7 (lobster), c/8 (walrus) | c/12 (Corderships), every rational speed below c/4 (Demonoid) |
| oblique | (2, 1)c/6, Sir Robin, the first elementary knightship | (23, 5)c/79 (waterbear); every slope at small enough speed (Geminoid) |

The walrus, found in 2023, is the first elementary c/8 diagonal spaceship.[^11]

## Appearances in Sources

- [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] - the whole chapter: speed, Theorem 4.1, tagalongs and flotillae, speed and period status
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - the four natural spaceships
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - speed of light, the c/4 and c/2 limits
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: the translate-of-itself definition (Kari calls every such object a "glider")

## Related Concepts

- [[glider](pages/glider.md)], [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)] - the basic spaceships
- [[cordership](pages/cordership.md)], [[puffer](pages/puffer.md)] - slower and debris-leaving moving objects
- [[signal-wire](pages/signal-wire.md)] - moving faster than the speed limits allow
- [[oscillator](pages/oscillator.md)] - a spaceship is periodic up to translation
- [[phoenix](pages/phoenix.md)] - no phoenix can be a spaceship

[^1]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.83 - "a spaceship is a pattern that returns to its initial phase after some number of generations, but at a different location from where it started ... the period of a spaceship is the smallest number of generations needed for it to return to its initial phase"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - a glider in Kari's general sense is a finite c with Gᵏ(c) equal to a translate of c
[^3]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.83 [synthesis] - speed is "the number of cells that they move on average per generation"; "this speed is typically referred to as the speed of light and is denoted by c"; glider c/4; xWSSes "2c/4 = c/2"
[^4]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.109 - "If we wish to emphasize that the light, middle, and heavyweight spaceships have period 4 then we would say that they travel at 2c/4 instead of at c/2"
[^5]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.99 [synthesis] - Theorem 4.1: "The maximum diagonal and orthogonal speeds that a finite object ... can travel through empty space are c/4 and c/2"; proof via cells X, A, B, C, K, L, M, N; two diagonal lines for c/2; n.22 "originally proved by Conway himself"; "such a lower bound does not exist"; the theorem "only applies to objects travelling through a vacuum"
[^6]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.106,109-110 [synthesis] - "a spaceship with speed c/n must have period at least n"; period 2 spaceships exist and "this period is minimal"; adjustable-period spaceships and rakes
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7-8,28 [synthesis] - glider, LWSS, MWSS, HWSS are the spaceships in ordinary soup ash
[^8]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.86-90 [synthesis] - tagalongs; "a sort of grammar for c/4 diagonal spaceships"; pushalongs; tubstretcher creates "a single arbitrarily large object"; flotillae; pseudo spaceships; Corderships; B-heptomino puffers
[^9]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.106-107 [synthesis] - "an elementary spaceship ... acts 'as a whole' rather than by piecing together many smaller reactions"; engineered spaceships "typically with thousands or millions of live cells"
[^10]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.107 - "oblique spaceship"; "speed is (x, y)c/n"; "oblique spaceships all have speed no greater than (2, 1)c/6 and period equal to at least 6"; Sir Robin (Goucher, March 2018)
[^11]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.106-108, Figs. 4.47-4.48 and Table 4.1 [synthesis] - elementary orthogonal and diagonal speeds; engineered caterpillar, silverfish, caterloopillar, Demonoid, waterbear, Geminoid; https://conwaylife.com/wiki/Spaceship (2024-09-11) - "In 2023, the first elementary c/8 diagonal spaceship was found: the walrus"
