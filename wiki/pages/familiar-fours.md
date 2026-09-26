---
title: Familiar fours
category: Patterns
summary: The five common ash formations of four identical objects - traffic light (4 blinkers), honey farm (4 beehives), blockade (4 blocks), fleet and bakery - and the unstable objects whose explosions produce them
tags: [pattern, life, constellation, traffic-light, honey-farm, blockade, fleet, bakery, ash]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life]
created: 2026-09-25
updated: 2026-09-25
---

# Familiar fours

## Description

The *familiar fours* are five formations of four simple objects that commonly occur in
ash: the traffic light, the honey farm, the blockade, the fleet and the bakery.[^1] Each
is common because a small unstable object that appears often in soups explodes
symmetrically into it. Life's rules ignore orientation, so symmetry once formed is never
broken.[^2]

- **Traffic light**: four [[blinker](pages/blinker.md)]s. The T-tetromino becomes one in
  9 generations; this explosion is why blinkers so often appear in that formation.[^3]
- **Honey farm**: four [[beehive](pages/beehive.md)]s, stable as a group. A seven-cell
  pre-honey farm becomes one in 17 generations.[^4] A horizontal row of seven cells also
  becomes one, in 14 generations.[^5]
- **Blockade**: four [[block](pages/block.md)]s. The stairstep hexomino becomes one in 63
  generations. The explosion and its intermediate stages are called *lumps of muck*.
  Because it is larger and slower to form, the blockade is less common in ash.[^6]
- **Fleet** and **bakery**: the other two. The 13-cell methuselah Lidka produces a fleet
  during its evolution.[^1]

A related messy explosion is the **pi-heptomino**, extremely common in soups. It settles
into 6 blocks, 5 blinkers and 2 ponds, and along the way moves forward 9 cells in 30
generations while leaving debris. Combined with objects that clear the debris, it can
carry a signal or act like a spaceship.[^7]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - §1.2: common evolutionary sequences; Ex. 1.8
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - the honey farm from a row of seven

## Related Concepts

- [[blinker](pages/blinker.md)], [[beehive](pages/beehive.md)], [[block](pages/block.md)] - their components
- [[soup-search](pages/soup-search.md)] - where these formations are seen
- [[r-pentomino](pages/r-pentomino.md)] - all of these unstable objects appear in its evolution

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.29, Ex. 1.8 - "There are 5 formations of 4 simple objects that commonly occur in ash: the traffic light, honey farm, and blockade that we saw in Section 1.2, and the fleet and bakery ... These arrangements are collectively called the familiar fours"; "(a) Evolve Lidka until you see a fleet"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.8 - "Since Life's rules do not care about the orientation of patterns, symmetry can never be broken once it has formed"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.8 - the T-tetromino "explodes into an arrangement of 4 blinkers that is called a traffic light"; "the common T-tetromino explosion is exactly why blinkers appear in this formation so frequently"; Fig. 1.11: 9 generations
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.9 - "explodes over the course of 17 generations in order to create a commonly occurring arrangement of 4 beehives called a honey farm. Appropriately enough, the 7-cell object that starts this evolution is called the pre-honey farm"
[^5]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "The stable honey farm ... results after 14 moves from a horizontal row of seven counters"
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.9 [synthesis] - "the stairstep hexomino ... takes 63 generations to stabilize into an arrangement of four blocks called the blockade"; "less commonly seen in ash"; "this evolutionary sequence, and any of the patterns that appear during its 63-generation explosion, are given a common name: lumps of muck"
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.9-10 [synthesis] - "the extremely common and extremely messy pi-heptomino"; "6 blocks, 5 blinkers, and 2 ponds"; "moves forward by 9 cells after 30 generations, while leaving behind some messy debris"; with debris removed it can "transmit a signal from one place in the Life plane to another or act like a spaceship"
