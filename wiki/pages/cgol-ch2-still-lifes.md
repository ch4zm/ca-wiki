---
title: "Still Lifes (Johnston and Greene, Ch. 2)"
category: Sources
summary: Chapter 2 of Conway's Game of Life - Mathematics and Construction - strict vs pseudo still lifes and their counts, the four-colour partition theorem, still-life grammar and induction coils, eaters (eater 1, 2, 3, 5, boat-bit, block pull) and welding, and the solved still-life density problem
tags: [source, chapter, life, still-life, eater, welding, density, enumeration]
sources: [cgol-ch2-still-lifes]
created: 2026-09-25
updated: 2026-09-25
---

# Still Lifes (Johnston and Greene, Ch. 2)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 2, printed pp. 33-52 (PDF pp. 47-66). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

The chapter treats [[still-life](pages/still-life.md)]s as objects with real structure.
It first lists all still lifes of up to 7 cells.[^1] Counting larger ones needs a
definition of which still lifes are non-trivial. A *strict* still life cannot be split
into separately stable parts. A *pseudo* still life can be split, but its parts crowd
each other. Counts of both are known up to 34 cells, and a four-colour-theorem argument
shows every pseudo still life splits into at most four stable pieces.[^2]

The middle sections are practical. *Still-life grammar* covers extendable families (the
"long" prefixes), stabilizing end pieces (pre-block and tail), the rule that a 2 × 2 live
square must be an isolated block, and *induction coils* that stabilize nearby cells without
touching them.[^3] *Eaters* are still lifes that delete a glider or other object and
recover: eater 1 is the smallest and fastest, and eater 2, eater 5, eater 3, the boat-bit
and the (2,1) block pull cover other cases. *Welding* merges several still lifes into one
that keeps each part's function, so components can be packed tightly or fitted into
constrained space ([[eater](pages/eater.md)]).[^4]

The last section solves the density problem: an infinite still life has density at most
1/2, with an elementary token-redistribution proof, and the exact maximum population in an
n × n box is known for every n ([[still-life-density](pages/still-life-density.md)]).[^5]
The notes trace still-life enumeration from hand counts to Ekström's program.[^6]

## Key Takeaways

- All still lifes with at most 7 cells: block, tub, boat, snake, ship, beehive, aircraft
  carrier, barge, long snake, long boat, loaf, eater 1.[^1]
- Still lifes have no thick parts: they are one-cell-thick paths plus isolated blocks.[^3]
- Eater 1 recovers 4 generations after eating a glider, the fastest possible for a glider
  eater.[^4]
- Maximum still-life density is exactly 1/2; for oscillators it is open.[^5]

## Entities & Concepts

- [[still-life](pages/still-life.md)], [[eater](pages/eater.md)], [[still-life-density](pages/still-life-density.md)]
- [[block](pages/block.md)], [[beehive](pages/beehive.md)], [[glider](pages/glider.md)], [[oscillator](pages/oscillator.md)]

## Relation to Other Wiki Pages

Eaters are the standard stabilizers for the shuttles and guns of
[[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)], such as the
[[queen-bee](pages/queen-bee.md)], and the glider-deleting parts of later circuitry.

[^1]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.33 [synthesis] - "the block, tub, boat, ship, beehive, and loaf. Some additional small still lifes are the aircraft carrier, barge, snake, long boat, long snake, and eater 1 ... we have just listed every single still life with 7 or fewer live cells"
[^2]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] §2.1, pp.34-37 [synthesis] - definitions of strict and pseudo still lifes; Table 2.1 counts to 23 cells, "computed up to 34 cells"; Theorem 2.1 (Four-Partitions of Pseudo Still Lifes) via the four color theorem
[^3]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] §2.2, pp.37-39 [synthesis] - long prefixes; pre-block and tail end pieces; a live 2 × 2 square must be a block with a dead border; "still lifes never have 'thick' sections"; induction coils
[^4]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] §§2.3-2.4, pp.39-44 [synthesis] - eaters defined; eater 1's "recovery time of 4 generations, which is the fastest possible for any glider eater"; eater 2, eater 5, rocks, boat-bit, loaf flip and eater 3, (2,1) block pull; welding; constrained eaters
[^5]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] §2.5, pp.44-48 [synthesis] - Theorems 2.2-2.4 on still-life density; "The related problem of finding the maximum density of an oscillator remains open"
[^6]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] §2.6, pp.49-50 [synthesis] - enumeration by Conway (7 cells), Wainwright (10), Petrie and Boyer (12), Buckingham (13-14), Raynham's program, Niemiec (24 by 1999), Ekström (2017: all to 30, counts to 34)
