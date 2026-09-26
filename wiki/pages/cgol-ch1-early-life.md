---
title: "Early Life (Johnston and Greene, Ch. 1)"
category: Sources
summary: Chapter 1 of Conway's Game of Life - Mathematics and Construction - the rule and B/S rulestrings, soups and ash, common evolutionary sequences, the queen bee and Gosper glider gun, twin bees, the switch engine and its puffers, methuselahs, Gardens of Eden and orphans, and the history of soup searching
tags: [source, chapter, life, soup, ash, methuselah, garden-of-eden, gosper-glider-gun, switch-engine]
sources: [cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Early Life (Johnston and Greene, Ch. 1)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 1, printed pp. 3-32 (PDF pp. 17-46). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

The chapter states the rule, then asks why this rule. Of the 2^18 = 262,144
[[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] rules, Life is
simple, balanced between chaos and stability, and the most studied.[^1] It introduces
rulestring notation (Life is B3/S23) and names the other ways to vary a rule, which the
book defers to Chapter 12.[^2]

The first technique is "random fumbling": run random *soups* and see what *ash* is left.
This finds the common still lifes, the blinker and other small oscillators, the
[[glider](pages/glider.md)], and the
[[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)].[^3]
Watching soups also turns up unstable objects whose explosions recur: the T-tetromino
(to traffic lights), the pre-honey farm, the stairstep hexomino (to the blockade) and the
pi-heptomino ([[familiar-fours](pages/familiar-fours.md)]).[^4] Some of these can be
tamed. The [[queen-bee](pages/queen-bee.md)] gives a period-30 shuttle and, in pairs, the
[[gosper-glider-gun](pages/gosper-glider-gun.md)]. The B-heptomino pairs as
[[twin-bees](pages/twin-bees.md)], giving a period-46 shuttle and gun.[^5] The
[[switch-engine](pages/switch-engine.md)] moves, and with the right debris becomes a
block-laying or glider-producing puffer, the only infinitely growing patterns ever seen to
arise from random soup.[^6]

The chapter closes with two questions of lifespan and ancestry. A
[[methuselah](pages/methuselah.md)] is a small pattern that takes unusually long to
stabilize; the R-pentomino takes 1,103 generations, and the record holders for 5 to 13
cells run from 1,105 to 29,126.[^7] Running Life backwards, a
[[garden-of-eden](pages/garden-of-eden.md)] has no parent. The chapter proves they exist,
shows how to build one cell by cell, and states what is known about the smallest ones and
about patterns with parents but no grandparents.[^8] The historical notes cover how Life
news circulated and the growth of automated [[soup-search](pages/soup-search.md)].[^9]

## Key Takeaways

- Life is B3/S23: born with 3 live neighbours, survives with 2 or 3.[^2]
- Still lifes, oscillators and spaceships are the three basic object types; everything
  larger is built from them.[^10]
- Most modern Life patterns are *engineered*: known reactions combined into new objects,
  as the queen bee shuttle is.[^11]
- Switch-engine puffers are the only infinitely growing patterns known to arise
  naturally, because they have very small predecessors while guns need many coordinated
  cells.[^6]
- "Stabilizes" and "methuselah" resist precise definition.[^12]
- Almost all large patterns are Gardens of Eden; no Garden of Eden has height 1, and
  orphans exist with height 5 but not 2 or 3.[^8]

## Entities & Concepts

- [[game-of-life](pages/game-of-life.md)], [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)], [[moore-neighbourhood](pages/moore-neighbourhood.md)]
- [[still-life](pages/still-life.md)], [[oscillator](pages/oscillator.md)], [[spaceship](pages/spaceship.md)], [[methuselah](pages/methuselah.md)]
- [[block](pages/block.md)], [[beehive](pages/beehive.md)], [[blinker](pages/blinker.md)], [[pulsar](pages/pulsar.md)], [[pentadecathlon](pages/pentadecathlon.md)], [[glider](pages/glider.md)], [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)], [[r-pentomino](pages/r-pentomino.md)]
- [[familiar-fours](pages/familiar-fours.md)], [[queen-bee](pages/queen-bee.md)], [[gosper-glider-gun](pages/gosper-glider-gun.md)], [[twin-bees](pages/twin-bees.md)], [[switch-engine](pages/switch-engine.md)]
- [[garden-of-eden](pages/garden-of-eden.md)], [[soup-search](pages/soup-search.md)]

