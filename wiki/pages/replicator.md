---
title: Replicator
category: Patterns
summary: A pattern that produces copies of itself - elementary replicators exist in a few dozen Life-like rules (HighLife's 12-cell replicator, the replicator rule B1357/S1357 where every pattern replicates in 8 directions, a single cell filling the plane in B12345678/S012345678); in Life itself replicators exist only as huge constructions, such as meta-fied HighLife replicators
tags: [pattern-class, replicator, self-reproduction, highlife, life-like, metacell]
sources: [eppstein-2010-growth-and-decay-in-life-like-ca, cgol-ch12-0e0p-metacell, lifewiki-unit-cell]
created: 2026-09-25
updated: 2026-09-25
---

# Replicator

## Description

A *replicator* is a pattern that produces arbitrarily many copies of itself.[^1] It is
the cellular-automaton form of [[self-reproduction](pages/self-reproduction.md)], but
small replicators do it through the rule's own dynamics, with no constructor or
description tape.

**Elementary replicators in Life-like rules.** Replicators of various shapes and speeds
are known in a few dozen [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]
rules; David Eppstein keeps a partial list.[^2]
- **[[highlife](pages/highlife.md)] (B36/S23).** A 12-cell replicator copies itself along a
  line every 12 generations. Colliding copies annihilate, so the count after n cycles is
  2^(number of 1 bits in n).[^3]
- **Replicator rule (B1357/S1357).** Every pattern is a replicator, copying itself in all
  eight orthogonal and diagonal directions.[^4]
- These two replicate in a sawtooth fashion: whenever two copies would be made in the same
  place they destroy each other, so the population keeps reaching new highs and then
  dropping back.[^4]
- **B12345678/S012345678.** A cell is born with any live neighbour and never dies, so a
  single cell fills the plane, repeatedly birthing all of its neighbours.[^5]
- Other growth modes are rarer. B34568/S15678 has a spiral-growth pattern (Dean
  Hickerson, 2006).[^5]

**Why replicators matter.** In Eppstein's survey replicators are the most productive
single ingredient outside Life: rows of them capped at both ends make oscillators of any
period, and combinations give guns, puffers, rakes and slow spaceships.[^6]
- **B36/S245** (Mark Niemiec). The replicator starts as a pair of 12-cell D-shaped
  *shuttles* that lay period-4 "eggs"; a shuttle meeting an egg hatches a new replicator.
  Dean Hickerson built puffers from them, and from those spaceships of speed 14c/300 and
  28c/1200.[^7]
- **B368/S12578.** A 1 × 5 line of cells copies itself every 13 steps, enough for
  oscillators of any period and guns for a small c/8 spaceship.[^7]
- **B25/S4.** A photon bounced between two period-3 replicators wanders in a
  pseudorandom walk, its typical distance from the start growing like the square root of
  the step count; HighLife can stage the same tug of war with its bomber.[^8]
- **B0 rules.** Rules that flash their background also replicate: B017/S1 has
  replicators of periods 8 and 14, B01367/S0124 one whose copies turn at right angles, and
  B02346/S023 one made of two cells a knight's move apart.[^9]
- **Fredkin's parity rule B1357/S1357.** A cell is alive exactly when the number of ways
  a chess king can walk to it from the initial live cells, in the given number of steps,
  is odd. At step multiples of a large enough power of 2 the pattern is copies of itself
  laid out like the single-cell pattern. Every pattern replicates and nothing else happens,
  and a random start stays random.[^10]

**In Life.** The replicators constructed in B3/S23 are huge: first a linear propagator, then a HighLife replicator meta-fied from
twelve 0E0P [[metacell](pages/metacell.md)]s. The 0E0P is itself self-reproducing in a
sense, since every metacell builds its neighbours.[^11]

**Replicators as 1D automata.** A replicator that copies itself along a line is running a
one-dimensional cellular automaton, with each copy site as one cell. HighLife's replicator
runs Rule 6, or [[rule-90](pages/rule-90.md)] if read at period 24; the 2^(number of 1
bits) count above is the number of live cells in row n of Rule 90's Sierpinski triangle (own reasoning). The U-pentomino and
T-tetromino are replicators that emulate [[rule-110](pages/rule-110.md)] in ranges of
isotropic non-totalistic rules, so a small natural pattern there carries a universal 1D
rule ([[metacell](pages/metacell.md)]).[^12]

## Appearances in Sources

- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - §12.1.1: replicators in Life-like rules and their import into Life
- [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] - replicators that emulate 1D rules
- [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] - replicators in B36/S245, B368/S12578, B25/S4, B0 rules and the parity rule

## Related Concepts

- [[highlife](pages/highlife.md)] - the best-known replicator rule
- [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)] - the parity rule is fertile but immortal
- [[self-reproduction](pages/self-reproduction.md)] - von Neumann's constructor-based version
- [[universal-constructor](pages/universal-constructor.md)] - the machinery Life's replicators need
- [[metacell](pages/metacell.md)] - carries replicators from other rules into Life
- [[rule-90](pages/rule-90.md)], [[rule-110](pages/rule-110.md)] - 1D rules that replicators emulate

