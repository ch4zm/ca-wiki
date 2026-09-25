---
title: Theory of Automata (von Neumann)
category: Concepts
summary: Von Neumann's program for a mathematical-logical theory of the structure, organization, and control of both natural and artificial automata
tags: [concept, theory-of-automata, von-neumann, foundations]
sources: [tsra-editors-introduction, tsra-lecture-1, tsra-lecture-3, tsra-lecture-4]
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
(1) how to build reliable systems from unreliable components ([[probabilistic-logic](pages/probabilistic-logic.md)]), and
(2) what logical organization is sufficient for an automaton to reproduce itself.[^5]
Both are problems of complexity, and von Neumann expected the theory's core to be a
rigorous concept of complexity (see [[complexity-threshold](pages/complexity-threshold.md)]).[^6]

**Why discrete.** Von Neumann argued that complicated functions need digital mechanisms.
Pure analog mechanisms can handle a complicated situation only by breaking it into parts
dealt with separately and in turn, which "is a digital trick."[^7]

**Mathematical character.** Von Neumann often called it a *logical* theory of automata.
It rests on the equivalence between formal logic and computation shown by Gödel and
Turing, which is also the basis of the [[universal-turing-machine](pages/universal-turing-machine.md)].
Automata can be specified as networks of idealized switch-delay elements such as the
[[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)].[^8] He also held that
existing formal logic, being all-or-none and combinatorial, was not adequate as "the"
logic of automata. He wanted a theory closer to probability, thermodynamics, and
continuous analysis.[^9] He divided the theory into a *strict* part (logic, finite
automata, Turing machines) and a *probabilistic* part (information theory, probabilistic
logic).[^10] Von Neumann's reason for the probabilistic half is that failure has to be
part of the axioms. All-or-none logic belongs to combinatorics, "that part of mathematics
of which we know the least", while probabilistic axioms would bring the theory closer to
analysis. Because information behaves like entropy (see [[maxwells-demon](pages/maxwells-demon.md)]), the theory should
also have much in common with thermodynamics.[^11]

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — Burks's reconstruction of the program, its scope, and its intended mathematics
- [[tsra-lecture-1](pages/tsra-lecture-1.md)] — computing machines as the tractable case; the switching/memory anatomy of automata
- [[tsra-lecture-3](pages/tsra-lecture-3.md)] — von Neumann's own statement of the probabilistic, thermodynamic program
- [[tsra-lecture-4](pages/tsra-lecture-4.md)] — why complicated functions need digital mechanisms

## Related Concepts

- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — entropy and irreversibility measured in actual cellular automata (Wolfram)
- [[self-reproduction](pages/self-reproduction.md)] — one of the two central problems
- [[complexity-threshold](pages/complexity-threshold.md)] — the complexity claim at the theory's core
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — the idealized element used to specify automata
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the logical base the theory builds on
- [[probabilistic-logic](pages/probabilistic-logic.md)] — the logic of the reliability problem
- [[maxwells-demon](pages/maxwells-demon.md)] — the entropy–information link
- [[self-repair](pages/self-repair.md)] — natural automata's answer to unreliable parts

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.18 — "This theory of automata was to be a coherent body of concepts and principles concerning the structure and organization of both natural and artificial systems, the role of language and information in such systems, and the programming and control of such systems."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.21 [synthesis] — natural automata "include nervous systems, self-reproductive and self-repairing systems, and the evolutionary and adaptive aspects of organisms"; automata theory "seeks general principles of organization, structure, language, information, and control" applicable to both kinds
[^3]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] p.32 — "Of all automata of high complexity, computing machines are the ones which we have the best chance of understanding. In the case of computing machines the complications can be very high, and yet they pertain to an object which is primarily mathematical and which we understand better than we understand most natural objects."
[^4]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] p.39 — "all these automata really consist of two important parts: the general switching part (an active part which affects the logical operations the automaton is supposed to perform), and the memory ... Hence in both the computer and the human nervous system, the dynamic part (the switching part) of the automaton is simpler than the memory."
[^5]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.19 — "How can reliable systems be constructed from unreliable components? What kind of logical organization is sufficient for an automaton to be able to reproduce itself?"
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "Von Neumann thought that the chief problems of automata theory center around the concept of complexity. This very concept needs rigorous definition."
[^7]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] pp.69-70 — "digital mechanisms are necessary for complicated functions. Pure analog mechanisms are usually not suited for very complicated situations. The only way to handle a complicated situation with analog mechanisms is to break it up into parts and deal with the parts separately and alternately, and this is a digital trick."
[^8]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.25 [synthesis] — Gödel and Turing make logic computational, "and so mathematical logic may be treated from the point of view of automata"; an automaton's organization "can be represented by a structure of idealized switch-delay elements"; von Neumann "often spoke of a 'logical theory of automata'"
[^9]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.19, 25-26 [synthesis] — formal logic "not adequate to serve as 'the' logic of automata"; the new logic will "interconnect with probability theory, thermodynamics, and information theory"; automata mathematics "should be closer to the continuous and should draw heavily on analysis"
[^10]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.27 — "The rigorous or strict part includes mathematical logic as extended to cover finite automata and Turing machines. The statistical or probabilistic part includes the work of Shannon on information theory and von Neumann's probabilistic logic."
[^11]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.62 [synthesis] — formal logic's all-or-none processes "are only weakly connected to analysis ... while they are closely connected to combinatorics, that part of mathematics of which we know the least"; the new theory "is likely to have a lot in common with thermodynamics" and "will be closer to analysis, because all axioms are likely to be of a probabilistic and not of a rigorous character"
