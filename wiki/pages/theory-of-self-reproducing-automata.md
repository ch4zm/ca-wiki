---
title: Theory of Self-Reproducing Automata
category: Sources
summary: Von Neumann's posthumous book (ed. Burks, 1966) — the 1949 Illinois lectures plus the unfinished manuscript designing a 29-state self-reproducing cellular automaton
tags: [book, von-neumann, self-reproduction, cellular-automata, foundational]
sources: [theory-of-self-reproducing-automata, tsra-editors-introduction]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf
**Date ingested:** 2026-09-24 (in progress, one unit at a time)
**Type:** book
**Author / editor:** von Neumann, edited and completed by Burks (University of Illinois Press, 1966)[^5]

> **Locators.** The PDF is an image-only scan (no text layer). Printed page numbers are
> used throughout; PDF page = printed page + 16 (Preface p. xv = PDF p. 12).

## Summary

This book combines two of
Von Neumann's unfinished works on the
[[theory-of-automata](pages/theory-of-automata.md)]:

- **Part I**: the five lectures "Theory and Organization of Complicated Automata," given in
  December 1949 at the University of Illinois. Their high point is a *kinematic* model of
  self-reproduction.
- **Part II**: the manuscript "The Theory of Automata: Construction, Reproduction,
  Homogeneity," begun in fall 1952. It gives the logical design of a self-reproducing
  *cellular* automaton.[^6]

Both parts were left in rough form and were edited by
Burks, who marks his own additions with brackets.[^1]
The Part II manuscript breaks off before the tape unit is finished, and Burks completes
the design in a concluding Chapter 5.[^2]

The book's organizing theme is that the central problems of automata are problems of
complexity. Von Neumann's two main questions were how to build reliable automata from
unreliable parts, and what logical organization is enough for an automaton to reproduce
itself.[^3] See [[self-reproduction](pages/self-reproduction.md)] and
[[complexity-threshold](pages/complexity-threshold.md)].

## Structure and ingest map

Each unit gets its own source page as it is ingested. Printed pages:

| Unit | Pages | Source page |
|---|---|---|
| Preface + Editor's Introduction (Burks) | xv–28 | [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] |
| Part I, Lectures 1–5 | 31–87 | *not yet ingested* |
| Part II, Ch. 1 General Considerations | 91–131 | *not yet ingested* |
| Part II, Ch. 2 A System of 29 States with a General Transition Rule | 132–156 | *not yet ingested* |
| Part II, Ch. 3 Design of Some Basic Organs | 157–200 | *not yet ingested* |
| Part II, Ch. 4 Design of a Tape and Its Control | 201–250 | *not yet ingested* |
| Part II, Ch. 5 [Automata Self-Reproduction] (Burks) | 251–296 | *not yet ingested* |
| Bibliography; Figures 1–56 | 297–378 | — |

## Key Takeaways

- Self-reproduction is modeled twice: kinematically in Part I (Lecture 5), and as a
  cellular automaton in Part II.[^4]
- The text has two layers: von Neumann's own writing (Part I is a reconstruction from a
  poor transcript), and Burks's bracketed commentary and completion.[^1]
- Self-reproduction and reliability are both treated as problems of complexity.[^3]

## Entities & Concepts

- [[theory-of-automata](pages/theory-of-automata.md)]
- [[self-reproduction](pages/self-reproduction.md)]
- [[complexity-threshold](pages/complexity-threshold.md)]
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]

## Relation to Other Wiki Pages

This is the wiki's first source. Its unit pages will be the primary citations for
Von Neumann's cellular model, the universal constructor, and the 29-state transition rule.

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xvii — "Where the writing is strictly my own, it appears in brackets."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xviii — "The construction stops before the tape unit is quite finished. In Chapter 5 I show how to complete the design of von Neumann's self-reproducing automaton."
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xvi — "The two main problems in automata theory that von Neumann concentrated on are both intimately related to complexity. These are the problems of reliability and self-reproduction."
[^4]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xvi — "Part II ... treats the logical design of a self-reproducing cellular automaton. Though the shorter Part I is devoted to complicated automata in general, its high point is the kinematic model of self-reproduction (Fifth Lecture)."
[^5]: raw/von-neumann-theory-of-self-reproducing-automata.pdf title page (PDF pp.1-2) — "JOHN VON NEUMANN edited and completed by Arthur W. Burks ... University of Illinois Press URBANA AND LONDON 1966"
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xv [synthesis] — Burks lists the five automata works; (2) the Illinois lectures of December 1949 are Part I and (4) the manuscript started in fall 1952 is Part II
