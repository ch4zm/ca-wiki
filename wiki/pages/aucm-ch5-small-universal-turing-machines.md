---
title: "Automata, Universality, Computation — Ch. 5: Margenstern's Contributions to Small Universal Turing Machines"
category: Sources
summary: Neary and Woods' survey of Margenstern's small-machine work - the state-symbol plot with its universal and non-universal curves and 39 open pairs between them, Collatz-iterating machines inside that gap, exact "frontiers" for colours and laterality, and 2-tag-system simulation with very few left moves
tags: [turing-machines, universality, small-universal-machines, tag-systems, collatz, margenstern, neary, woods]
sources: [aucm-ch5-small-universal-turing-machines]
created: 2026-09-24
updated: 2026-09-24
---

# Automata, Universality, Computation — Ch. 5: Margenstern's Contributions to Small Universal Turing Machines

**Source:** assets/adamatzky-2015-automata-universality-computation.pdf, printed pp. 117–126 (PDF pp. 126–135)
**Date ingested:** 2026-09-24
**Type:** book chapter (survey)
**Authors:** Turlough Neary and Damien Woods
**Part of:** [[automata-universality-computation](pages/automata-universality-computation.md)]

## Summary

The field of small universal Turing machines puts upper and lower bounds on the program
size of a universal machine. It looks for the shortest programs capable of universal
computation, and shows that below some threshold such behaviour is impossible.[^1] Small
universal machines, along with Post's tag systems and [[rule-110](pages/rule-110.md)],
are the standard stepping stones for proving other models universal.[^2] Neary and Woods
survey Maurice Margenstern's part in this field. He contributed upper bounds (small
universal programs), lower bounds (sizes at which halting is decidable), and machines that
probe the region in between.[^3]

For the standard model (deterministic, one tape, a blank symbol), size is the pair
(states, symbols). Plotting the smallest known universal machines gives a *universal
curve*. Plotting the pairs with a decidable halting problem gives a *non-universal curve*.
Thirty-nine pairs lie between them and are open.[^4] Margenstern explored that gap with
machines that iterate the [[collatz-function](pages/collatz-function.md)]. For any machine
at least that large, deciding whether it reaches a target configuration is at least as
hard as the Collatz problem.[^5]

For some syntactic properties other than size, Margenstern found matching upper and lower
bounds, which he calls *frontiers*.[^6] The chapter closes with his simulations of 2-tag
systems ([[tag-system](pages/tag-system.md)]). They use a new algorithm that needs very
few left-moving instructions, where Minsky's classic algorithm needs many.[^7]

## Key Takeaways

- **The known sizes (standard model).**[^8]

  | | State-symbol pairs |
  |---|---|
  | Universal: Rogozhin | (2, 18), (4, 6), (5, 5) |
  | Universal: Kudlek and Rogozhin | (3, 9) |
  | Universal: Neary and Woods | (5, 5), (6, 4), (9, 3), (15, 2) |
  | Halting decidable | (2, 2), (3, 2), (2, 3) (Pavlotskaya, unpublished), (1, n), (n, 1) |

  "Decidable" here means that no machine of that size halts exactly when the machine it
  simulates halts.[^9]
- **Collatz machines in the gap.** Margenstern's Collatz iterators have sizes (11, 2),
  (5, 3), (4, 4), (3, 6) and (2, 10). Baiocchi reduced some of them to (10, 2), (5, 3),
  (4, 4), (3, 5) and (2, 8). The unary-encoded machines take O(x) time per iteration.
  Margenstern's binary-encoded (11, 2) and (5, 3) machines take O(log x).[^10]
- **Colours frontier.** A 2-symbol machine's *colours* are its distinct (read symbol,
  move, write symbol) triples. Standard universal machines exist with 3 colours but not 2
  (Pavlotskaya). Non-erasing universal machines exist with 5 but not 4 (Margenstern).
  A non-erasing machine may only overwrite blanks.[^11]
- **Laterality frontier.** *Laterality* is the smaller of a 2-symbol machine's left-move
  and right-move instruction counts. The universal thresholds are 2 for standard machines
  (Margenstern and Pavlotskaya) and 3 for non-erasing ones (Margenstern).[^12]
