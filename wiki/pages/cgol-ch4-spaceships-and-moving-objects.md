---
title: "Spaceships and Moving Objects (Johnston and Greene, Ch. 4)"
category: Sources
summary: Chapter 4 of Conway's Game of Life - Mathematics and Construction - glider colour, lanes and timing; tagalongs, flotillae and pseudo spaceships; Corderships; puffers and rakes (space rake, Schick engine, Coe ship); the c/4 and c/2 speed limits; wires, signals, fuses and teleporting collisions; the catalogue of known spaceship speeds and adjustable periods
tags: [source, chapter, life, spaceship, cordership, rake, puffer, speed-limit, signal, wire]
sources: [cgol-ch4-spaceships-and-moving-objects]
created: 2026-09-25
updated: 2026-09-25
---

# Spaceships and Moving Objects (Johnston and Greene, Ch. 4)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 4, printed pp. 83-120 (PDF pp. 97-134). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

New spaceships are hard to find, so the chapter mostly studies what can be done with
known ones.[^1] For the [[glider](pages/glider.md)] it sets up the bookkeeping later
circuitry needs: *colour*, which fixes which reflectors can be combined, plus *lanes* and
*timing*. It then covers *tagalongs*, objects a spaceship drags along, such as the crab
tubstretcher.[^2] The [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)]
give off strong sparks. They can delete debris, combine into *flotillae*, and stabilize
"overweight" ships that are unstable alone.[^3]

The chapter builds slower and busier moving objects from these parts. The
[[cordership](pages/cordership.md)] turns mutually stabilizing switch engines into c/12
diagonal spaceships.[^4] A [[puffer](pages/puffer.md)] made from a B-heptomino flanked by
lightweight spaceships leads to the ecologist, and then to *rakes*, which are moving
guns. The space rake, the Schick engine and the Coe ship give rakes of period 16, 20, 60,
80 and 240.[^5]

The theory part proves the speed limits: c/4 diagonally and c/2 orthogonally through
empty space.[^6] It then shows how *signals* on *wires* and *fuses* burning *wicks* move
faster, and how glider collisions can appear to "teleport" objects without breaking the
lightspeed limit ([[signal-wire](pages/signal-wire.md)]).[^7] It ends with the catalogue
of known [[spaceship](pages/spaceship.md)] speeds and a construction of spaceships and
rakes with arbitrarily large periods.[^8]

## Key Takeaways

- Every glider loop uses an even number of colour-changing reflectors.[^2]
- Some tagalongs build a single object that grows forever, where earlier unbounded
  growth produced many small objects.[^2]
- No finite object crosses empty space faster than c/4 diagonally or c/2 orthogonally,
  but no lower speed limit exists.[^6]
- Signals through non-empty wires can reach c; teleporting collisions never beat it.[^7]

## Entities & Concepts

- [[spaceship](pages/spaceship.md)], [[glider](pages/glider.md)], [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)]
- [[cordership](pages/cordership.md)], [[puffer](pages/puffer.md)], [[signal-wire](pages/signal-wire.md)]
- [[switch-engine](pages/switch-engine.md)], [[twin-bees](pages/twin-bees.md)], [[reflector](pages/reflector.md)]

## Relation to Other Wiki Pages

The switch engine and its arks from [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)]
become Corderships here. The Snark and twin bees shuttle from
[[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] are the standard colour-preserving
and colour-changing reflectors.[^2]

[^1]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.83-84 - "constructing new ones is actually quite a difficult problem ... much of this chapter will focus on investigating what we can do with the spaceships that we already have"
[^2]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] §4.1, pp.84-87 [synthesis] - glider color; Snark "color-preserving", twin bees shuttle color-changing; "every glider loop must make use of an even number of color-changing reflectors"; lanes and timing; tagalongs; tubstretcher "creates a single arbitrarily large object"
[^3]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] §4.2, pp.87-90 [synthesis] - xWSS sparks; eating an HWSS; tagalongs, pseudo spaceships and flotillae; the overweight spaceship
[^4]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] §4.3, pp.90-93 [synthesis] - Corderships from switch engines
[^5]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] §4.4, pp.94-98 [synthesis] - B-heptomino puffer, ecologist, forward and backward space rakes, Schick engine, p60 rakes, Coe ship, p16, p80 and p240 rakes
[^6]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] §4.5, pp.98-99 [synthesis] - Theorem 4.1 (Spaceship Speed Limits); "such a lower bound does not exist"
[^7]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] §§4.5.1-4.5.3, pp.99-105 [synthesis] - wires and signals, Theorems 4.2-4.3, fuses and wicks, the fast forward force field and diagonal lightspeed glider collision
[^8]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] §4.6, pp.106-110 [synthesis] - Table 4.1 speeds; adjustable-period rake with period 264 + 32n
