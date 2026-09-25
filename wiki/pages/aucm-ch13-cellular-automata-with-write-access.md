---
title: "Automata, Universality, Computation — Ch. 13: Algorithms with Active Cells Modeled by Cellular Automata with Write-Access (CA-w)"
category: Sources
summary: Hoffmann's CA-w model - active cells that can write to a dynamically chosen neighbour, switch it on or off, and resolve write conflicts - shown on the rule-184 traffic rule (push and pull forms), Pascal's triangle, Fibonacci numbers, sorting on a ring with moving agents, and leader election
tags: [ca-variant, write-access, gca, agents, rule-184, traffic, sorting, leader-election, hoffmann]
sources: [aucm-ch13-cellular-automata-with-write-access]
created: 2026-09-24
updated: 2026-09-24
---

# Automata, Universality, Computation — Ch. 13: Algorithms with Active Cells Modeled by Cellular Automata with Write-Access (CA-w)

**Source:** assets/adamatzky-2015-automata-universality-computation.pdf, printed pp. 277–295 (PDF pp. 282–300)
**Date ingested:** 2026-09-24
**Type:** book chapter (model and worked examples)
**Author:** Rolf Hoffmann
**Part of:** [[automata-universality-computation](pages/automata-universality-computation.md)]

## Summary

Some distributed algorithms are naturally written in terms of *active cells*: moving
agents or particles, whose number and positions change over time. An ordinary
[[cellular-automaton](pages/cellular-automaton.md)] can express them, but only awkwardly,
because a cell can read its neighbours and never change them. Hoffmann's fix is the
[[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)]
(CA-w). An active cell selects a neighbour, reads it, and may write a new state into it,
which can also switch that neighbour's activity on or off. CA-w is the locally restricted
form of GCA-w, where links may reach any cell.[^1]

Writes bring the possibility of conflicts, which a conflict rule resolves. The examples
are designed to avoid them.[^2] The payoff is concise, "natural" descriptions of
problems with moving agents, and less computation, since only active cells do any
work.[^3] The chapter demonstrates this on [[rule-184](pages/rule-184.md)] (the traffic
rule), Pascal's triangle, Fibonacci numbers, sorting on a ring, and leader election.[^4]

## Key Takeaways

- **Three kinds of cell.** Active cells compute. Passive cells do not compute but can be
  switched on by others. Dead cells stay fixed forever. Passive or dead cells can also
  mark termination, for example when every cell has become passive.[^5]
- **No extra power at radius 1.** In a one-handed CA-w with read/write radius 1, a cell's
  next state depends on cells up to distance 2. So it can be emulated by an ordinary CA of
  radius 2.[^6]
- **Rule 184 four ways.** The traffic rule can be written as a normal CA rule, as a
  substitution 10 → 01, as a *push* rule (particles are active and move themselves right),
  or as a *pull* rule (empty cells are active and pull a particle in from the left). The
  substitution, moved onto the left or the right cell, becomes the push or the pull
  rule.[^7]
- **Only useful cells work.** For Pascal's triangle, an ordinary CA keeps updating cells
  that hold nothing useful yet, and on average only about a third of them produce
  coefficients. The CA-w version keeps just the frontier active, and it switches on one new
  cell at the right edge each step.[^8]
- **Sorting with agents.** Agents on a ring each carry out steps of odd-even transposition
  sort as they move. A marker at the end of the sequence flips the order test once. The
  method works with any number of agents except a full ring all facing the same way. It
  also works under asynchronous updating. More agents are not always faster: five agents
  all facing right do no better than one.[^9]
- **Leader election.** Agents turn at the marker, and when two meet head-on one of them
  drops out. The agent that has seen both borders becomes leader.[^10]

## The model in brief

A GCA-w is a tuple (I, Q, δ, h, f, g, e).[^11]

- Cells are indexed by I = {0, …, N−1}. The index is visible to the cell, which allows
  non-uniform rules.
- States split into active, passive and dead sets.
- δ is a special "don't write" value.
- h(i, q) picks the neighbour, by absolute or relative address.
- The local rule f(i, q, q*) gives the cell's own new state.
- The write rule g(i, q, q*) gives the value sent to the chosen neighbour.
- The conflict rule e combines f with every incoming g into the next state.

Updating is synchronous. A dead cell never changes. An active cell applies e to f and the
incoming writes. A passive cell applies e to the incoming writes alone, with f = δ, so
that it can still be activated. If e returns δ, the state stays as it was.[^12] In CA-w
the neighbour lies within radius R. A cell may have k "hands", each able to read or write
one neighbour, but most applications need only one.[^13]

**Related models.** The Parallel Substitution Algorithm model also rewrites target cells,
using a base and a context. The CRCW-PRAM also allows concurrent writes, but it is framed
in terms of processors and global memory rather than local rules on logical cells.[^14]

## Entities & Concepts

