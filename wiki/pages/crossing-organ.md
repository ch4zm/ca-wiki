---
title: Crossing Organ
category: Concepts
summary: J. E. Gorman's organ for crossing two signal paths in von Neumann's 29-state CA without a crossing state — five clocks gate the two streams into alternate time slots so they pass through shared confluent cells, each emerging 15 steps later
tags: [concept, wire-crossing, organ, 29-state, von-neumann]
sources: [tsra-part2-ch5]
created: 2026-09-24
updated: 2026-09-24
---

# Crossing Organ

## Description

[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] has no state that lets two
wires cross. Von Neumann avoided crossings with a [[coded-channel](pages/coded-channel.md)].
Burks shows that a genuine crossing can also be built from the existing states. His Fig. 42
gives a **crossing organ** designed by J. E. Gorman.[^1]

**How it works.** Five "clocks" feed alternating 0s and 1s into six confluent cells. At the
two input junctions, each incoming stream is split so that its even-numbered bits travel
one route and its odd-numbered bits another. The clocks are out of phase, so at every shared
confluent cell the two streams occupy alternate time slots and never meet. The halves are
then recombined. Information passes from a₁ to b₁ and from a₂ to b₂ with no interference,
and each stream comes out delayed by 15 time units.[^2]

**Use.** Burks uses four crossing organs to fix the interference problem in von Neumann's
memory control for the [[cellular-tape](pages/cellular-tape.md)]. They let stop signals
reach the periodic pulsers directly, which removes most of the delay circuitry.[^3]

**Cost.** The clocks are active, so an organ with running clocks is not an
[[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] and cannot be laid
down by a constructor. Burks builds each organ with passive cells and attaches a small
constructing device that starts its clocks in phase when the machine is switched on.[^4]

**Why the rule has no crossing state.** Burks notes that a crossing primitive could be added
to the rule, and that several later cellular systems include one. He suggests von Neumann
left it out to keep the number of states small.[^5]

## Appearances in Sources

- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] — the design (Fig. 42) and its use in the memory control

## Related Concepts

- [[coded-channel](pages/coded-channel.md)] — von Neumann's alternative to crossing wires
- [[signal-coding-organs](pages/signal-coding-organs.md)] — the organ library it extends
- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] — the constraint its clocks violate
- [[cellular-tape](pages/cellular-tape.md)] — its application

[^1]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.262 [synthesis] — "It is actually possible to synthesize a crossing organ in von Neumann's cellular structure"; footnote: the crossing organ of Fig. 42 was designed by J. E. Gorman
[^2]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.262-263 [synthesis] — five clocks send alternate zeros and ones into six confluent states; input sequences split into even and odd bits and interleaved; outputs delayed 15 units; information passes from a₁ to b₁ and a₂ to b₂ without cross interference
[^3]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.263-264 [synthesis] — four crossing organs let the stop signals go directly to the periodic pulsers and considerably reduce the delay circuitry
[^4]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.264-265 [synthesis] — the organ contains excited states; built with passive replacements and started by a constructing device on the starting stimulus
[^5]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.261-262 [synthesis] — the 29 states could be augmented by a crossing primitive; systems with crossing primitives discussed by Church, Burks, Holland; von Neumann probably wanted to keep the number of states small
