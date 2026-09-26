---
title: Heisenburp
category: Patterns
summary: A Life mechanism that detects or copies a passing spaceship without affecting it at all - the passing glider only overcrowds a nearby spark so it becomes a new glider; named against Heisenberg's uncertainty principle
tags: [pattern-class, life, heisenburp, duplicator, detector, circuitry]
sources: [cgol-ch6-periodic-circuitry]
created: 2026-09-25
updated: 2026-09-25
---

# Heisenburp

## Description

A *Heisenburp* is a duplicator in which the input [[glider](pages/glider.md)] is not
affected at all, even temporarily. It only overpopulates cells near a spark, the way an
induction coil stabilizes a still life, and that changes the spark into a new glider. The
name plays on Heisenberg's uncertainty principle: in Life a particle can be detected and
copied without disturbing it.[^1]

**Examples.**[^2]
- The simplest: two perpendicular [[twin-bees](pages/twin-bees.md)] shuttles whose spark,
  slightly suppressed by a passing glider, becomes a block and then a new glider. The
  period is 92, and it was found by Brice Due in 2005.
- The *MWSS out of the blue* (Peter Rott, 1997): two twin bees shuttles release a
  middleweight spaceship in the opposite direction when a lightweight spaceship passes.
  In general, any spark whose evolution a passing object changes enough can be turned
  into an output.
- A glider, an MWSS and an HWSS collide cleanly if a passing glider is nearby, and make a
  glider if not (Jason Summers, 1999). The reaction has repeat time 35, so with an
  [[inverter](pages/inverter.md)] to flip the output it gives Heisenburps of any period 35
  or more, for example at period 46.

**Stable ones.** Heisenburps made only of still lifes exist for spaceships whose sparks
make a still life explode into a signal. A glider has no accessible sparks, so a glider
Heisenburp needs an oscillating part.[^3]

## Appearances in Sources

- [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] - §6.3.3: Heisenburps

## Related Concepts

- [[inverter](pages/inverter.md)] - ordinary duplicators, which do touch the glider
- [[sparker](pages/sparker.md)] - Heisenburps work by nudging sparks
- [[twin-bees](pages/twin-bees.md)] - the simplest one uses two shuttles

[^1]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.168-169 [synthesis] - "there exist duplicators for which this is not necessary, as the input glider is not actually affected at all (even temporarily)"; "the passing glider itself is not affected at all in the process, but rather just serves to overpopulate other nearby cells (much like how we used induction coils)"; n.18 named for Heisenberg's uncertainty principle
[^2]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.169-170 [synthesis] - Fig. 6.31 "A small period 92 Heisenburp that uses two twin bees shuttles" (n.19 Brice Due, January 2005); Fig. 6.32 MWSS out of the blue (n.20 Peter Rott, November 1997); "all that is needed is a spark whose evolution is changed sufficiently by the passing spaceship"; Fig. 6.33 glider + MWSS + HWSS reaction with "a repeat time of 35 generations" (n.21 Jason Summers, June 1999); Fig. 6.34 period 46 Heisenburp
[^3]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.171 - "it is even possible to construct stable Heisenburps ... using a spark from the to-be-detected spaceship to cause a still life to explode ... However, a glider Heisenburp must have an oscillating component, as gliders have no accessible sparks that could be detected by still lifes"