- [[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)]
- [[rule-184](pages/rule-184.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]
- [[rule-90](pages/rule-90.md)]

## Relation to Other Wiki Pages

The ordinary rule Center ← Left + Right that Hoffmann uses for Pascal's triangle is
[[rule-90](pages/rule-90.md)] over the integers. Reduced mod 2, it gives the Sierpinski
pattern that the wiki describes there (own reasoning; the chapter does not mention rule
90). [[rule-184](pages/rule-184.md)] moves particles without creating or destroying them,
so the number of 1s is a [[conserved-quantity](pages/conserved-quantity.md)] (own
reasoning from the substitution 10 → 01).

[^1]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.277-278 [synthesis] — active cells, "also called active particles [12] or agents"; "in CA a cell can only read information from its neighbors and cannot change its neighbors' states directly. Therefore the movement of agents, the change of neighboring data, and the control of activity becomes difficult to describe"; "If the neighborhood of the GCA-w model is locally restricted, we will call the model CA-w"; a GCA cell "can dynamically establish links to any of its global neighbors"
[^2]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.279, 281 [synthesis] — "A potential difficulty is that write-conflicts may appear"; rules should be designed so that no conflict occurs (as for the traffic rule), or conflicts are few or locally resolvable; "if the rules fulfill the exclusive-write condition (as in the following algorithms)"
[^3]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] p.294 — "Compared to CA, the CA-w descriptions for such problems are more concise and 'natural' because the change of the system's state is only controlled by the active cells. Furthermore, the computational effort to simulate CA-w is minimized because only active cells have to be computed, thereby minimizing the energy consumption, too."
[^4]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] p.277 (Abstract) — "The usefulness of the model is demonstrated for basic computational problems, the well-known 1-D CA traffic rule, Pascal's triangle, Fibonacci numbers, sorting on the ring by agents, and leader election for agents."
[^5]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.280-281 [synthesis] — active, passive, dead "operational states"; "Dead cells are totally excluded from the computation because they remain dead forever. Passive cells do not compute themselves but can be activated by other cells"; passive or dead cells "can be used to define a termination condition"
[^6]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] p.283 — "data from the neighbors within the radius 2 can influence the new state of the own cell. Therefore the CA-w model with radius 1 can be emulated by a CA model with radius 2."
[^7]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.284-285 [synthesis] — rule 184, C ← (C ∧ R) ∨ (L ∧ C̄); four cases: CA cell rule, substitution (10 → 01), push rule (particles active, set(1) to the right neighbour, set(0) to itself, "inherently conflict-free"), pull rule (empty cells active); "The substitution ... can be shifted to the left cell, yielding the push rule, or shifted to the right, yielding the pull rule."
[^8]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.286-287 [synthesis] — in a CA with n cells "always (n − 1) cells are updated"; "On average, approximately only one third of the cells are producing the coefficients"; CA-w program: the rightmost active cell writes 1 to its right neighbour and activates it, each active cell adds its left neighbour's value, "at every time step, a new cell active cell is generated at the right margin"
[^9]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.288-291 [synthesis] — odd-even sort; a marker (dot) inverts the ordering relation once; config 2: five right-moving agents "not faster than the (config: 0)-system"; six agents all facing right "are unable to solve the task because all of them are stuck"; "the a-algorithm works for any initial configuration, except for the one where the ring is fully packed with agents having the same direction"; works with asynchronous updating
[^10]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.292-294 [synthesis] — states {init, leftborder, rightborder, leader, lost}; agents that perceive the marker turn; head-on meetings swap and update states by Table 13.1, making one agent lost; an agent in state 1/2 that detects the other border becomes leader (state 3)
[^11]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.279-280 [synthesis] — GCA-w = (I, Q, δ, h, f, g, e); I = {0, …, N−1}; Q = A ∪ P ∪ D; δ the Don't-Write symbol; h: I × Q → I (or relative h_rel); f: I × Q × Q → Q_δ; g: I × Q × Q → Q_δ; e: I × Q_δ^{N+1} → Q_δ; "The index can also be accessed by the cell itself in order to implement non-uniform rules"
[^12]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.280-281 [synthesis] — Rule Application (16)-(18): synchronous; active cells apply e to f and the messages g_{j→i}; dead cells or e = δ leave the state unchanged; passive cells use f = δ, "the conflict-rule e has to be awake because activating messages might arrive"
[^13]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.282-283 [synthesis] — CA-w: neighbour address within radius R; "the CA-w model may use k 'hands' to access k neighbors in parallel ... Many applications can be described with one hand only"; access rights may differ from hand to hand
[^14]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] p.283 [synthesis] — PSA (Parallel Substitution Algorithm) "allows also to modify a set of arbitrary target cells ... using a base and a context"; CRCW-PRAM "is based on a physical view with p processors that have global memory access", while GCA-w "is based on logical computing cells with local memory tailored to the application"
