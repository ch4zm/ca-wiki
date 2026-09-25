---
title: Von Neumann's 29-State Cellular Automaton
category: Rules
summary: The first cellular automaton designed for universal construction and self-reproduction — a 2D, 5-cell (von Neumann) neighbourhood rule with 29 states split between signal transmission/logic and construction/destruction
tags: [rule, von-neumann, 29-state, self-reproduction, universal-construction]
sources: [tsra-part2-ch2, tsra-part2-ch1]
created: 2026-09-24
updated: 2026-09-24
---

# Von Neumann's 29-State Cellular Automaton

## Description

Von Neumann's 29-state rule is the [[cellular-automaton](pages/cellular-automaton.md)] in
which he designed a [[universal-constructor](pages/universal-constructor.md)] and a
self-reproducing machine. It runs on an infinite square lattice. Each cell updates from its
own state and those of its four orthogonal neighbours; this five-cell neighbourhood is now
called the *von Neumann neighbourhood*. Every cell starts blank except for a finite initial
pattern.[^1]

The rule is built around two kinds of signal:

- **Ordinary stimuli** carry logic and control.
- **Special stimuli** carry construction and destruction.

## The 29 states

| Group | Count | What it is |
|---|---|---|
| **Ordinary transmission** | 8 | a directed wire cell: 4 output directions × quiescent/excited |
| **Special transmission** | 8 | the same, but carries special stimuli |
| **Confluent** | 4 | undirected junction; quiescent/excited × a one-step memory of its next excitation |
| **Unexcitable (U)** | 1 | the blank background, or "vacuum" |
| **Sensitized** | 8 | transient states that occur only while a blank cell is being built |

Of these, 16 + 4 + 1 + 8 = 29.[^2]

## How the rule behaves

**Transmission.** A transmission cell points in one output direction and accepts input from
its other three sides. It becomes excited one step after any neighbour of its own class
pointing into it was excited. A line of such cells is a wire that moves a signal one cell
per step. A cell fed from two or more sides acts as an **OR** gate.[^3]

**Confluence.** A confluent cell has no direction. It fires when *every* ordinary
transmission cell pointing into it is excited, so it acts as an **AND** gate. It sends its
output to every adjacent transmission cell not pointing into it, so it also splits a
signal, and it converts ordinary stimuli into special ones. Its response takes two steps
instead of one. Without that, the square lattice (where path-length differences are always
even) could not produce odd delays.[^4]

**Destruction (reverse process).** An excited transmission cell of one class pointing into
a working cell of the opposite class kills it back to U. Special stimuli kill ordinary and
confluent cells, and ordinary stimuli kill special cells. A kill overrides any stimulus
arriving at the same moment.[^5]

**Construction (direct process).** A stimulus of either class arriving at a U cell starts a
build. Over the next few steps each arriving stimulus counts as 1 and each gap counts as 0.
The resulting 3–4-bit code, stepping through the sensitized states, decides which of the 9
quiescent working states the cell becomes: 8 transmission (either class, 4 directions) or
confluent.[^6]

**Negation** has no state of its own. It is done by cutting a signal path with a kill and
rebuilding it with a construction, so the rule's own logic uses both processes.[^4]

**Quiescence.** If every cell is in U or a quiescent working state, nothing ever changes. A
finite machine can therefore be laid out in quiescent cells and left dormant until
stimulated.[^7]

## Notable behaviours

- **Endless growth.** A small loop that recirculates a construction code feeds a line of
  cells that grows to the right forever. This is the first pattern in the rule shown to
  grow without limit.[^8]
- **Remote construction.** With the [[construction-arm](pages/construction-arm.md)]
  technique, a fixed device fed two binary input strings can build any finite quiescent
  pattern at a distance.[^8]

## Appearances in Sources

- [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] — derivation of the states and the full transition rule
- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — the editor's preview of the state set and the direct/reverse processes

## Related Concepts

- [[cellular-automaton](pages/cellular-automaton.md)] — the general model
- [[construction-arm](pages/construction-arm.md)] — the construction technique the rule supports
- [[universal-constructor](pages/universal-constructor.md)] — designed in this rule
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — transmission and confluent cells realize neuron-like logic
- [[self-reproduction](pages/self-reproduction.md)] — the goal the rule was built for

[^1]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.132-134, 151-152 [synthesis] — quadratic lattice; next state depends on the cell and its four nearest neighbours at t−1; editor: finite initial cell assignment, all other cells unexcitable
[^2]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.148-149 [synthesis] — rigorous list of states: 16 transmission, 4 confluent, 1 unexcitable, 8 sensitized; N = 29
[^3]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.135-136, 150-151 [synthesis] — transmission states with one output direction, inputs from the others, delay 1; a transmission cell with several inputs is a + neuron
[^4]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.136-138, 146-148, 152-153 [synthesis] — confluent states excited when all incoming ordinary transmission cells are excited (· neuron), output to all non-incoming transmission cells, delay 2 via one-step memory; odd delays unavailable from path differences; negation synthesized from reverse and direct processes; editor: confluent cells also split lines and convert ordinary to special stimuli
[^5]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.140-142, 154 [synthesis] — the reverse process: special stimuli kill ordinary transmission and confluent cells, ordinary stimuli kill special transmission cells; editor: killing dominates reception
[^6]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.142-145, 151 [synthesis] — direct process by binary-coded stimulus sequences through sensitized states to the nine quiescent states; either stimulus class suffices
[^7]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.107 [synthesis] — editor: if every cell is in one of the ten quiescent states nothing changes; a quiescent finite automaton can be embedded and later stimulated
[^8]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.153-156 [synthesis] — editor: a storage loop feeding a construction code produces an ever-lengthening line, the first pattern that grows indefinitely; construct-and-retract builds any finite quiescent array from two binary sequences
