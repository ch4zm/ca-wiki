---
title: Conway's Game of Life
category: Rules
summary: Conway's two-state, eight-neighbour (Moore neighbourhood) totalistic rule - a cell survives with two or three live neighbours and is born with exactly three; home of blocks, blinkers, gliders and glider guns, and computationally universal via glider-stream circuits, with undecidable death of finite patterns; stub pending the Gardner and Winning Ways ingests
tags: [rule, life, conway, two-dimensional, totalistic, universality]
sources: [statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey, aucm-ch16-phyllosilicate-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Conway's Game of Life

> **Stub.** Everything here comes from the short treatment in Sec. V of
> [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)],
> §2.6 of
> [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)],
> and passing remarks in [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)],
> plus the Life-like rules of
> [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)].
> Conway, Gardner (1970-72) and Berlekamp, Conway and Guy (1982) are cited via those papers
> and have not been read yet.

## Description

**The rule.** Life is a two-dimensional [[cellular-automaton](pages/cellular-automaton.md)]
with two states per cell, "alive" (1) and "dead" (0), on a square lattice. Each cell looks
at its eight orthogonal and diagonal neighbours, the neighbourhood Wolfram calls
*type-II* and that is also known as the Moore neighbourhood. A cell dies unless two or
three neighbours are alive. With exactly two live neighbours it keeps its current state.
With exactly three it becomes alive.[^1] The new value depends only on the neighbourhood
*sum*, which makes Life *totalistic*.[^2]

**Known structures** (as surveyed in 1983):[^3]

- **Still lifes**, which do not change: the "block" (four live cells) and the "beehive"
  (six).
- **Oscillators**: the "blinker", a line of three cells that repeats every two steps.
  Oscillators with periods 3, 5 and 7 were known, and others can be built by composition.
- **Moving structures**: the "glider", five live cells that travel across the lattice
  through a cycle of internal states.
- **Glider guns**, which emit an endless stream of gliders, so the number of live cells
  grows without bound. The simplest then known evolves from a configuration of 26 live
  cells.

Structures separated by four or more empty cells can coexist without interfering.[^3]

**Life-like rules on other lattices.** Life's toolkit of gliders, oscillators, still lifes,
eaters and guns also appears in rules on non-square lattices. Adamatzky found it in three
rules of the [[phyllosilicate-automaton](pages/phyllosilicate-automaton.md)], a silicate-sheet
lattice with 3-neighbour and 6-neighbour nodes. Those rules have gliders of periods 16, 12
and 4, an oscillator that eats gliders, a still life, and a glider gun. Most of their glider
collisions explode.[^4] He compares them with B3/S23 by normalizing thresholds by
neighbourhood size, which gives Life birth at 3/8 and survival at 2/8 or 3/8.[^5] The
chapter also points to Life-like work on triangular tessellations (Bays: glider guns) and
Penrose tilings (Goucher; Owens and Stepney), cited via Adamatzky and not read.[^6]

**From random starts.** Monte Carlo runs suggest that a random N × N region usually
settles into a steady state within about N² steps, and often ten times sooner. It visits
very few of its 2^(N²) configurations. Complex structures such as guns almost never arise
by chance. Roughly, the density of structures with L live cells falls off like e^(−L₋)/L,
where L₋ is the size of the smallest configuration that turns into the structure in one
step.[^7]

**Irreversibility.** Like the one-dimensional rules
([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]), Life is
irreversible and so has [[garden-of-eden](pages/garden-of-eden.md)] configurations,
which can occur only as initial states. The simplest known in 1983 had about 300
cells.[^8]

**Universality.** Glider streams can act as wires, with a glider or its absence as one bit.
Structures where streams meet decide whether the wires cross or combine through a NAND
gate. Memories are needed too. With these, Life can simulate a digital computer, so it is
computationally universal. Circuits such as binary adders have been built, and they appear
to run only a constant factor slower than the computers they imitate.[^9] Compare von
Neumann's [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)], which is also
universal but uses 29 states and the five-cell neighbourhood
([[universal-turing-machine](pages/universal-turing-machine.md)]).

**Place in rule space.** Life's [[lambda-parameter](pages/lambda-parameter.md)] is 0.273, which lies inside the
order-chaos transition region for 2-state, 9-neighbour rules. Langton reads its gliders
(used as signals) and blinkers (used as storage) in the universality proof as the kind of
moving and static structures that appear near the transition ([[edge-of-chaos](pages/edge-of-chaos.md)]).[^10]
He also notes that Bak had suggested Life is a self-organized critical system (cited via
Langton, not read).[^11]

**Formal definitions and undecidability (Kari 2005).** Kari defines Life's objects in
terms of finite configurations c and the global map G:[^12]

- a **still life** is a finite fixed point, G(c) = c;
- an **oscillator** is a finite c with Gᵏ(c) = c for some k ≥ 2;
- a **glider** is a finite c with Gᵏ(c) equal to a translate of c;
- a **glider gun** is periodic like an oscillator and emits one or more gliders each
  period.

