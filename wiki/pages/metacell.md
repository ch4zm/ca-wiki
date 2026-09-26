---
title: Metacell
category: Patterns
summary: A large Life pattern (also called a unit cell) that behaves as a single cell of some cellular automaton, so tiled copies emulate that rule at a huge scale - the p5760 metacell (Life only), the OTCA metapixel (any Life-like rule), the p1 megacell (any 2-state Moore rule) and the self-constructing 0E0P metacell (any such rule where empty stays empty, with empty space as its off state); unit cells that emulate Rule 110 are the standard proof that a rule is Turing-complete
tags: [pattern-class, life, metacell, 0e0p, otca-metapixel, rule-emulation, universal-construction, self-reproduction]
sources: [cgol-ch12-0e0p-metacell, lifewiki-unit-cell, lifewiki-wireworld]
created: 2026-09-25
updated: 2026-09-25
---

# Metacell

## Description

A *metacell* is a pattern larger than 1 × 1 that emulates the behaviour of a single
cell. Arranged in the shape of any pattern, copies of it evolve at a zoomed-out scale
the way that pattern would.[^1] A metacell that can be programmed with a rule makes Life a
host for other [[cellular-automaton](pages/cellular-automaton.md)]s: patterns from those
rules can be "meta-fied" into Life patterns. Scripts such as isotropic_metafier.py and
Golly's metafier.lua do this automatically.[^2]

**Unit cells.** LifeWiki's general name is *unit cell*: a finite tile, usually a
rectangle, together with a fixed set of patterns it can hold, such that the tiled plane
emulates some cellular automaton, possibly the host rule itself. A unit Life cell emulates
Life. Single cells do not count (the tile must be bigger than 1 × 1), and neither do
infinite structures such as HighLife's one-cell-thick bars that emulate Rule 54.[^3]
Unit cells can also be stacked: Jared James Prince's "deep cell" (2004) modified Bell's
design to hold two, and so any number of, layered Life universes.[^4]

**Lineage.**[^5]

| Metacell | Builder, year | Size | Period | Emulates | Needs dead-cell background? |
|---|---|---|---|---|---|
| p5760 metacell | David Bell, 1996 | 500 × 500 | 5,760 | Life only | yes |
| OTCA metapixel | Brice Due, 2005-2006 | 2048 × 2048 | 35,328 | any of 2^18 Life-like rules | yes |
| p1 megacell | Adam P. Goucher, 2008 | 2^15 × 2^15 | 2^24 | all 2^512 two-state Moore rules | yes |
| 0E0P metacell | Adam P. Goucher, 2014-2018 | 2^18 × 2^18 | 2^36 per generation | the 2^511 zero-preserving two-state Moore rules | no |

- **p5760.** It is hard-wired to Life. Its state is a single glider, hard to see from far
  away. Dead metacells must fill the plane, so a spaceship would need infinitely many.
- **OTCA metapixel.** Named for "Outer-Totalistic Cellular Automata". Its rule is set by an
  array of eaters on one edge. Live metapixels fill with streams of lightweight spaceships,
  so from a distance they *look* alive; a 1 × 3 row makes a blinker 2,048 times larger and
  35,328 times slower. It is built almost entirely from period-46 circuitry.
- **p1 megacell.** Built from stable parts, plus one timing gun whose power-of-two period
  helps HashLife. Up to 512 eaters encode which neighbourhoods give birth. It can even run
  rules where an empty neighbourhood gives birth, if the plane is tiled with dead
  megacells.
- **0E0P.** "State 0 Encoded by 0 Population": a dead cell is empty space. It builds its
  neighbours by universal construction, made possible by single-channel glider synthesis
  (2017).

**The 0E0P's key trick.** It never emulates a Moore-neighbourhood rule directly. Doing so
would mean building up to eight neighbours around live ones, with circuitry reused
across many generations.[^6]
- Instead it runs an **8-state von Neumann-neighbourhood rule in which every cell dies
  every generation**, so every pattern is a [[phoenix](pages/phoenix.md)]. Patterns
  alternate between the two colours of a checkerboard, so a metacell's four diagonal
  neighbours are always empty, leaving room to build.
- Any two-state Moore rule M maps into such a rule at half speed. States 0 and 7 are dead
  and alive in even generations; states 1-6 are helper states in odd generations.
- A fixed table sends each 2 × 2 block of 0s and 7s to a helper state. Because that map is
  one-to-one, the odd-to-even step can recover each 3 × 3 neighbourhood and apply M.
- Emulated at a 45-degree angle, one generation of the 8-state rule takes 2^35
  generations, so one generation of M takes 2^36.

