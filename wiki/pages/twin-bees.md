---
title: Twin bees
category: Patterns
summary: A pair of B-heptominoes that reflects itself every 23 generations; stabilized by blocks it gives the period-46 twin bees shuttle, and two pairs make the period-46 twin bees gun
tags: [pattern, life, twin-bees, b-heptomino, shuttle, period-46, gun]
sources: [cgol-ch6-periodic-circuitry, cgol-ch3-oscillators, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Twin bees

## Description

**B-heptomino.** The B-heptomino is a commonly occurring unstable seven-cell object.
After 10 generations it becomes a copy of itself 5 cells forward plus trailing junk, which
then destroys it.[^1] It takes 148 generations to stabilize.[^2]

**Twin bees.** B-heptominoes sometimes occur in pairs, called *twin bees* (both "twin Bs"
and an echo of the [[queen-bee](pages/queen-bee.md)]). The pair survives longer than one
alone and reflects itself after 23 generations, leaving junk that soon explodes and
destroys it.[^3]

**Twin bees shuttle.** Two [[block](pages/block.md)]s placed by the debris eat it in 5
generations and survive. With blocks on both sides, the twin bees reflect back and forth
with their debris cleaned up each time, giving the **twin bees shuttle**, a period-46
[[oscillator](pages/oscillator.md)] (23 + 23). Bill Gosper found this stabilization in
1971, and there are other ways to stabilize the shuttle.[^4]

**Twin bees gun.** Colliding two pairs of twin bees, the way two queen bees make the
[[gosper-glider-gun](pages/gosper-glider-gun.md)], gives a period-46 glider gun, also
found by Gosper. It was the smallest period-46 gun until a smaller one was found in
December 2021.[^5]

**Herschel and sparks.** Left alone, a B-heptomino becomes a block and a
[[herschel](pages/herschel.md)] in 20 generations. The twin bees shuttle gives off duoplet sparks that
can turn a glider by 90 degrees ([[sparker](pages/sparker.md)]).[^6]

**Period-46 circuitry.** The twin bees shuttle and gun anchor a family of period-46 parts.[^7]
- Reflections of gliders and LWSSes, glider-LWSS conversion both ways, and a period-23
  gun made by merging two period-46 streams ([[reflector](pages/reflector.md)]).
- An LWSS-to-MWSS converter for small MWSS guns.
- A reflector that also duplicates, used in ticker tapes and [[memory-cell](pages/memory-cell.md)]s.
- The simplest [[heisenburp](pages/heisenburp.md)].

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - §1.4: the B-heptomino, twin bees, shuttle and gun

## Related Concepts

- [[memory-cell](pages/memory-cell.md)], [[heisenburp](pages/heisenburp.md)] - period-46 circuits built on the shuttle
- [[herschel](pages/herschel.md)] - what a B-heptomino becomes
- [[sparker](pages/sparker.md)] - the shuttle's duoplet sparks
- [[queen-bee](pages/queen-bee.md)] - the period-30 analogue
- [[gosper-glider-gun](pages/gosper-glider-gun.md)] - built the same way
- [[r-pentomino](pages/r-pentomino.md)] - produces a B-heptomino-like object in generation 28

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.11-12 - "after 10 generations it evolves into a copy of itself 5 cells forward, plus some extra junk behind it ... However, it is then quickly killed by its trailing debris"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.16 - "the B-heptomino and the random configuration depicted in Figure 1.5, which take 148 and 2 901 generations to stabilize, respectively"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.12 [synthesis] - "B-heptominoes occasionally occur in pairs, in a configuration that is called the twin bees"; "they now reflect themselves, just like the queen bee did (albeit after 23 generations instead of 15)"; the mess "explodes and destroys them very shortly after the first reflection"; n.12 on the name
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.12-13 [synthesis] - Fig. 1.21: two blocks destroy the debris in 5 generations; "This whole process takes 23 + 23 = 46 generations to complete, and results in the period 46 oscillator known as the twin bees shuttle"; n.13 "This stabilization was found by Bill Gosper in 1971"; "there are many other ways to stabilize the twin bees shuttle"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.13, n.14 - "This gun was also found by Bill Gosper, and was the smallest p46 gun until ConwayLife.com forums user 'iNoMed' found a smaller version in December 2021"
[^6]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.61,68 [synthesis] - "The B-heptomino takes 20 generations to evolve into a block and a Herschel"; "Some sparkers create a duoplet spark ..., such as the twin bees shuttle"; duoplet sparks reflect gliders by 90 degrees
[^7]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.163-169 [synthesis] - "we can also use the twin bees shuttle ... and the related twin bees gun ... to build up a set of period 46 circuitry"; Fig. 6.23 reflections and conversions; Fig. 6.24 p23 gun, p46 LWSS gun, LWSS-to-MWSS converter; Fig. 6.25 reflecting and duplicating; Fig. 6.31 Heisenburp
