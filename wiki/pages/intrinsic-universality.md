---
title: Intrinsic Universality
category: Concepts
summary: The strong, CA-native form of universality - a cellular automaton that, after blocking, shifting and recolouring, contains every space-time diagram of every CA of its dimension, infinite configurations included; smallest known 1D example has 6 states (Ollinger); whether rule 110 qualifies is open
tags: [concept, universality, intrinsic-universality, simulation, ollinger]
sources: [theory-of-cellular-automata-a-survey, statistical-mechanics-of-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Intrinsic Universality

## Description

**Two kinds of universality.** Simulating a Turing machine in a CA is not hard, so
*computational* universality is easy to get. Very simple rules such as the
[[game-of-life](pages/game-of-life.md)], [[rule-110](pages/rule-110.md)] and Margolus's
billiard-ball computer ([[margolus-neighbourhood](pages/margolus-neighbourhood.md)]) have
it. Kari, citing Wolfram (2002), calls it the rule rather than the exception among CA.[^1]
The proofs for Life and rule 110 go through a Turing machine
([[universal-turing-machine](pages/universal-turing-machine.md)]). **Intrinsic
universality** is stronger and belongs to CA themselves: an intrinsically universal CA
simulates every other CA, including its evolution on infinite configurations.[^2]

**Simulation.** CA A *simulates* CA B if, after a suitable colouring of blocks of states,
every space-time diagram of B is among those of A, up to a shift (Ollinger gives the
detailed definition). A is *intrinsically universal* if it simulates every CA of the same
dimension. Every computation of every CA then appears among its evolutions, after
blocking, shifting and recolouring.[^2]

**Examples.** Albert and Culik gave a simple intrinsically universal CA in 1987. The
smallest known 1D one is Ollinger's, with 6 states and the nearest-neighbour neighbourhood
(−1, 0, 1). Whether smaller ones exist is open, and so is whether rule 110 is intrinsically
universal.[^3]

**Wolfram's version.** Wolfram (1983) already described a universal CA that simulates any
other CA with a suitable encoding of its initial configuration, and conjectured that
rules which can simulate one another under short encodings account for the universality
classes he saw ([[self-organization](pages/self-organization.md)]).[^4] (Own reasoning:
that is close to Kari's notion. Wolfram's form is informal and does not specify the block
colouring.)

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §6, Theorem 13, Open problem 5
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - universal CA that simulate other CA

## Related Concepts

- [[universal-turing-machine](pages/universal-turing-machine.md)] - the weaker, Turing-machine form of universality
- [[rule-110](pages/rule-110.md)] - Turing-universal; intrinsic universality open
- [[game-of-life](pages/game-of-life.md)] - Turing-universal via glider circuits
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Wolfram's conjecture that class 4 rules are universal
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] - the first universal CA

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.22 [synthesis] - "It is not difficult to simulate an arbitrary Turing machine by a CA"; "Even very simple rules such as GOL, rule 110 and the billiard ball computer are computationally universal. It seems that computational universality is a very common property in CA, a rule rather than an exception [76]."
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.23 [synthesis] - "The universality of GOL and rule 110 is based on performing Turing machine simulations"; "Intrinsically universal CA can simulate any other CA, including its evolutions on infinite configurations"; simulation after a suitable colouring of blocks of states, modulo a shift; see [56]; intrinsically universal = simulates all CA of the same dimension
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.23 [synthesis] - Albert and Culik [1] in 1987; Theorem 13 (Ollinger [56]): 6 states and N = (−1, 0, 1); "It is an open problem whether smaller ones exist"; Open problem 5: "Is rule 110 intrinsically universal?"
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.629-630, 641 [synthesis] - universal cellular automata may simulate any other cellular automaton, the interpreter being an encoding of configurations; the conjecture that the universality classes arise because rules simulate each other under short encodings
