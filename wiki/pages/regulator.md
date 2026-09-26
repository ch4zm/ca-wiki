---
title: Regulator
category: Patterns
summary: A Life mechanism that accepts a glider arriving at any time and emits one aligned to a fixed period, so unsynchronized signals can enter periodic circuitry; a universal regulator (Paul Chapman, 2003) works at any sufficiently large period, built on the boat-bit and a duoplet spark from a glider-LWSS collision
tags: [pattern-class, life, regulator, circuitry, timing, boat-bit]
sources: [cgol-ch6-periodic-circuitry]
created: 2026-09-25
updated: 2026-09-25
---

# Regulator

## Description

Periodic circuitry needs its gliders on schedule. If an input glider is known to arrive
only at multiples of some n, it is easy to re-time. A period-n gun and an
[[inverter](pages/inverter.md)] do it, with the input deleting one gun glider, and
[[reflector](pages/reflector.md)]s adjust the input's path until the deletion is clean.
For small n, such as multiples of 8, Snarks, bumpers and bouncers set lane and timing.[^1]
If the input timing is completely unknown, neither method works. The first fails for
some timings, and reflectors can fix the first glider's timing but not the gaps between
later ones.[^2] A *regulator* emits a glider aligned to a chosen period whatever the input
timing, as long as inputs are spaced at least one period apart. A *universal regulator*
can be adjusted to any period.[^2]

**The universal regulator** (Paul Chapman, March 2003).[^3]
- **Core: the boat-bit.** An input glider hitting an eater 1 leaves a boat
  ([[eater](pages/eater.md)]).
- **Test.** A duoplet spark does nothing to the eater alone. If the boat is present, the
  spark destroys boat and eater and releases a glider. That glider's timing is fixed by
  the spark, not by the input.
- **Spark on schedule.** The spark comes from a glider-LWSS collision on a regular
  schedule, which also cleans up a leftover beehive. So the output follows the schedule,
  and the only period restriction is having guns of that period.
- **Rebuilding the eater 1.** A head-on LWSS-MWSS collision rebuilds it. Suppressor glider
  streams normally stop those ships, and the output glider knocks out one suppressor
  glider of each, so the eater is rebuilt only after it has been used.

Johnston and Greene show a period-60 implementation. Swapping in other guns gives any
sufficiently large period.[^4]

## Appearances in Sources

- [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] - §6.5: glider timing and the universal regulator

## Related Concepts

- [[inverter](pages/inverter.md)] - re-timing gliders on a known schedule
- [[eater](pages/eater.md)] - the boat-bit at the regulator's core
- [[reflector](pages/reflector.md)] - adjusting lanes and timing

[^1]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.172-173 [synthesis] - with inputs once every n ticks, "line up a period n gun with an inverter of the same period, and then find a way for the arriving glider to cleanly delete a glider"; Fig. 6.37 re-timing with buckaroos; for multiples of 8 "reflect the glider with Snarks and period 8 bouncers and bumpers"
[^2]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.173-174 [synthesis] - with unknown timing, interrupting a gun stream fails for some timings and reflectors fix only the first glider; "A mechanism that accomplishes this for a particular output period is called a regulator, and a mechanism that can be adjusted to work at any period is known as a universal regulator"
[^3]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.174-175 [synthesis] - n.26 "By Paul Chapman in March 2003"; boat bit with an eater 1; "a duoplet spark can be used to test whether or not the boat bit is present"; "the output glider always has a precise known timing relative to the creation of the duoplet spark"; Fig. 6.40 glider-and-LWSS collision creates the spark and destroys the beehive; LWSS-and-MWSS collision rebuilds the eater 1, gated by suppressing glider streams
[^4]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.175 - Fig. 6.41 "a period 60 implementation of, this universal regulator ... a universal regulator with any (sufficiently large) period can be constructed using these same reactions"
