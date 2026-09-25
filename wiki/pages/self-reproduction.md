---
title: Self-Reproduction (automata)
category: Concepts
summary: The problem of what logical organization lets an automaton construct a copy of itself — von Neumann's founding question for cellular automata
tags: [concept, self-reproduction, von-neumann, construction]
sources: [tsra-editors-introduction, tsra-lecture-5, tsra-part2-ch1, tsra-part2-ch2, tsra-part2-ch5, machine-models-of-self-reproduction]
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
  cellular structure, a [[cellular-automaton](pages/cellular-automaton.md)].[^4]

The cellular model is carried out in [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]. Even simple patterns in it can grow without
limit: a small loop that recirculates a construction code extends a line forever.[^5]

He hoped to follow these with a continuous model of self-reproduction.[^6] Burks also
notes that self-reproduction is closely related to [[self-repair](pages/self-repair.md)], so results on one were
expected to help with reliability.[^7]

**How it works.** An automaton builds its offspring from a description rather than by
inspecting itself. A [[universal-constructor](pages/universal-constructor.md)] A builds anything from its description, a copier B duplicates
descriptions, and a controller C coordinates them. Supplied with its own description,
A + B + C produces a copy of itself together with a copy of the description. None of the
three parts reproduces on its own.[^8]

**Carried out.** Burks completes the cellular model in Ch. 5. The universal constructor is
extended to give each offspring a tape holding a copy of the description, and to start it.
Fed its own description, it builds a copy of itself with that tape. "Hence, a
self-reproducing automaton can be embedded in von Neumann's 29-state cellular
structure."[^9] With a universal Turing machine as the payload, the offspring can compute
as well. Burks's closing line: "self-reproduction is a special case of construction, and
construction and computation are similar activities."[^10] Everything built this way
starts as an [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)].

**Copying the description.** The copier works on a quiescent description, never on the
live automaton, which could not be probed without disturbing it. This separation is what
makes non-degenerating reproduction possible ([[descriptions-vs-originals](pages/descriptions-vs-originals.md)]).[^11]

**What counts as self-reproduction.** Naive definitions admit trivial cases such as
growing crystals. Von Neumann proposed requiring the capacity for *inheritable mutation*.
If an extra payload P is added to the description, a random change in P is passed on to later
generations. Changes to A, B, or C are usually lethal or leave the offspring unable to
reproduce.[^12]

In the cellular model, mutations sort by where they fall. Changes to the machinery are
usually lethal or sterilizing. Changes to the part of the description that specifies a
payload P give viable offspring making P′, a change of hereditary strain. Conflicts over
space between independently reproducing organisms are a possible route to natural
selection, though von Neumann leaves evolution open.[^13]

**A formal definition.** Moore defines a configuration c as *self-reproducing* if, started
alone in a quiescent plane at time 0, it reaches for every n a time at which the
non-quiescent region contains at least n disjoint copies of c.[^14] The definition admits
trivial cases. In a two-state rule where a cell turns X whenever a neighbour is X, a single
X cell qualifies, which Moore calls "more nearly a model of crystal growth". He notes that
von Neumann avoided such cases by requiring each configuration to contain a universal Turing
machine, and asks whether "less trivial" could be made into a partial order on
machines.[^15]

**Limits.** Offspring cannot multiply exponentially in a cellular universe. Moore's
Theorem 1 bounds the offspring by time T by kT² in two dimensions (kT^N in N), because the
active region grows by at most one cell per step.[^16] No self-reproducing configuration
can contain a [[garden-of-eden](pages/garden-of-eden.md)] pattern, and in any structure with
an [[erasable-configuration](pages/erasable-configuration.md)] such patterns exist. So no
self-reproducer can contain every given configuration.[^17] Whether self-reproduction is
possible without erasable configurations is one of Moore's open problems.[^18]

## Appearances in Sources

- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] — formal definition, trivial cases, the quadratic bound, Garden-of-Eden limits, kinematic models
- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] — the self-reproducing automaton completed in the 29-state rule
- [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] — the rule in which the cellular model is built
- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — the cellular setting, copying descriptions, mutation classes
- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — states the problem and places it in von Neumann's program
- [[tsra-lecture-5](pages/tsra-lecture-5.md)] — the kinematic model, the A + B + C scheme, and inheritable mutation

## Related Concepts

- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] — the form every offspring is built in
- [[garden-of-eden](pages/garden-of-eden.md)] — patterns no self-reproducer can contain
- [[erasable-configuration](pages/erasable-configuration.md)] — whether self-reproduction needs it is open
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] — the rule of the cellular model
- [[cellular-automaton](pages/cellular-automaton.md)] — the medium of the second model
- [[descriptions-vs-originals](pages/descriptions-vs-originals.md)] — why reproduction copies a description
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
[^5]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.153-154 [synthesis] — editor: a storage loop feeding a construction code grows a line indefinitely, the first pattern shown to grow without limit
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.27 — "His first models of self-reproduction were discrete, but he hoped later to develop a continuous model of self-reproduction."
[^7]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.20 — "It is also to be expected that because of the close relation of self-reproduction to self-repair, results on self-reproduction would help solve the reliability problem."
[^8]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.84-86 [synthesis] — A (universal constructor), B (copier), C (control); (A + B + C) + φ(A + B + C) produces a copy of itself; none of A, B, or C is self-reproductive alone
[^9]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.294-295 — "Hence, a self-reproducing automaton can be embedded in von Neumann's 29-state cellular structure."
[^10]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.295-296 — "In this cellular structure, self-reproduction is a special case of construction, and construction and computation are similar activities."
[^11]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.121-122 [synthesis] — copying requires exploration; quiescent descriptions can be explored without disturbance; this is the decisive step making reproduction without degeneration possible
[^12]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.86-87 [synthesis] — self-reproduction is hard to define since crystals qualify naively; requiring inheritable mutation resolves this; mutations in the payload part are inherited, those in A, B, or C usually lethal or sterilizing
[^13]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.130-131 [synthesis] — mutation classes by location in the self-reproducer with payload; conflicts between independent organisms and natural selection; evolution left open
[^14]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.22 [synthesis] - definitions of copy, containing n disjoint copies, reproducing n offspring by time T, and self-reproducing configuration
[^15]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.22-23, 29 [synthesis] - the two-state X/0 rule makes one X cell self-reproducing, "more nearly a model of crystal growth than of self-reproduction"; von Neumann required each configuration to contain a universal Turing machine; could "less trivial" be formalized as a partial ordering
[^16]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.23 [synthesis] - Theorem 1, f(T) < kT²; finite velocity of propagation of the non-quiescent region; kT^N for N dimensions
[^17]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23-24, 26 [synthesis] - a self-reproducing configuration containing a copy of any given configuration is impossible by Theorem 2; no self-reproducing configuration can contain a Garden-of-Eden configuration
[^18]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.30 - "Can a tessellation structure have a self-reproducing configuration without having an erasable configuration ?"
