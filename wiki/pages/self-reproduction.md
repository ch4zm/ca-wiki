---
title: Self-Reproduction (automata)
category: Concepts
summary: The problem of what logical organization lets an automaton construct a copy of itself — von Neumann's founding question for cellular automata
tags: [concept, self-reproduction, von-neumann, construction]
sources: [tsra-editors-introduction, tsra-lecture-5]
created: 2026-09-24
updated: 2026-09-24
---

# Self-Reproduction (automata)

## Description

The self-reproduction problem, as von Neumann posed
it, asks: "What kind of logical organization is sufficient for an automaton to be able to
reproduce itself?"[^1] It is one of the two central problems of his
[[theory-of-automata](pages/theory-of-automata.md)]. The other is reliability ([[probabilistic-logic](pages/probabilistic-logic.md)]). Both are
tied to complexity, because "self-reproduction requires an automaton of considerable
complexity."[^2] The question depends on the
[[complexity-threshold](pages/complexity-threshold.md)]: below a minimum level of
organization, automata cannot make anything as complex as themselves.[^3]

Von Neumann produced two discrete models:

- **Kinematic model** (Part I, Lecture 5 of
  [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]),
  in which parts are assembled physically ([[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)]).
- **Cellular model** (Part II), in which self-reproduction happens inside a homogeneous
  cellular structure.[^4]

He hoped to follow these with a continuous model of self-reproduction.[^5] Burks also
notes that self-reproduction is closely related to [[self-repair](pages/self-repair.md)], so results on one were
expected to help with reliability.[^6]

**How it works.** An automaton builds its offspring from a description rather than by
inspecting itself. A [[universal-constructor](pages/universal-constructor.md)] A builds anything from its description, a copier B duplicates
descriptions, and a controller C coordinates them. Supplied with its own description,
A + B + C produces a copy of itself together with a copy of the description. None of the
three parts reproduces on its own.[^7]

**What counts as self-reproduction.** Naive definitions admit trivial cases such as
growing crystals. Von Neumann proposed requiring the capacity for *inheritable mutation*.
If an extra part D is added to the description, a random change in D is passed on to later
generations. Changes to A, B, or C are usually lethal or leave the offspring unable to
reproduce.[^8]

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — states the problem and places it in von Neumann's program
- [[tsra-lecture-5](pages/tsra-lecture-5.md)] — the kinematic model, the A + B + C scheme, and inheritable mutation

## Related Concepts

- [[complexity-threshold](pages/complexity-threshold.md)] — the level of complexity at which self-reproduction becomes possible
- [[universal-constructor](pages/universal-constructor.md)] — the constructive mechanism
- [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] — the first model
- [[theory-of-automata](pages/theory-of-automata.md)] — the broader program
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the model for von Neumann's universal constructor
- [[probabilistic-logic](pages/probabilistic-logic.md)] — the other central problem; self-repair links the two
- [[self-repair](pages/self-repair.md)] — the closely related capacity to maintain oneself

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.19 — "What kind of logical organization is sufficient for an automaton to be able to reproduce itself?"
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xvi — "The reliability of components limits the complexity of the automata we can build, and self-reproduction requires an automaton of considerable complexity."
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "He thought, for example, that below a certain level, complexity is degenerative, and self-reproduction is impossible."
[^4]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xvi — "Part II ... treats the logical design of a self-reproducing cellular automaton. Though the shorter Part I is devoted to complicated automata in general, its high point is the kinematic model of self-reproduction (Fifth Lecture)."
[^5]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.27 — "His first models of self-reproduction were discrete, but he hoped later to develop a continuous model of self-reproduction."
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.20 — "It is also to be expected that because of the close relation of self-reproduction to self-repair, results on self-reproduction would help solve the reliability problem."
[^7]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.84-86 [synthesis] — A (universal constructor), B (copier), C (control); (A + B + C) + φ(A + B + C) produces a copy of itself; none of A, B, or C is self-reproductive alone
[^8]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.86-87 [synthesis] — self-reproduction is hard to define since crystals qualify naively; requiring inheritable mutation resolves this; mutations in the D part are inherited, those in A, B, or C usually lethal or sterilizing
