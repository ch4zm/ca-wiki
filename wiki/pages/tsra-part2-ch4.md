---
title: "Theory of Self-Reproducing Automata — Part II, Ch. 4: Design of a Tape and Its Control"
category: Sources
summary: Von Neumann's design of an unbounded tape inside the 29-state CA — bit encoding, connecting and timing loops, destructive reads, relative addressing and timing, the 31 loop-moving operations, and the memory-control layout, with the editor's corrections
tags: [von-neumann, 29-state, tape, memory-control, turing-machine, engineering]
sources: [tsra-part2-ch4]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Part II, Ch. 4: Design of a Tape and Its Control

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 201–250 (PDF pp. 217–265)
**Date ingested:** 2026-09-24
**Type:** book chapter (von Neumann manuscript, 1952–53, with editorial commentary and corrections)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

> The chapter abstract (§4.1.1), the layout summary (§4.3.1), and the corrections to organ
> sizes and the control organ are editorial. From around printed p. 236 the PDF offset
> becomes 15 instead of 16.

## Summary

Ch. 4 builds the memory half of the [[universal-constructor](pages/universal-constructor.md)]:
an indefinitely extendible tape embedded in
[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)], together with the machinery
that reads it, writes it, and moves along it ([[cellular-tape](pages/cellular-tape.md)]).[^1]

Von Neumann's starting point is that a general logical automaton has two parts. One is a
finite switching network, which is easy to build. The other is an arbitrarily large
external memory with the network needed to use it, and that is the hard part.[^2] The
chapter solves the hard part with five units:

| Unit | Role |
|---|---|
| **Tape** | a horizontal row of cells storing bits: blank = 0, a quiescent downward wire cell = 1 |
| **Connecting loop** | a wire from the memory control along the top of the tape to cell xₙ and back along the bottom; used to read and write xₙ |
| **Timing loop** | a second, parallel loop whose length tracks n; used to time how long repeated operations run |
| **Memory control** | executes read / write / move commands on the tape and loops |
| **Constructing unit** | a finite-state controller that issues those commands |

The complete universal constructor is the constructing unit plus the memory control, tape,
and the two loops.[^1]

## Engineering

**Relative addressing.** The index n of the cell being scanned has no upper bound, so it
cannot be held inside a finite control. Every step therefore moves n by exactly ±1, as in
Turing's machine.[^3] The constructing unit is specified as a finite automaton with three
functions of its state and the bit just read: the next state, the bit to write back, and the
direction to move. A subset of its states triggers the next memory cycle. The constructing
unit together with the tape is thus a Turing machine laid out in cells.[^4]

**The read cycle.** The memory control sends the probe 10101 into the connecting loop. At
cell xₙ:[^5]

- If xₙ is **0** (blank), the first four pulses 1010 act as a construction code. They step
  the cell through the sensitized states and turn it into a 1 cell, and only the last pulse
  emerges from the loop.
- If xₙ is **1**, every pulse passes through and the full 10101 emerges.

A 1-vs-10101 discriminator then reports "zero" or "one" to the constructing unit. Either way
the cell ends up as 1, so reading is destructive and the correct bit has to be written
back.[^5]

**Writing and moving.** Turning a 1 back into 0 needs special stimuli at xₙ. The memory
control gets them there by temporarily converting the upper line of the connecting loop
from ordinary to special transmission cells, firing a kill, and converting the line back.
Each conversion is a fixed short sequence that must be injected once per cell of the line,
so about n times.[^6] Writing is merged into moving: the bit is set while the loop is being
lengthened or shortened by one cell, instead of in a separate pass.[^7]

**Relative timing: the timing loop.** An operation that must repeat about n times is driven
by a periodic pulser that stays on for about 6n steps. The finite control can't count to n,
so the tape supplies the count. The timing loop runs parallel to the tape with length about
2n, and a pulse sent round it three times by a triple-return counter takes about 6n + 6
steps. Fixed leftover delays are absorbed by adjustable delay paths inside the memory
control.[^8] Addressing and timing are both handled relative to the tape rather than stored
in the control.

**The operation catalogue.** Moving the head one cell means lengthening or shortening both
loops. Von Neumann works out every step as injections of fixed sequences into the loops'
four inputs. This gives **31 operations**: 16 are repeated n ± 1 times through periodic
pulsers timed by the triple-return counters, and 15 are single injections. The editor
tabulates them (Tables II–V).[^9]

