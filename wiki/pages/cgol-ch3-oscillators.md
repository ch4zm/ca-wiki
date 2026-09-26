---
title: "Oscillators (Johnston and Greene, Ch. 3)"
category: Sources
summary: Chapter 3 of Conway's Game of Life - Mathematics and Construction - techniques for building oscillators of every period - billiard tables, eater-stabilized corners, sparks and composite periods, hasslers and shuttles, glider loops with reflectors (Snark), Herschel tracks for every period 61 or more, the omniperiodicity problem, and phoenices
tags: [source, chapter, life, oscillator, sparker, hassler, reflector, herschel, omniperiodicity, phoenix]
sources: [cgol-ch3-oscillators]
created: 2026-09-25
updated: 2026-09-25
---

# Oscillators (Johnston and Greene, Ch. 3)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 3, printed pp. 53-82 (PDF pp. 67-96). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

The chapter's goal is an [[oscillator](pages/oscillator.md)] of every period.[^1] It
starts with rare natural oscillators found by computer soup searches, then works through
construction methods of increasing precision.[^2]
- **Billiard tables** trap oscillating cells inside a stable wall.
- **Eater-stabilized corners** let [[eater](pages/eater.md)]s absorb debris bouncing
  between them.
- **Composite periods** come from combining oscillators whose short-lived *sparks*
  interact ([[sparker](pages/sparker.md)]).
- **Hasslers and shuttles** repeatedly push a standard unstable object such as a
  pre-honey farm, pi-heptomino, T-tetromino or pre-pulsar ([[hassler](pages/hassler.md)]).

The precise methods move a signal around a closed track. A *glider loop* bounces gliders
between reflectors; four Snarks give every period 43 or more
([[reflector](pages/reflector.md)]). A *Herschel track* moves a
[[herschel](pages/herschel.md)] through conduits; two conduits, R64 and Fx77, provably
give every period 61 or more.[^3] Intermediate periods, too large for search and too small for tracks,
are the hardest to fill ([[omniperiodicity](pages/omniperiodicity.md)]).[^4] The
chapter ends with [[phoenix](pages/phoenix.md)] oscillators, in which every live cell
dies each generation. Every phoenix is an oscillator, and none has period 3.[^5]

## Key Takeaways

- An oscillator counts as non-trivial only if some cell oscillates at its full period;
  side-by-side oscillators of periods 2 and 3 do not make a real period-6 oscillator.[^6]
- Sparks, which are cells that appear briefly and die, make oscillators combinable and
  can reflect gliders.[^7]
- Stable reflectors turn glider loops into oscillators of every sufficiently large
  period. The Snark, with repeat time 43, is the smallest and fastest.[^3]
- R64 and Fx77 Herschel conduits give oscillators of every period 61 or more, proved with
  Bézout's identity.[^3]

## Entities & Concepts

- [[oscillator](pages/oscillator.md)], [[omniperiodicity](pages/omniperiodicity.md)], [[phoenix](pages/phoenix.md)]
- [[sparker](pages/sparker.md)], [[hassler](pages/hassler.md)], [[reflector](pages/reflector.md)], [[herschel](pages/herschel.md)]
- [[eater](pages/eater.md)], [[pentadecathlon](pages/pentadecathlon.md)], [[queen-bee](pages/queen-bee.md)], [[twin-bees](pages/twin-bees.md)], [[pulsar](pages/pulsar.md)], [[glider](pages/glider.md)]

## Relation to Other Wiki Pages

The shuttles of [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] (queen bee, twin
bees) are hasslers in this chapter's terms, and the constrained eater built in
[[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] is what lets the R64 Herschel
conduit repeat every 61 generations.[^8]

[^1]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.53 - "develop techniques for constructing as wide a variety of oscillators as possible, in the hope of finding one of every single period"
[^2]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] §§3.1-3.4, pp.53-65 [synthesis] - rare natural oscillators (Fig. 3.1); billiard tables; stabilizing corners with eater 1 and eater 2; composite periods and sparks; hasslers and shuttles
[^3]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] §§3.5-3.6, pp.65-73 [synthesis] - reflectors and glider loops; the Snark with repeat time 43; Theorems 3.1-3.2: R64 and Fx77 give oscillators of any period 61 or larger
[^4]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] §3.7, pp.73-75 [synthesis] - omniperiodicity problem; Table 3.1; gaps at intermediate periods
[^5]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] §3.8, pp.75-77 [synthesis] - Theorem 3.3 (Phoenices are Oscillators); Theorem 3.4 (No Phoenices with Period 3)
[^6]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.57 - "it is typically required that an oscillator must have at least one cell that oscillates at its full period in order to be considered non-trivial"
[^7]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.57-61 [synthesis] - sparks "configurations of cells that die when left alone"; combining sparks gives composite periods; duoplet and banana sparks "can be used to reflect gliders by 90 degrees"
[^8]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.69 [synthesis] - "we can use the eater that we constructed back in Figure 2.24(b), which lets this conduit accept Herschels that are spaced 61 or more generations apart"; n.21 that eater's size constraints were designed for this conduit
