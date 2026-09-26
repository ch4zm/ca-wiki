---
title: Initially Quiescent Automaton
category: Concepts
summary: A finite pattern in von Neumann's 29-state CA whose cells all start in one of the 10 quiescent states and which is switched on by a stimulus at its edge — the class of machines a universal constructor can build
tags: [concept, quiescence, construction, von-neumann, 29-state]
sources: [tsra-part2-ch5, tsra-part2-ch1, machine-models-of-self-reproduction]
created: 2026-09-24
updated: 2026-09-26
---

# Initially Quiescent Automaton

## Description

Burks defines an *initially quiescent automaton* as "a finite area of von Neumann's 29-state
cellular structure every cell of which is in 1 of the 10 quiescent states": the blank state
U, the eight quiescent transmission states, or the quiescent confluent state C₀₀. Nothing in
such a pattern changes until a starting stimulus reaches its edge.[^1]

**Why the class matters.** A constructor lays down cells one at a time. A part that became
active as soon as it was placed could interfere with the rest of the construction. Von
Neumann therefore has offspring built entirely quiescent and started only once they are
complete.[^2] The [[universal-constructor](pages/universal-constructor.md)] is exactly
universal for this class: for every initially quiescent automaton M there is a description
φ(M) from which it builds M.[^3]

**A constraint on the design.** Anything that is meant to be built, including the
self-reproducer itself, must be initially quiescent. So organs that depend on running
clocks cannot simply be laid down. The [[crossing-organ](pages/crossing-organ.md)] has
active clocks, and Burks makes it fit by building it with passive cells and having a small
constructing device start its clocks when the machine is switched on.[^4] Both the tape
unit and a universal Turing machine can be built as initially quiescent automata.[^5]

**Not everything is constructible.** Patterns that can be specified at time zero are a
larger class than patterns that can be built. A constructor can build every initially
quiescent automaton and many active ones, but not all active ones. Burks's example is a
3 × 3 block of the sensitized state S₀ surrounded by C₀₀ cells.[^6] Patterns that have no
predecessor at all are [[garden-of-eden](pages/garden-of-eden.md)] configurations. Moore
proved they exist in any structure that has an
[[erasable-configuration](pages/erasable-configuration.md)].[^7]

## Appearances in Sources

- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] — the definition, and its use as the target class for construction
- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] — the Garden-of-Eden theorem
- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — offspring built quiescent and activated by a starting stimulus

## Related Concepts

- [[universal-constructor](pages/universal-constructor.md)] — construction-universal for this class
- [[crossing-organ](pages/crossing-organ.md)] — an organ that must be adapted to meet the constraint
- [[garden-of-eden](pages/garden-of-eden.md)] — an extreme case of non-constructibility
- [[erasable-configuration](pages/erasable-configuration.md)] — Moore's condition forcing Garden-of-Eden patterns
- [[descriptions-vs-originals](pages/descriptions-vs-originals.md)] — quiescence is also what makes descriptions safe to copy
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] — the rule whose 10 quiescent states define the class
- [[construction-arm](pages/construction-arm.md)] - the device that lays down such patterns and starts them
- [[object-synthesis](pages/object-synthesis.md)] - the Life counterpart: building any constructible pattern from gliders
- [[cellular-tape](pages/cellular-tape.md)] - the tape unit can itself be built initially quiescent

[^1]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.264 — "we define an *initially quiescent automaton* to be a finite area of von Neumann's 29-state cellular structure every cell of which is in 1 of the 10 quiescent states U, T_uα0, and C₀₀"
[^2]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.126-129 [synthesis] — secondaries are built quasi-quiescent and started by a single stimulus
[^3]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.286 — "for each initially quiescent automaton M, there is a coded description D(M) of M such that, when D(M) is placed on a tape L attached to M_c, M_c will construct M."
[^4]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.264-265 [synthesis] — crossing organs contain excited states, so MC is modified to contain only passive states initially, with a constructing device that starts each organ's clocks
[^5]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.265, 270 [synthesis] — italicized results: an initially quiescent tape unit with unlimited memory, and an initially quiescent universal Turing machine, can be embedded
[^6]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 [synthesis] — constructible automata are a proper subclass of those specifiable at time zero; a constructor can build every initially quiescent automaton and many active ones; the 3 × 3 sensitized S₀ in C₀₀ is not constructible
[^7]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.26 - "THEOREM 2. For a tessellation structure for which there exist erasable configurations, there exist Garden-of-Eden configurations."