- **Machine plus finite automaton.** A Turing machine can be paired with a finite
  automaton that writes a symbol whenever the head enters a fresh blank cell. In that
  model a 2-state, 3-symbol machine with 5 instructions is universal. With 4 instructions,
  halting is decidable, which took a 58-page proof.[^13]
- **Few left moves.** Margenstern's 2-symbol universal machines have 59 states with 6
  left-move instructions, and 190 states with 3. A non-erasing one has 218 states with 3.
  For comparison, the smallest known 2-symbol universal machine uses 15.[^14]

## Tag-system simulation in detail

**Minsky's algorithm.** Minsky's 7-state, 4-symbol universal machine simulates 2-tag
systems, and its algorithm inspired many later small machines.[^15] The tape holds the
encoded productions on the left, separated by markers b, and the dataword on the right,
with symbol σᵢ written in unary as eⁱd. One tag step takes three stages:[^16]

1. The eⁱ of the first symbol serves as a unary index. For each e, the head marks off one
   b, which locates the production P(σᵢ).
2. The head deletes the second symbol, then scans back and forth to copy P(σᵢ) onto the
   right end.
3. The head unmarks the productions.

Every one of these stages scans left in a different context. Each left scan has to carry
information without destroying it, and on a 2-symbol machine that costs even more
left-move rules.[^17]

**Margenstern's 6-left-move machine.** This machine reverses the order of the productions
and puts a *stage bit* at the left end of the tape. Its 6 left-move instructions split
into two sets of 3: one set for returning left with the stage bit unchanged, and one for
returning left while flipping it. A left scan therefore carries exactly one bit, "same
stage" or "next stage", and that is enough to sequence the three stages.[^18]

**The 3-left-move machines.** With only 3 left-move instructions, only one kind of signal
can travel left, so a stage bit cannot be updated. Instead the machine repeatedly copies
its whole configuration to the right. The stage is recorded as a pair of end-words, u…v
for stage 0 and c…k for stage 1. The copy passes over the old right-end word, and that
word becomes the new left-end word, with its stage updated as needed. The stage is
updated during the rightward copy, so no left scan has to carry it. The 218-state
non-erasing machine works the same way.[^19]

## Entities & Concepts

- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[tag-system](pages/tag-system.md)]
- [[collatz-function](pages/collatz-function.md)]
- [[rule-110](pages/rule-110.md)]

## Relation to Other Wiki Pages

Wolfram (1983) calls a 7-state, 4-symbol machine the simplest known universal Turing
machine
([[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)]).
That matches the size of Minsky's 1962 tag-system simulator.[^15] Of the later machines
listed here, all but (2, 18) and (15, 2) have a state-symbol product below Minsky's 28
(own reasoning: Wolfram does not name the machine). The chapter cites Cook (2004) as the
proof that [[rule-110](pages/rule-110.md)] is universal, and gives rule 110 as a standard
route to universality proofs for other models.[^2] The frontier idea is a discrete counterpart to von Neumann's
complexity threshold ([[complexity-threshold](pages/complexity-threshold.md)]): below
some size or syntactic budget universality is impossible, and above it universality
appears (own reasoning).

