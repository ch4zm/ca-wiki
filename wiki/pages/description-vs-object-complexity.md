---
title: Description vs. Object Complexity
category: Concepts
summary: Von Neumann's conjecture that simple automata are easier to describe than to build, but sufficiently complex automata are simpler than any description of their behavior — with Gödel's type-theoretic reading
tags: [concept, complexity, description, godel, von-neumann]
sources: [tsra-lecture-2, tsra-editors-introduction]
created: 2026-09-24
updated: 2026-09-24
---

# Description vs. Object Complexity

## Description

**The conjecture.** Von Neumann claimed that for automata of low complexity, a
description of what the automaton does is simpler than the automaton itself. At high
complication this reverses: "the actual object is simpler than the literary
description."[^1] Put another way, for simple objects it is easier to talk about the
object than to produce it, and easier to predict its properties than to build it. In the
complicated parts of formal logic, it is always an order of magnitude harder to say what
an object can do than to produce it.[^2]

**Motivating example.** His example is visual analogy, such as recognizing "a triangle"
across endlessly varied drawings. It is not clear a priori that there is any simpler
description of what counts as a visual analogy than a description of the visual brain
itself.[^3]

**Consequence for the McCulloch–Pitts theorem.** The theorem that any rigorously
describable behavior can be realized by a network of
[[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]s "simplifies matters
enormously at low complication levels." At high complication its value may run the other
way. It still guarantees that logic can be expressed in networks, but the converse
direction, going from a network to a usable description, may fail.[^4]

**Logical basis: two readings.** Von Neumann attributed the idea, "twisting a logical
theorem a little," to Gödel. His version was that the description of an object is one
logical type higher than the object and therefore "asymptotically (?) infinitely longer
to describe."[^5] Gödel, asked about the passage, identified the relevant result as the
theorem that truth for a language cannot be defined within that language. On that
reading, describing what a mechanism does can require higher types than describing the
mechanism, but "this implies nothing as to the number of symbols necessary." Gödel's
suggested reading instead comes from the
[[universal-turing-machine](pages/universal-turing-machine.md)]. No decision procedure
predicts its behavior, so a complete description of that behavior could only be an
enumeration of all instances, which is infinite, while the machine itself is finite.[^6]

**Connection to universality.** The same pattern appears in the fact that you can build
an automaton that does anything any automaton can do, but not one that predicts whether
an arbitrary automaton will do a given thing. Deciding feasibility belongs to a higher
logical type than the feasible operations themselves.[^7] See
[[complexity-threshold](pages/complexity-threshold.md)] for the related claim that
self-reproduction becomes possible only above a critical complexity.

## Appearances in Sources

- [[tsra-lecture-2](pages/tsra-lecture-2.md)] — von Neumann's primary statement, and Gödel's reply
- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — the editor's summary of the conjecture

## Related Concepts

- [[descriptions-vs-originals](pages/descriptions-vs-originals.md)] — why self-reproducers carry a passive self-description
- [[complexity-threshold](pages/complexity-threshold.md)] — the other claim about behavior changing above a critical complexity
- [[universal-turing-machine](pages/universal-turing-machine.md)] — Gödel's reconstruction runs through undecidability of its behavior
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — the equivalence theorem whose usefulness the conjecture limits

[^1]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.47 — "There is a good deal in formal logics to indicate that the description of the functions of an automaton is simpler than the automaton itself, as long as the automaton is not very complicated, but that when you get to high complications, the actual object is simpler than the literary description."
[^2]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.51 — "it is characteristic of objects of low complexity that it is easier to talk about the object than produce it and easier to predict its properties than to build it. But in the complicated parts of formal logic it is always one order of magnitude harder to tell what an object can do than to produce the object."
[^3]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] pp.46-47 [synthesis] — the triangle / visual-analogy example; "It's absolutely not clear a priori that there is any simpler description of what constitutes a visual analogy than a description of the visual brain"
[^4]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.47 — "The insight that a formal neuron network can do anything which you can describe in words is a very important insight and simplifies matters enormously at low complication levels. It is by no means certain that it is a simplification on high complication levels. It is perfectly possible that on high complication levels the value of the theorem is in the reverse direction"
[^5]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.47 — "I am twisting a logical theorem a little, but it's a perfectly good logical theorem. It's a theorem of Gödel that the next logical step, the description of an object, is one class type higher than the object and is therefore asymptotically (?) infinitely longer to describe."
[^6]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] pp.55-56 [synthesis] — Gödel's letter: the relevant theorem is that "a complete epistemological description of a language A cannot be given in the same language A"; it shows the description needs "higher types. However, this implies nothing as to the number of symbols necessary"; more likely meaning: for the universal Turing machine "the complete description of its behavior is infinite because, in view of the non-existence of a decision procedure predicting its behavior, the complete description could be given only by an enumeration of all instances"
[^7]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.51 — "you can perform within the logical type that's involved everything that's feasible, but the question of whether something is feasible in a type belongs to a higher logical type."

