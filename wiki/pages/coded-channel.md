---
title: Coded Channel
category: Concepts
summary: Von Neumann's solution to wire-crossing in a 2D cellular automaton — all signals share one line, each sender injects a distinct code and each receiver decodes only its own, with codes chosen so none contains another
tags: [concept, wire-crossing, coded-channel, signal-coding, von-neumann]
sources: [tsra-part2-ch3, tsra-part2-ch4, tsra-part2-ch5]
created: 2026-09-24
updated: 2026-09-24
---

# Coded Channel

## Description

**The problem.** In three dimensions, wires can pass over one another without touching.
In two dimensions some networks cannot be drawn without crossings. For example, five
points that must all be connected to each other cannot be joined in the plane without
two lines intersecting. In a 2D [[cellular-automaton](pages/cellular-automaton.md)],
lines that meet interact, so the signal on one leaks into the other.[^1]

One fix would be to add a wire-crossing primitive to the rule, but that would need extra
states. Von Neumann kept the rule as it was and solved the problem with coding.[^1] He
regarded this as preferable to giving up two-dimensionality, which is otherwise
worthwhile.[^2]

**The solution.** All signals travel on a single **main channel**, a line of ordinary
transmission cells.[^3]

- Each input a_v is attached to the main channel through a
  [[signal-coding-organs](pages/signal-coding-organs.md)] pulser that injects a code
  sequence s_v.
- Each output b_v is attached through a decoder for the same code.
- A pulse at a_v travels the channel as s_v and triggers only decoder b_v.

Inputs and outputs can be attached in any order along the channel, so the physical layout
no longer has to follow the connection graph.[^3]

**Choosing the codes.** A decoder fires on any pattern containing its code's 1s, so no code
may contain another. Von Neumann uses all codes of length m that begin with 1 and contain
exactly k ones. No such code contains another, and there are C(m−1, k−1) of them, enough
for n channels whenever C(m−1, k−1) ≥ n. Taking k ≈ m/2 gives the most codes for a given
length.[^4]

**Timing discipline.** If two messages are injected too close together, their overlap could
form a third code and trigger the wrong decoder. Von Neumann derives minimum spacings
between stimulations that depend on the relative positions of the injection points, which
rules out any such false match.[^5] A variant loops the channel so that outputs can lie
"upstream" of inputs. The editor notes that von Neumann gave no anti-corruption rule for
that cyclic version and later used the non-cyclic one.[^6]

**Significance.** The coded channel trades space and time for rule simplicity: a
topological obstacle is removed by coding, without adding states. The same trade shows up
throughout von Neumann's design, where missing primitives are synthesized from available
ones rather than added to the rule.

**In practice.** The memory control of the cellular tape needs about 30 crossing lines
between its read-write-erase unit and that unit's control. Von Neumann chose 9-bit codes
with 5 ones (70 codes). The editor found that the decoders for those codes were taller than
von Neumann had allowed, and switched to 9-bit codes with 4 ones (56 codes), which fit. The finished memory control needs 39 distinct codes, so 56 is enough.[^8] Burks also shows that a true crossing can be built from existing states, the [[crossing-organ](pages/crossing-organ.md)].

## Appearances in Sources

- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] — the final code count, and the crossing organ as an alternative
- [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] — the coded channel inside the memory control
- [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] — the wire-crossing problem and the construction of the coded channel

## Related Concepts

- [[crossing-organ](pages/crossing-organ.md)] — an actual wire crossing built from existing states
- [[cellular-tape](pages/cellular-tape.md)] — its main application
- [[signal-coding-organs](pages/signal-coding-organs.md)] — the pulsers and decoders it is built from
- [[cellular-automaton](pages/cellular-automaton.md)] — 2D media force the crossing problem
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] — the rule it keeps unchanged

[^1]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.190-191 [synthesis] — editor: in 3D wires cross without touching, in 2D intersecting channels are topologically necessary; a crossing primitive would need extra states; von Neumann solved it with a coded channel; example of points that must all be interconnected
[^2]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] p.191 [synthesis] — the difficulty doesn't arise in 3D, but it is worth keeping the dimensionality low, so the line-crossing difficulty is accepted and overcome by special constructions
[^3]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.192-193 [synthesis] — coding by a pulser at every input and a decoder at every output, joined by a single main channel of transmission states; inputs and outputs can be arranged in any order
[^4]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] p.194 [synthesis] — sequences of length m beginning with 1 with exactly k ones; C(m−1, k−1) ≥ n required; k ≈ m/2 is the practical choice
[^5]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.196-198 [synthesis] — corruption by superposition of shifted sequences; rule of minimum delays between stimulations depending on the distance between tie-in points
[^6]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.198-200 [synthesis] — cyclic coded channel; editor: von Neumann gave no corruption rule for the cyclic version and later used a non-cyclic coded channel in the control organ
[^7]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.239-243 [synthesis] — about 30 connections require a coded channel; von Neumann chose m = 9, k = 5; editor finds the decoder heights underestimated and uses m = 9, k = 4
[^8]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.258-259 [synthesis] — MC needs 39 different coded sequences; the code of length 9 with four ones, allowing 56, is confirmed adequate