**Anatomy and lifecycle of the 0E0P.**[^7]
- **Shell.** Four symmetric spiral arms that take in a construction recipe from any side.
  Only one arm is used; symmetry ensures a child is built in the same orientation whichever
  parent builds it.
- **Kernel.** Routing to four construction arms and recipe outputs, a control clock gun
  firing every 2^29 generations, and logic that computes the new state from a lookup table.
- **Nucleus.** A boustrophedonic glider loop of period 2^29 holding about 3.6 million
  gliders: a complete single-channel construction recipe for the metacell, plus the
  lookup table for the emulated rule. Its walls hold 2 × 1,024 two-Snark reflectors, built
  by two temporary "subroutine loops" that each repeat one reflector recipe 256 times.
- **Lifecycle.** 64 stages of 2^29 generations:
  - build the four diagonal neighbours and fill their nuclei;
  - empty its own nucleus;
  - send its state as 0 or 2-8 gliders, which the children store as missing blocks;
  - self-destruct.
- **Children.** Each child reads its state from the lookup table by delaying a clock gun
  by an amount set by the parents' states. A child in state 0 then dies early; the rest
  wait, "looking like a cell", before becoming parents.

The 0E0P was deliberately left unoptimized; its authors estimate that removing the waiting
stages alone would make it run four times faster.[^8] At 18.6 million cells it was, when
completed in 2018, the largest interesting Life pattern by population. Simulating a
metaglider through four metagenerations would take years with HashLife and months with
Goucher's StreamLife algorithm.[^9]

**Emulating one-dimensional rules.** A unit cell need not emulate a 2D rule.[^10]
- *Natural cases.* Parity-rule [[replicator](pages/replicator.md)]s are 1D automata in
  disguise. HighLife's replicator ([[highlife](pages/highlife.md)]) runs Rule 6 on a
  half-range 1D neighbourhood; read at period 24 in place of 12 it runs Rule 90
  ([[rule-90](pages/rule-90.md)]), to which it is often, loosely, simplified. About a dozen
  elementary rules are known to arise this way.
- *Rule 110 for free.* The U-pentomino is a period-8 natural replicator that emulates
  [[rule-110](pages/rule-110.md)] across a whole range of isotropic non-totalistic rules,
  and the T-tetromino does the same at period 2 in another range.

**Borrowing universality.** Because Rule 110 is Turing-complete, a unit cell that emulates
it carries that universality into its host. Constructed Rule 110 unit cells are the
standard way to prove a rule Turing-complete, and they exist for Life itself (a
"polyglot" that also works in EightLife, Pedestrian Life and HoneyLife) and for about
fifteen other rules. These include [[highlife](pages/highlife.md)], Day & Night, Life
without Death, [[seeds-rule](pages/seeds-rule.md)] (a Rule 110 "unit stripe"),
[[brians-brain](pages/brians-brain.md)], [[star-wars-rule](pages/star-wars-rule.md)] (by
a cyclical emulator) and the [[larger-than-life](pages/larger-than-life.md)] rule Bosco's
Rule.[^11] A different route to the same end is [[wireworld](pages/wireworld.md)], which is
Turing-complete given an infinite tiling of suitable wires.[^12]

## Appearances in Sources

- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - the whole chapter
- [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] - unit cells in general, 1D emulation, Rule 110 universality proofs
- [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] - the 0E0P's population compared with the caterpillar

## Related Concepts

- [[single-channel-construction](pages/single-channel-construction.md)] - the recipe technique the 0E0P metacell builds with
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)], [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)], [[non-isotropic-rule](pages/non-isotropic-rule.md)] - the rule families it can emulate
- [[replicator](pages/replicator.md)] - HighLife's replicator, meta-fied into Life
- [[universal-constructor](pages/universal-constructor.md)], [[self-reproduction](pages/self-reproduction.md)] - the 0E0P builds copies of itself
- [[reverse-caber-tosser](pages/reverse-caber-tosser.md)] - another single-channel construction
- [[phoenix](pages/phoenix.md)] - every pattern of the emulated 8-state rule is one
- [[rule-110](pages/rule-110.md)] - the 1D rule whose unit cells prove other rules universal

