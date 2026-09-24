---
title: Theory of Automata (von Neumann)
category: Concepts
summary: Von Neumann's program for a mathematical-logical theory of the structure, organization, and control of both natural and artificial automata
tags: [concept, theory-of-automata, von-neumann, foundations]
sources: [tsra-editors-introduction]
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
material for its general principles.[^2]

**Central problems.** The two main problems are
(1) how to build reliable systems from unreliable components, and
(2) what logical organization is sufficient for an automaton to reproduce itself.[^3]
Both are problems of complexity, and von Neumann expected the theory's core to be a
rigorous concept of complexity (see [[complexity-threshold](pages/complexity-threshold.md)]).[^4]

**Mathematical character.** Von Neumann often called it a *logical* theory of automata.
It rests on the equivalence between formal logic and computation shown by Gödel and
Turing, which is also the basis of the [[universal-turing-machine](pages/universal-turing-machine.md)].
Automata can be specified as networks of idealized switch-delay elements such as the
[[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)].[^5] He also held that
existing formal logic, being all-or-none and combinatorial, was not adequate as "the"
logic of automata. He wanted a theory closer to probability, thermodynamics, and
continuous analysis.[^6] He divided the theory into a *strict* part (logic, finite
automata, Turing machines) and a *probabilistic* part (information theory, probabilistic
logic).[^7]

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — Burks's reconstruction of the program, its scope, and its intended mathematics

## Related Concepts

- [[self-reproduction](pages/self-reproduction.md)] — one of the two central problems
- [[complexity-threshold](pages/complexity-threshold.md)] — the complexity claim at the theory's core
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — the idealized element used to specify automata
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the logical base the theory builds on

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.18 — "This theory of automata was to be a coherent body of concepts and principles concerning the structure and organization of both natural and artificial systems, the role of language and information in such systems, and the programming and control of such systems."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.21 [synthesis] — natural automata "include nervous systems, self-reproductive and self-repairing systems, and the evolutionary and adaptive aspects of organisms"; automata theory "seeks general principles of organization, structure, language, information, and control" applicable to both kinds
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.19 — "How can reliable systems be constructed from unreliable components? What kind of logical organization is sufficient for an automaton to be able to reproduce itself?"
[^4]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "Von Neumann thought that the chief problems of automata theory center around the concept of complexity. This very concept needs rigorous definition."
[^5]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.25 [synthesis] — Gödel and Turing make logic computational, "and so mathematical logic may be treated from the point of view of automata"; an automaton's organization "can be represented by a structure of idealized switch-delay elements"; von Neumann "often spoke of a 'logical theory of automata'"
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.19, 25-26 [synthesis] — formal logic "not adequate to serve as 'the' logic of automata"; the new logic will "interconnect with probability theory, thermodynamics, and information theory"; automata mathematics "should be closer to the continuous and should draw heavily on analysis"
[^7]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.27 — "The rigorous or strict part includes mathematical logic as extended to cover finite automata and Turing machines. The statistical or probabilistic part includes the work of Shannon on information theory and von Neumann's probabilistic logic."
