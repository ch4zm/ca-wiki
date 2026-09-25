---
title: "Theory of Self-Reproducing Automata — Part II, Ch. 2: A System of 29 States with a General Transition Rule"
category: Sources
summary: Von Neumann's derivation of the 29-state cellular automaton — transmission, confluent, unexcitable, and sensitized states; ordinary vs. special stimuli; direct (construction) and reverse (destruction) processes; plus the editor's growing-line and construction-arm examples
tags: [von-neumann, cellular-automata, 29-state, transition-rule, construction]
sources: [tsra-part2-ch2]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Part II, Ch. 2: A System of 29 States with a General Transition Rule

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 132–156 (PDF pp. 148–172)
**Date ingested:** 2026-09-24
**Type:** book chapter (von Neumann manuscript, 1952–53, with editorial commentary)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

> §2.8.3 (pp. 151–156), the illustrations of the rule, is editorial. Notation is simplified
> to the wiki's own; see [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)].

## Summary

This chapter builds the first concrete model that can do everything Ch. 1 asked of the
[[cellular-automaton](pages/cellular-automaton.md)]: logic, universal construction, and
self-reproduction. It uses a square lattice in which each cell sees its four orthogonal
neighbours. A cell's next state is a function of its own state and theirs at the previous
step. With N states there are N^(N⁵) possible rules, so for N = 29 the space of rules is
astronomically large. Von Neumann derives the specific rule step by step, adding each kind
of state only when a needed function calls for it.[^1]

The states fall into two jobs. **Logic** is carried by *ordinary* stimuli moving through
directed transmission cells (wires and OR) and confluent cells (AND, splitting, delay).
**Construction** is carried by *special* stimuli, which convert the blank state U into
working cells (the direct process) and kill working cells back to U (the reverse process).
Construction goes through a short binary code that passes through 8 *sensitized* states. In
total there are 16 transmission, 4 confluent, 1 unexcitable, and 8 sensitized states,
making 29 ([[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]).[^2]

The editor's closing section shows the rule at work. A small storage loop that endlessly
feeds a construction code grows a line to the right forever. A technique of building a
distant cell and then retracting the path that built it
([[construction-arm](pages/construction-arm.md)]) lets a fixed device build any finite
quiescent pattern from two binary input strings.[^3]

## Key Takeaways

- **Five-cell neighbourhood.** Each cell's update depends only on itself and its four
  orthogonal neighbours.[^1]
- **Logic from wires.** OR comes from transmission cells with several inputs, AND from
  confluent cells. Negation has no state of its own and is done by destroying a path and
  rebuilding it.[^4]
- **Two stimulus classes.** Ordinary stimuli compute, special stimuli build and destroy, and
  each class can kill the other.[^5]
- **Construction as a code.** A blank cell becomes one of 9 quiescent types according to a
  3–4-bit sequence of stimuli, passing through sensitized states on the way.[^6]
- **Timing.** The square lattice only gives even path-length differences, so confluent
  cells carry a one-step memory that supplies odd delays.[^7]
- **Unbounded growth and the construction arm.** A loop can grow a line forever, and any
  finite pattern can be built remotely by a fixed device.[^3]

## Entities & Concepts

- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]
- [[construction-arm](pages/construction-arm.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]
- [[universal-constructor](pages/universal-constructor.md)]

## Relation to Other Wiki Pages

This chapter makes the abstract model of [[tsra-part2-ch1](pages/tsra-part2-ch1.md)]
concrete. The construction-arm result shows why the
[[universal-constructor](pages/universal-constructor.md)] needs a self-description: a fixed
builder is always bigger than what it builds. Ch. 3 designs the basic organs out of these
states.

[^1]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.132-134 [synthesis] — quadratic lattice; the four nearest neighbours chosen over eight for simplicity; the next state is a function of the cell's and its four neighbours' states at t−1; N^(N⁵) possible rules
[^2]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.148-149 [synthesis] — summary list of states: 16 transmission, 4 confluent, 1 unexcitable, 8 sensitized, N = 29; 29^(29⁵) ≈ 10^(59,000,000) possible rules
[^3]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.153-156 [synthesis] — editor: a storage loop feeding a construction code yields a line growing without limit; two input channels build a remote cell and retract the constructing path; any finite quiescent array can be built by a fixed device fed two binary sequences, the device always being larger
[^4]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.136-138 [synthesis] — transmission cells with several inputs act as + (OR) neurons; confluent cells need all incoming transmission cells excited (· neuron); negation is not represented by a state but synthesized from the reverse and direct processes
[^5]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.139-142 [synthesis] — ordinary vs. special stimuli; special stimuli kill ordinary transmission and confluent cells to U, ordinary stimuli kill special transmission cells; the two classes are dual
[^6]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.142-145 [synthesis] — the direct process: U is converted to one of nine quiescent states by binary-coded stimulus sequences of length 3–4, passing through the sensitized states
[^7]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.146-148 [synthesis] — in the quadratic lattice path differences between two points are even; a single delay is introduced by giving confluent states a one-step memory (four confluent states instead of two)
