---
title: "Theory of Self-Reproducing Automata — Preface and Editor's Introduction"
category: Sources
summary: Burks's preface and introduction to von Neumann's automata book — the program of a logical theory of automata, the two core problems (reliability, self-reproduction), and the complexity threshold
tags: [von-neumann, burks, theory-of-automata, self-reproduction, complexity]
sources: [tsra-editors-introduction]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Preface and Editor's Introduction

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. xv–xix and 1–28 (PDF pp. 12–16, 17–44)
**Date ingested:** 2026-09-24
**Type:** book section (editorial front matter)
**Author:** Burks (1965)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

## Summary

Burks's front matter does two things. It explains how the book was put together, and it
reconstructs von Neumann's overall program for a [[theory-of-automata](pages/theory-of-automata.md)].
Von Neumann meant this to be a mathematical and logical theory covering both natural
systems and artificial computers.[^1] Burks traces the theory back to von Neumann's
computer design work, especially his use of idealized switch-delay elements modeled on
the [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]. Those elements let a
machine's logical design be treated separately from its physical realization, which
Burks calls "a step in the direction of a theory of automata."[^2]

On Burks's account, the theory's core is two questions: how reliable systems can be
built from unreliable components, and what logical organization is sufficient for an
automaton to reproduce itself.[^3] Both are questions about complexity.[^4] Von Neumann
argued that below a certain level, complexity is "degenerative" and self-reproduction is
impossible, while above it organization need not degrade and can even grow. Burks
presents this as the automata analogue of thermodynamic degeneration (see
[[complexity-threshold](pages/complexity-threshold.md)]).[^5]

The introduction also sets out what kind of mathematics von Neumann wanted. The logic
of automata was to be close to logic and to Turing's theory of computability. The
[[universal-turing-machine](pages/universal-turing-machine.md)] is the model behind his
later universal constructor.[^6] But he found all-or-none formal logic inadequate and
wanted a theory that would lean on probability, thermodynamics, and analysis.[^7] In line
with this, his self-reproduction models were discrete, but he hoped eventually to build
a continuous one.[^8]

## Key Takeaways

- **Two problems, one theme.** Reliability and [[self-reproduction](pages/self-reproduction.md)]
  are the two main problems of the theory, and both come down to complexity.[^4]
- **Complexity threshold.** Below a critical level of complexity, automata can only build
  simpler things. Above it, self-reproduction and growth in complexity become possible.[^5]
- **Symbolic description vs. automaton.** Von Neumann suggested that for simple automata a
  symbolic description of the behavior is simpler than the automaton, but for extremely
  complex automata the automaton is simpler than any description of its behavior.[^9]
- **Discrete first, continuous hoped for.** The kinematic and cellular models are
  discrete, but von Neumann wanted the mathematics of automata to move toward the
  continuous.[^8]
- **Editorial layering.** Part I is Burks's reconstruction of a poorly transcribed lecture
  series. Part II is a first-draft manuscript with design errors, and it stops before the
  tape unit is finished. Burks's additions are bracketed, and his Chapter 5 completes the
  design.[^10]

## Entities & Concepts

- [[theory-of-automata](pages/theory-of-automata.md)]
- [[self-reproduction](pages/self-reproduction.md)]
- [[complexity-threshold](pages/complexity-threshold.md)]
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]

## Relation to Other Wiki Pages

This is the framing unit of [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)].
It names the questions that Part I, Lecture 5 (the kinematic model) and Part II (the
cellular model) answer. Its account of the complexity threshold is second-hand (Burks
summarizing von Neumann); the primary statement is in Part I, Lectures 4–5.

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xv — "He envisaged a systematic theory which would be mathematical and logical in form and which would contribute in an essential way to our understanding of natural systems (natural automata) as well as to our understanding of both analog and digital computers (artificial automata)."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.9-10 — "When designing the ENIAC, we developed logical design rules, but these were inextricably tied in with rules governing circuit design. With idealized computing elements one can distinguish the purely logical (memory and truth-functional) requirements for a computer from the requirements imposed by the state of technology ... Second, the use of idealized computing elements is a step in the direction of a theory of automata."
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.19 — "How can reliable systems be constructed from unreliable components? What kind of logical organization is sufficient for an automaton to be able to reproduce itself?"
[^4]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xvi — "The reliability of components limits the complexity of the automata we can build, and self-reproduction requires an automaton of considerable complexity."
[^5]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.28 — "he found an analog of thermodynamic degeneration in the theory of self-reproducing automata: below a certain minimum level, complexity and degree of organization are degenerative, but above that level they are not degenerative and may even increase."
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.14, 25 [synthesis] — Burks ties automatic programming to Turing's universal machine ("a finite automaton with an indefinitely expandable tape"), and notes that via Gödel and Turing "mathematical logic may be treated from the point of view of automata"
[^7]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.19, 25-26 [synthesis] — formal logic "not adequate to serve as 'the' logic of automata"; the new logic "will strongly resemble and interconnect with probability theory, thermodynamics, and information theory"; automata mathematics "should be closer to the continuous and should draw heavily on analysis"
[^8]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.27 — "In his own work in automata theory von Neumann moved from the discrete toward the continuous. ... His first models of self-reproduction were discrete, but he hoped later to develop a continuous model of self-reproduction."
[^9]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "in the case of simple automata a symbolic description of the behavior of an automaton is simpler than the automaton itself, but that in the case of exceedingly complex automata the automaton is simpler than a symbolic description of its behavior."
[^10]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.xvi-xviii [synthesis] — Illinois lecture recording and typescript "turned out badly, with gaps in the text"; the Part II manuscript "seems to have been a first draft," "contained many errors," and "is incomplete"; editorial additions including Ch. 5 "are in brackets"
