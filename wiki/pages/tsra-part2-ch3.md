---
title: "Theory of Self-Reproducing Automata — Part II, Ch. 3: Design of Some Basic Organs"
category: Sources
summary: Von Neumann's library of basic organs in the 29-state rule — pulsers, decoders, periodic pulsers (flip-flops), the triple-return counter, the 1-vs-10101 discriminator, and the coded channel that solves wire-crossing in 2D
tags: [von-neumann, 29-state, organs, signal-coding, wire-crossing]
sources: [tsra-part2-ch3]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Part II, Ch. 3: Design of Some Basic Organs

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 157–200 (PDF pp. 173–216)
**Date ingested:** 2026-09-24
**Type:** book chapter (von Neumann manuscript, 1952–53, with editorial commentary and corrections)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

## Summary

This chapter starts building the self-reproducing machine inside
[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]. The approach is a small
library of *organs*, each made from simpler ones and each given a name, so that later
chapters can assemble them.[^1] Signals are exact bit patterns in time, where a stimulus
is 1 and its absence is 0. Timing is rigid, so a missing pulse is as meaningful as a
present one.[^2] Although the cellular medium permits unlimited parallelism, the machine
works like a serial computer, with most organs dormant most of the time.[^3]

The organs fall into three groups. The first group turns single pulses into patterns and
patterns back into pulses ([[signal-coding-organs](pages/signal-coding-organs.md)]):

- **Pulsers** turn a single pulse into a pattern.
- **Decoders** fire when a pattern containing a target's 1s arrives.
- **Periodic pulsers** repeat a pattern until stopped, and serve as flip-flops.

The second group is two special-purpose parts for the tape:

- A **triple-return counter** relays a signal out and back through another organ three
  times, keeping count with three flip-flops.[^4]
- A **discriminator** tells a lone pulse from the pattern 10101, which is how a tape bit is
  read.[^5]

The third is the **coded channel**, which solves a problem specific to two dimensions:
wires that have to cross. All signals share one line, and senders and receivers are
matched by codes ([[coded-channel](pages/coded-channel.md)]).[^6]

The editor finds and fixes several slips in von Neumann's designs. They include a missing
row in the decoder, a sizing case for the pulser, and the periodic pulser misbehaving when
"stop" arrives before "start". The editor also simplifies some organs.[^7]

## Key Takeaways

- **Organs are hierarchical.** Complex parts are built from named simpler ones, as in
  circuit design.[^1]
- **Coding and decoding are inverses.** A pulser splits one pulse into delayed copies, and a
  decoder delays copies so that they coincide.[^8]
- **Stopping needs destruction.** The rule has no inhibition, so a repeating loop is
  stopped by killing one of its cells and rebuilding it.[^9]
- **Wire-crossing is solved by coding, not by a new state.** A single shared channel
  carries codes chosen so that none contains another.[^6]

## Entities & Concepts

- [[signal-coding-organs](pages/signal-coding-organs.md)]
- [[coded-channel](pages/coded-channel.md)]
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]

## Relation to Other Wiki Pages

These organs are the building blocks of the tape unit (Ch. 4, [[tsra-part2-ch4](pages/tsra-part2-ch4.md)]) and the constructor's control
(Ch. 5, [[tsra-part2-ch5](pages/tsra-part2-ch5.md)]). They use the transmission, confluent, and kill/build behaviours defined in
[[tsra-part2-ch2](pages/tsra-part2-ch2.md)].

[^1]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] p.158 [synthesis] — organs are constructed successively from simple to more complicated, each composite of previous ones, each given a name and symbol; von Neumann gave algorithms, not minimal designs
[^2]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] p.157 [synthesis] — free vs. rigid timing; rigidly timed sequences written as strings of 1s (stimulus) and 0s (no stimulus); in rigid timing the absence of a stimulus is as definite as its presence
[^3]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.157-158 [synthesis] — editor: the cellular structure allows unlimited parallelism, but the self-reproducing automaton works like a serial computer with most organs quiescent
[^4]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.179-186 [synthesis] — triple-return counter: routes a stimulus through a responding organ three times, using three periodic pulsers as the count memory; used with the tape's connecting loops
[^5]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.187-190 [synthesis] — the 1 vs. 10101 discriminator, used in reading the tape; the editor's simplified version and a general exact-match recognizer
[^6]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.190-194 [synthesis] — in 2D, communication channels must sometimes cross; instead of a crossing primitive, a coded channel: one main line, pulsers at inputs, decoders at outputs, codes of fixed length and fixed number of 1s
[^7]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.161, 172-174, 178, 188 [synthesis] — editorial corrections: pulser height rule, periodic-pulser phasing when stop precedes start, an overlooked decoder row; simplified discriminator
[^8]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.159-160, 175-177 [synthesis] — pulser splits the input into paths of different delays; the decoding organ is very similar, since a pulser is in fact a coder; decoder brings delayed paths into coincidence
[^9]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] p.165 [synthesis] — there is no state expressing inhibition, so stopping is done by changing a cell of the repeater cycle with special stimuli and then restoring it