**Memory-control layout.** The memory control is roughly **547 cells high × 87 wide**. It
has three main parts:[^10]

- a *read-write-erase unit*: the pulsers, periodic pulsers, two triple-return counters, and
  the discriminator attached directly to the loops;
- its *control*: 16 control organs, one for each repeated operation, each holding a
  flip-flop that remembers what follow-up move comes next;
- a [[coded-channel](pages/coded-channel.md)] linking them, since about 30 lines between the
  read-write-erase unit and its control would otherwise have to cross.

A delay area supplies the roughly 2000-step waits needed while a signal travels the full
round trip before a periodic pulser can be switched off.[^10]

**Corrections.** Von Neumann sized the coded channel with 9-bit codes containing 5 ones
(70 codes), but underestimated how tall the decoders for such codes are. He gave one
section of the channel a height of 239 cells when it actually needs over 300. The editor switches to 9-bit
codes with 4 ones (56 codes, still enough) and recomputes the dimensions. The editor also
corrects the control-organ design in four respects, including a case where a flip-flop
would be damaged by a stop signal arriving while it is inactive.[^11]

## Key Takeaways

- **Tape plus finite control is a Turing machine in the CA.** It supplies the unbounded
  memory needed for logical universality.[^4]
- **Relative addressing and relative timing.** The finite control stores neither n nor time
  proportional to n. The tape measures both.[^3][^8]
- **Destructive reads.** Reading always turns the cell into a 1, so every read is paired with
  a rewrite.[^5]
- **Moving the head means rebuilding wires.** Each ±1 move re-lays both loops using
  ordinary/special conversions.[^6]
- **Scale.** The memory control alone is about 47,000 cells (547 × 87).[^10]

## Entities & Concepts

- [[cellular-tape](pages/cellular-tape.md)]
- [[universal-constructor](pages/universal-constructor.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]
- [[signal-coding-organs](pages/signal-coding-organs.md)]
- [[coded-channel](pages/coded-channel.md)]

## Relation to Other Wiki Pages

The chapter assembles the organs of [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] into a
working memory. The manuscript stops a little later, before the constructing unit is
designed. Ch. 5 completes the design.

[^1]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.201-202 [synthesis] — editor's abstract: tape, connecting loop, timing loop, memory control, constructing unit; the universal constructor is the constructing unit plus memory control, tape, and both loops
[^2]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.202-203 [synthesis] — a general logical automaton = a network for propositional functions plus an arbitrarily large external memory and its control; the first part is easy, the second is the tape
[^3]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] p.204 [synthesis] — n cannot be held inside the finite automaton; "relative" specification: each new n differs from the previous one by ±1, citing Turing
[^4]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.205-206 [synthesis] — the constructing unit as a finite automaton with next-state, write-value, and move functions of its state and the bit read, plus a subset of states that start the memory control
[^5]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.207-209 [synthesis] — reading by injecting 10101 into the connecting loop; a blank cell is converted to a 1 by the first four pulses and only the last emerges; a 1 cell passes the whole sequence; the discriminator distinguishes the two; the cell is always left as 1
[^6]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.210-213 [synthesis] — altering a cell needs special stimuli; the upper line of the connecting loop is converted to special transmission cells and back by injecting fixed sequences n times
[^7]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.224-226 [synthesis] — the alteration of xₙ is merged into the lengthening and shortening procedures rather than done separately
[^8]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.213-216 [synthesis] — the timing loop parallel to the tape; with a triple-return counter its round trip gives a delay of about 6n; fixed excess delays compensated inside the memory control
[^9]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.216-237, 248-249 [synthesis] — lengthening and shortening procedures; 31 operations, 16 repeated via periodic pulsers and 15 single; editor's Tables II–V
[^10]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.226-228, 243 [synthesis] — editor: memory control 547 × 87 cells; read-write-erase unit and its control of 16 control organs, each with a flip-flop; coded channel; delay area for about 2000 units
[^11]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.239-246 [synthesis] — coded-channel sizing with m = 9, k = 5; editor finds the decoder height underestimated and switches to k = 4 (56 codes); editor's four corrections to the control organ, including flip-flop damage by an unwanted stop stimulus
