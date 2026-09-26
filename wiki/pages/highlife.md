---
title: HighLife
category: Rules
summary: The Life-like rule B36/S23 - Life plus birth on six neighbours - famous for a small replicator that copies itself every 12 generations, so the replicator count after n cycles is 2 to the number of 1 bits in n; meta-fied into Life it gave a replicator in B3/S23
tags: [rule, life-like, highlife, b36-s23, replicator]
sources: [eppstein-2010-growth-and-decay-in-life-like-ca, cgol-ch12-0e0p-metacell]
created: 2026-09-25
updated: 2026-09-26
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

**Building with the replicator.** Most of HighLife's patterns behave as in Life, since it
differs only in the rare case of a dead cell with six neighbours, but the replicator
adds a technology Life lacks.[^3]
- Rows of replicators capped by oscillators or blocks give oscillators of arbitrarily
  large period.
- A replicator and a blinker make the *bomber*, a c/6 diagonal spaceship: one copy of the
  replicator moves forward while the other destroys the blinker and rebuilds it further on.
- Bombers and replicators combine into puffers and rakes, and replicator oscillators into
  guns of any period, including a rake gun whose gliders fill a quarter of the plane with
  quadratic growth.
- Timed replicators can push a blinker forward, which with the bomber's pull suggests
  spaceships of arbitrarily slow speed.

**Fertile, mortal, and Life-like from random starts.** HighLife is fertile and mortal, and
like Life its random fields settle into still lifes and small oscillators because
replicators cannot get through the debris. Eppstein puts it in the same Wolfram class as
Life, II or IV, and uses it as evidence that engineering tracks fertility and mortality
better than the random-start class ([[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)]).[^4]

**Imported into Life.** Twelve 0E0P [[metacell](pages/metacell.md)]s programmed with
HighLife's rule, arranged like the replicator's cells, give a replicator that runs in
B3/S23 itself.[^5]

## Appearances in Sources

- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - the rule, the replicator, its meta-fied version
- [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] - bombers, replicator oscillators, guns and rakes; fertile and mortal

## Related Concepts

- [[replicator](pages/replicator.md)] - its most famous pattern
- [[rule-90](pages/rule-90.md)] - the same 2^(number of 1 bits) count from a single seed
- [[game-of-life](pages/game-of-life.md)] - differs only by B6
- [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)] - a fertile, mortal rule
- [[metacell](pages/metacell.md)] - imports its replicator into Life

[^1]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.386 - "the cellular automaton that has all the same rules as Life, plus the additional rule that a dead cell comes to life if it has exactly 6 live neighbors (i.e., the Life-like cellular automaton with rulestring B36/S23). This cellular automaton is called HighLife"
[^2]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.386 [synthesis] - Fig. 12.2 "A replicator in the HighLife (B36/S23) Life-like cellular automaton that duplicates itself every 12 generations. Found by Nathan Thompson in February 1994"; copies at the same spot "mutually annihilate"; "after n replication cycles (i.e., at generation 12n), the number of replicators is exactly 2^B(n), where B(n) is the binary weight of n"; in Life "it merely degenerates into a configuration of eight blinkers"
[^3]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.14-16 [synthesis] - "it differs from Life only in the comparatively rare case of a dead cell with six live neighbors"; capped rows give "oscillators of arbitrarily large periods"; "A single replicator together with a blinker oscillator produces the bomber, a c/6 diagonal spaceship"; puffers and rakes; guns "of arbitrarily high period"; Fig. 9 rake gun "filling a quarter of the plane with a quadratically growing number of live cells"; Hickerson's blinker push and "very large spaceships that move at arbitrarily slow speeds"
[^4]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.14,16 [synthesis] - HighLife among the fertile-and-mortal rules; "random fields in HighLife seem to eventually settle down to still lifes and small oscillators: the replicators cannot make progress through the other patterns that surround them. Thus, HighLife should probably be assigned the same Wolfram class as Life, either Class II or Class IV"
[^5]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.386-387 [synthesis] - "programming the 0E0P metacell to emulate HighLife and then arranging 12 copies of that metacell in the same formation as the 12 cells that make up the replicator"; Fig. 12.3 "A replicator in Conway's Game of Life that is made up of twelve 0E0P metacells"
