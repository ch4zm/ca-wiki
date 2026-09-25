---
title: "Automata, Universality, Computation: Tribute to Maurice Margenstern"
category: Sources
summary: Adamatzky (ed.), Springer ECC vol. 12 (2015) - 17 chapters honouring Margenstern on small universal machines, reversible computing, P systems, splicing, and cellular automata; the wiki covers the automata-theoretic and cellular-automata chapters one at a time
tags: [book, festschrift, margenstern, universality, turing-machines, cellular-automata]
sources: [automata-universality-computation, aucm-ch5-small-universal-turing-machines, aucm-ch6-reversible-turing-machines-by-rlem, aucm-ch12-linear-cellular-automata-and-decidability, aucm-ch13-cellular-automata-with-write-access, aucm-ch14-broadcasting-automata, aucm-ch15-real-time-prime-generators, aucm-ch16-phyllosilicate-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Automata, Universality, Computation: Tribute to Maurice Margenstern

**Source:** assets/adamatzky-2015-automata-universality-computation.pdf
**Date ingested:** 2026-09-24 (one chapter at a time; all seven chapters in scope covered)
**Type:** book (edited volume)
**Editor:** Andrew Adamatzky (Springer, Emergence, Complexity and Computation vol. 12, 2015; DOI 10.1007/978-3-319-09039-9)[^1]

> **Locators.** Printed page numbers are used throughout. PDF page = printed page + 9 for
> Chs. 5-6 (p. 117 = PDF p. 126), + 5 for Chs. 12-13 (p. 259 = PDF p. 264), and + 4 for
> Chs. 14-16 (p. 297 = PDF p. 301).

## Summary

The volume is a tribute to Maurice Margenstern. Its
preface, by Serge Grigorieff, singles out two of his themes. The first is the frontier
between small machines with a decidable halting problem and small universal ones. The
second is computation with cellular automata in hyperbolic space.[^2] The seventeen
chapters range well beyond both. They cover combinatorics of curves, logic, the philosophy
of computer-assisted mathematics, two-way automata, small and reversible Turing machines,
the grossone methodology, P systems, splicing, cellular automata, and optimization in
bioinformatics.[^3]

## The honoree

Margenstern was born in Paris on 6 June 1947. He started out in constructive mathematics,
studying in Leningrad with N. A. Shanin. His interests then moved to computability. In the
late 1980s he joined the LITP computer-science laboratory in Paris, and there he began
studying the simplest machines with an undecidable halting problem and the most complex
ones with a decidable one. His 1994 habilitation was on that frontier. He then became a
professor at the University of Lorraine at Metz, where he founded the LITA laboratory. By
2015 he was emeritus there.[^4] The preface credits him with putting small machines
forward as one of the important themes in computability. He did it through his own results
and through the conference series *Machines, Computations and Universality*, which he set
up in 1995.[^5] His small-machine results are surveyed in Ch. 5
([[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)]).

In the early 2000s he developed computation with cellular automata in the hyperbolic plane
and in hyperbolic spaces of dimension 3 and 4, and solved long-open tiling problems. The
usual tool in hyperbolic geometry is group theory, but he invented combinatorial tools
instead. The preface also says he proved that hyperbolic computation gets around some
infeasibility results that hold in the Euclidean setting.[^6]

## Chapters covered in the wiki

The wiki takes the chapters on automata and universality and the chapters on cellular
automata:

| Ch. | Title | Authors | Page |
|---|---|---|---|
| 5 | Maurice Margenstern's Contributions to the Field of Small Universal Turing Machines | Neary, Woods | [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] |
| 6 | Constructing Reversible Turing Machines by Reversible Logic Element with Memory | Morita | [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] |
| 12 | Linear Cellular Automata and Decidability | Sutner | [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] |
| 13 | Algorithms with Active Cells Modeled by Cellular Automata with Write-Access (CA-w) | Hoffmann | [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] |
| 14 | Broadcasting Automata and Patterns on Z² | Nickson, Potapov | [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] |
| 15 | Real-Time Prime Generators Implemented on Small-State Cellular Automata | Umeo, Miyamoto, Abe | [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] |
| 16 | Phyllosilicate Automata | Adamatzky | [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] |

The rest are outside the wiki's scope: Ch. 1 (Courcelle, Gauss words), 2 (Choffrut and
Grigorieff, the additive monoid of subsets of ℕ), 3 (De Mol, mathematics and computer
science), 4 (Dang, Ibarra and Li, sampling two-way finite automata), 7 (Sergeyev and
Garro, grossone), 8-10 (P systems), 11 (Rogozhin and Verlan, splicing) and 17 (Le Thi,
DC programming in bioinformatics).[^3]

