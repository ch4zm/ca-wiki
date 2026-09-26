---
title: "Self-Supporting Spaceships (Johnston and Greene, Ch. 10)"
category: Sources
summary: Chapter 10 of Conway's Game of Life - Mathematics and Construction - spaceships that push a moving reaction along a track and use its output gliders to build the track ahead - the 31c/240 silverfish (Herschel on blocks), the 17c/45 caterpillar (pi-heptomino on blinkers), helices of any speed and slope, the (23, 5)c/79 waterbear, and caterloopillars of every rational speed below c/4
tags: [source, chapter, life, spaceship, self-supporting-spaceship, silverfish, caterpillar, waterbear, caterloopillar, helix, crawler]
sources: [cgol-ch10-self-supporting-spaceships]
created: 2026-09-25
updated: 2026-09-25
---

# Self-Supporting Spaceships (Johnston and Greene, Ch. 10)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 10, printed pp. 311-344 (PDF pp. 325-358). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

The chapter previews universal construction, the ability to build anything that can be
built. A [[self-supporting-spaceship](pages/self-supporting-spaceship.md)] moves a
reaction along a track and uses the reaction's output to construct the track in front of
itself.[^1]

- **Silverfish (31c/240).** A [[herschel](pages/herschel.md)] hits a [[block](pages/block.md)]
  and moves forward 31 cells in 240 generations, leaving a second block and two
  [[glider](pages/glider.md)]s.[^2] Herschels crawling along six parallel block tracks
  form rakes and rephasers that can fire a glider on any lane. The front of the track is
  held up by heavyweight spaceships that the ship rebuilds from their own debris with a
  13-glider [[slow-salvo](pages/slow-salvo.md)].[^3]
- **Caterpillar (17c/45).** A [[blinker](pages/blinker.md)] moves a pi-heptomino forward
  17 cells in 45 generations. That is faster than a glider, so gliders cannot be sent
  forward directly. The ship instead builds a *helix*, a line of xWSS flotillae that a
  glider burns through while firing gliders to the side. Helices can be made for any
  rational orthogonal speed below c/2.[^4]
- **Waterbear ((23, 5)c/79).** A Herschel on a glider track moves obliquely while
  duplicating the track. The same helix parts give oblique helices matching any oblique
  spaceship.[^5]
- **Caterloopillars.** The roles are reversed: trains of spaceships push and pull a trail
  of loaves, and the pushing and pulling flotillae build each other. A
  [[caterloopillar](pages/caterloopillar.md)] exists for every rational orthogonal speed
  below c/4.[^6]

The notes list other *crawlers* (objects moving through a stable or glider wick) that
could support such ships, and describe the half-baked knightships built on the half-bakery
crawler.[^7]

## Key Takeaways

- A moving reaction plus a way to build its own track ahead is enough for a
  spaceship.[^1]
- Reactions faster than c/4 need a helix to get signals to the front.[^4]
- Helices exist at every rational speed below c/2 orthogonally and at the speed and slope
  of any oblique spaceship.[^4][^5]
- Caterloopillars give every rational orthogonal speed below c/4.[^6]

## Entities & Concepts

- [[self-supporting-spaceship](pages/self-supporting-spaceship.md)], [[caterloopillar](pages/caterloopillar.md)]
- [[spaceship](pages/spaceship.md)], [[herschel](pages/herschel.md)], [[block](pages/block.md)], [[blinker](pages/blinker.md)], [[glider](pages/glider.md)], [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)]
- [[slow-salvo](pages/slow-salvo.md)], [[object-synthesis](pages/object-synthesis.md)], [[heisenburp](pages/heisenburp.md)], [[puffer](pages/puffer.md)]

## Relation to Other Wiki Pages

The chapter builds on the kickback reaction and slow salvos of
[[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] and the speed limits and
speed catalogue of [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)].
The HWSS debris-maker is a [[heisenburp](pages/heisenburp.md)] in the sense of
[[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)].[^3]

[^1]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.311 - "self-supporting spaceships (the topic of this chapter) work by manipulating a reaction that moves along a track so as to construct the track in front of itself"
[^2]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.311-312 - "a Herschel collides with a block in such a way that it moves forward by 31 cells over the course of 240 generations. At the same time, the block is moved back by 22 cells, a second block is created, and two gliders are released"
[^3]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] §10.1, pp.312-321 [synthesis] - reburnable block wick, six-track rakes and rephasers, MWSS front support, HWSS pair rebuilt by a Heisenburp and a 13-glider slow salvo, the completed silverfish
[^4]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] §10.2, pp.321-327 [synthesis] - blinker wick and pi crawler; "because the 17c/45 reaction that we are using travels faster than c/4, we cannot fire gliders forward"; helices; Theorem 10.1 "any rational speed slower than c/2"; the caterpillar
[^5]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] §10.3, pp.327-330 [synthesis] - the (23, 5)c/79 Herschel-and-glider reaction; Theorem 10.2 oblique helices "exist that travel at the same speed and direction as any oblique spaceship"; the waterbear
[^6]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] §10.4, pp.330-337 [synthesis] - "we use an infinite trail of spaceships to move a stable object"; loaf tracks; Theorem 10.3 "Caterloopillar spaceships can be constructed that travel at any rational speed slower than c/4"
[^7]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] §10.5, pp.337-340 [synthesis] - shield bug and centipede; "reactions that involve an object moving through a stable or glider-based wick--such reactions are called crawlers or climbers"; half-baked knightships
