---
title: Hassler
category: Patterns
summary: An oscillator (or gun) in which surrounding objects repeatedly move or change a central object, typically an unstable standard sequence - pre-honey farm, pi-heptomino, T-tetromino, pre-pulsar - or even still lifes; a shuttle is a hassler that moves its object back and forth, and mixing shuttling reactions gives many periods
tags: [pattern-class, life, hassler, shuttle, oscillator, pre-pulsar, t-tetromino]
sources: [cgol-ch3-oscillators, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Hassler

## Description

One pattern *hassles* another when it repeatedly moves or changes it, usually
periodically, to make an [[oscillator](pages/oscillator.md)] or gun. An oscillator built
this way is a *hassler*. A hassler that moves its object back and forth between two
positions is a *shuttle*, like the [[queen-bee](pages/queen-bee.md)] shuttle.[^1] Many
eater-stabilized oscillators turn out to be hasslers of standard unstable sequences:
dinner table bounces a pre-beehive, honey thieves a pre-honey farm.[^2]

**What gets hassled.**[^3]
- **Pre-honey farms**: among the most effective, usually found by computer searches
  that try honey-farm placements among small still lifes and
  [[sparker](pages/sparker.md)]s. Examples have periods 16, 17, 18, 21 and 32.
- **Pi-heptominoes**: rotated 90 degrees by some still-life formations, or re-formed
  elsewhere by taming their debris. Examples are the gourmet (p32), a p37, and Tanner's
  p46, which is very sparky and shares the [[twin-bees](pages/twin-bees.md)] shuttle's
  period.
- **Still lifes**: sparks can make still lifes explode and re-form. A dot spark hassles
  two ponds and two blocks, which take 20 generations to recover, so the reaction doubles
  or triples a sparker's period. David Hilbert (p23), the first period-23 oscillator,
  hassles two B-heptominoes that shuttle a beehive.

**Shuttles and mixing reactions.** Shuttle reactions can be mixed as long as each
offsets the central object by the same distance. The period is then the sum of the
reaction times.[^4]
- **T-tetromino.** Usually hassled by sparkers. A dot spark moves it 2 cells and mirrors
  it in 11 generations; three dot sparks do the same in 9. Together they make a period-20
  shuttle.
- **Pre-pulsar.** Two T-tetrominoes side by side form a *pre-pulsar*, which copies itself
  in 15 generations and left alone becomes a [[pulsar](pages/pulsar.md)]. That is why
  pulsars are common in soup.[^5] Pre-pulsar pushers move it 3 cells in 12, 14 or 15
  generations, giving shuttles of period 26, 29 and 30 (eureka).
- **Constraints.** Not every sum works. Two 12-generation pushers cannot be tied off at
  the ends, two 14s interfere, and 12 + 15 = 27 fails because the 12-generation reaction
  needs a period-2 beacon, and 2 does not divide 27.[^6]

## Appearances in Sources

- [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] - §3.4: hasslers and shuttles
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - the queen bee and twin bees shuttles

## Related Concepts

- [[oscillator](pages/oscillator.md)] - the class
- [[sparker](pages/sparker.md)] - sparks do much of the hassling
- [[queen-bee](pages/queen-bee.md)], [[twin-bees](pages/twin-bees.md)] - the first shuttles
- [[familiar-fours](pages/familiar-fours.md)] - the unstable objects commonly hassled

[^1]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.61 - "we say that one pattern hassles another one if it repeatedly moves or changes it, typically in a periodic way so as to create an oscillator or gun. Oscillators created in this way are called hasslers. In the special case when a hassler moves an object back and forth between two positions (such as the queen bee shuttle from Section 1.3), it is called a shuttle"
[^2]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.61 - "the dinner table ... bounces around a pre-beehive, the honey thieves ... bounce around a pre-honey farm"
[^3]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.62-63 [synthesis] - pre-honey farm hasslers of periods 16, 18, 21, 32 (Fig. 3.18) and honey thieves p17; "more commonly found via computer searches"; pi-heptomino hasslers: gourmet (p32), p37, Tanner's p46 "particularly useful due to how sparky it is and the fact that it has the same period (46) as the twin bees shuttle"; still-life hassler taking 20 generations "can be used to double the period of a sparker with period 10-19 or triple the period of a sparker with period 7-9"; David Hilbert (n.9: "the first p23 oscillator found")
[^4]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.63-64 [synthesis] - "T-tetrominoes are typically hassled by oscillators (sparkers in particular)"; dot spark moves it 2 cells in 11 generations; three dot sparks in 9; "we can mix-and-match different shuttling reactions, as long as the distances that they offset the central object ... are the same"; 11 + 9 = 20
[^5]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.64 - "place two T-tetrominoes next to each other, creating a pattern called a pre-pulsar ... if left alone, it evolves into a pulsar ... (in fact, this small arrangement of two T-tetrominoes is exactly why pulsars occur so frequently in random soups)"; "it duplicates itself over the course of 15 generations"
[^6]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.65 [synthesis] - pre-pulsar pushers in 12, 14 or 15 generations; shuttles of periods 26, 29, 30 (eureka, David Buckingham 1980); 12 + 12 has "no known way of tying off the ends"; 14 + 14 hasslers "interfere"; 12 + 15 fails because "the 12-generation reaction depends on the beacon, which has period 2"