## Relation to Other Wiki Pages

The chapter's Garden-of-Eden existence proof is the Life case of Moore's argument
([[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]); the book credits the
general theorem to Moore and Myhill.[^13]

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.4 [synthesis] - "there are 2^18 = 262 144 distinct Life-like cellular automata"; three properties "make Life special (but by no means unique)": its rules are simple; "It strikes a balance between being chaotic and stable"; "It is historical"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.3,5 [synthesis] - survival on 2 or 3 live neighbours, birth on exactly 3, applied simultaneously to the 8 touching cells; "a rulestring of the form Bx/Sy"; "the Game of Life is described by the rulestring B3/S23"; von Neumann neighbourhood, hexagonal or triangular grids, 1D or 3D, "isotropic rules, or INT rules" deferred to Chapter 12
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.5-8 [synthesis] - "Random starting configurations like this one are sometimes called soup, and the objects that they leave behind are called ash"; block, tub, boat, ship, beehive, loaf, pond, blinker and glider "frequently appear in the ash"; pulsar, toad, beacon, clock, pentadecathlon; LWSS, MWSS, HWSS
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.8-10 [synthesis] - T-tetromino to traffic light in 9 generations; pre-honey farm to honey farm in 17; stairstep hexomino to blockade in 63 ("lumps of muck"); pi-heptomino moves forward 9 cells in 30 generations leaving debris
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.10-13 [synthesis] - queen bee reflects every 15 generations leaving a beehive; blocks eat the beehives giving the period 30 queen bee shuttle; two queen bees give the Gosper glider gun; B-heptomino; twin bees reflect after 23 generations; period 46 twin bees shuttle and twin bees gun
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.13-15 [synthesis] - switch engine of 8 cells reappears every 48 generations moving away; block-laying and glider-producing switch engines; "puffers based on switch engines are the only infinitely growing patterns that have ever formed as a result of randomly filling some portion of the Life plane"; "they have some very small predecessors ... whereas glider guns require a comparatively large number of 'coordinated' live cells"
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.16-18 [synthesis] - methuselah defined; R-pentomino "takes 1 103 generations to stabilize"; Table 1.1: longest-lived known methuselahs with 5-13 cells, lifespans 1 105 to 29 126
[^8]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.19-26 [synthesis] - Theorem 1.1 (existence of Gardens of Eden); spiral construction; orphans; smallest-known orphans (Fig. 1.36); Theorem 1.2 (no Gardens of Eden of height 1); no orphans of height 2 or 3, one of height 5, height 4 open; a pattern with a parent but no grandparent; "almost all large patterns are Gardens of Eden" (n.30)
[^9]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] §1.8, pp.26-28 [synthesis] - Gardner's articles, the Lifeline newsletter, mailing lists, LifeNews, the conwaylife.com forums; soup searches by Flammenkamp, Okrasinski, TOLLCASS and apgsearch (Table 1.2)
[^10]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7 - "Still lifes, oscillators, and spaceships are the three most basic types of objects that we will study in Life, and they form the building blocks of all of the more complicated patterns that we will construct"
[^11]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11 - "The queen bee shuttle is our first example of an engineered object ... This is how most recent discoveries in the Game of Life have been made"
[^12]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.16-19 [synthesis] - "this definition is very imprecise: there is no completely objective way to say that some patterns are methuselahs"; gliders aimed at far-away blinkers, regular infinite growth, and the 736 692-generation ark as problem cases
[^13]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.22, n.31 - "This more general theorem was proved by Edward F. Moore and John Myhill in the early 1960s"
