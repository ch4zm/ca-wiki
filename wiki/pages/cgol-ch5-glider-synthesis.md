---
title: "Glider Synthesis (Johnston and Greene, Ch. 5)"
category: Sources
summary: Chapter 5 of Conway's Game of Life - Mathematics and Construction - building objects by colliding gliders - the 71 two-glider collisions, useful 3- and 4-glider syntheses, incremental synthesis, syntheses of rakes and Corderships, reverse-engineering syntheses from soups, a Gosper-gun breeder with quadratic growth, and the universality of slow salvos
tags: [source, chapter, life, glider-synthesis, slow-salvo, breeder, incremental-synthesis, seed]
sources: [cgol-ch5-glider-synthesis]
created: 2026-09-25
updated: 2026-09-25
---

# Glider Synthesis (Johnston and Greene, Ch. 5)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 5, printed pp. 121-152 (PDF pp. 135-166). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

Guns and rakes make endless gliders. [[object-synthesis](pages/object-synthesis.md)]
turns those gliders into other objects by colliding them, so that almost any object can
be built almost anywhere.[^1] The chapter catalogues all 71 two-glider collisions and a
selection of useful three- and four-glider syntheses. It then introduces *incremental
synthesis*, which builds an object in stages that each need only a few synchronized
gliders.[^2] It applies these to composite moving objects: the ecologist and space rake,
the Schick engine, the Coe ship, and the 3-engine Cordership.[^3] It also shows how a new
synthesis can be reverse-engineered from a soup that happened to produce the object,
using Rich's p16 as the example.[^4]

Two applications follow. Rakes that synthesize [[gosper-glider-gun](pages/gosper-glider-gun.md)]s
make a [[breeder](pages/breeder.md)], whose population grows quadratically.[^5] And a
*slow salvo*, a one-direction stream of gliders that interact one at a time with a seed
object, is shown to be exactly as powerful as unrestricted glider synthesis. The proof
uses block moves, one-time turners, splitters, timing adjusters and the clock inserter
([[slow-salvo](pages/slow-salvo.md)]).[^6]

## Key Takeaways

- There are exactly 71 ways two gliders can collide; among the results are the block,
  beehive, blinker, eater 1, B-heptomino and pi-heptomino.[^2]
- A valid synthesis must use gliders that could have arrived from arbitrarily far
  away.[^1]
- Oscillators are usually synthesized stator first, then rotor; billiard tables resist
  this.[^2]
- Every glider-synthesizable pattern can be built by a p1 slow salvo from one block.[^6]

## Entities & Concepts

- [[object-synthesis](pages/object-synthesis.md)], [[slow-salvo](pages/slow-salvo.md)], [[breeder](pages/breeder.md)]
- [[gosper-glider-gun](pages/gosper-glider-gun.md)], [[glider](pages/glider.md)], [[block](pages/block.md)], [[puffer](pages/puffer.md)], [[cordership](pages/cordership.md)]

## Relation to Other Wiki Pages

The rakes of [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)]
supply the gliders these syntheses need, and the block pull from
[[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] becomes a slow-salvo move.[^6]

[^1]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.121-122 [synthesis] - "collide gliders with each other and with other objects so as to create (or 'synthesize') new ones"; "we will be able to create patterns that construct almost any object in almost any location"; "we require that the gliders in a synthesis could arrive at their positions from arbitrarily far away"
[^2]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] §§5.1-5.3, pp.122-129 [synthesis] - Table 5.1 "all 71 possible 2-glider collisions"; Table 5.2 3-glider syntheses; Table 5.3 syntheses with 4 or more gliders; incremental synthesis; stator-then-rotor, "billiard table oscillators are much more difficult to synthesize"
[^3]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] §5.4, pp.129-131 [synthesis] - syntheses of the ecologist, space rake, Schick engine, Coe ship and an 11-glider 3-engine Cordership
[^4]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] §5.5, pp.131-134 [synthesis] - "find a soup that leaves behind the pattern of interest in its ash, and try to reverse-engineer"; 18-glider synthesis of Rich's p16
[^5]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] §5.6, pp.134-135 [synthesis] - a breeder "grows quadratically"; rakes synthesize Gosper glider guns
[^6]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] §5.7, pp.136-145 [synthesis] - slow salvos; (2,1) block pull; one-time turners; blockic splitters; clock inserter; Theorems 5.1-5.2