[^1]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.117 — "The topic of small universal Turing machines is concerned with putting upper and lower bounds on the program size of universal Turing machines. In other words, finding the shortest programs that are capable of universal computation and showing that below this threshold such complicated behaviour is impossible."
[^2]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.117-118 — "Simulation of small universal Turing machines and other simple universal models such as Post's tag systems [36] and the cellular automaton rule 110 [4] is by now a standard way to prove that a large number of other models of computation, including a variety of physically-inspired systems, are computationally universal."; [4] = Cook, "Universality in elementary cellular automata", Complex Systems 15(1) (2004)
[^3]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.117 (Abstract) [synthesis] — numerous small universal programs; "complemented by Margenstern's negative results, or lower bounds, on universal program size"; small programs iterating the Collatz function explore "the space in-between"
[^4]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.118-119 [synthesis] — standard model: "deterministic single-tape model with the usual notion of blank symbol"; size is the (state, symbol) pair; Fig. 5.1 universal and non-universal curves; "39 state-symbols pairs for which the universality/non-universality question remains open"
[^5]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.119 — "So for the class of machines with program size equal (or greater than) Margenstern's Collatz function simulators the following problem is at least as difficult as solving the Collatz conjecture: give an algorithm that takes one of these machines, an initial configuration and a target configuration as input, and decides whether or not the machine reaches the target from the initial configuration."
[^6]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.120 — "Margenstern has found matching upper and lower bounds (which he calls a frontier) on various syntactic properties of universal 2-symbol Turing machine programs."
[^7]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.121 [synthesis] — §5.4.1: Minsky's simulation algorithm and "why Margenstern had to come up with a completely new simulation algorithm for his restricted machine model"
[^8]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.118 — "the smallest known Turing machines were given by Rogozhin [38] ((2, 18), (4, 6), and (5, 5)), Kudlek and Rogozhin [7] (3, 9), and Neary and Woods [31] ((5, 5), (6, 4), (9, 3) and (15, 2)). ... The halting problem has been shown to be decidable for the following state-symbol pairs: (2, 2) [6, 33], (3, 2) [35], (2, 3) (Pavlotskaya, unpublished), (1, n) [5] and (n, 1) (trivial) for n ⩾ 1."
[^9]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.118-119 — "Thus there are no universal machines of this size that have the property of halting exactly when the simulated Turing machine halts."
[^10]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.119-120 [synthesis] — Margenstern: (11, 2), (5, 3), (4, 4), (3, 6), (2, 10); Baiocchi: (10, 2), (5, 3), (4, 4), (3, 5), (2, 8); unary encodings take O(x) per iteration, Margenstern's (11, 2) and (5, 3) use binary and take O(log x)
[^11]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.120-121 [synthesis] — colours = number of distinct triples (α, D, δ); Pavlotskaya: standard universal machines with 3 colours, none with 2; Margenstern: non-erasing universal machines with 5 colours, none with 4; non-erasing machines "are permitted to only overwrite blank symbols"
[^12]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.120 [synthesis] — laterality number = minimum of left-move and right-move instruction counts; Margenstern and Pavlotskaya: universal with 2, none with 1; Margenstern: non-erasing universal with 3, none with 2
[^13]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.120-121 [synthesis] — (Turing machine, finite automaton) pair; the automaton writes a symbol on entering a blank cell, depending on both states; "a 2-state, 3-symbol Turing machine that uses only 5 instructions and is universal"; "via a 58-page proof, that the halting problem is decidable for such machines with 4 instructions"
[^14]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.122-123 — "The smallest known 2-symbol universal Turing machine [31] uses 15 left-move instructions. Surprisingly, Margenstern's managed to give 2-symbol universal Turing machines with very few left-move instructions: a Turing machine with 59 states and only 6 left-move instructions [21], another machine with 190 states and only 3 left-move instructions [12, 21], and a 218-state non-erasing machine with only 3 left-move instructions [16,21]."
[^15]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.121 — "Minsky [28] constructed a 7-state, 4-symbol universal Turing machine that simulates 2-tag systems and his machine's simulation algorithm was the inspiration for many of the small universal machines to follow"
[^16]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.122 (Fig. 5.2) [synthesis] — productions on the left separated by b; σᵢ encoded as eⁱd; Stage 1 marks off one b per e to locate P(σᵢ); Stage 2 deletes the second symbol and copies P(σᵢ) to the right end; Stage 3 unmarks the productions
[^17]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.122 [synthesis] — left scans in several contexts cost states and symbols; information in e, d, b words "must not be destroyed during these leftward scans"; on a 2-symbol machine the left-move count would further increase
[^18]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.123-124 (Fig. 5.3) [synthesis] — productions in reverse order; stage bit at the left end; "The 6 left-move instructions are split into two disjoint sets of 3 instructions. The first set scans left when the stage bit should remain unchanged and the second set scans left when the stage bit should change."
[^19]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.124 [synthesis] — "with only 3 left-move instructions ... we can send only 1 type of signal to the left"; the machine "repeatedly copies the entire configuration to the right"; end-words u/v (stage 0) and c/k (stage 1); the rightmost word becomes the new leftmost word, updated as it is carried over; the 218-state non-erasing machine "uses a similar algorithm"