His examples are a period-two oscillator, a period-four glider and a period-30 glider
gun. Random starts quickly produce such objects, which interact by collisions "leading to
extraordinary complexity".[^12] For any Turing machine M one can build a finite Life
configuration that *dies*, meaning it eventually becomes all-dead, iff M halts on the
blank tape. So Life is computationally universal and **whether a finite configuration
dies is undecidable** (Berlekamp, Conway and Guy).[^13] Life's gliders correspond to the
signals of class-4 1D rules such as [[rule-110](pages/rule-110.md)], but signals cross
far more easily in two dimensions.[^14]

## Appearances in Sources

- [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] - Life-like gliders, oscillators, eaters and a gun on the phyllosilicate lattice; B3/S23 normalized by neighbourhood size
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: formal definitions of still lifes, oscillators, gliders and guns; Theorem 1 (universality, undecidable death)
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — Sec. V: the rule, standard structures, statistics from random starts, Garden-of-Eden size, universality via glider streams
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - λ = 0.273, gliders and blinkers as signals and storage

## Related Concepts

- [[edge-of-chaos](pages/edge-of-chaos.md)] - Life sits in the transition region
- [[cellular-automaton](pages/cellular-automaton.md)] — the general notion; type-I vs type-II neighbourhoods
- [[garden-of-eden](pages/garden-of-eden.md)] — Life has them, and the smallest known is large
- [[universal-turing-machine](pages/universal-turing-machine.md)] — computational universality in cellular automata
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] — the earlier universal cellular automaton
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — the irreversibility Life shares with 1D rules
- [[rule-110](pages/rule-110.md)] - the 1D counterpart, with signals in place of gliders
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - whether a finite pattern dies is undecidable
- [[intrinsic-universality](pages/intrinsic-universality.md)] - Life's universality is the Turing-machine kind
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Life's gliders as the 2D counterpart of class-4 signals
- [[phyllosilicate-automaton](pages/phyllosilicate-automaton.md)] - Life-like rules on a silicate-sheet lattice

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] — "a type-II two-dimensional cellular automaton"; the local rules take a site to "die" unless two or three of its neighbours are "alive"; with two alive the value is unchanged, with three it always becomes one; n.14: types I and II are known as von Neumann and Moore neighbourhoods
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 — "The game of 'Life' is an example of a special class of 'totalistic' cellular automata, in which the value of a site depends only on the sum of the values of its neighbors at the previous time step"
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] — "square" (block) of four and "hexagon" (beehive) of six; "blinker" with period two; oscillators with periods 3, 5 and 7, others by composition; structures separated by four or more unfilled sites coexist; the "glider" of five live sites moving uniformly; glider guns; the simplest known gun evolves from 26 live cells
[^4]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.367-376 [synthesis] — R65, R68, R72 each generate a glider (periods 16, 12, 4, Table 16.1) and oscillators; oscillator-eater O¹²₇₂; still life in R68; glider gun in R72; "Most collisions between gliders in rule R65 lead to explosions"
[^5]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.377 — "Classical Conway's Game of Life automata have rule B3/S23 ... Normalised Conway's Game of Life rule is B 3/8 /S 2/8 3/8."
[^6]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.353, 380-381 (References) [synthesis] — CA on triangular tessellations and Penrose tilings [14, 21, 35]: Bays, "The discovery of glider guns in a Game of Life for the triangular tessellation" (2007); Goucher, "Gliders in cellular automata on Penrose tilings"; Owens and Stepney, "Investigations of Game of Life cellular automata rules on Penrose tilings" (2010)
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] — a disordered state of N² cells usually evolves to a steady state within about N² time steps, typically an order of magnitude quicker; very few configurations visited; glider guns very rarely produced; density of L-site structures decreases like e^(−L₋)/L
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 — "the simplest known 'unreachable' configuration contains around 300 sites"
[^9]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] — glider streams from glider guns used as wires, bits as presence or absence of gliders; meeting points determine crossing or a "NAND gate"; memories required; "The Life-game cellular automaton is thus computationally universal"; binary adders; circuits run slower "only by a constant multiplicative factor"
[^10]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - "The λ value for the Game of Life (λ_Life = 0.273) lies within the transition region for K = 2, N = 9 2D CAs"; the universality proof "employs propagating 'gliders' as signals and the period-2 'blinkers' as storage elements"
[^11]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.35 - "Bak has suggested that Conway's game of Life is a self-organized critical system, although he does not bring Life's computational capacity into the discussion."
[^12]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - Game of Life by Conway; still life, oscillator, glider, glider gun defined via finite configurations; Fig. 5: still life, period two oscillator, period four glider, period 30 glider gun; objects emerge from random configurations and interact through collisions, "leading to extraordinary complexity"
[^13]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 [synthesis] - "for any given Turing machine M one can effectively construct a finite GOL configuration that dies if and only if machine M halts on the blank tape"; Theorem 1 (Berlekamp et al. [6])
[^14]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 [synthesis] - "gliders in GOL are analogous to the complicated localized structures, or signals, that emerge in class 4 elementary CA"; "in two dimensions it is much easier to make signals cross each other"
