---
title: Von Neumann's 29-State Cellular Automaton
category: Rules
summary: The first cellular automaton designed for universal construction and self-reproduction — a 2D, 5-cell (von Neumann) neighbourhood rule with 29 states split between signal transmission/logic and construction/destruction
tags: [rule, von-neumann, 29-state, self-reproduction, universal-construction]
sources: [tsra-part2-ch2, tsra-part2-ch1, tsra-part2-ch3, tsra-part2-ch4, tsra-part2-ch5, computation-at-the-edge-of-chaos]
created: 2026-09-24
updated: 2026-09-25
---

# Von Neumann's 29-State Cellular Automaton

## Description

Von Neumann's 29-state rule is the [[cellular-automaton](pages/cellular-automaton.md)] in
which he designed a [[universal-constructor](pages/universal-constructor.md)] and a
self-reproducing machine. It runs on an infinite square lattice. Each cell updates from its
own state and those of its four orthogonal neighbours; this five-cell neighbourhood is now
called the *von Neumann neighbourhood* ([[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)]), in contrast to the nine-cell
[[moore-neighbourhood](pages/moore-neighbourhood.md)]. Every cell starts blank except for a finite initial
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
- **Universality.** The rule is computation-universal, construction-universal, and self-reproductive. It holds an initially quiescent universal Turing machine, a universal constructor, and a self-reproducer.[^11]
- **Non-constructible patterns.** Some configurations cannot be built, for example a 3 × 3 block of sensitized S₀ surrounded by C₀₀ cells ([[garden-of-eden](pages/garden-of-eden.md)]).[^12]

## Organs built from the rule

Von Neumann assembles a library of named components from these states. [[signal-coding-organs](pages/signal-coding-organs.md)] turn
pulses into timed bit patterns and back, and repeating loops act as flip-flops. Since the
rule has no inhibitory state, a loop is stopped by killing one of its cells and
rebuilding it. The rule also has no wire-crossing state, and signals that must cross
share one line by coding instead ([[coded-channel](pages/coded-channel.md)]), or pass through a [[crossing-organ](pages/crossing-organ.md)] built from existing states.[^9] These organs
are assembled into an unbounded [[cellular-tape](pages/cellular-tape.md)] with its memory control.[^10]

## Appearances in Sources

- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] — the finished constructor, universality results, and self-reproduction
- [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] — the tape and memory control built in the rule
- [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] — the basic organs built from the rule
- [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] — derivation of the states and the full transition rule
- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — the editor's preview of the state set and the direct/reverse processes
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - cited as the first proof of a universal computer/constructor in a CA, the starting point for asking which rules can support computation[^13]

## Related Concepts

- [[game-of-life](pages/game-of-life.md)] — a later universal rule with 2 states and the eight-cell Moore neighbourhood
- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] — patterns of its 10 quiescent states
- [[crossing-organ](pages/crossing-organ.md)] — a wire crossing synthesized in the rule
- [[cellular-tape](pages/cellular-tape.md)] — unbounded memory in the rule
- [[signal-coding-organs](pages/signal-coding-organs.md)] — pulsers, decoders, flip-flops
- [[coded-channel](pages/coded-channel.md)] — wire-crossing by coding
- [[cellular-automaton](pages/cellular-automaton.md)] — the general model
- [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)] - the four-neighbour neighbourhood named after it
- [[construction-arm](pages/construction-arm.md)] — the construction technique the rule supports
- [[universal-constructor](pages/universal-constructor.md)] — designed in this rule
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — transmission and confluent cells realize neuron-like logic
- [[self-reproduction](pages/self-reproduction.md)] — the goal the rule was built for
- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - the five-cell rule as a special case of Moore's nine-cell scheme
- [[edward-f-moore](pages/edward-f-moore.md)] - author of the nine-cell tessellation scheme
- [[edge-of-chaos](pages/edge-of-chaos.md)] - Langton's answer to which rules, among all of them, can support computation

[^1]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.132-134, 151-152 [synthesis] — quadratic lattice; next state depends on the cell and its four nearest neighbours at t−1; editor: finite initial cell assignment, all other cells unexcitable
[^2]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.148-149 [synthesis] — rigorous list of states: 16 transmission, 4 confluent, 1 unexcitable, 8 sensitized; N = 29
[^3]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.135-136, 150-151 [synthesis] — transmission states with one output direction, inputs from the others, delay 1; a transmission cell with several inputs is a + neuron
[^4]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.136-138, 146-148, 152-153 [synthesis] — confluent states excited when all incoming ordinary transmission cells are excited (· neuron), output to all non-incoming transmission cells, delay 2 via one-step memory; odd delays unavailable from path differences; negation synthesized from reverse and direct processes; editor: confluent cells also split lines and convert ordinary to special stimuli
[^5]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.140-142, 154 [synthesis] — the reverse process: special stimuli kill ordinary transmission and confluent cells, ordinary stimuli kill special transmission cells; editor: killing dominates reception
[^6]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.142-145, 151 [synthesis] — direct process by binary-coded stimulus sequences through sensitized states to the nine quiescent states; either stimulus class suffices
[^7]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.107 [synthesis] — editor: if every cell is in one of the ten quiescent states nothing changes; a quiescent finite automaton can be embedded and later stimulated
[^8]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.153-156 [synthesis] — editor: a storage loop feeding a construction code produces an ever-lengthening line, the first pattern that grows indefinitely; construct-and-retract builds any finite quiescent array from two binary sequences
[^9]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.158-200 [synthesis] — pulsers, decoders, periodic pulsers, counter, discriminator, and coded channel, each built from transmission and confluent states; stopping via kill-and-rebuild; the coded channel avoids a wire-crossing primitive
[^10]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.201-250 [synthesis] — design of the tape, connecting and timing loops, and memory control from the basic organs
[^11]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.296 — "His 29-state cellular structure is computation-universal, construction-universal, and self-reproductive."
[^12]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 [synthesis] — not all automata specifiable at time zero can be constructed; the 3 × 3 configuration of sensitized S₀ surrounded by C₀₀
[^13]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.16 [synthesis] - "Von Neumann's proof of the possibility of machine self-reproduction involves the demonstration of the existence of a universal computer/constructor in a 29-state CA"; Codd, Smith, Conway and co-workers, Fredkin and Toffoli later found much simpler universal rules
