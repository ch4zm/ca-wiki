---
title: Methuselah
category: Patterns
summary: A small Life pattern that takes exceptionally long to stabilize for its size; the R-pentomino (1,103 generations) and acorn are classics, the longest-lived known with 5-13 cells run from 1,105 to 29,126 generations, and the notion resists precise definition
tags: [pattern-class, life, methuselah, lifespan, stabilization]
sources: [cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Methuselah

## Description

A methuselah is a pattern that takes exceptionally long to stabilize compared with other
patterns of similar size, where size means either the number of live cells or the area of
the bounding box. There is no objective cutoff; a pattern is called a methuselah by
comparing it with the longest known lifespans at its size.[^1] "Stabilize" here means
breaking down into non-interacting still lifes, oscillators and spaceships.[^2] No good
search method is known, so methuselahs are found by random guessing or exhaustive
search.[^3]

**Records by cell count.** The longest-lived known methuselahs in reasonably small
bounding boxes:[^4]

| Cells | Pattern | Lifespan (generations) |
|---|---|---|
| 5 | R-pentomino grandparents | 1,105 |
| 6 | R-pentomino great-great-great-grandparents | 1,108 |
| 7 | acorn (Charles Corderman) | 5,206 |
| 8 | (Tomas Rokicki, 2005) | 7,468 |
| 9 | bunnies 9 (Paul Callahan, 1997) | 17,410 |
| 10 | bunnies 10b (Nick Gotts, 2019) | 17,431 |
| 11 | (Simon Ekström, 2016) | 23,334 |
| 12 | (Simon Ekström, 2017) | 23,801 |
| 13 | Lidka (Ekström's compact version) | 29,126 |

These are proved optimal only up to 9 cells, by exhaustive computer searches.[^5] The
[[r-pentomino](pages/r-pentomino.md)] itself lasts 1,103 generations, longer than any
other pattern in a 3 × 3 box and any other polyomino of 5 or fewer cells.[^6] By bounding
box, a methuselah in a 16 × 16 box lasts 52,514 generations, the longest known for that
size.[^7]

**Why the definition is slippery.**[^8]
- An 8- or 9-cell pattern can last as long as desired by aiming a glider at a distant
  blinker or block, so a small bounding box has to be required.
- Some 11- and 12-cell patterns, the switch-engine puffers, grow forever, though
  regularly. They can be said to stabilize once they enter their periodic phase.
- Arks built from switch engines can take hundreds of thousands of generations to settle
  while being "mostly" stable throughout ([[switch-engine](pages/switch-engine.md)]). The
  book leaves methuselah-hood as something "we know when we see".
- Life can compute, so patterns can encode problems whose long-term behaviour cannot be
  determined.

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - §1.6: definition, Table 1.1, problem cases

## Related Concepts

- [[r-pentomino](pages/r-pentomino.md)] - the classic example
- [[switch-engine](pages/switch-engine.md)] - its arks give the longest-lived small patterns
- [[soup-search](pages/soup-search.md)] - some methuselahs were found by soup screensavers

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.16 [synthesis] - "A pattern that takes exceptionally long to stabilize, relative to other similarly sized patterns, is called a methuselah"; "there is no completely objective way"; "'size' may refer to either the number of live cells in the pattern, or to the area of its bounding box"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.16, n.17 - "it just means that the pattern has broken down into non-interacting still lifes, oscillators, and spaceships"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.16 - "No good search methods are known for finding methuselahs, so all of them have been found essentially by random guessing or exhaustive search"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.18, Table 1.1 [synthesis] - longest-lived known methuselahs with 5-13 cells and their discoverers
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.17 [synthesis] - "these patterns are only known to be optimal for n ≤ 9"; n.22: exhaustive searches by Callahan (1997), Rokicki (2005) and Gotts (2019)
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.17 [synthesis] - the R-pentomino "takes considerably longer to stabilize than any other pattern that fits with in a 3 × 3 bounding box, and also much longer to stabilize than any other polyomino with 5 or fewer live cells"; Fig. 1.28: 1 103 generations
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.17 - "fits within a 16 × 16 bounding box and has a lifespan of 52 514 generations, which is longer than any other known pattern of this size"
[^8]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.17-19 [synthesis] - glider aimed at a far away blinker or block; switch-engine puffers "grow forever, they do so in a regular and predictable way"; the 736 692-generation ark "was 'mostly' stable"; "a phenomenon that we know when we see"; Chapter 9 patterns "whose long-term behavior ... we have absolutely no hope of determining"
