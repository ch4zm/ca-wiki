---
title: "Theory of Self-Reproducing Automata — Part I, Lecture 1: Computing Machines in General"
category: Sources
summary: Von Neumann's first Illinois lecture (1949) — computing machines as the tractable case of complicated automata, element count as a measure of complexity, and the switching/memory anatomy of automata
tags: [von-neumann, theory-of-automata, complexity, memory]
sources: [tsra-lecture-1]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Part I, Lecture 1: Computing Machines in General

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 31–41 (PDF pp. 47–57)
**Date ingested:** 2026-09-24
**Type:** book section (reconstructed lecture, December 1949)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

> The lecture text was reconstructed from a poor transcript. Bracketed passages are the
> editor's paraphrase, and the unbracketed text is also heavily edited.[^1]

## Summary

The first lecture sets the agenda for the series: the behavior of very complicated
automata, and the difficulties that high complication causes. Von Neumann proposes to
compare artificial automata with organisms, treated as natural automata, and to sort
their differences into those due to our lack of skill and those that are matters of
principle.[^2] He starts with computing machines because, of all highly complex automata,
they are the ones we are most likely to understand: their complication is high, but they
are basically mathematical objects. He also states that the theory needed for such
automata does not yet exist.[^3]

Most of the lecture is about computing practice. It covers the heuristic value of
computing for nonlinear problems, analog versus digital machines, and questions of speed
and memory. This page records only the parts that concern the abstract
[[theory-of-automata](pages/theory-of-automata.md)].

The first of these is complexity. As a working measure, von Neumann proposes counting an
automaton's basic switching elements. On that measure the machines of his day were of
order 10⁴, while the human nervous system is estimated at 10¹⁰ neurons. We have no
experience at all with automata of that size.[^4] The second is the anatomy of an
automaton. Every automaton has an active switching part and a memory, and in both
computers and nervous systems the switching part is the simpler of the two.[^5] The
third is how to measure memory: Burks reconstructs von Neumann's proposal as the base-2
logarithm of the number of possible configurations.[^6]

## Key Takeaways

- **Computers are the tractable case.** They are the highly complex automata we are best
  placed to understand, because they are mathematical objects.[^3]
- **Complexity measured by element count.** A first, crude measure of an automaton's
  complexity is its number of switching elements. On this measure natural automata
  exceed artificial ones by roughly six orders of magnitude.[^4]
- **Switching part plus memory.** Every automaton splits into an active switching part
  and a memory, and the memory is the harder part.[^5]
- **Memory capacity as information.** Capacity is measured by log₂ of the number of
  configurations (per the editor's paraphrase).[^6]
- **A theory is missing.** The lecture's main conclusion is that a theory of complicated
  automata is badly needed and does not yet exist.[^3]

## Entities & Concepts

- [[theory-of-automata](pages/theory-of-automata.md)]
- [[complexity-threshold](pages/complexity-threshold.md)]

## Relation to Other Wiki Pages

This lecture gives the first concrete measure of complexity (element count). That is the
quantity behind the [[complexity-threshold](pages/complexity-threshold.md)], which is
stated in later lectures. It also makes concrete the comparison of natural and artificial
automata described in [[tsra-editors-introduction](pages/tsra-editors-introduction.md)].

[^1]: raw/von-neumann-theory-of-self-reproducing-automata.pdf Part I Editorial Note (PDF p.46) — "The editor's writing is in brackets. The reconstructed edition of von Neumann's work is not bracketed, but much of the unbracketed text is heavily edited."
[^2]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] p.32 — "I will talk about automata—the behavior of very complicated automata and the very specific difficulties caused by high complication. ... We must consider the similarities, the dissimilarities, the extent to which the dissimilarities are due to our skill or clumsiness (the latter being the more normal phenomenon), and the extent to which these dissimilarities are really matters of principle."
[^3]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] p.32 — "Of all automata of high complexity, computing machines are the ones which we have the best chance of understanding. In the case of computing machines the complications can be very high, and yet they pertain to an object which is primarily mathematical and which we understand better than we understand most natural objects. ... one of our main conclusions is that we need very badly a theory which we do not at this moment possess."
[^4]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] pp.36-37 [synthesis] — "It is not completely obvious how to measure the complexity of an automaton. For computing machines, probably the reasonable way is to count how many vacuum tubes are involved"; "the order of magnitude of the complexity of these machines is 10 thousand"; nerve cells in the human central nervous system "estimated to be 10 billion", and "we have absolutely no experience with such orders of magnitude"
[^5]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] p.39 — "all these automata really consist of two important parts: the general switching part (an active part which affects the logical operations the automaton is supposed to perform), and the memory ... Hence in both the computer and the human nervous system, the dynamic part (the switching part) of the automaton is simpler than the memory."
[^6]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] p.40 — "Von Neumann next discussed how to measure memory capacity. He suggested using the logarithm (to the base two) of the configuration number (i.e., the number of alternatives)."
