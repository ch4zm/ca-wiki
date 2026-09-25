---
title: Cellular Automaton with Write-Access
category: Concepts
summary: Hoffmann's CA-w (and global GCA-w) - a cellular automaton whose active cells may write into a dynamically selected neighbour and switch its activity, with active/passive/dead cells and a conflict rule; radius-1 CA-w is emulated by a radius-2 ordinary CA, so the gain is description and efficiency, not power
tags: [concept, ca-variant, write-access, gca, agents, hoffmann]
sources: [aucm-ch13-cellular-automata-with-write-access]
created: 2026-09-24
updated: 2026-09-24
---

# Cellular Automaton with Write-Access

## Description

In an ordinary [[cellular-automaton](pages/cellular-automaton.md)], a cell reads its
neighbours and updates only itself. No write conflicts can occur, which keeps hardware and
software simple. It also makes moving agents, or a changing set of active cells, awkward to
describe.[^1] A **cellular automaton with write-access (CA-w)** lets a cell write to a
neighbour as well. Information can be sent to a destination, and the destination can be
switched on or off.[^2]

**Ingredients.**[^3]

- **Operational states.** Cells are active (they compute), passive (they wait to be
  activated from outside), or dead (fixed forever).
- **Links.** An address function h picks the neighbour to read and write. It can change
  from step to step. In **GCA-w** (global CA with write-access), links may reach any cell.
  In **CA-w** they stay within a radius R. A cell may have several "hands" (links).
- **Three rules.** The local rule f gives the cell's own new state. The write rule g gives
  the value sent to the chosen neighbour. The conflict rule e merges f with all incoming
  writes, ignoring the "don't write" value δ.

**Conflicts.** In the worst case every cell writes to the same target. Hoffmann recommends
rules that avoid conflicts entirely (*exclusive write*, as in the traffic rule), keep them
local, or resolve them with a reduction such as summing the inputs.[^4]

**Power.** In a one-handed CA-w of radius 1, a cell's next state depends on cells up to
distance 2. An ordinary CA of radius 2 can therefore emulate it.[^5] (Own reasoning: CA-w
is a way to describe and to economize, not a stronger model of computation, at least for
bounded radius.) Only active cells compute, which cuts the simulation effort and the
energy used.[^6]

**Examples.** [[rule-184](pages/rule-184.md)] can be written as a push rule, where
particles move themselves, or as a pull rule, where empty cells pull them in. Others are
Pascal's triangle and Fibonacci numbers computed by a moving frontier, sorting on a ring
with agents, and leader election
([[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)]).[^7]

## Appearances in Sources

- [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] - definition of GCA-w and CA-w, and five algorithms

## Related Concepts

- [[cellular-automaton](pages/cellular-automaton.md)] - the read-only model it extends
- [[rule-184](pages/rule-184.md)] - the traffic rule in push and pull form
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - another departure from the standard neighbourhood scheme, where a block rule updates several cells at once
- [[broadcasting-automaton](pages/broadcasting-automaton.md)] - another variant whose links change with state
- [[one-bit-communication-cellular-automaton](pages/one-bit-communication-cellular-automaton.md)] - a variant that restricts neighbours to one bit per step

[^1]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.277-278 [synthesis] — "in CA a cell can only read information from its neighbors and cannot change its neighbors' states directly"; "CA and GCA do not allow to modify the state of a neighbor. Therefore no write-conflict can occur, simplifying implementations in hardware and in software"
[^2]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] p.278 — "These models allow a cell to write information to its neighbors. This feature is very important because information can actively be transferred to a destination, and the activity of the destination can be switched on or off."
[^3]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.279-283 [synthesis] — GCA-w = (I, Q, δ, h, f, g, e) with active, passive, dead states; h absolute or relative neighbour address; f local rule, g write rule, e conflict rule; CA-w restricts h to radius R; k-handed variants
[^4]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.279, 281 [synthesis] — worst case "all cells want to write onto the same cell"; rules should be designed so that no conflict occurs, conflicts are few, or they can be resolved locally; exclusive-write condition; conflict resolution may correspond "to a reduction operator (e.g. summing up the inputs)"
[^5]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] p.283 — "Therefore the CA-w model with radius 1 can be emulated by a CA model with radius 2."
[^6]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] p.294 — "the computational effort to simulate CA-w is minimized because only active cells have to be computed, thereby minimizing the energy consumption, too."
[^7]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.284-294 [synthesis] — push and pull forms of the traffic rule; Pascal's triangle; Fibonacci numbers; sorting on the ring with agents; leader election
