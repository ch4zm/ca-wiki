---
title: Block
category: Patterns
summary: The 2 × 2 square still life, the smallest stable Life pattern; it has many parents, so it is among the commonest objects in ash, and it eats beehives and other debris, making it the standard stabilizer
tags: [pattern, life, still-life, block, eater]
sources: [cgol-ch2-still-lifes, cgol-ch1-early-life, fantastic-combinations-of-john-conways-life]
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

**Smallest eater.** The block is the smallest [[eater](pages/eater.md)]: it eats a beehive or a loaf.
It cannot eat a single glider, but in the *(2,1) block pull* a glider is destroyed while
moving the block 2 cells one way and 1 the other, and a second glider from the opposite
direction moves it back. Moving blocks with gliders is a basic construction tool.[^5]
It is also the densest still life in a 2 × 2 box, and blocks and snakes serve as
induction coils that stabilize rows of cells ([[still-life-density](pages/still-life-density.md)],
[[still-life](pages/still-life.md)]).[^6]

**Block-laying.** The block-laying switch engine lays 8 blocks every 288 generations.[^4]
Gliders colliding in pairs can also leave blocks.[^7]

## Appearances in Sources

- [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] - smallest eater, (2,1) block pull, induction coils, densest 2 × 2 still life
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - parents, eating reactions, stabilizations
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - name; glider collisions that leave blocks

## Related Concepts

- [[eater](pages/eater.md)] - the block is the smallest one
- [[still-life](pages/still-life.md)] - its class
- [[beehive](pages/beehive.md)] - the other common small still life, and what the block eats
- [[queen-bee](pages/queen-bee.md)] - stabilized by blocks
- [[garden-of-eden](pages/garden-of-eden.md)] - the block and pre-block drive the existence proof

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.4 - "a stable 'block' (two-by-two square)"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7,19 [synthesis] - the block among objects that "frequently appear in the ash"; "Some patterns, such as the block, have numerous parents ..., which is part of the reason why they appear so frequently"; Fig. 1.32: "the block, pre-block, and grin" and three unnamed parents
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.10-13 [synthesis] - "a block being placed next to a beehive results in the beehive being destroyed and the block surviving unharmed"; queen bee shuttle; two blocks destroy twin bees debris in 5 generations; Gosper glider gun "by bouncing two queen bees back and forth between two blocks"; twin bees gun with "two stabilizing pairs of blocks"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.14 [synthesis] - "if we place a block next to a switch engine ... it evolves into ... the block-laying switch engine"; "8 blocks every 288 generations"
[^5]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.41 [synthesis] - "a block is the smallest eater of all, as it can be used to eat a beehive (and for that matter, it can also eat a loaf)"; "the (2,1) block pull reaction ..., in which a glider is destroyed while moving a block by 2 cells horizontally and 1 cell vertically. A second glider coming from the opposite direction then moves the block back"; "the general idea of using gliders to move blocks around the Life plane is a very useful one"
[^6]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.39,47 [synthesis] - "Blocks and snakes are useful because they can be placed next to each other with gaps of 1 or 2 dead cells between them, to stabilize rows of connected cells of any length"; Table 2.2: block is the densest still life for n = 2
[^7]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "Then the gliders crash in pairs to become eight blocks"
