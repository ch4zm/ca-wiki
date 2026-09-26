---
title: Primer
category: Patterns
summary: A Life gun that emits a stream of lightweight spaceships in which the n-th ship is present exactly when n is prime - a sieve of Eratosthenes built from an LWSS stream and breeders that lay ever-longer inline-inverter guns; relatives include a twin primer, whose infinite output is an open problem
tags: [pattern, life, primer, computation, primes, sieve, breeder, circuitry]
sources: [cgol-ch6-periodic-circuitry]
created: 2026-09-25
updated: 2026-09-25
---

# Primer

## Description

A *primer* is a gun whose output stream of lightweight spaceships has a ship in position
n exactly when n is prime.[^1] Dean Hickerson built the first in November 1991.[^2]

**Idea: a sieve.** Make a regular LWSS stream of period p, then aim glider guns of period
2p, 3p, 4p, ... at it. The gun of period kp deletes every ship whose position is a
multiple of k. A glider and an LWSS can be aimed to destroy each other. The survivors are
the primes. A small version with only 2p and 3p guns leaves ships at positions not
divisible by 2 or 3.[^3]

**Infinitely many guns.** A period-120n gun is made of two Gosper guns at a distance
set by n, with a glider bouncing between them ([[inverter](pages/inverter.md)]). So one
set of rakes travels north laying Gosper guns and another travels east doing the same,
and the diagonal gap between paired guns grows without bound. That lays guns of ever-larger
period ([[breeder](pages/breeder.md)]).[^4]

**Making it work.**[^5]
- The period-60 breeders space guns 30 cells apart, so the gun periods step by 240. The
  breeders therefore make guns for 3p, 5p, 7p, ..., and one hand-placed 2p gun handles
  even positions.
- Guns 30 cells apart are too close for diagonal bouncing, so one stabilizing block is
  swapped for an eater 1 (as in the buckaroo), laid by a modified breeder.
- A row of middleweight spaceships deletes the stray gliders released before the paired
  rows sync up.
- A single block under each gun absorbs its first glider, so the ship at position k
  itself survives.

The finished primer uses a compact 6-rake breeder, a period-120 LWSS stream synthesized
by three space rakes, and inline-inverter guns of period 240 and 360 + 240n.[^6]

**Relatives.**
- A *twin primer* emits a ship at position n exactly when n − 2 and n are both prime.
  Whether infinitely many twin primes exist is a famous open problem, so whether that
  pattern emits infinitely many ships is unknown.[^7]
- Conway and Gosper's proof that Life is universal already implied primes could be
  computed in Life, years before a primer was built.[^8]

## Appearances in Sources

- [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] - §6.2: construction; §6.6: history, twin primer

## Related Concepts

- [[inverter](pages/inverter.md)] - its guns are inline-inverter guns
- [[breeder](pages/breeder.md)] - lays those guns
- [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)] - the output stream
- [[game-of-life](pages/game-of-life.md)] - computation in Life

[^1]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.159 - "we build a pattern that emits a stream of lightweight spaceships with the property that the n-th spaceship in the stream is present if and only if n is prime ... We call guns of this type primers"
[^2]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.159, n.6 - "The first primer was constructed by Dean Hickerson in November 1991"
[^3]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.159-161 [synthesis] - Fig. 6.16 a glider and an LWSS destroying each other; guns of periods 2p and 3p delete multiples of 2 and 3 (Fig. 6.18); "aim glider guns with periods 2p, 3p, 4p, 5p, and so on at the gun"
[^4]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.161 [synthesis] - "the period 120n guns based on the inline inverter are perfect candidates for this task, since their periods are determined solely by how far apart the two Gosper glider guns at their ends are"; rakes north and east lay the endpoint guns; Fig. 6.19 schematic
[^5]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.161-162 [synthesis] - four problems: 240-step periods fixed with 3p, 5p, 7p, ... plus a manual 2p gun; eater 1 replaces a block; MWSSes destroy excess gliders; a block below each gun spares the prime itself
[^6]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.162-163 [synthesis] - Fig. 6.20 compact breeder with 6 space rakes; Fig. 6.22 completed primer with a period 120 LWSS stream from 3 space rakes and inline inverter guns of period 240 and 360 + 240n
[^7]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.176 - "A twin primer ... the n-th spaceship in the stream is present if and only if both n − 2 and n are prime ... it is currently unknown whether or not there are infinitely many twin primes ... so it is unknown whether or not it emits infinitely many lightweight spaceships"
[^8]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.178 - "John Conway and Bill Gosper used little more than some basic period 30 circuitry ... to demonstrate that the Game of Life is universal ... Thus, for example, we knew that prime numbers could be computed in the Game of Life for several years before the first primer was explicitly constructed"
