---
title: Block
category: Patterns
summary: The 2 × 2 square still life, the smallest stable Life pattern; it has many parents, so it is among the commonest objects in ash, and it eats beehives and other debris, making it the standard stabilizer
tags: [pattern, life, still-life, block, eater]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life]
created: 2026-09-25
updated: 2026-09-25
---

# Block

## Description

The block is a two-by-two square of live cells, a [[still-life](pages/still-life.md)].[^1]
It is among the objects that appear most often in the ash of random soups, partly because
it has so many parents: the pre-block, the grin, and several unnamed small patterns all
become a block in one generation.[^2] Four blocks together form the blockade
([[familiar-fours](pages/familiar-fours.md)]).

**As a stabilizer.** A block placed next to a [[beehive](pages/beehive.md)] destroys it
in 7 generations and survives unharmed. That reaction turns the
[[queen-bee](pages/queen-bee.md)] into a period-30 shuttle. Pairs of blocks eat the
debris of [[twin-bees](pages/twin-bees.md)] in 5 generations, and blocks stabilize both
the [[gosper-glider-gun](pages/gosper-glider-gun.md)] and the twin bees gun.[^3] A block
placed next to a [[switch-engine](pages/switch-engine.md)] can turn it into a puffer.[^4]

**Block-laying.** The block-laying switch engine lays 8 blocks every 288 generations.[^4]
Gliders colliding in pairs can also leave blocks.[^5]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - parents, eating reactions, stabilizations
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - name; glider collisions that leave blocks

## Related Concepts

- [[still-life](pages/still-life.md)] - its class
- [[beehive](pages/beehive.md)] - the other common small still life, and what the block eats
- [[queen-bee](pages/queen-bee.md)] - stabilized by blocks
- [[garden-of-eden](pages/garden-of-eden.md)] - the block and pre-block drive the existence proof

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.4 - "a stable 'block' (two-by-two square)"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7,19 [synthesis] - the block among objects that "frequently appear in the ash"; "Some patterns, such as the block, have numerous parents ..., which is part of the reason why they appear so frequently"; Fig. 1.32: "the block, pre-block, and grin" and three unnamed parents
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.10-13 [synthesis] - "a block being placed next to a beehive results in the beehive being destroyed and the block surviving unharmed"; queen bee shuttle; two blocks destroy twin bees debris in 5 generations; Gosper glider gun "by bouncing two queen bees back and forth between two blocks"; twin bees gun with "two stabilizing pairs of blocks"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.14 [synthesis] - "if we place a block next to a switch engine ... it evolves into ... the block-laying switch engine"; "8 blocks every 288 generations"
[^5]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "Then the gliders crash in pairs to become eight blocks"
