---
title: "Theory of Self-Reproducing Automata — Part II, Ch. 1: General Considerations"
category: Sources
summary: Von Neumann's heuristic groundwork for the cellular model — five questions (universality through evolution), the move from kinematics to a homogeneous crystalline medium, the description tape, universal construction, self-reproduction by copying descriptions, and mutation
tags: [von-neumann, cellular-automata, self-reproduction, universal-constructor, homogeneity]
sources: [tsra-part2-ch1]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Part II, Ch. 1: General Considerations

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 91–131 (PDF pp. 107–147)
**Date ingested:** 2026-09-24
**Type:** book chapter (von Neumann manuscript, 1952–53, with editorial commentary)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

> Notation follows the wiki convention in [[universal-constructor](pages/universal-constructor.md)],
> not the book's lettering. Several passages are editorial: the survey of von Neumann's five models (pp. 93–99), the
> preview of the 29-state system (pp. 106–108, 111), the description of the tape mechanism
> (pp. 114–116), and the discussion of Richard's paradox (pp. 123–126).

## Summary

Part II sets out to answer five questions rigorously.

- **Logical universality.** When can a class of automata perform every finite logical
  operation?
- **Constructibility.** Can an automaton build another?
- **Construction-universality.** Can one automaton build every automaton?
- **Self-reproduction.** Can an automaton build copies of itself, possibly while also
  doing other tasks?
- **Evolution.** Can construction progress from simpler to more complex or more
  efficient types?

Logical universality is already settled by Turing. The next three are answered
affirmatively. Evolution needs a sharper notion of efficiency. All of this is done within a
rigidly specified kind of automaton with "crystalline regularity", a restriction von
Neumann considers as instructive as the answers.[^1]

To reach that setting he removes, one after another, the features that made the
[[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] model messy.
Geometry and mechanics go first: parts no longer move. Instead, stationary cells switch
between a quiescent state and active states. Next, space becomes a discrete homogeneous
medium in which every cell obeys the same rules. Finally, growth is recast as turning
unexcitable cells into excitable ones, so that empty space is simply cells in a special
state.[^2] The result is the [[cellular-automaton](pages/cellular-automaton.md)]: in its
final form, an infinite square lattice of identical 29-state cells, each connected to its
four neighbours.[^3]

Within that medium the chapter sketches the solution. A linear tape of cells ([[cellular-tape](pages/cellular-tape.md)]), outside
the automaton, supplies unbounded memory, and so logical universality.[^4] Describing
any automaton by its bounding rectangle and the state of every cell gives a universal plan,
and so construction-universality.[^5] Self-reproduction then follows from the
[[universal-constructor](pages/universal-constructor.md)] scheme of Lecture 5:
(A + B + C) + φ(A + B + C).[^6] The key step is copying the *description* instead of the original
([[descriptions-vs-originals](pages/descriptions-vs-originals.md)]).[^7] The chapter closes
with how offspring are positioned and activated
([[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)]), the analogues of genes and mutation, and a
brief look ahead at evolution.[^8][^9]

## Key Takeaways

- **Five questions** frame Part II: universality, constructibility, construction-universality,
  and self-reproduction are answered, and evolution is left open.[^1]
- **Crystalline medium.** Stationary cells, homogeneous rules, and growth as changes of
  state replace moving parts.[^2]
- **Two dimensions suffice.** Three dimensions are usable, two are usable, and one probably
  isn't. Von Neumann uses the square lattice.[^10]
- **The description tape** gives unbounded memory and carries the universal plan.[^4][^5]
- **Copy descriptions, not originals.** A quiescent description can be copied safely,
  while a reactive original cannot.[^7]
- **Genes and mutation.** A self-reproducer with payload P produces P much as a gene
  produces enzymes. Mutations in the P part of the description change the hereditary
  strain.[^9]

## Entities & Concepts

- [[cellular-automaton](pages/cellular-automaton.md)]
- [[descriptions-vs-originals](pages/descriptions-vs-originals.md)]
- [[universal-constructor](pages/universal-constructor.md)]
- [[self-reproduction](pages/self-reproduction.md)]
- [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]

## Relation to Other Wiki Pages

This chapter carries the scheme of [[tsra-lecture-5](pages/tsra-lecture-5.md)] from the
kinematic model into the cellular one. It is also where the
[[cellular-automaton](pages/cellular-automaton.md)] appears as a formal model. Ch. 2 will
supply the actual 29-state transition rule. Moore's formal version of the same cellular
model is [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)].

[^1]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.92-93 [synthesis] — the five main questions; logical universality answered by Turing; constructibility, construction-universality, and self-reproduction to be answered affirmatively; evolution needs a sharper notion of efficiency; all within automata of "crystalline regularity"
[^2]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.102-104, 109 [synthesis] — avoiding geometry, kinematics, and mechanics; stationary quiescent vs. active states; discrete homogeneous medium; growth as transformation of unexcitable cells into excitable ones; the "structure of the vacuum"
[^3]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.94, 106 [synthesis] — editor: infinite array of square cells, each containing the same 29-state automaton connected to its four neighbours; suggested by Ulam
[^4]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.112-114 [synthesis] — an external linear tape with digit, comma, and period states; purely logical automata lack only unbounded memory, and the tape supplies it
[^5]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.116-118 [synthesis] — universal plan: bounding-rectangle coordinates and the state of every cell, encoded on the tape, give construction-universality
[^6]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.118-119 [synthesis] — A universal constructor, B copier of the description, C control; (A + B + C) with its own description attached reproduces itself; adding a payload P to the description also builds P
[^7]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.121-122 [synthesis] — copying requires exploration; a quasi-quiescent description can be explored without disturbance, a reactive original cannot
[^8]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.126-129 [synthesis] — positioning successive descendants to avoid collisions; offspring built quiescent, then activated by a starting stimulus; single-action vs. sequential self-reproduction
[^9]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.130-131 [synthesis] — the self-reproducer with payload compared to a gene producing enzymes; classification of mutations by where they occur; conflicts between organisms as a possible route to natural selection
[^10]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.105 [synthesis] — dimension 3 usable and probably minimal a priori, but 2 is also usable and 1 unlikely to work; maximum regularity chosen (quadratic class in 2D)
