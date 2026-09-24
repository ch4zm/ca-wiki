---
title: Self-Reproduction (automata)
category: Concepts
summary: The problem of what logical organization lets an automaton construct a copy of itself — von Neumann's founding question for cellular automata
tags: [concept, self-reproduction, von-neumann, construction]
sources: [tsra-editors-introduction]
created: 2026-09-24
updated: 2026-09-24
---

# Self-Reproduction (automata)

## Description

The self-reproduction problem, as von Neumann posed
it, asks: "What kind of logical organization is sufficient for an automaton to be able to
reproduce itself?"[^1] It is one of the two central problems of his
[[theory-of-automata](pages/theory-of-automata.md)]. The other is reliability. Both are
tied to complexity, because "self-reproduction requires an automaton of considerable
complexity."[^2] The question depends on the
[[complexity-threshold](pages/complexity-threshold.md)]: below a minimum level of
organization, automata cannot make anything as complex as themselves.[^3]

Von Neumann produced two discrete models:

- **Kinematic model** (Part I, Lecture 5 of
  [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]),
  in which parts are assembled physically.
- **Cellular model** (Part II), in which self-reproduction happens inside a homogeneous
  cellular structure.[^4]

He hoped to follow these with a continuous model of self-reproduction.[^5] Burks also
notes that self-reproduction is closely related to self-repair, so results on one were
expected to help with reliability.[^6]

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — states the problem and places it in von Neumann's program

## Related Concepts

- [[complexity-threshold](pages/complexity-threshold.md)] — the level of complexity at which self-reproduction becomes possible
- [[theory-of-automata](pages/theory-of-automata.md)] — the broader program
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the model for von Neumann's universal constructor

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.19 — "What kind of logical organization is sufficient for an automaton to be able to reproduce itself?"
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xvi — "The reliability of components limits the complexity of the automata we can build, and self-reproduction requires an automaton of considerable complexity."
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "He thought, for example, that below a certain level, complexity is degenerative, and self-reproduction is impossible."
[^4]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xvi — "Part II ... treats the logical design of a self-reproducing cellular automaton. Though the shorter Part I is devoted to complicated automata in general, its high point is the kinematic model of self-reproduction (Fifth Lecture)."
[^5]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.27 — "His first models of self-reproduction were discrete, but he hoped later to develop a continuous model of self-reproduction."
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.20 — "It is also to be expected that because of the close relation of self-reproduction to self-repair, results on self-reproduction would help solve the reliability problem."
