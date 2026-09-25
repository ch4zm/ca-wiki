---
title: Cellular Tape
category: Concepts
summary: An unbounded Turing-style tape embedded in a cellular automaton, read and written through an extendible wire loop, with position and timing both measured relative to the tape — von Neumann's mechanism for unbounded memory in the 29-state CA
tags: [concept, tape, memory, turing-machine, engineering, von-neumann]
sources: [tsra-part2-ch4, tsra-part2-ch1]
created: 2026-09-24
updated: 2026-09-24
---

# Cellular Tape

## Description

A finite machine in a [[cellular-automaton](pages/cellular-automaton.md)] gets unbounded
memory by using a row of cells outside itself as a tape. That turns the machine into a
Turing machine: finite control plus unbounded tape. The tape also holds the description
φ that a [[universal-constructor](pages/universal-constructor.md)] reads.[^1] The hard part
is *access*. In a cellular medium nothing moves, so the design has to answer how a fixed
controller reaches cell n when n has no bound. This page describes von Neumann's answer in
[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)].

## Design

**Bit encoding.** The tape is a horizontal row of cells x₀, x₁, x₂, … . A blank cell (U)
stands for 0 and a quiescent ordinary transmission cell pointing down stands for 1. Both are
quiescent, so the tape is inert while it isn't being read. Beyond some position every cell
is 0, and the tape merges into the blank background.[^2]

**Access by a loop.** Rather than moving the tape or a head, the controller keeps both fixed
and extends a wire to the cell it needs, like a tape whose "head" is the tip of a lengthening
wire.[^3] The *connecting loop* runs from the memory control along the top of the tape to
cell xₙ and back along the bottom. Moving to xₙ₊₁ or xₙ₋₁ means lengthening or shortening
both of its lines by one cell.[^4]

**Reading.** The controller injects 10101 into the loop.[^5]

| Cell holds | What happens at xₙ | Returns |
|---|---|---|
| 0 (blank) | the first four pulses act as a construction code and build a 1 cell | a lone final pulse |
| 1 | every pulse passes through | 10101 |

A discriminator from the [[signal-coding-organs](pages/signal-coding-organs.md)] family
tells the two outputs apart. Reading is **destructive**: the cell always ends up as 1, so
the bit is rewritten afterwards.[^5]

**Writing and moving.** Setting a cell to 0 needs a kill, which means special stimuli. The
controller temporarily converts the loop's upper line from ordinary to special transmission
cells, sends the kill, and converts the line back. Moving the loop likewise re-lays its lines
one cell longer or shorter. The bit is written during the move rather than in a separate
step.[^6] All of this breaks down into 31 fixed operations, each an injection of a short
fixed bit sequence. Sixteen of them must be repeated about n times.[^7]

**Relative addressing.** The controller never stores n. Each cycle moves exactly one cell
left or right, just as a Turing machine's head does.[^8]

**Relative timing.** Repeating an operation about n times needs a delay of about n, and a
finite controller can't count to n either. A second *timing loop* runs parallel to the tape
with length about 2n. A pulse sent round it three times by a triple-return counter gives a
delay of about 6n, which is exactly how long the periodic pulsers need to stay on. **The tape
measures its own length**, so both position and duration are handled relative to the tape.[^9]

**Cost.** The memory control that runs all this is about 547 × 87 cells. Internally it is
wired through a [[coded-channel](pages/coded-channel.md)].[^10]

## Why it matters

- It gives the cellular model **logical universality**. Purely logical automata lack only
  unbounded memory, and the tape supplies it.[^1]
- It is how the universal constructor reads an arbitrary-length description.
- The relative tricks show a general principle: a finite machine can operate on unbounded
  structures as long as every quantity that grows with the structure is measured by the
  structure itself.

## Appearances in Sources

- [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] — the full design: encoding, loops, read/write/move, timing, and layout
- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — the tape as unbounded memory and as the carrier of the universal plan

## Related Concepts

- [[universal-turing-machine](pages/universal-turing-machine.md)] — controller plus cellular tape is a Turing machine
- [[universal-constructor](pages/universal-constructor.md)] — reads its description from this tape
- [[construction-arm](pages/construction-arm.md)] — the same extend-and-retract idea applied to building
- [[signal-coding-organs](pages/signal-coding-organs.md)] — the pulsers, counters, and discriminator used
- [[coded-channel](pages/coded-channel.md)] — wiring inside the memory control
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] — the rule it is built in

[^1]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.112-117 [synthesis] — the external linear array as unbounded memory closing the gap to logical universality, and as the carrier of the universal plan
[^2]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.201, 203 [synthesis] — zero represented by U and one by a quiescent downward ordinary transmission state; the tape is a horizontal sequence of cells whose far end merges into the field of U's
[^3]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.114-115 [synthesis] — editor: rather than moving the tape or the head, a "wire" is extended and contracted to reach the needed square
[^4]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.207-208 [synthesis] — the connecting loop runs from the memory control along the upper side of the tape to xₙ and back along the lower side; moving one square lengthens or shortens both lines
[^5]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.208-209 [synthesis] — injecting 10101: a blank cell is converted to a 1 cell by 1010 and only the last pulse emerges; a 1 cell passes the whole sequence; the discriminator distinguishes; the cell is left as 1 in either case
[^6]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.210-213, 224-226 [synthesis] — altering a cell requires special stimuli, obtained by converting the loop's upper line to special transmission states and back; writing is merged into lengthening and shortening
[^7]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.234-235 [synthesis] — 31 operations, 16 repeated n ± 1 times through periodic pulsers and 15 single injections (Table II)
[^8]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] p.204 [synthesis] — n is not stored; each step changes n by ±1, following Turing
[^9]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.213-214 [synthesis] — the timing loop of length about 2n parallel to the tape; with a triple-return counter it provides a delay of about 6n + 6 for the periodic pulsers
[^10]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] p.243 [synthesis] — editor: memory control 547 cells high and 87 wide, built around a coded channel
