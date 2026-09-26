---
title: Eater
category: Patterns
summary: A still life that destroys a glider or other object hitting it in the right place and recovers undamaged; eater 1 (7 cells, recovery time 4, the fastest possible) is the standard, with eater 2, eater 3, eater 5, the boat-bit and the block pull for special cases, and welding to merge eaters into tight spaces
tags: [pattern, life, eater, eater-1, still-life, glider, welding, stabilizer]
sources: [cgol-ch2-still-lifes, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Eater

## Description

An eater is an object, almost always a [[still-life](pages/still-life.md)], such that a
[[glider](pages/glider.md)] or other object hitting it the right way is deleted while the
eater suffers no permanent damage. Constructions that send gliders around need to create,
move and delete them, and eaters handle deletion.[^1] The *recovery time* is how many
generations the eater takes to return to its original state.[^2]

**Eater 1** (also called the fishhook) is the smallest, first discovered and most widely
used glider eater. It has 7 cells and a recovery time of 4 generations, the fastest
possible for any glider eater; computer searches show no still life can eat a glider and
recover in 3. Other eaters tie it at 4.[^2] Only its 3-cell corner, a pre-block, takes part
in eating; its tail just stabilizes that corner.[^3] It also eats the lightweight and
middleweight spaceships, blinkers, pre-beehives and much other debris hitting that corner,
which makes it a general-purpose stabilizer. It can stabilize a
[[queen-bee](pages/queen-bee.md)], for example.[^4] It was found early as the smallest
asymmetric still life; Bill Gosper's group at MIT found its eating properties in 1971.[^5]

**Other eaters.**[^6]
- **Eater 2** is larger and recovers in 5 generations. It is symmetric and eats gliders on
  4 different parallel paths.
- **Eater 5** (tub with tail eater, TWIT) is small, recovers in 6 generations, and is made
  of two still lifes. It eats gliders on 2 perpendicular paths and can eat a glider passing
  very close to its edge, so it fits in tight places.
- **Eater 3** is built on a loaf: one glider flips a loaf over, and a stabilizing object
  beside it flips it back.

**Rocks and near-eaters.** A *rock* eats without even temporary damage. No rock is known
that eats gliders, but some objects act as rocks for pairs of gliders.[^7]
- **Boat-bit.** A snake, or any still life with a pre-block, turns one glider into a boat,
  which a second glider on the same path then destroys, and the snake is never disturbed.
  At 6 cells it is the smallest known way to erase a glider stream, and it can store one
  bit of memory.
- **Loaf flip.** A loaf alone can eat two gliders from opposite directions by flipping
  twice.
- **(2,1) block pull.** A glider hitting a [[block](pages/block.md)] is destroyed and moves
  the block 2 cells one way and 1 the other, and an opposite glider moves it back.
  The block is also the smallest eater of all, eating a beehive or a loaf.

**Welding.** Two eaters placed too close together interfere and stop being stable.
*Welding* merges still lifes into one still life that keeps each part's function. For two
eater 1s, keep both pre-blocks and replace the two tails with one stabilizing piece,
found by the still-life grammar, trial and error, or computer search. Welding lets large
constructions pack components tightly and fit eaters into restricted regions. One example
is an eater 5 reshaped to live inside a given box: its tub becomes a boat, and extra cells
overpopulate the cells that would otherwise be born.[^8]

## Appearances in Sources

- [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] - §2.3 eaters, rocks, boat-bit, block pull; §2.4 welding and constrained eaters
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - blocks eating beehives; eater 1 stabilizing a queen bee

## Related Concepts

- [[still-life](pages/still-life.md)] - the class eaters belong to
- [[glider](pages/glider.md)] - the main thing they eat
- [[block](pages/block.md)] - the smallest eater
- [[queen-bee](pages/queen-bee.md)] - stabilized by eaters

[^1]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.39 [synthesis] - "we will need simple ways of creating, moving, and deleting gliders"; eaters are "still lifes with the property that if a glider (or another object) collides with them in the right away, the glider is deleted and the eater suffers no permanent damage"; n.11 an eater need not be a still life
[^2]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.39 [synthesis] - "The smallest, first discovered, and most widely used glider eater is the 7-cell still life called eater 1"; "a recovery time of 4 generations, which is the fastest possible for any glider eater"; n.13 other eaters tie it; "no still life can completely eat a glider and recover in only 3 generations"; p.33 Fig. 2.1 "eater 1 (which is sometimes called fishhook)"
[^3]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.42 - "the only part of eater 1 that is actually involved in the glider eating reaction ... is its pre-block (i.e., the 3-cell corner at its top-left)--its tail is just there to stabilize the pre-block"
[^4]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.39-40 [synthesis] - "eater 1 can also be used to eat lightweight spaceships, middleweight spaceships, blinkers, and numerous other objects"; Fig. 2.15 pre-beehive; "extremely useful not just as an eater, but also as a stabilizer"; used to stabilize a queen bee (Ex. 1.10)
[^5]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.39, n.12 - "Eater 1 itself was almost immediately discovered independently by several Life enthusiasts as the smallest asymmetric still life, but its eating properties were discovered by Bill Gosper's group at MIT in 1971"
[^6]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.40-41 [synthesis] - eater 2: recovery 5, symmetric, "4 different parallel paths"; eater 5 "(sometimes called the tub with tail eater, or TWIT)", recovery 6, two still lifes, "2 different perpendicular paths", eats gliders close to its edge; eater 3 from the loaf-flipping reaction (Fig. 2.19)
[^7]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.40-42 [synthesis] - "an eater is called a rock if it does not even suffer temporary damage"; "no known rocks that eat gliders"; boat-bit: snake "not even temporarily disturbed", "the smallest known way of erasing such a glider stream (in particular, it contains only 6 cells)", n.15 stores a bit; loaf eats two gliders; "a block is the smallest eater of all, as it can be used to eat a beehive (and ... a loaf)"; (2,1) block pull (Fig. 2.20)
[^8]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.42-44 [synthesis] - two eater 1s too close "will no longer be stable"; welding "combine multiple still lifes into a single still life that retains the properties of each of its components"; keep pre-blocks, replace tails; reasons: restricted space and tight packing; eater 5 adapted to a region by changing the tub to a boat and overpopulating two cells (Figs. 2.23-2.24)
