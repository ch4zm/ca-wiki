---
title: WireWorld
category: Rules
summary: Brian Silverman's 1987 four-state Moore-neighbourhood rule (empty, electron head, electron tail, conductor) in which all activity runs along fixed wires that can never be built or destroyed; electrons behave like the Generations rule /12/3 on a conductor background, logic gates are tiny, and the Moore-Owen WireWorld computer runs in Golly computing the primes
tags: [rule, multistate, wireworld, circuitry, electrons, turing-complete, silverman]
sources: [lifewiki-wireworld]
created: 2026-09-25
updated: 2026-09-25
---

# WireWorld

## Description

**Origin.** WireWorld is a four-state rule on the range-1
[[moore-neighbourhood](pages/moore-neighbourhood.md)]. Brian Silverman proposed it in 1987
for his program *Phantom Fish Tank*, and A. K. Dewdney's "Computer Recreations" column
(1990) made it widely known. It is built for simulating digital electronic circuits.[^1]

**The rule.**[^2]
- State 0, *empty*: stays empty.
- State 1, *electron head*: becomes an electron tail.
- State 2, *electron tail*: becomes conductor.
- State 3, *conductor*: becomes an electron head if exactly one or two neighbours are
  electron heads, otherwise stays conductor.

**Wires are fixed.** Nothing ever becomes empty, and empty never becomes anything else, so
the layout of wires is fixed for all time. Patterns can change the states of wire cells,
never create, alter or destroy the wires themselves.[^3] This inverts the situation in
[[game-of-life](pages/game-of-life.md)], where circuitry is itself made of live cells and
has to be built and protected (own reasoning).

**Electrons as a Generations rule.** Heads and tails moving through a pure conductor
background behave like the explosive [[generations-rule](pages/generations-rule.md)]
**/12/3**: birth on one or two heads, no survival, one refractory state (the tail).[^2]
The tail is what gives an electron a direction: the conductor behind a head is still a
tail and cannot fire again, so the pulse runs forward (own reasoning). It is the same
refractory mechanism that sets [[brians-brain](pages/brians-brain.md)]'s patterns moving.

**Circuitry.** A wire loop that passes electrons round periodically is an
[[oscillator](pages/oscillator.md)]; a *clock*, a circuit that emits electrons, plays the
part of a [[gun](pages/gun.md)]. Very small, robust logic gates, diodes, triggers and memory
banks can be built, and from them complex computing devices.[^4] Given an infinite tiling
of suitably placed wires, WireWorld is Turing-complete.[^1]

**The WireWorld computer.** David Moore and Mark Owen released a full WireWorld computer in
2004, designed with many others between 1990 and 1992. It has a highly orthogonal RISC
instruction set, a bank of 64 16-bit registers holding program, CPU status and data, and
seven-segment displays driven by running electrons. The version shipped with Golly is
programmed to compute and display the prime numbers.[^5] Life has its own prime generator,
the [[primer](pages/primer.md)], built from glider streams (own reasoning, connecting the
two).

## Appearances in Sources

- [[lifewiki-wireworld](pages/lifewiki-wireworld.md)] - rule, history, and the WireWorld computer

## Related Concepts

- [[generations-rule](pages/generations-rule.md)] - electrons on conductor act like /12/3
- [[brians-brain](pages/brians-brain.md)] - another Silverman rule driven by a refractory state
- [[signal-wire](pages/signal-wire.md)] - Life's analogue: signals running through fixed structures
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] - another rule where signals travel along fixed transmission cells
- [[primer](pages/primer.md)] - Life's prime-number pattern

[^1]: [[lifewiki-wireworld](pages/lifewiki-wireworld.md)] L9 - "WireWorld is a 4-state cellular automaton operating in a range-1 2-dimensional Moore neighborhood. It was first proposed by Brian Silverman in 1987 and included in his program PHANTOM FISH TANK. It became widely known after A. K. Dewdney publicized WireWorld in his \"Computer Recreations\" column. WireWorld is particularly suited for simulating digital electronic circuits. Given an infinite tiling of properly put \"wires\", WireWorld is Turing-complete."; L31 - Dewdney, January 1990, Scientific American 262 (1)
[^2]: [[lifewiki-wireworld](pages/lifewiki-wireworld.md)] L12-22 - states 0 empty, 1 electron head, 2 electron tail, 3 conductor; "conductor → electron head if exactly one or two of the neighboring cells are electron heads, otherwise remains conductor. In other words, patterns composed of state 1 and state 2 cells in a pure state 3 background behave like /12/3, an explosive Generations rule."
[^3]: [[lifewiki-wireworld](pages/lifewiki-wireworld.md)] L10 - "the entire evolution of WireWorld patterns is confined within so-called wires, static structures, which may not be created, modified or destroyed, but may change the state of their cells in a way resembling the behavior of electronic circuits"
[^4]: [[lifewiki-wireworld](pages/lifewiki-wireworld.md)] L7,L10,L24 - "Two WireWorld diodes"; "Oscillators in WireWorld are wire structures that pass \"electrons\" as signals periodically, while clocks, electron-producing circuits, may be considered an analogue of guns."; "WireWorld rules allow to construct very small and robust logic gates, triggers, memory banks etc., from which complex computational devices could be easily built."
[^5]: [[lifewiki-wireworld](pages/lifewiki-wireworld.md)] L25 - "In September 2004 David Moore and Mark Owen released a WireWorld computer, in which the results of calculations are shown in seven-segment displays by running \"electrons\". The computer's instruction set is a highly orthogonal RISC architecture. The program, CPU status and data are stored in a bank of 64 16-bit registers. According to the authors, the computer was designed, with the help of many others, between 1990 and 1992. The version of it included in Golly is preprogrammed to compute and display the sequence of prime numbers."
