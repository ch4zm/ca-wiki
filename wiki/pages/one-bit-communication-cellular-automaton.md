---
title: One-Bit Communication Cellular Automaton
category: Concepts
summary: A 1D CA whose cells cannot see their neighbours' states but exchange just one bit per step over each one-way link (CA1-bit); it simulates any ordinary CA with a slowdown of ⌈log₂|Q|⌉ and still generates primes in real time with 25 states
tags: [concept, ca-variant, one-bit-communication, communication-complexity, umeo, mazoyer]
sources: [aucm-ch15-real-time-prime-generators]
created: 2026-09-24
updated: 2026-09-24
---

# One-Bit Communication Cellular Automaton

## Description

**The model.** In a CA with 1-bit inter-cell communication (CA1-bit), neighbouring cells on
a line are joined by a pair of one-way links, one in each direction, and each link carries
a single bit per step. A cell does not see its neighbours' states, only the bits they
send. Its rule is δ: Q × {0, 1} × {0, 1} → Q × {0, 1} × {0, 1}. From its state p and the
bits x and y arriving from left and right, the cell moves to a state q and sends bits
x′ left and y′ right. A quiescent state satisfies δ(q, 0, 0) = (q, 0, 0).[^1]

**Relation to ordinary CA.** In an ordinary 3-neighbour
[[cellular-automaton](pages/cellular-automaton.md)], neighbours effectively exchange their
whole states, O(1) bits per step. CA1-bit is a special subclass. Conversely, a CA1-bit can
simulate one step of an ordinary CA with state set Q in ⌈log₂|Q|⌉ steps, by sending each
state bit by bit and decoding it on arrival. So any ordinary CA running in T(n) steps is
simulated in kT(n) steps with k = ⌈log₂|Q|⌉ (Mazoyer 1996; Umeo and Kamikawa 2002).[^2]
(Own reasoning: the model asks how much of a CA's power survives when bandwidth, not the
number of states, is the scarce resource.)

**What it can still do in real time.** Powers of two, squares and the Fibonacci numbers
can be generated in real time, and the primes too, first with 34 states and then with 25
states and 86 rules
([[sequence-generation-by-cellular-automata](pages/sequence-generation-by-cellular-automata.md)]).[^3]
Mazoyer's paper on optimal solutions to the firing squad synchronization problem is among
the sources for the simulation theorem.[^4]

## Appearances in Sources

- [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] - definition, the simulation theorem, the 25-state prime generator

## Related Concepts

- [[cellular-automaton](pages/cellular-automaton.md)] - the ordinary model it restricts
- [[sequence-generation-by-cellular-automata](pages/sequence-generation-by-cellular-automata.md)] - the real-time generation results in this model
- [[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)] - a variant that changes what neighbours can do to each other, in the opposite direction

[^1]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.342-343 [synthesis] — each C_i connected to its neighbours "via a left and right one-way communication link"; "Each one-way communication link can transmit only one bit at each step in each direction"; δ: Q × {0, 1} × {0, 1} → Q × {0, 1} × {0, 1}, δ(p, x, y) = (q, x′, y′); quiescent state with δ(q, 0, 0) = (q, 0, 0)
[^2]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.343 [synthesis] — "the CA1−bit is a special subclass of normal (i.e., conventional) cellular automata"; in a normal CA "the amount of information exchanged per step between neighboring cells is O(1) bits"; states encoded in ⌈log₂|Q|⌉ bits and sent bit by bit; Theorem 1 (Mazoyer [1996], Umeo and Kamikawa [2002]): simulation in kT(n) steps with k = ⌈log₂|Q|⌉
[^3]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.343, 345 [synthesis] — Umeo and Kamikawa [2002]: {2ⁿ}, {n²}, Fibonacci in real time, primes in twice real time; Umeo and Kamikawa [2003]: primes in real time with 34 states and 107 rules; Theorem 2: 25 states and 86 rules
[^4]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.352 (References) [synthesis] — [7] Mazoyer, "On optimal solutions to the firing squad synchronization problem", Theoretical Computer Science 168 (1996), cited for Theorem 1
