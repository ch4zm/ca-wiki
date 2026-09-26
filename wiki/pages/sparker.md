---
title: Sparker
category: Patterns
summary: An oscillator that gives off a spark - a small group of cells that dies on its own, placed where the oscillator is otherwise empty; domino, dot, finger, thumb, duoplet and banana sparks let oscillators be combined into new composite periods, hassle other objects, and reflect gliders
tags: [pattern-class, life, sparker, spark, oscillator, composite-period, reflector]
sources: [cgol-ch3-oscillators]
created: 2026-09-25
updated: 2026-09-25
---

# Sparker

## Description

A *spark* is a group of cells that dies when left alone. The term is mostly used for a
piece of an oscillator or spaceship that dies and sits where the object is empty in its
other phases. A *sparker* is an oscillator that gives off sparks.[^1]

**Composite periods.** Two [[oscillator](pages/oscillator.md)]s placed side by side with
no interaction make only a *trivial* oscillator, with no cell oscillating at the combined
period. If their sparks are placed to interact briefly and die, the result is a
non-trivial oscillator whose period is the least common multiple of the two.[^2] For
example, a period-15 [[pentadecathlon](pages/pentadecathlon.md)] next to a period-9
snacker gives a non-trivial period-45 oscillator, with two cells alive one generation in
every 45.[^3]

**Spark types.**[^4]
- **Domino**: two orthogonally adjacent cells, as from the pentadecathlon, the snacker
  and the figure eight. Sparks far from the oscillator's body are easier to use.
- **Pipsquirter**: an oscillator whose domino spark points perpendicular to its nearest
  edge.
- **Dot**: a single isolated cell, as from the mold or the middleweight spaceship. Two dot
  sparks cannot together cause a birth, so they pair with other spark types.
- **Emulators, volcanoes, supervolcanoes**: named for sparks resembling a middleweight or
  heavyweight spaceship's. Emulators emit in the adjacent row, volcanoes one row out, and
  supervolcanoes two rows out.
- **Finger** and **thumb**: sparks attached to the body, orthogonally (finger) or
  diagonally (thumb). They are harder to reach, so they are usually paired with dot or
  domino sparks.
- **Duoplet**: two diagonally connected cells, as from the
  [[twin-bees](pages/twin-bees.md)] shuttle.
- **Banana**: from the buckaroo, a [[queen-bee](pages/queen-bee.md)] shuttle variant.

Duoplet and banana sparks can turn a [[glider](pages/glider.md)] by 90 degrees, which
makes these sparkers usable as reflectors ([[reflector](pages/reflector.md)]).[^5]

**The caterer.** The caterer is the smallest known period-3 oscillator and a finger
sparker. Its spark is used in the smallest known oscillators of periods 21, 24, 33, 39,
66 and 93.[^6] Billiard tables, which enclose all their oscillating cells, give off no
sparks and are less useful for this reason.[^7]

## Appearances in Sources

- [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] - §3.3: composite periods, the spark catalogue, spark-based reflection

## Related Concepts

- [[oscillator](pages/oscillator.md)] - sparkers are oscillators
- [[hassler](pages/hassler.md)] - sparks push the objects that hasslers move
- [[reflector](pages/reflector.md)] - duoplet and banana sparks reflect gliders
- [[pentadecathlon](pages/pentadecathlon.md)] - the classic domino sparker

[^1]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.57-58 [synthesis] - "sparks: configurations of cells that die when left alone"; n.5 "most commonly used to refer to a piece of an oscillator or spaceship that dies and is in a location that is unoccupied during its other phases"; "oscillators that provide sparks (called sparkers)"
[^2]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.57 [synthesis] - a blinker next to a pulsar returns to its initial phase only at lcm(2, 3) = 6; "an oscillator must have at least one cell that oscillates at its full period in order to be considered non-trivial"; sparks placed to interact give "a non-trivial oscillator whose period is the least common multiple"
[^3]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.57, Fig. 3.10 - "A pentadecathlon strategically placed next to a snacker makes a non-trivial period 45 oscillator, since the two cells shown in green on the right are only alive 1 generation out of every 45"
[^4]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.58-61 [synthesis] - domino spark; pipsquirters produce "a domino spark that points perpendicular to the oscillator's nearest edge"; dot spark (mold, middleweight spaceship); "two dot sparks cannot give the three live neighbors required"; emulators, volcanoes, supervolcanoes; finger and thumb sparks; duoplet (twin bees shuttle); banana spark (buckaroo)
[^5]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.61, Fig. 3.17 - "Duoplet and banana sparks can be used to reflect gliders by 90 degrees"
[^6]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.61 - "Not only is it the smallest known period 3 oscillator, but its spark is used in the construction of what are currently the smallest known oscillators of period 21, 24, 33 ..., 39, 66, and 93"
[^7]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.58, n.6 - "Billiard tables are a notable exception, which makes them somewhat less useful than other oscillators"