## Key Takeaways

- **Small universal machines (Ch. 5).** Neary and Woods map the gap between the smallest
  universal Turing machines and the largest decidable ones. They survey Margenstern's
  Collatz-iterating machines inside that gap, his exact frontiers for colours and
  laterality, and his 2-tag simulations with very few left moves
  ([[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)]).[^7]
- **Reversible Turing machines from one element (Ch. 6).** Morita builds any reversible
  Turing machine as an infinite circuit of rotary elements, and realizes the rotary element
  in the billiard ball model without synchronizing the balls. Every non-degenerate 2-state
  element with three or more symbols is universal
  ([[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)]).[^8]
- **Where decidability ends in 1D (Ch. 12).** Sutner shows that every first-order property
  of a 1D rule's one-step relation is decidable by automata on the de Bruijn graph, while
  orbit questions are undecidable at graded levels. Reachability can have any r.e. degree,
  and testing universality is Σ⁰₄-complete
  ([[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)]).[^9]
- **Cells that write (Ch. 13).** Hoffmann's CA-w lets active cells write to a chosen
  neighbour and switch it on or off, which makes agents and particles easy to describe. It
  is shown on the traffic rule 184, Pascal's triangle, Fibonacci numbers, sorting on a
  ring, and leader election
  ([[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)]).[^10]
- **Waves of variable radius (Ch. 14).** Nickson and Potapov's broadcasting automata send
  messages to everyone within a state-dependent Euclidean radius. The waves trace discrete
  discs that generalize the von Neumann and Moore neighbourhoods. Composing discs can never
  produce some gradients or any non-convex shape, while aggregating two wave trains can
  ([[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)]).[^11]
- **Primes on a clock (Ch. 15).** Umeo, Miyamoto and Abe give the smallest known real-time
  prime generators: an 8-state ordinary CA and a 25-state CA whose cells exchange one bit
  per step. Both run a signal-based sieve of Eratosthenes and fire the end cell at exactly
  2, 3, 5, 7, 11, …
  ([[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)]).[^12]
- **Life on a silicate sheet (Ch. 16).** Adamatzky's phyllosilicate automata give each of
  two node types its own totalistic rule. A 100,000-rule survey is classified by pattern
  shape and interior. Three Life-like rules have gliders, oscillators, eaters, a still life
  and a glider gun
  ([[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)]).[^13]

## Entities & Concepts

- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[tag-system](pages/tag-system.md)]
- [[collatz-function](pages/collatz-function.md)]
- [[reversible-turing-machine](pages/reversible-turing-machine.md)]
- [[reversible-logic-element-with-memory](pages/reversible-logic-element-with-memory.md)]
- [[billiard-ball-model](pages/billiard-ball-model.md)]
- [[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]
- [[de-bruijn-graph](pages/de-bruijn-graph.md)]
- [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]
- [[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)]
- [[rule-184](pages/rule-184.md)]
- [[broadcasting-automaton](pages/broadcasting-automaton.md)]
- [[neighbourhood-sequence](pages/neighbourhood-sequence.md)]
- [[sequence-generation-by-cellular-automata](pages/sequence-generation-by-cellular-automata.md)]
- [[one-bit-communication-cellular-automaton](pages/one-bit-communication-cellular-automaton.md)]
- [[phyllosilicate-automaton](pages/phyllosilicate-automaton.md)]

## Relation to Other Wiki Pages

Ch. 5 extends the wiki's account of universality
([[universal-turing-machine](pages/universal-turing-machine.md)]) from "which systems are
universal" to "how small a universal system can be". Ch. 6 does the same for reversible
computing, which the wiki otherwise meets through
[[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]s. Ch. 12 explains
the shape of the 1D column of
[[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)].

[^1]: [[automata-universality-computation](pages/automata-universality-computation.md)] copyright page [synthesis] — Andrew Adamatzky (ed.), Emergence, Complexity and Computation 12, Springer International Publishing Switzerland 2015, DOI 10.1007/978-3-319-09039-9
[^2]: [[automata-universality-computation](pages/automata-universality-computation.md)] pp.V-VI (Preface, signed Serge Grigorieff) [synthesis] — Margenstern's "investigation of the simplest (resp. most complex) machines with an undecidable (resp. decidable) halting problem"; "In the early 2000's Maurice developed the subject of computation with cellular automata in the hyperbolic world"; "the two themes presented above do not exhaust the subjects Maurice investigated"
[^3]: [[automata-universality-computation](pages/automata-universality-computation.md)] pp.VII-XI (Contents) [synthesis] — chapter titles and authors, Ch. 1-17
[^4]: [[automata-universality-computation](pages/automata-universality-computation.md)] pp.V-VI (Preface) [synthesis] — "Maurice was born in Paris on June 6, 1947"; constructive mathematics in Leningrad with Nicolaï A. Shanin; "In the late 80's he joined the computer science laboratory LITP (now LIAFA) in Paris and started his amazing investigation of the simplest (resp. most complex) machines with an undecidable (resp. decidable) halting problem"; Habilitation 1994; professor at the university of Lorraine at Metz, created the LITA laboratory; "now emeritus professor at the university of Lorraine"
[^5]: [[automata-universality-computation](pages/automata-universality-computation.md)] pp.V-VI (Preface) — "Maurice is to be credited for putting it up as one of the important themes in computability. He did so via his own contributions and via a triennial international conference Machines, Computations and Universality he set up in 1995"
[^6]: [[automata-universality-computation](pages/automata-universality-computation.md)] p.VI (Preface) — "In the early 2000's Maurice developed the subject of computation with cellular automata in the hyperbolic world (dimension 2, 3 or 4) and brought solutions to long open difficult tiling problems. Besides these technical achievements, Maurice proved that hyperbolic computability allows to overcome known unfeasibility results of the Euclidean world. The classical tool in hyperbolic geometry is the theory of groups but Maurice invented completely new tools: combinatorial ones."
[^7]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.117-124 [synthesis] — universal and non-universal curves with 39 open pairs, Collatz simulators, colour and laterality frontiers, 2-tag simulation with 6 and 3 left-move instructions
[^8]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.129-137 [synthesis] — any RTM as an infinite circuit of REs; RE realized in BBM with a stationary state ball, no input synchronization; every non-degenerate 2-state k-symbol RLEM with k > 2 is universal
[^9]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.259-273 [synthesis] — Theorems 1, 3, 5 (first-order decidability), Theorem 8 (Reachability any r.e. degree), universality testing Σ⁰₄-complete
[^10]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] p.277 (Abstract) [synthesis] — CA-w lets an active cell send data to a neighbouring cell, activate or deactivate it; demonstrated on the traffic rule, Pascal's triangle, Fibonacci numbers, sorting on the ring, leader election
[^11]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.297-334 [synthesis] — Broadcasting Automata with state-dependent radius; discrete discs with r² = 1, 2 as von Neumann and Moore; gradients that cannot be produced (Proposition 6); closure under composition (Corollary 2); non-convex shapes by moiré aggregation
[^12]: [[aucm-ch15-real-time-prime-generators](pages/aucm-ch15-real-time-prime-generators.md)] pp.341-350 [synthesis] — Theorem 2 (25 states, 86 rules, CA1−bit), Theorem 3 (8 states, 305 rules); sieve of Eratosthenes via signals; C₁ in state 1 at the prime times (Figs. 15.4, 15.8)
[^13]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.353-378 [synthesis] — silicon (3 neighbours) and oxygen (6 neighbours) automata; 100K random rules classified C1-C5 and M1-M5; rules R65, R68, R72 with gliders, oscillators, still life and glider gun
