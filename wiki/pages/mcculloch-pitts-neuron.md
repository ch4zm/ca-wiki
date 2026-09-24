---
title: McCulloch–Pitts Neuron
category: Concepts
summary: Idealized threshold element with excitatory/inhibitory inputs and unit delay — von Neumann's basic logical building block, later echoed in his cellular automaton's states
tags: [concept, logic-element, threshold, neuron, von-neumann]
sources: [tsra-editors-introduction, tsra-lecture-2]
created: 2026-09-24
updated: 2026-09-24
---

# McCulloch–Pitts Neuron

## Description

The McCulloch–Pitts neuron is an idealized switch-delay element. In
von Neumann's version it has one to three excitatory
inputs, possibly one or two inhibitory inputs, a threshold (1, 2, or 3), and a unit
delay. It fires at time *t* + 1 exactly when, at time *t*, no inhibitory input is
stimulated and the number of stimulated excitatory inputs is at least the threshold.[^1]

Building automata from these elements separates *logical* organization (memory and
truth-functional structure) from any particular physical realization. It is also the
reason the same vocabulary can describe both nervous systems and computers.[^2] Von
Neumann's threshold elements elsewhere are similar, but they differ in how inhibitory
inputs work.[^3] The idealization is deliberate. A neuron has just two states, excited
or not, and McCulloch and Pitts axiomatized an "extremely amputated, simplified,
idealized object" rather than the real cell.[^4]

**Equivalence with logic.** Von Neumann calls this the *synthetic* approach to automata:
axiomatize only the elements and let complexity come from combining them. It contrasts
with Turing's *integral* approach.[^5] The main result is that any behavior that can be
stated rigorously in finitely many words can be realized by a network of these elements,
so "the generality of neural systems is exactly the same as the generality of logics."
A network with an unbounded tape attached is equivalent to a Turing machine.[^6] The result
shows what is possible, not that nature builds circuits this way.[^7] Von Neumann also
doubted that it helps at high complication, where a network may be simpler than any
description of its behavior (see [[description-vs-object-complexity](pages/description-vs-object-complexity.md)]).[^8]

In the [[theory-of-automata](pages/theory-of-automata.md)], these elements are the
standard way to specify an automaton's logical organization.[^9] The TOC of
[[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]
shows that the 29-state cellular system of Part II realizes neuron-like functions
("+ neuron", "· neuron", "− neuron") through its transmission and confluent states.[^10]

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — definition as used in von Neumann's EDVAC logical design
- [[tsra-lecture-2](pages/tsra-lecture-2.md)] — the synthetic method and the equivalence of nets with logic

## Related Concepts

- [[theory-of-automata](pages/theory-of-automata.md)] — idealized elements as its basic vocabulary
- [[probabilistic-logic](pages/probabilistic-logic.md)] — generalizes these all-or-none elements to unreliable ones
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the other half of the logical base: finite control plus unbounded tape
- [[description-vs-object-complexity](pages/description-vs-object-complexity.md)] — limits the usefulness of the equivalence theorem at high complexity

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.9 — "Each such element has one to three excitatory inputs, possibly one or two inhibitory inputs, a threshold number (1, 2, 3), and a unit delay. It emits a stimulus at time t + 1 if and only if two conditions are satisfied at time t: (1) no inhibitory input is stimulated, (2) the number of excitatory inputs stimulated is at least as great as the threshold number."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.9-10 [synthesis] — idealized elements let one "distinguish the purely logical (memory and truth-functional) requirements for a computer from the requirements imposed by the state of technology"; the approach "facilitates a comparison and contrast between different types of automata elements, both computer elements on the one hand and neurons on the other"
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.9 fn13 — "The threshold elements of 'Probabilistic Logics and the Synthesis of Reliable Organisms from Unreliable Components,' Collected Works 5.332, are similar, but differ with respect to the operation of inhibitory inputs."
[^4]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] pp.43-44 [synthesis] — they used "the axiomatic method, stating a few simple postulates and not being concerned with how nature manages to achieve such a gadget"; "an extremely amputated, simplified, idealized object"; a neuron "has two states: it's excited or not"
[^5]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.43 — "McCulloch and Pitts described structures which are built up from very simple elements, so that all you have to define axiomatically are the elements, and then their combination can be extremely complex."
[^6]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.45 [synthesis] — "you can always put a neural network in the box which will realize these conditions, which means that the generality of neural systems is exactly the same as the generality of logics"; (editor) when a network with cyclic memory "is augmented by an infinite tape, the result is a Turing machine"
[^7]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.46 — "It does not prove that any circuit you are designing in this manner really occurs in nature."
[^8]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.47 — "simplifies matters enormously at low complication levels. It is by no means certain that it is a simplification on high complication levels."
[^9]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.25 — "The logical organization of an automaton can be represented by a structure of idealized switch-delay elements and then translated into logical symbolism."
[^10]: raw/von-neumann-theory-of-self-reproducing-automata.pdf p.vii (Contents) [synthesis] — Ch. 2 §2.3 "Neurons—Confluent States": 2.3.1 "The + neuron", 2.3.2 "Confluent states: the · neuron", 2.3.3 "The − neuron"
