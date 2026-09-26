---
title: Signals, wires and fuses
category: Concepts
summary: Moving information faster than spaceships can - signals travelling through repeating "wire" patterns (up to c parallel to zebra stripes, at most 2c/3 across them), fuses that burn through wicks, and glider collisions that seem to teleport objects while never exceeding lightspeed
tags: [concept, life, signal, wire, zebra-stripes, fuse, wick, lightspeed]
sources: [cgol-ch4-spaceships-and-moving-objects]
created: 2026-09-25
updated: 2026-09-25
---

# Signals, wires and fuses

## Description

The c/4 and c/2 limits on [[spaceship](pages/spaceship.md)] speeds hold only in empty
space. Nothing can exceed c, since a cell affects only its eight neighbours, but a
disturbance moving through a non-empty background can reach c.[^1]

**Wires and signals.** A *signal* is an object that moves through a repeating non-empty
pattern, the *wire*, and leaves it intact. Zebra stripes, alternating rows of live and
dead cells, carry several lightspeed signals.[^2]
- Every finite signal moving parallel to zebra stripes travels at exactly c (Dean
  Hickerson, 1993). If its leading edge ever advances, a neighbour count forces it to keep
  advancing one cell per generation.[^3]
- Signals across the stripes are at most 2c/3 (Hartmut Holzwart, 2006). Known examples
  reach 2c/3, and they are large.[^4]
- Diagonal signals on more complex wires are known at 2c/3, 5c/9 and c/2. 2c/3 is the
  fastest diagonal signal known through a stable wire.[^5]
- A *source* creates a signal and a *sink* destroys it; together they make a billiard
  table oscillator with the source's period. They are analogous to guns and eaters.[^6]
- A *signal elbow* would turn a signal around a corner, the way a reflector turns a
  glider. One corner turns the 2c/3 diagonal signal but duplicates it, so it cannot close a
  loop. Known elbows convert the signal into Herschels and back, and they are very
  slow.[^7]

In practice signals on wires see little use: it is simpler to aim a
[[glider](pages/glider.md)], and far more machinery exists for moving and retiming
gliders.[^8]

**Fuses and wicks.** When the object destroys the pattern it moves through, the pattern
is a *wick* and the object a *fuse*.[^9]
- Fuses are much easier to find than signals; debris placed near a row of blinkers soon
  makes one burn.
- *Clean* fuses leave nothing behind. The blinker fuse (period 18) and the bi-block fuse
  (period 12) both burn at 2c/3; a beehive-wick fuse reaches 4c/5.
- The bi-block fuse is the block-eats-beehive reaction, modified by the second block so
  that it repeats.
- Fuses power adjustable-period rakes and spaceships ([[puffer](pages/puffer.md)]).

**Teleportation.** Some glider collisions seem to move an object faster than spaceships
can.[^10]
- **Fast forward force field** (Dietrich Leithner, 1994): three gliders destroy each
  other, but an LWSS in their path reappears 11 cells ahead only 6 generations later.
  - The collision always makes an LWSS. The incoming one only decides whether a spark
    destroys it.
  - Only after about 24 generations is the outcome readable, for an effective speed of
    5c/6.
- **Diagonal lightspeed collision** (Jason Summers, 1999): a long diagonal glider
  collision carries one glider's information about 150 cells in 193 generations, at c
  within the collision.
  - It is the only known way to send information diagonally at lightspeed.
  - It needs very closely spaced gliders, so a pattern using it would be very large.

## Appearances in Sources

- [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] - §4.5.1 wires and signals; §4.5.2 fuses and wicks; §4.5.3 teleportation

## Related Concepts

- [[spaceship](pages/spaceship.md)] - the speed limits signals get around
- [[reflector](pages/reflector.md)] - the glider analogue of a signal elbow
- [[puffer](pages/puffer.md)] - fuses give adjustable-period rakes
- [[still-life-density](pages/still-life-density.md)] - zebra stripes are a density-1/2 still life

[^1]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.99-100 [synthesis] - Theorem 4.1 "only applies to objects travelling through a vacuum"; through a repeating non-empty pattern "an object may be able to travel through it at up to lightspeed"; n.23 "No object ... can possibly have a speed greater than c, since in one generation it can only affect its 8 neighbors"
[^2]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.100 - "An object that moves through a non-empty pattern like this is called a signal, and the pattern that it is able to move through is called a wire"; Fig. 4.36 lightspeed signals through zebra stripes
[^3]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.100 [synthesis] - Theorem 4.2 "Every finite signal that moves parallel through a zebra stripes wire travels at a speed of c"; proof via cells X, Y, Z; n.25 Dean Hickerson, 1993
[^4]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.101-102 [synthesis] - perpendicular signals "rather large" and cannot travel at lightspeed; Theorem 4.3 "The maximum speed at which a finite signal can travel perpendicularly through zebra stripes is 2c/3" (n.28 Holzwart, 2006); Fig. 4.39 signals at 2c/3
[^5]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.102 [synthesis] - diagonal signals at 2c/3, 5c/9 and c/2 (Fig. 4.41); "The 2c/3 diagonal signal is the fastest one known ... through a stable (p1) wire"
[^6]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.101 [synthesis] - "an object that can create the signal (called a source) and an object that can destroy the signal (called a sink)"; combined they form "a billiard table oscillator with period equal to that of the signal source"; n.26 analogy with guns, eaters and reflectors
[^7]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.101-103 [synthesis] - signal elbow defined; n.27 "Very large signal elbows are known that work by converting signals into things like Herschels ... they are all very slow"; Fig. 4.42 corner that reflects the 2c/3 diagonal signal "but which also creates a second copy"
[^8]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.113 - "it is typically simpler to just point a glider in the right direction ... we have a lot of machinery for repositioning and re-timing gliders, but hardly any such machinery for signals"
[^9]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.103-104 [synthesis] - "the wire is instead called a wick, and the objects that 'burns' through the wick is called a fuse"; easier to find; "burn cleanly"; Fig. 4.43 blinker fuse (p18) and bi-block fuse (p12) at 2c/3; 4c/5 fuse (Ex. 4.28); bi-block fuse uses the block and beehive of Fig. 1.16
[^10]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.104-105 [synthesis] - fast forward force field (n.30 Leithner, 1994): LWSS reappears "6 generations later, 11 cells in front"; "the glider collision produces an LWSS as its output regardless"; effective "20c/24 = 5c/6"; Fig. 4.46 diagonal collision (Summers, 1999) teleports a glider about 150 cells in 193 generations, "at a speed of exactly c"; "we had no way of transmitting information diagonally at the speed of light"; such a pattern "would be extremely large"
