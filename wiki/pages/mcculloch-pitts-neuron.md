---
title: McCulloch–Pitts Neuron
category: Concepts
summary: Idealized threshold element with excitatory/inhibitory inputs and unit delay — von Neumann's basic logical building block, later echoed in his cellular automaton's states
tags: [concept, logic-element, threshold, neuron, von-neumann]
sources: [tsra-editors-introduction]
created: 2026-09-24
updated: 2026-09-24
---

# McCulloch–Pitts Neuron

## Description

The McCulloch–Pitts neuron is an idealized switch-delay element. In
Von Neumann's version it has one to three excitatory
inputs, possibly one or two inhibitory inputs, a threshold (1, 2, or 3), and a unit
delay. It fires at time *t* + 1 exactly when, at time *t*, no inhibitory input is
stimulated and the number of stimulated excitatory inputs is at least the threshold.[^1]

Building automata from these elements separates *logical* organization (memory and
truth-functional structure) from any particular physical realization. It is also the
reason the same vocabulary can describe both nervous systems and computers.[^2] Von
Neumann's threshold elements elsewhere are similar, but they differ in how inhibitory
inputs work.[^3]

In the [[theory-of-automata](pages/theory-of-automata.md)], these elements are the
standard way to specify an automaton's logical organization.[^4] The TOC of
[[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]
shows that the 29-state cellular system of Part II realizes neuron-like functions
("+ neuron", "· neuron", "− neuron") through its transmission and confluent states.[^5]

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — definition as used in von Neumann's EDVAC logical design

## Related Concepts

- [[theory-of-automata](pages/theory-of-automata.md)] — idealized elements as its basic vocabulary
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the other half of the logical base: finite control plus unbounded tape

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.9 — "Each such element has one to three excitatory inputs, possibly one or two inhibitory inputs, a threshold number (1, 2, 3), and a unit delay. It emits a stimulus at time t + 1 if and only if two conditions are satisfied at time t: (1) no inhibitory input is stimulated, (2) the number of excitatory inputs stimulated is at least as great as the threshold number."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.9-10 [synthesis] — idealized elements let one "distinguish the purely logical (memory and truth-functional) requirements for a computer from the requirements imposed by the state of technology"; the approach "facilitates a comparison and contrast between different types of automata elements, both computer elements on the one hand and neurons on the other"
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.9 fn13 — "The threshold elements of 'Probabilistic Logics and the Synthesis of Reliable Organisms from Unreliable Components,' Collected Works 5.332, are similar, but differ with respect to the operation of inhibitory inputs."
[^4]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.25 — "The logical organization of an automaton can be represented by a structure of idealized switch-delay elements and then translated into logical symbolism."
[^5]: raw/von-neumann-theory-of-self-reproducing-automata.pdf p.vii (Contents) [synthesis] — Ch. 2 §2.3 "Neurons—Confluent States": 2.3.1 "The + neuron", 2.3.2 "Confluent states: the · neuron", 2.3.3 "The − neuron"
