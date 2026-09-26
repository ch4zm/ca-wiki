---
title: Switch engine
category: Patterns
summary: An eight-cell unstable Life object that travels diagonally, reflecting itself every 48 generations; stabilized by its own debris it becomes the block-laying or glider-producing switch engine, puffers that are the only infinitely growing patterns ever seen to arise from random soup; pairs of switch engines make arks
tags: [pattern, life, switch-engine, puffer, ark, infinite-growth, methuselah]
sources: [cgol-ch5-glider-synthesis, cgol-ch4-spaceships-and-moving-objects, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Switch engine

## Description

The switch engine is an unstable configuration of 8 live cells. Every 48 generations it
reappears reflected across the diagonal, leaving chaotic junk behind. After 96 generations
it is back in its original orientation, 8 cells northeast of where it started, so it keeps
moving away like a spaceship. Left alone, it appears for the last time in generation 1,152,
when its junk catches up and destroys it.[^1] It takes 3,911 generations to stabilize,
much longer than most patterns of 8 or fewer cells.[^2] Charles Corderman found it while
studying nonominoes (nine-cell polyominoes), one of which evolves into it.[^3]

**Puffers.** A *puffer* is an object that moves but leaves periodic junk behind it.
A single block placed next to a switch engine can make its debris settle into a moving
stabilization, giving one of two puffers:[^4]
- the **block-laying switch engine**, which lays 8 blocks every 288 generations;
- the **glider-producing switch engine**, which leaves 4 blinkers, 8 still lifes and a
  glider every 384 generations. The glider travels the same way at 3 cells per 12
  generations, against the engine's 1 cell per 12, and soon passes it.

These two puffers are the only infinitely growing patterns that have ever formed from a
randomly filled region of the Life plane. They have very small predecessors, 11 or 12
cells, while glider guns need many coordinated live cells.[^5]

**Arks.** A puffer made of two switch engines stabilizing each other is an *ark*. Dozens
can be found by trying different relative positions and phases. One example leaves 2
gliders, 2 toads, 8 blinkers and 42 still lifes every 576 generations, moving 48 cells
diagonally.[^6] The first ark, Noah's ark, was found by Corderman in 1971 and named for
the pairs of objects in its debris; the general term comes from it.[^7] A 16-cell pattern
made of two switch-engine predecessors takes 736,692 generations to stabilize, and a
19-cell one of two predecessors plus a blinker takes 6,526,574.[^8]

Switch engines that clean up all of each other's debris make c/12 diagonal spaceships,
the [[cordership](pages/cordership.md)]s.[^9]

Three gliders can synthesize a switch engine, and one three-glider collision makes a
glider-producing switch engine plus junk, the only known way to get infinite growth
from three gliders ([[object-synthesis](pages/object-synthesis.md)]).[^10]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - §1.5: switch engine, its two puffers, arks; §1.6 long-lived arks

## Related Concepts

- [[cordership](pages/cordership.md)] - spaceships made of switch engines
- [[gosper-glider-gun](pages/gosper-glider-gun.md)] - the other kind of unbounded growth
- [[methuselah](pages/methuselah.md)] - long-lived arks strain the definition
- [[soup-search](pages/soup-search.md)] - the searches in which switch-engine puffers are the only infinite growth seen

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.13-14 [synthesis] - "the switch engine, which is the configuration of 8 live cells"; reappears after 48 generations "in a different location and orientation"; Fig. 1.24: after 96 generations back in original orientation 8 cells northeast; "appears for the last time in generation 1 152"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.16 - "the 8-cell switch engine, which takes 3 911 generations to stabilize--considerably longer than most other patterns with 8 or fewer cells"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.27 - "the switch engine was originally found by Charles Corderman when he was investigating the evolution of nonominoes (i.e., polyominoes with 9 live cells), one of which evolves in the exact same way as the switch engine"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.14-15 [synthesis] - "block-laying switch engine ... (8 blocks every 288 generations)"; "An object like this one, which moves but leaves periodic junk behind it, is called a puffer"; glider-producing switch engine leaves "4 blinkers, 8 still lifes, and one glider ... every 384 generations"; glider at "3 cells every 12 generations, versus the switch engine's 1 cell every 12 generations"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.15 [synthesis] - "puffers based on switch engines are the only infinitely growing patterns that have ever formed as a result of randomly filling some portion of the Life plane and then evolving it"; small predecessors "like the 12-cell objects" (n.16: 11 cells with one block cell removed) "whereas glider guns require a comparatively large number of 'coordinated' live cells to form"
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.15-16 [synthesis] - "any puffer created by using two switch engines is called an ark, and dozens can be found just by trying different positions and phases"; Fig. 1.27: "two gliders, two toads, eight blinkers, and 42 still lifes ... every 576 generations", offset 48 cells diagonally
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.30, n.48 - "This ark was found in 1971 by Charles Corderman, and was the first-discovered ark. Its name refers to the fact that the debris it leaves behind contains pairs of many different objects. The general term 'ark' is derived from the name of this pattern"
[^8]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.18,31 [synthesis] - Fig. 1.30: "A 16-cell pattern that takes a whopping 736 692 generations to stabilize ... this pattern is an ark"; Ex. 1.17: "The 19-cell pattern ... consists of two switch engine predecessors and a blinker, and takes a staggering 6 526 574 generations to stabilize"
[^9]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.90 - using switch engines "to stabilize each other and erase their debris entirely (thus creating a spaceship) ... Spaceships constructed in this way are called Corderships"
[^10]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.124-125 [synthesis] - Table 5.2 3-glider syntheses of the switch engine and the glider-producing switch engine; "the only known way of generating infinite growth with just 3 gliders"