[^1]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.386 - "a simple replicator: a pattern that produces arbitrarily many copies of itself"
[^2]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.388 - "elementary replicators of various shapes and speeds are known in a few dozen different Life-like cellular automata"; n.5 www.ics.uci.edu/~eppstein/ca/replicators/index.html "for a partial list"
[^3]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.386 [synthesis] - HighLife replicator duplicates "every 12 generations"; the number of replicators after n cycles "is exactly 2^B(n), where B(n) is the binary weight of n"
[^4]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.388 [synthesis] - "in the appropriately named replicator rule (B1357/S1357), every pattern is a replicator that repeatedly produces copies of itself in all 8 orthogonal and diagonal directions"; "replicate in a sawtooth-like fashion--whenever two copies would be created in the same place, they cleanly destroy each other instead, so their populations repeatedly reach new heights and then jump back down"
[^5]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.388 [synthesis] - "the rule B12345678/S012345678 in which a cell is born if it ever has at least one live neighbor, and then lives forever. In this rule, a single cell acts as a replicator"; Fig. 12.6 spiral growth in B34568/S15678 (Dean Hickerson, June 2006)
[^6]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.14-16 [synthesis] - HighLife: "Rows of replicators can be capped by oscillators or blocks, producing oscillators of arbitrarily large periods"; the bomber; "Combinations of bombers and replicators can produce puffers and rakes"; guns "of arbitrarily high period"
[^7]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.16 [synthesis] - B368/S12578 replicator "in the form of a 1× 5 block of cells; it copies itself every 13 time steps", guns "for a small c/8 diagonal spaceship"; B36/S245 found by Mark Niemiec, "a pair of 'shuttles', sets of twelve live cells with a 3 × 6 bounding box, in the shape of a capital letter D", "eggs" (period 4 oscillators); Hickerson's puffers and "large spaceships that move at speed 14c/300 and 28c/1200"
[^8]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.22 - "Placing a photon between two appropriately spaced replicators ... leads to a pattern in which the photon repeatedly bounces back and forth ... following a pseudorandom walk in which the typical distance of the photon from its starting point at step n appears to be proportional to √n"; "a similar system can be set up in HighLife: the bomber reaction allows two sets of replicators to play tug of war with a blinker"
[^9]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.26-27 [synthesis] - "B017/S1 supports two different replicators, with periods 8 and 14"; B01367/S0124 "the two copies formed from this replicator are turned at right angles"; B02346/S023 "very tiny replicators consisting of two live cells a knight's move apart"
[^10]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.23 - "Cell (x, y) is alive at step i if and only if the number of ways that a chess king could take i steps to walk from an initially-live cell to (x, y) is odd"; "in this rule there is nothing but replicators. If a starting state has all cells set to live or dead uniformly and independently at random, then the same is true at each subsequent step"
[^11]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.385-387 [synthesis] - "a self-reproducing pattern that interacts with nearby copies of itself"; the meta-fied HighLife replicator "is not the first replicator to be constructed in Life (that honor goes to the linear propagator ...)"
[^12]: [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] L22-24 [synthesis] - "Parity rule replicators can be described as simulating a one-dimensional cellular automaton. For example, the replicator in HighLife can be described as simulating Rule 6 ... If considered as being period 24 rather than period 12, it could be considered as following Rule 90"; "the U-pentomino is a period-8 natural replicator that emulates Rule 110"; the T-tetromino "with period 2"
