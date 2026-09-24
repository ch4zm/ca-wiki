---
title: Complexity Threshold
category: Concepts
summary: Von Neumann's claim that below a critical level of complexity automata can only build simpler things, while above it self-reproduction and growth of complexity become possible
tags: [concept, complexity, self-reproduction, von-neumann]
sources: [tsra-editors-introduction, tsra-lecture-1, tsra-lecture-2]
created: 2026-09-24
updated: 2026-09-24
---

# Complexity Threshold

## Description

Von Neumann held that complexity has a critical level.
Below it, complexity is *degenerative*: an automaton can only produce automata less
complicated than itself, so [[self-reproduction](pages/self-reproduction.md)] is
impossible.[^1] Above it, complexity and organization are no longer degenerative and can
even increase. Burks calls this an analogue of
thermodynamic degeneration within the theory of self-reproducing automata.[^2]

A related claim concerns descriptions: at high complexity, the automaton is simpler than
any description of its behavior. See [[description-vs-object-complexity](pages/description-vs-object-complexity.md)].[^3]

**Threshold for universality.** Turing's universal machine shows the same pattern in
computation. Below a certain minimum complexity, no instructions let an automaton
perform certain operations. At a definite finite point, an automaton given suitable
instructions can do anything any automaton can do.[^4] The self-reproduction threshold
is the counterpart of this for construction.

As a working measure of complexity, von Neumann counts an automaton's basic switching
elements. On that measure the computing machines of 1949 were of order 10⁴, while the
human nervous system is estimated at 10¹⁰ neurons, a size for which "we have absolutely
no experience."[^5]

In von Neumann's view, complexity is the organizing concept of the whole
[[theory-of-automata](pages/theory-of-automata.md)], and it still needed a rigorous
definition.[^6]

The degeneration threshold for self-reproduction is so far reported only second-hand, in
the Editor's Introduction. Von Neumann's own statement is expected in Part I, Lectures 4–5
of [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)].

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — Burks's summary, with the thermodynamic analogy
- [[tsra-lecture-1](pages/tsra-lecture-1.md)] — element count as the working measure of complexity
- [[tsra-lecture-2](pages/tsra-lecture-2.md)] — the minimum complexity for universality

## Related Concepts

- [[self-reproduction](pages/self-reproduction.md)] — becomes possible above the threshold
- [[theory-of-automata](pages/theory-of-automata.md)] — complexity is its central concept
- [[description-vs-object-complexity](pages/description-vs-object-complexity.md)] — the description-side claim about high complexity
- [[universal-turing-machine](pages/universal-turing-machine.md)] — universality also needs a minimum complexity

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "He thought, for example, that below a certain level, complexity is degenerative, and self-reproduction is impossible."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.28 — "he found an analog of thermodynamic degeneration in the theory of self-reproducing automata: below a certain minimum level, complexity and degree of organization are degenerative, but above that level they are not degenerative and may even increase."
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "in the case of simple automata a symbolic description of the behavior of an automaton is simpler than the automaton itself, but that in the case of exceedingly complex automata the automaton is simpler than a symbolic description of its behavior. See the Second Lecture of Part I."
[^4]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.50 — "... a simpler thing will never perform certain operations, no matter what instructions you give it; but there is a very definite finite point where an automaton of this complexity can, when given suitable instructions, do anything that can be done by automata at all."
[^5]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] pp.36-37 [synthesis] — "It is not completely obvious how to measure the complexity of an automaton. For computing machines, probably the reasonable way is to count how many vacuum tubes are involved"; complexity of current machines of order "10 thousand"; human nervous system "estimated to be 10 billion", and "we have absolutely no experience with such orders of magnitude"
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "Von Neumann thought that the chief problems of automata theory center around the concept of complexity. This very concept needs rigorous definition."
