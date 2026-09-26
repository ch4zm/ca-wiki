---
title: HighLife
category: Rules
summary: The Life-like rule B36/S23 - Life plus birth on six neighbours - famous for a small replicator that copies itself every 12 generations, so the replicator count after n cycles is 2 to the number of 1 bits in n; meta-fied into Life it gave a replicator in B3/S23
tags: [rule, life-like, highlife, b36-s23, replicator]
sources: [cgol-ch12-0e0p-metacell]
created: 2026-09-25
updated: 2026-09-25
---

# HighLife

## Description

HighLife is the [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]
with rulestring **B36/S23**: all of [[game-of-life](pages/game-of-life.md)]'s rules,
plus birth for a dead cell with exactly six live neighbours.[^1]

**The replicator.** HighLife has a simple [[replicator](pages/replicator.md)]: a 12-cell
pattern that duplicates itself every 12 generations (Nathan Thompson, 1994).[^2]
- Each copy tries to replicate again. Copies that would land on the same spot at the same
  time annihilate, while the outer copies survive.
- So after n cycles (generation 12n) there are exactly 2^B(n) replicators, where B(n) is
  the number of 1 bits in n's binary representation.
- In Life the same 12 cells just decay into eight blinkers, since the six-neighbour birth
  is missing.

**Imported into Life.** Twelve 0E0P [[metacell](pages/metacell.md)]s programmed with
HighLife's rule, arranged like the replicator's cells, give a replicator that runs in
B3/S23 itself.[^3]

## Appearances in Sources

- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - the rule, the replicator, its meta-fied version

## Related Concepts

- [[replicator](pages/replicator.md)] - its most famous pattern
- [[game-of-life](pages/game-of-life.md)] - differs only by B6
- [[metacell](pages/metacell.md)] - imports its replicator into Life

[^1]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.386 - "the cellular automaton that has all the same rules as Life, plus the additional rule that a dead cell comes to life if it has exactly 6 live neighbors (i.e., the Life-like cellular automaton with rulestring B36/S23). This cellular automaton is called HighLife"
[^2]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.386 [synthesis] - Fig. 12.2 "A replicator in the HighLife (B36/S23) Life-like cellular automaton that duplicates itself every 12 generations. Found by Nathan Thompson in February 1994"; copies at the same spot "mutually annihilate"; "after n replication cycles (i.e., at generation 12n), the number of replicators is exactly 2^B(n), where B(n) is the binary weight of n"; in Life "it merely degenerates into a configuration of eight blinkers"
[^3]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.386-387 [synthesis] - "programming the 0E0P metacell to emulate HighLife and then arranging 12 copies of that metacell in the same formation as the 12 cells that make up the replicator"; Fig. 12.3 "A replicator in Conway's Game of Life that is made up of twelve 0E0P metacells"
