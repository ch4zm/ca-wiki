---
title: Complexity Threshold
category: Concepts
summary: Von Neumann's claim that below a critical level of complexity automata can only build simpler things, while above it self-reproduction and growth of complexity become possible
tags: [concept, complexity, self-reproduction, von-neumann]
sources: [tsra-editors-introduction, tsra-lecture-1]
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

A related claim concerns descriptions. For simple automata, a symbolic description of
the behavior is simpler than the automaton itself. For exceedingly complex automata, the
automaton is simpler than a symbolic description of its behavior.[^3]

As a working measure of complexity, von Neumann counts an automaton's basic switching
elements. On that measure the computing machines of 1949 were of order 10⁴, while the
human nervous system is estimated at 10¹⁰ neurons, a size for which "we have absolutely
no experience."[^4]

In von Neumann's view, complexity is the organizing concept of the whole
[[theory-of-automata](pages/theory-of-automata.md)], and it still needed a rigorous
definition.[^5]

The Editor's Introduction reports these claims second-hand. Von Neumann's own statement
is in Part I (Lectures 2, 4, and 5) of
[[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)],
which this wiki has not ingested yet.

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — Burks's summary, with the thermodynamic analogy
- [[tsra-lecture-1](pages/tsra-lecture-1.md)] — element count as the working measure of complexity

## Related Concepts

- [[self-reproduction](pages/self-reproduction.md)] — becomes possible above the threshold
- [[theory-of-automata](pages/theory-of-automata.md)] — complexity is its central concept

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "He thought, for example, that below a certain level, complexity is degenerative, and self-reproduction is impossible."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.28 — "he found an analog of thermodynamic degeneration in the theory of self-reproducing automata: below a certain minimum level, complexity and degree of organization are degenerative, but above that level they are not degenerative and may even increase."
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "in the case of simple automata a symbolic description of the behavior of an automaton is simpler than the automaton itself, but that in the case of exceedingly complex automata the automaton is simpler than a symbolic description of its behavior. See the Second Lecture of Part I."
[^4]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] pp.36-37 [synthesis] — "It is not completely obvious how to measure the complexity of an automaton. For computing machines, probably the reasonable way is to count how many vacuum tubes are involved"; complexity of current machines of order "10 thousand"; human nervous system "estimated to be 10 billion", and "we have absolutely no experience with such orders of magnitude"
[^5]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "Von Neumann thought that the chief problems of automata theory center around the concept of complexity. This very concept needs rigorous definition."
