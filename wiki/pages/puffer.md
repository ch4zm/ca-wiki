---
title: Puffer
category: Patterns
summary: A moving Life object that leaves debris behind; a rake is a puffer whose output is spaceships, a moving gun - switch-engine puffers, the B-heptomino puffer, the space rake (p20), Schick engine and Coe ship rakes (p16, p60, p80, p240), and adjustable rakes of any period 264 + 32n
tags: [pattern-class, life, puffer, rake, space-rake, schick-engine, coe-ship, infinite-growth]
sources: [cgol-ch4-spaceships-and-moving-objects, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Puffer

## Description

A *puffer* is an object that moves but leaves periodic junk behind it.[^1] A *rake* is a
[[spaceship](pages/spaceship.md)] that creates other spaceships as it travels: a moving
glider gun.[^2] Both grow without limit.

**Switch-engine puffers.** The block-laying and glider-producing
[[switch-engine](pages/switch-engine.md)]s travel at c/12 diagonally; pairs of engines
make arks.[^1] A Corderrake fires gliders sideways ([[cordership](pages/cordership.md)]).

**The standard route to a rake.** Rakes are built in two steps.[^2]
- **Puffer.** A B-heptomino moves 5 cells in 10 generations, and two of the front three
  columns of a lightweight spaceship are a B-heptomino in some phases. A lightweight
  spaceship on each side, whose rear dot spark overpopulates the interfering debris,
  stabilizes it into a c/2 puffer. The debris takes 5,532 generations to settle and then
  repeats with period 140. This puffer is sometimes called "puffer 2", the second
  found.[^3]
- **Debris into gliders.** An extra lightweight spaceship makes the debris die off
  completely, giving the period-20 *ecologist*, which trails a large spark. One more
  lightweight spaceship turns that spark into a glider: the **forward space rake**
  (gliders moving with it) or, moved slightly, the **backward space rake**. Either
  releases one glider every 20 generations, 10 cells apart.[^4]

**Thinning and mixing streams.**
- The **Schick engine** is a period-12 c/2 spaceship: two lightweight spaceships with a
  pulsating tagalong (Paul Schick, 1972). Placed beside a space rake, it destroys a third
  of the gliders and converts a third into blocks, which a middleweight spaceship then
  removes. The result is forward and backward rakes firing one glider every 60
  generations.[^5]
- The **Coe ship** is a period-16 c/2 spaceship with a pulsating trailing spark (Tim Coe,
  1995). Two heavyweight spaceships behind it give a period-16 backward rake; two more
  reflect the gliders forward. The same two-ship reflector turns any c/2 backward rake of
  period a multiple of 4, at least 16, into a forward rake.[^6]
- Crossing a period-20 space rake's stream with a period-16 Coe rake's gives rakes of
  period lcm(16, 20) = 80; using the period-60 rake gives period 240.[^7]

**Adjustable periods.** A period-2 spaceship (Dean Hickerson, 1989) with one rear spark
changed becomes a puffer, and a heavyweight spaceship turns that into a period-8 rake.[^8]
- Two period-8 rakes lay a trail of bi-blocks, a wick that a 2c/3 fuse burns faster than
  the rake moves ([[signal-wire](pages/signal-wire.md)]).
- Relighting the fuse each time gives a rake of any period 264 + 32n; each extra
  bi-block adds 32 generations.
- Deleting the output glider turns it into a spaceship of arbitrarily large period.
- A blinker-fuse design gives every sufficiently large multiple of 4.

## Appearances in Sources

- [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] - §4.4 puffers and rakes; §4.6.2 adjustable-period rakes and spaceships
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - switch-engine puffers and arks

## Related Concepts

- [[self-supporting-spaceship](pages/self-supporting-spaceship.md)] - rakes that crawl along block and blinker tracks, used to build spaceships
- [[switch-engine](pages/switch-engine.md)] - the natural puffers
- [[gosper-glider-gun](pages/gosper-glider-gun.md)] - the stationary counterpart of a rake
- [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)] - the parts rakes are made of
- [[signal-wire](pages/signal-wire.md)] - fuses and wicks behind adjustable rakes

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.14-15 [synthesis] - "An object like this one, which moves but leaves periodic junk behind it, is called a puffer"; block-laying and glider-producing switch engines; arks
[^2]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.94 [synthesis] - "a rake--a spaceship that creates additional spaceships as it travels"; step 1 construct a puffer; step 2 use xWSSes to transform the debris into a glider
[^3]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.94-95 [synthesis] - B-heptomino "moves forward by 5 cells in 10 generations"; n.17 xWSSes contain a B-heptomino in 2 of 4 phases; lightweight spaceship on either side; debris takes 5 532 generations, then period 140; n.18 found by Bill Gosper in the early 1970s, "puffer 2"
[^4]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.95-96 [synthesis] - extra LWSS gives "a period 20 spaceship called the ecologist"; another LWSS turns the spark into a glider travelling northeast or southwest; "the forward and backward space rake"; one glider every 20 generations, 10 cells apart
[^5]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.96-97 [synthesis] - Schick engine: period 12, pulsating tagalong behind two LWSSes (n.19 Paul Schick, 1972); destroys 1/3, leaves 1/3, turns 1/3 into blocks cleared by an MWSS; p60 forward and backward rakes
[^6]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.97-98 [synthesis] - Coe ship, c/2 period 16 (n.20 Tim Coe, 1995); two HWSSes give a p16 backward rake, two more a forward rake; n.21 the two-HWSS configuration turns any c/2 backward rake with period a multiple of 4 and at least 16 into a forward rake
[^7]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.98 [synthesis] - space rake and Coe rake streams cross, lcm(16, 20) = 80; period 80 forward or backward rakes; period 60 variant gives lcm(16, 60) = 240
[^8]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.109-110 [synthesis] - p2 spaceship (Hickerson 1989) becomes a p8 puffer and, with an HWSS, a p8 rake; two rakes lay the bi-block wick; fuse at 2c/3 catches up; Fig. 4.52 adjustable rake of period 264 + 32n; n.36 each bi-block adds 32 generations; extra LWSS deletes the glider; blinker-fuse method for all sufficiently large multiples of 4 (Bell 1992)
