---
title: Still-life density
category: Concepts
summary: How densely live cells can pack in a Life still life - at most 1/2 asymptotically (Elkies 1998; elementary token proof), with the exact maximum population M(n) in an n × n box known for every n; the analogous oscillator problem is open, with an 8/13 upper bound
tags: [concept, life, still-life, density, theorem, extremal]
sources: [cgol-ch2-still-lifes]
created: 2026-09-25
updated: 2026-09-25
---

# Still-life density

## Description

**Density 1/2 is the limit.** Many infinite [[still-life](pages/still-life.md)]s fill the
plane at density 1/2, such as zebra stripes, chicken wire and onion rings, and none does
better. A still life in an n × n bounding box has at most ⌊n²/2⌋ + 2n live cells, so the
asymptotic density of still lifes is at most 1/2.[^1] Noam Elkies proved the density
bound in 1998, following earlier bounds of 6/11 (Hickerson, 1992) and 15/28 (Holzwart).
His proof also finds the maximum still-life density in many other Life-like rules.[^2]

**Token proof.** A simpler proof specific to Life works by redistributing tokens.[^3]
- Give every cell 2 tokens.
- Each dead cell hands its tokens only to orthogonal live neighbours, following a fixed
  rule based on how many it has.
- In a still life every live cell then ends up with at least 4 tokens. The one bad local
  configuration always sits next to one with a spare token, which covers it.
- Counting tokens in an n × n square gives 4L ≤ 2(n² + 4n), where L is the number of live
  cells.

Cells ending with exactly 4 tokens are the most densely packable. In the ship, the
densest 3 × 3 still life, every cell ends with exactly 4.[^4]

**Finite boxes.** Tightening the boundary count, since at most 2 of every 3 edge cells can
be alive, gives a bound of ⌊n²/2⌋ + ⌈2n/3⌉. That bound is exact for n = 2, 3 and 5, met by
a block, a ship, and four blocks.[^5] The exact maximum M(n) is known for all n:[^6]
- computed for n ≤ 60 by increasingly sophisticated computer searches, from Bosch (1999)
  to Chu and colleagues (2009, 2012);
- for n ≥ 61, M(n) = ⌊n²/2 + 17n/27 − 2⌋ when n mod 54 is one of 0, 1, 3, 8, 9, 11, 16,
  17, 19, 25, 27, 31, 33, 39, 41, 47, 49, and ⌊n²/2 + 17n/27 − 1⌋ otherwise.

| n | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|
| M(n) | 4 | 6 | 8 | 16 | 18 | 28 | 36 | 43 | 54 |

**Oscillators (open).** No one has found the maximum density of an
[[oscillator](pages/oscillator.md)], even an infinite one.[^7]
- Individual phases can exceed 1/2: a period-6 infinite oscillator reaches 3/4 in two
  phases. The density averaged over all phases appears never to exceed 1/2.
- None of the three known still-life proof techniques extends to that average.
- An infinite pattern's average density over any number of generations cannot exceed 8/13
  (Holzwart and Hickerson, 1992).
- The highest possible single-phase density is conjectured to be 3/4.

## Appearances in Sources

- [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] - §2.5: Theorems 2.2-2.4, Tables 2.2-2.3, oscillator density

## Related Concepts

- [[still-life](pages/still-life.md)] - the objects being packed
- [[oscillator](pages/oscillator.md)] - where the density question is open
- [[block](pages/block.md)] - the densest still life in a 2 × 2 box

[^1]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.44 [synthesis] - "many examples of infinite still lifes were known with density 1/2"; Fig. 2.25 zebra stripes, chicken wire, onion rings; Theorem 2.2: "A still life contained in an n × n bounding box has no more than ⌊n²/2⌋ + 2n live cells. In particular, the asymptotic density of still lifes as n → ∞ is no greater than 1/2"
[^2]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.44, nn.17-18 [synthesis] - bound of 6/11 by Dean Hickerson in 1992, 15/28 by Hartmut Holzwart, 1/2 by Noam Elkies in 1998; Elkies's proof "also finds the maximum asymptotic density of still lifes in many other Life-like cellular automata"
[^3]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.44-46 [synthesis] - each cell has 2 tokens; dead cells give tokens to von Neumann neighbours per Fig. 2.26; 15 of 16 live-cell configurations get at least 4 tokens and the red one is always beside the yellow one, which transfers a token; 4L ≤ 2(n² + 4n); n.18 the simpler proof was first presented in [CSdlB09]
[^4]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.46 - "the densest still life in a 3 × 3 square is the ship ..., and every live cell in the ship also ends up with exactly 4 tokens"
[^5]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.46-47 [synthesis] - "only 2 out of every 3 cells on the outer edge of the square can be alive"; Theorem 2.3: "no more than ⌊n²/2⌋ + ⌈2n/3⌉ live cells"; exact when n = 2, 3, or 5 (block, ship, four blocks); Table 2.2
[^6]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.47-48 [synthesis] - "we actually know a complete answer"; computer searches for n ≤ 60 (n.19: Bosch 1999, Bosch and Trick 2004, Larrosa, Morancho and Niso 2005, Chu et al. 2009 and 2012); Theorem 2.4 formula for n ≥ 61; Table 2.3 M(n) values
[^7]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.48 [synthesis] - "The related problem of finding the maximum density of an oscillator remains open"; Fig. 2.30 period 6 oscillator with density 3/4 in two phases; "none of the three known proof techniques ... seem to be strong enough"; "an infinite pattern cannot have average density ... that exceeds 8/13" (n.20: Holzwart and Hickerson, September 1992); highest single-phase density "suspected" to be 3/4
