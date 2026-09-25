---
title: Conway's Game of Life
category: Rules
summary: Conway's two-state, eight-neighbour (Moore neighbourhood) totalistic rule - a cell survives with two or three live neighbours and is born with exactly three; home of blocks, blinkers, gliders and glider guns, and computationally universal via glider-stream circuits; stub pending the Gardner and Winning Ways ingests
tags: [rule, life, conway, two-dimensional, totalistic, universality]
sources: [statistical-mechanics-of-cellular-automata, universality-and-complexity-in-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Conway's Game of Life

> **Stub.** Everything here comes from the short treatment in Sec. V of
> [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)]
> and the class 4 comparison in
> [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)].
> Conway, Gardner (1970-72) and Berlekamp, Conway and Guy (1982) are cited via that paper
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

**From random starts.** Monte Carlo runs suggest that a random N × N region usually
settles into a steady state within about N² steps, and often ten times sooner. It visits
very few of its 2^(N²) configurations. Complex structures such as guns almost never arise
by chance. Roughly, the density of structures with L live cells falls off like e^(−L₋)/L,
where L₋ is the size of the smallest configuration that turns into the structure in one
step.[^4]

**Irreversibility.** Like the one-dimensional rules
([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]), Life is
irreversible and so has [[garden-of-eden](pages/garden-of-eden.md)] configurations,
which can occur only as initial states. The simplest known in 1983 had about 300
cells.[^5]

**Universality.** Glider streams can act as wires, with a glider or its absence as one bit.
Structures where streams meet decide whether the wires cross or combine through a NAND
gate. Memories are needed too. With these, Life can simulate a digital computer, so it is
computationally universal. Circuits such as binary adders have been built, and they appear
to run only a constant factor slower than the computers they imitate.[^6] Compare von
Neumann's [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)], which is also
universal but uses 29 states and the five-cell neighbourhood
([[universal-turing-machine](pages/universal-turing-machine.md)]).

**The model for class 4.** Wolfram (1984) calls Life "essentially totalistic" and uses it
as the template for class 4 of the [[wolfram-classes](pages/wolfram-classes.md)]. The
one-dimensional class 4 rule with k = 2, r = 2 and code 20 behaves in a way "strongly
reminiscent" of Life, with fixed, periodic and moving structures. Life's universality is
the basis for the conjecture that class 4 rules are universal.[^7] The proof of Life's
universality (Gosper; Wainwright 1974; Berlekamp, Conway and Guy 1982, cited via Wolfram
and not read) builds wires and NAND gates from cellular structures. Code 20 has many of
the needed parts, but no one had found an analogue of the glider gun.[^8]

## Appearances in Sources

- [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] - Life as the model for class 4, and code 20 as its 1D analogue
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — Sec. V: the rule, standard structures, statistics from random starts, Garden-of-Eden size, universality via glider streams

## Related Concepts

- [[wolfram-classes](pages/wolfram-classes.md)] - Life is the template for class 4
- [[totalistic-cellular-automaton](pages/totalistic-cellular-automaton.md)] - the rule family Life belongs to
- [[cellular-automaton](pages/cellular-automaton.md)] — the general notion; type-I vs type-II neighbourhoods
- [[garden-of-eden](pages/garden-of-eden.md)] — Life has them, and the smallest known is large
- [[universal-turing-machine](pages/universal-turing-machine.md)] — computational universality in cellular automata
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] — the earlier universal cellular automaton
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — the irreversibility Life shares with 1D rules

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] — "a type-II two-dimensional cellular automaton"; the local rules take a site to "die" unless two or three of its neighbours are "alive"; with two alive the value is unchanged, with three it always becomes one; n.14: types I and II are known as von Neumann and Moore neighbourhoods
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 — "The game of 'Life' is an example of a special class of 'totalistic' cellular automata, in which the value of a site depends only on the sum of the values of its neighbors at the previous time step"
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] — "square" (block) of four and "hexagon" (beehive) of six; "blinker" with period two; oscillators with periods 3, 5 and 7, others by composition; structures separated by four or more unfilled sites coexist; the "glider" of five live sites moving uniformly; glider guns; the simplest known gun evolves from 26 live cells
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] — a disordered state of N² cells usually evolves to a steady state within about N² time steps, typically an order of magnitude quicker; very few configurations visited; glider guns very rarely produced; density of L-site structures decreases like e^(−L₋)/L
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 — "the simplest known 'unreachable' configuration contains around 300 sites"
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] — glider streams from glider guns used as wires, bits as presence or absence of gliders; meeting points determine crossing or a "NAND gate"; memories required; "The Life-game cellular automaton is thus computationally universal"; binary adders; circuits run slower "only by a constant multiplicative factor"
[^7]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.30 [synthesis] - code 20 behaviour "strongly reminiscent of the two-dimensional (essentially totalistic) cellular automaton known as the 'Game of Life'"; "The Game of Life has been shown to have the important property of computational universality"; the speculation that class 4 is characterized by universal computation
[^8]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.30-31 [synthesis] - the proof of universality for Life [22] "uses the existence of cellular automaton structures which emulate components (such as 'wires' and 'NAND gates')"; [22] Gosper, Wainwright (1974), Berlekamp, Conway and Guy (1982); for code 20 "A major missing element is a configuration (dubbed the 'glider gun' in the Game of Life)"; "the required initial configuration is quite large, and is very difficult to find"
