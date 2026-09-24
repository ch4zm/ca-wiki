---
title: Theory of Automata (von Neumann)
category: Concepts
summary: Von Neumann's program for a mathematical-logical theory of the structure, organization, and control of both natural and artificial automata
tags: [concept, theory-of-automata, von-neumann, foundations]
sources: [tsra-editors-introduction, tsra-lecture-1]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Automata (von Neumann)

## Description

Von Neumann's "theory of automata" was meant to be
"a coherent body of concepts and principles concerning the structure and organization of
both natural and artificial systems, the role of language and information in such
systems, and the programming and control of such systems."[^1] Cellular automata first
appear within this program, as the medium for his model of
[[self-reproduction](pages/self-reproduction.md)].

**Scope.** The theory treats natural automata (nervous systems, self-reproducing and
self-repairing systems, evolution and adaptation) and artificial automata (computers and
communication systems) in the same terms. Their similarities and differences are the
material for its general principles.[^2] Von Neumann begins with computing machines
because, among highly complex automata, they are the ones we can best understand: they
are basically mathematical objects.[^3] Every automaton, natural or artificial, has two
parts: an active switching part that carries out logical operations, and a memory. In
both computers and nervous systems the memory is the harder part.[^4]

**Central problems.** The two main problems are
(1) how to build reliable systems from unreliable components, and
(2) what logical organization is sufficient for an automaton to reproduce itself.[^5]
Both are problems of complexity, and von Neumann expected the theory's core to be a
rigorous concept of complexity (see [[complexity-threshold](pages/complexity-threshold.md)]).[^6]

**Mathematical character.** Von Neumann often called it a *logical* theory of automata.
It rests on the equivalence between formal logic and computation shown by Gödel and
Turing, which is also the basis of the [[universal-turing-machine](pages/universal-turing-machine.md)].
Automata can be specified as networks of idealized switch-delay elements such as the
[[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)].[^7] He also held that
existing formal logic, being all-or-none and combinatorial, was not adequate as "the"
logic of automata. He wanted a theory closer to probability, thermodynamics, and
continuous analysis.[^8] He divided the theory into a *strict* part (logic, finite
automata, Turing machines) and a *probabilistic* part (information theory, probabilistic
logic).[^9]

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — Burks's reconstruction of the program, its scope, and its intended mathematics
- [[tsra-lecture-1](pages/tsra-lecture-1.md)] — computing machines as the tractable case; the switching/memory anatomy of automata

## Related Concepts

- [[self-reproduction](pages/self-reproduction.md)] — one of the two central problems
- [[complexity-threshold](pages/complexity-threshold.md)] — the complexity claim at the theory's core
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — the idealized element used to specify automata
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the logical base the theory builds on

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.18 — "This theory of automata was to be a coherent body of concepts and principles concerning the structure and organization of both natural and artificial systems, the role of language and information in such systems, and the programming and control of such systems."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.21 [synthesis] — natural automata "include nervous systems, self-reproductive and self-repairing systems, and the evolutionary and adaptive aspects of organisms"; automata theory "seeks general principles of organization, structure, language, information, and control" applicable to both kinds
[^3]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] p.32 — "Of all automata of high complexity, computing machines are the ones which we have the best chance of understanding. In the case of computing machines the complications can be very high, and yet they pertain to an object which is primarily mathematical and which we understand better than we understand most natural objects."
[^4]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] p.39 — "all these automata really consist of two important parts: the general switching part (an active part which affects the logical operations the automaton is supposed to perform), and the memory ... Hence in both the computer and the human nervous system, the dynamic part (the switching part) of the automaton is simpler than the memory."
[^5]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.19 — "How can reliable systems be constructed from unreliable components? What kind of logical organization is sufficient for an automaton to be able to reproduce itself?"
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "Von Neumann thought that the chief problems of automata theory center around the concept of complexity. This very concept needs rigorous definition."
[^7]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.25 [synthesis] — Gödel and Turing make logic computational, "and so mathematical logic may be treated from the point of view of automata"; an automaton's organization "can be represented by a structure of idealized switch-delay elements"; von Neumann "often spoke of a 'logical theory of automata'"
[^8]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.19, 25-26 [synthesis] — formal logic "not adequate to serve as 'the' logic of automata"; the new logic will "interconnect with probability theory, thermodynamics, and information theory"; automata mathematics "should be closer to the continuous and should draw heavily on analysis"
[^9]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.27 — "The rigorous or strict part includes mathematical logic as extended to cover finite automata and Turing machines. The statistical or probabilistic part includes the work of Shannon on information theory and von Neumann's probabilistic logic."
