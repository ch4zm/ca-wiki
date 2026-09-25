---
title: "Theory of Self-Reproducing Automata — Part I, Lecture 5: Re-evaluation of the Problems of Complicated Automata — Problems of Hierarchy and Evolution"
category: Sources
summary: Von Neumann's fifth Illinois lecture (1949) — the kinematic model, the complexity threshold for synthesis, the A + B + C universal-constructor scheme for self-reproduction, and inheritable mutation
tags: [von-neumann, self-reproduction, universal-constructor, kinematic-model, complexity, evolution]
sources: [tsra-lecture-5]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Part I, Lecture 5: Problems of Hierarchy and Evolution

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 74–87 (PDF pp. 90–103)
**Date ingested:** 2026-09-24
**Type:** book section (reconstructed lecture, December 1949, with editorial commentary)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

> The description of the parts (pp. 80–82) is editorial, reconstructed from von Neumann's
> June 1948 lectures at the Institute for Advanced Study.

## Summary

This lecture is the high point of Part I. So far every automaton considered has produced
outputs quite unlike itself: marks on a tape, or pulses. Von Neumann now turns to automata
whose outputs are automata. His setting is the
[[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] model: an automaton
floating in a medium with an unlimited supply of elementary parts, which it picks up and
assembles.[^1]

He first poses a paradox. Organisms reproduce and, over evolutionary time, become more
complex. Yet an automaton that builds another seems to need a complete description of its
product, so builders would always be more complex than what they build. His resolution is
the [[complexity-threshold](pages/complexity-threshold.md)]. Below a critical size,
synthesis is degenerative. Above it, an automaton can build others as complex as itself or
more so.[^2]

He then shows how self-reproduction works above the threshold, with the
[[universal-constructor](pages/universal-constructor.md)] scheme. A universal constructor
A builds any automaton from its description, a copier B duplicates descriptions, and a
controller C coordinates the two. Supplied with its own description, A + B + C produces a
copy of itself with a copy of the description attached.[^3] Adding an arbitrary component
P to the description gives an automaton that reproduces and also makes P. A random change
in the P part of the description is inherited by later generations, which gives a
primitive form of inheritable mutation.[^4]

## Key Takeaways

- **Automata that make automata.** The core question moves from computing to constructing,
  in a medium of freely available parts.[^1]
- **Threshold for synthesis.** Below a critical complexity, construction degenerates. Above
  it, construction can produce equal or greater complexity. Von Neumann guesses the
  critical number of parts is large, perhaps in the millions.[^2]
- **Build from descriptions.** It is easier to build from a logical description than to copy
  an existing object. This is Turing's trick transferred to construction.[^5]
- **A + B + C + φ(A + B + C).** Constructor, copier, and controller together self-reproduce,
  though none of them does so alone.[^3]
- **Heredity.** Changes to the payload P in the description are inherited. Von Neumann
  suggests the capacity for inheritable mutation as what distinguishes real
  self-reproduction from trivial cases such as crystal growth.[^4]

## Entities & Concepts

- [[universal-constructor](pages/universal-constructor.md)]
- [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)]
- [[self-reproduction](pages/self-reproduction.md)]
- [[complexity-threshold](pages/complexity-threshold.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]

## Relation to Other Wiki Pages

This lecture gives the primary statement of the
[[complexity-threshold](pages/complexity-threshold.md)] for self-reproduction, which
[[tsra-editors-introduction](pages/tsra-editors-introduction.md)] summarizes. It carries the
[[universal-turing-machine](pages/universal-turing-machine.md)] over from computation to
construction. Its kinematic model is the forerunner of the cellular model in Part II.

[^1]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.74-75 [synthesis] — Turing machines, neural nets, and computers all produce outputs unlike themselves; the broader view considers automata whose outputs are like themselves, built by picking up parts from an unlimited supply
[^2]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.78-80 [synthesis] — the paradox of degenerative synthesis versus organic reproduction and evolution; resolved by a minimum complexity below which synthesis degenerates and above which it "can become explosive"; the minimum is probably in the millions of parts
[^3]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.84-86 [synthesis] — definitions of A, B, and C; with X = A + B + C, the system (A + B + C) + φ(A + B + C) produces a copy of itself; none of A, B, or C is self-reproductive alone
[^4]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.86-87 [synthesis] — the payload by-product; mutations in A, B, or C are usually lethal or sterilizing, while a mutation in the payload part is inherited; inheritable mutation proposed as a criterion for self-reproduction
[^5]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.83-84 [synthesis] — constructing from a description is simpler than copying an object; the approach is compared to Turing's trick with universal automata
