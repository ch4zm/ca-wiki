---
title: "Automata, Universality, Computation — Ch. 15: Real-Time Prime Generators Implemented on Small-State Cellular Automata"
category: Sources
summary: Umeo, Miyamoto and Abe's two smallest-known real-time prime generators - a 25-state, 86-rule CA whose cells exchange only one bit per step, and an 8-state, 305-rule ordinary CA - both running a signal-based sieve of Eratosthenes so that the end cell fires at exactly t = 2, 3, 5, 7, 11, …
tags: [sequence-generation, primes, sieve-of-eratosthenes, real-time, one-bit-communication, signals, small-state, umeo, korec]
sources: [aucm-ch15-real-time-prime-generators]
created: 2026-09-24
updated: 2026-09-24
---

# Automata, Universality, Computation — Ch. 15: Real-Time Prime Generators Implemented on Small-State Cellular Automata

**Source:** assets/adamatzky-2015-automata-universality-computation.pdf, printed pp. 341–352 (PDF pp. 345–356)
**Date ingested:** 2026-09-24
**Type:** book chapter (constructions, outlined)
**Authors:** Hiroshi Umeo, Kunio Miyamoto and Yasuyuki Abe
**Part of:** [[automata-universality-computation](pages/automata-universality-computation.md)]

## Summary

The chapter builds cellular automata that output the primes. The array is a half-line of
cells C₁, C₂, … that are all quiescent at time 0 except the end cell C₁. The CA
*generates* an increasing sequence t₁, t₂, … in *real time* if C₁ enters a special state
"1" at exactly the times tₙ
([[sequence-generation-by-cellular-automata](pages/sequence-generation-by-cellular-automata.md)]).[^1]
For the primes, that means C₁ fires at t = 2, 3, 5, 7, 11, 13, …, which the published
snapshots show.[^2]

Two constructions are given, each the smallest known in its model. The first runs on a
[[one-bit-communication-cellular-automaton](pages/one-bit-communication-cellular-automaton.md)],
where neighbours exchange only one bit per step in each direction. It uses 25 states and
86 rules, improving the 34-state generator of Umeo and Kamikawa (2003). The second runs on
an ordinary CA (called "constant-bit communication") with 8 states and 305 rules,
improving Korec's 9-state generator (1998).[^3] Both implement the sieve of Eratosthenes
with *signals*, information that travels along straight lines in the space-time diagram.
They are presented as outlines: transition tables and snapshots, without full
correctness proofs.[^4]

## Key Takeaways

- **The sieve, adapted.** For each odd k ≥ 3, cross out every 2k-th number starting at k².
  That suffices, because the multiples of k below k², and the even multiples from k² + k
  on, were already crossed out at earlier stages. What survives is the primes. C₁ performs
  every crossing-out.[^5]
- **Partitions as scaffolding.** The array is marked in advance with a symbol w that divides
  it into blocks. The 25-state CA puts the marks at cells (i² + 3i + 4)/2 for i ≥ 2, and
  the i-th partition holds 2i + 3 cells. The 8-state CA puts them at the squares i², and the
  i-th partition holds 2i + 2 cells. Signals bouncing between the partition walls time the
  crossings-out of the multiples of 3, 5, 7, ….[^6] How the partitions themselves are set
  up is omitted.[^7]
- **Records.**[^8]

  | Model | States | Rules | Previous best |
  |---|---|---|---|
  | 1-bit communication | 25 | 86 | 34 states, 107 rules (Umeo and Kamikawa 2003) |
  | ordinary (constant-bit) CA | 8 | 305 | 9 states (Korec 1998); 11 states (Korec 1997) |

- **The speed limit.** No signal can move faster than one cell per step.[^9]
- **Related results.** Fischer (1965) first generated primes in real time on a
  one-dimensional iterative array. Umeo and Kamikawa (2002) generated {2ⁿ}, {n²} and the
  Fibonacci numbers in real time on 1-bit CA, and the primes in twice real time.[^10]

## Entities & Concepts

- [[sequence-generation-by-cellular-automata](pages/sequence-generation-by-cellular-automata.md)]
- [[one-bit-communication-cellular-automaton](pages/one-bit-communication-cellular-automaton.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]
- [[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)]

## Relation to Other Wiki Pages

Sequence generation is the output-side twin of
[[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)].
Both read the answer off cell 1 against a clock, but "real time" means different things.
A recognizer accepts at time n − 1 on an input of length n. A generator must fire at
exactly each tₙ from an empty start (own comparison). The signals here are the same kind
of object as the colliding localized structures of [[rule-110](pages/rule-110.md)] (own
reasoning), and they obey the same finite-speed bound as
[[cellular-automaton](pages/cellular-automaton.md)] light cones. Like the small universal
Turing machines of
[[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)],
this is a race to the smallest program for a fixed task, here measured in CA states.

[^1]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.343 [synthesis] — all cells except C₁ quiescent at t = 0; C₁ outputs 1 to its right link at t = 0; "We say that M generates a sequence {tₙ | n = 1, 2, 3, ...} in k linear-time if and only if the leftmost end cell of M falls into a special state '1' (one) in Q at time t = ktₙ ... We call M a real-time generator when k = 1."
[^2]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.347, 351 (Figs. 15.4, 15.8) [synthesis] — in the snapshots C₁ is in state 1 at t = 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, … and 0 otherwise
[^3]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.341 (Abstract) — "there exists a real-time prime generator on a 1-bit inter-cell communication cellular automaton with 25-states, which is an improvement over a 34-state implementation given in Umeo and Kamikawa [2003]. In addition, we show that an infinite prime sequence can be generated in real-time by an eight-state cellular automaton with constant-bit communications ... our eight-state implementation is an improvement over a nine-state prime generator developed by Korec [1998]."
[^4]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.342-343 [synthesis] — "Both algorithms are based on the sieve of Eratosthenes. Due to the space available we only give an outline of our two constructions"; "A signal (wave) is an information flow that is described as a straight line in the space-time diagram"
[^5]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.344-345 [synthesis] — "for any odd integer k ≥ 3, every 2k-th member of the list beginning with k² will be crossed out, since the k-th members less than k² ... and 2k-th members beginning with k² + k ... should have been crossed out in the previous stages ... Those integers never being crossed out are the primes"; "Each cross-out operation is performed by C1"
[^6]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.345, 348 [synthesis] — 25-state version: mark "w" on C_{(i²+3i+4)/2} for i ≥ 2, S_i contains (2i + 3) cells excluding both ends; 8-state version: mark on C_{i²} for i ≥ 1, S_i contains (2i + 2) cells including both ends; partitions "used to generate reciprocating signals for the detection of every multiples of odds"
[^7]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.345 — "How to set up the partitions in terms of 1-bit communication is omitted."
[^8]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.343, 345, 350 [synthesis] — Theorem 2: "a CA1−bit with 25-states and 86-rules that can generate prime sequence in real-time"; Theorem 3: "a cellular automaton having 8-states and 305-rules"; Umeo and Kamikawa [2003]: "34 internal states and 107 transition rules"; Korec 1998 (9 states), Korec 1997 (11 states, reference [5])
[^9]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.343 — "Note that any signal cannot propagate at speed more than one cell per one step."
[^10]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] p.343 [synthesis] — Arisawa, Fischer, Korec and Mazoyer and Terrier studied sequence generation; "Umeo and Kamikawa [2002] showed that infinite non-regular sequences such as {2ⁿ}, {n²} and Fibonacci sequences can be generated in real-time and the prime sequence in twice real-time by CA1−bit"; Fischer [3]: "Generation of primes by a one-dimensional real-time iterative array" (1965)
