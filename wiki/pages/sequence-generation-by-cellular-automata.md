---
title: Sequence Generation by Cellular Automata
category: Concepts
summary: A CA on a half-line, quiescent but for its end cell, generates an increasing integer sequence (tₙ) in real time if the end cell fires at exactly each tₙ; primes, powers of two, squares and Fibonacci numbers are all real-time generable, and the prime generators race toward the fewest states (8 states ordinary, 25 states with 1-bit links)
tags: [concept, sequence-generation, real-time, primes, signals, small-state, umeo, korec, fischer]
sources: [aucm-ch15-real-time-prime-generators]
created: 2026-09-24
updated: 2026-09-24
---

# Sequence Generation by Cellular Automata

## Description

**The problem.** Take a one-dimensional CA on a half-line of cells C₁, C₂, …. At time 0
every cell is quiescent except the end cell C₁, which starts the computation. Given an
increasing sequence of positive integers (tₙ) with tₙ ≥ n, the CA *generates* it in
*k-linear time* if C₁ enters a distinguished state "1" at exactly the times k·tₙ. With
k = 1 it is a *real-time generator*.[^1] (Own reasoning: this makes the CA a clock that
ticks on a prescribed set of times. The whole output is written in the time axis of a
single cell.)

**Signals.** Generators are designed in terms of *signals*, flows of information drawn as
straight lines in the space-time diagram, rather than as transition tables. No signal can
move faster than one cell per step.[^2] A signal sent out and reflected back to C₁ returns
after a delay set by the distance it travelled. Arranging such returns to land exactly at
the tₙ is the core of every construction (own reasoning from the constructions described).

**What can be generated.**[^3]

- **Primes.** Fischer (1965) generated them in real time on a one-dimensional iterative
  array.
- **{2ⁿ}, {n²} and the Fibonacci numbers** can be generated in real time by CA with 1-bit
  links, and the primes in twice real time (Umeo and Kamikawa 2002).
- Arisawa (1971), Korec (1997, 1998) and Mazoyer and Terrier (1999) also studied the
  problem.

**Prime generators and the state-count race.** The prime constructions run the sieve of
Eratosthenes. For each odd k ≥ 3, every 2k-th number from k² is crossed out, which suffices
because smaller and even multiples fall at earlier stages. The end cell performs every
crossing-out, while signals bouncing inside a precomputed division of the array into
partitions supply the timing.[^4] The smallest known real-time prime generators
are:[^5]

| Model | States (rules) | Source |
|---|---|---|
| ordinary 3-neighbour CA | 11 | Korec 1997 |
| ordinary 3-neighbour CA | 9 | Korec 1998 |
| ordinary 3-neighbour CA | **8 (305 rules)** | Umeo, Miyamoto and Abe 2015 |
| 1-bit communication CA | 34 (107 rules) | Umeo and Kamikawa 2003 |
| 1-bit communication CA | **25 (86 rules)** | Umeo, Miyamoto and Abe 2015 |

The 2015 constructions are published as outlines, with transition tables and simulation
snapshots but no full proofs.[^6]

**Real time here vs in recognition.** In
[[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)],
real time means accepting at time n − 1 on an input of length n, the earliest time cell 1
can have heard from every letter. In generation there is no input. Real time means firing
at exactly tₙ, as early as the sequence itself allows (own comparison).

## Appearances in Sources

- [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] - the definition, the sieve algorithm, the 25- and 8-state prime generators, earlier results

## Related Concepts

- [[one-bit-communication-cellular-automaton](pages/one-bit-communication-cellular-automaton.md)] - the restricted model of the 25-state generator
- [[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)] - the input-side counterpart
- [[cellular-automaton](pages/cellular-automaton.md)] - the finite speed of signals
- [[universal-turing-machine](pages/universal-turing-machine.md)] - another race toward the smallest machine for a task

[^1]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.343 [synthesis] — {tₙ} "an infinite monotonically increasing positive integer sequence ... such that tₙ ≥ n"; semi-infinite array, all cells except C₁ quiescent at t = 0; "M generates a sequence {tₙ | n = 1, 2, 3, ...} in k linear-time if and only if the leftmost end cell of M falls into a special state '1' (one) in Q at time t = ktₙ ... We call M a real-time generator when k = 1."
[^2]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.343 — "we often use signals or waves, instead of transition tables. A signal (wave) is an information flow that is described as a straight line in the space-time diagram. Note that any signal cannot propagate at speed more than one cell per one step."
[^3]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.343 [synthesis] — "Arisawa [1971], Fischer [1965], Korec [1997, 1998] and Mazoyer and Terrier [1999] have considered the sequence generation problem"; "Umeo and Kamikawa [2002] showed that infinite non-regular sequences such as {2ⁿ}, {n²} and Fibonacci sequences can be generated in real-time and the prime sequence in twice real-time by CA1−bit"; Fischer, "Generation of primes by a one-dimensional real-time iterative array", J. ACM 12(3) (1965)
[^4]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.344-345, 348 [synthesis] — the modified sieve (every 2k-th member from k² for odd k ≥ 3); "Each cross-out operation is performed by C1"; the space divided by partitions marked "w" that "will be used to generate reciprocating signals"
[^5]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.341, 343, 345, 350 [synthesis] — Theorem 2 (25 states, 86 rules, CA1−bit); Theorem 3 (8 states, 305 rules); Umeo and Kamikawa 2003 (34 states, 107 rules); Korec 1998 (9 states); Korec 1997, "Real-time generation of primes by a one-dimensional cellular automaton with 11 states" (reference [5])
[^6]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.342 — "Due to the space available we only give an outline of our two constructions."