[^1]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.385,422 [synthesis] - "metacells--patterns of size larger than 1 × 1 that emulate the behavior of a single cell"; "if we arrange copies of it on the Life plane then, at a zoomed-out macroscopic scale, it evolves in the same way that the corresponding arrangement of cells would evolve"
[^2]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.386-387,423 [synthesis] - "any pattern from one of those other cellular automata can be straightforwardly 'imported' into Life simply by meta-fying it"; n.3 slsparse's isotropic_metafier.py; n.35 Golly's metafier.lua
[^3]: [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] L6 - "A unit cell (or metacell) is a subset (usually rectangular or square) of the Life plane that tiles over the plane, along with a fixed number of distinct patterns, with each tile assuming one of the patterns, such that it simulates a cellular automaton, possibly itself. ... the size of a unit cell must be greater than 1 × 1. It is also a restriction that only finite sized patterns are accepted as unit cells excluding infinite one-cell thick bars in HighLife for example, which simulates Rule 54"
[^4]: [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] L16 - "In 2004, Jared James Prince modified David Bell's unit Life cell to support two (and therefore multiple) layers of Life universes, coined "deep cell""
[^5]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] §12.9, pp.422-424 [synthesis] - p5760 metacell (Bell, January 1996, 500 × 500, period 5 760; hard-wired to Life, single-glider state, needs a dead background); OTCA metapixel (Due, 2005-2006, 2048 × 2048, period 35 328, any of 2^18 outer-totalistic rules, eater array, LWSS streams look alive, metablinker, mostly p46 circuitry); p1 megacell (Goucher, 2008, 2^15 × 2^15, period 2^24, stable components plus one gun, all 2^512 rules via up to 512 eaters, n.37 can emulate all-dead-births with a tiled background); 0E0P (Goucher, 2014-2018) needs no background; "the advent of single-channel glider synthesis in 2017 provided the key breakthrough"
[^6]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] §12.2, pp.391-393 [synthesis] - quantity of neighbours and survival problems; "an 8-state von-Neumann-neighborhood CA in which every cell dies in every generation"; n.13 "every pattern is a phoenix"; checkerboard keeps diagonal neighbours dead; states 0 and 7 for dead and alive, 1-6 as helpers; Equation (12.2) transition table; the map from {0,7}^9 to {0,...,6}^4 is injective; "It takes 2^35 generations ... and therefore 2^36 generations to emulate one generation of the corresponding 2-state Moore-neighborhood rule"; can run the 8^8 − 1 zero-preserving 8-state rules of this type
[^7]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] §§12.3-12.8, pp.393-421 [synthesis] - shell, kernel and nucleus; control clock gun "sends out a single glider every 2^29 generations"; nucleus "a massive boustrophedonic loop that houses roughly 3.6 million gliders" with walls of 2^10 two-Snark reflectors each; subroutine loops CN and CE repeated 256 times; 64 stages of 2^29 generations; state sent "via a sequence of 0 or 2–8 gliders"; lookup table of 8^4 − 1 = 4 095 chunks; state-0 children self-destruct early
[^8]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.406,408 [synthesis] - n.28 "it could be modified to run 4 times as quickly by removing this wait time"; "The 0E0P metacell could be reduced in size and made to run several times faster with these kinds of optimizations"
[^9]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.385 [synthesis] - evolving the metaglider through four metagenerations "would take a couple of years on a modern desktop computer via standard Life simulation algorithms"; n.2 HashLife; Goucher's StreamLife "would require several months"; [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.112 - the caterpillar "was the largest interesting Life pattern by live cell count until being surpassed in 2018 by the 0E0P metacell with 18.6 million live cells"
[^10]: [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] L22-37 [synthesis] - "the replicator in HighLife can be described as simulating Rule 6 on a range-1/2 one-dimensional neighbourhood. If considered as being period 24 rather than period 12, it could be considered as following Rule 90, to which the replicator's habit is commonly, if erroneously, simplified to"; "the U-pentomino is a period-8 natural replicator that emulates Rule 110"; the T-tetromino "with period 2"; list of twelve known 1D rules
[^11]: [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] L41-59 [synthesis] - "the containing automaton inherits some useful properties of the embedded, which is usually not trivial to prove. Such properties are logic universality, Turing-completeness"; Jason Summers's CGoL unit cell "is a polyglot (works in EightLife, too)"; list of Life-like rules with constructed W110 unit cells, including HighLife, Life without death, Day & Night, Seeds, Brian's Brain, "Star Wars using a cyclical emulator", Bosco's Rule; [[lifewiki-seeds](pages/lifewiki-seeds.md)] L21 - Naszvadi "proved that Seeds is Turing-complete on an infinite, periodically-tiled grid by constructing a Rule 110 "unit stripe""
[^12]: [[lifewiki-wireworld](pages/lifewiki-wireworld.md)] L9 - "Given an infinite tiling of properly put "wires", WireWorld is Turing-complete"
