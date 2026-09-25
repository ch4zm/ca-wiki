---
title: "Automata, Universality, Computation — Ch. 6: Constructing Reversible Turing Machines by Reversible Logic Element with Memory"
category: Sources
summary: Morita's survey of reversible logic elements with memory - the rotary element, the count and universality of 2-state elements, a synchronization-free billiard-ball realization, and a simpler construction of any reversible Turing machine as an infinite circuit of rotary elements
tags: [reversible-computing, reversible-turing-machines, rotary-element, billiard-ball-model, logic-elements, morita]
sources: [aucm-ch6-reversible-turing-machines-by-rlem]
created: 2026-09-24
updated: 2026-09-24
---

# Automata, Universality, Computation — Ch. 6: Constructing Reversible Turing Machines by Reversible Logic Element with Memory

**Source:** assets/adamatzky-2015-automata-universality-computation.pdf, printed pp. 127–138 (PDF pp. 136–147)
**Date ingested:** 2026-09-24
**Type:** book chapter (survey and tutorial)
**Author:** Kenichi Morita
**Part of:** [[automata-universality-computation](pages/automata-universality-computation.md)]

## Summary

Reversible computing is computation whose every step can be traced back uniquely, which
ties it to reversibility in physics. Its primitives are reversible logic elements, whose
function is one-to-one. Some have no memory (reversible logic gates) and some have
memory.[^1] Morita argues that elements with memory are the more convenient primitive,
because with a suitable one many reversible machines can be built simply.[^2] His
standard example is the rotary element (RE), a 2-state, 4-symbol
[[reversible-logic-element-with-memory](pages/reversible-logic-element-with-memory.md)].[^3]

The chapter covers three things. First, how RLEMs are defined, counted and classified,
and which of them are universal. Second, how an RE can be realized directly in the
[[billiard-ball-model](pages/billiard-ball-model.md)] without synchronizing the balls.
Third, a new construction of any
[[reversible-turing-machine](pages/reversible-turing-machine.md)] as an infinite circuit
of REs, simpler than Morita's earlier one (2001).[^4] Stacking the second on the third
puts a whole reversible Turing machine inside the billiard-ball model.[^5]

## Key Takeaways

- **The rotary element.** It holds a bar that is either horizontal (state H) or vertical
  (V). A particle entering parallel to the bar passes straight through and the bar stays
  put. A particle entering across the bar turns right and rotates the bar 90°
  counterclockwise. If no particle arrives, nothing happens.[^6]
- **RE is universal.** Any reversible sequential machine can be built from REs alone, and
  so can any reversible Turing machine, as an infinite circuit.[^7]
- **Counting and the universality frontier.** There are (2k)! two-state k-symbol RLEMs: 24,
  720 and 40,320 for k = 2, 3, 4. Up to renaming of states and symbols there are 8, 24 and
  82 classes. Of those, 4, 14 and 55 are non-degenerate: they are not just wires, and not
  equivalent to an element with fewer symbols. Every non-degenerate 2-state RLEM with
  k > 2 can simulate RE and is therefore universal. Among the four non-degenerate 2-symbol
  ones, three are proved non-universal and one is open. Morita presents this as a
  universality frontier in Margenstern's sense
  ([[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)]).[^8]
- **RE in billiard balls without timing.** Building an RE from reversible gates needs many
  gates and exactly synchronized balls. Morita's direct realization uses one stationary
  state ball and reflectors. The signal ball may arrive at any time and any speed. Only
  the interval between its two collisions with the state ball must be exact.[^9]
- **Read by writing.** In the new tape-cell design, the instruction "write 0" or "write 1"
  also reports the old symbol, as R0 or R1. A read is therefore "write 0", followed by
  writing the symbol back. This uses 4 read/write signal types instead of the 8 in the 2001
  design, which needed separate read, write-complement and inverse-read instructions.[^10]

## The construction

**Tape.** Each square of a 2-symbol tape is a *memory cell*: a reversible sequential
machine with state (h, s), where s is the stored symbol and h says whether the head is
there. It has ten input signals, each with a matching output: W0, W1, R0, R1 for writing
and its response, and SL, SLI, SLc and SR, SRI, SRc for shifting.[^11] A cell without the
head passes every signal on to the right, except SLI and SRI. The head cell answers a
write with the old symbol, sent back left. On SL it clears h and sends SLI to its left
neighbour, which sets its own h and answers SLc. Shifting right works the same way.[^12]
Chaining infinitely many RE copies of this cell to the right gives the tape unit.[^13]

**Finite control.** The control is also a reversible sequential machine, so it too is
built from REs. Each quintuple runs as three rounds: W0 to read, W0 or W1 to write, then SL
or SR to shift. The REs are laid out in four rows: one element per state sends the read,
the next row writes and changes state, and the top two rows shift the head.[^14]

**Example.** T_parity is a 5-state reversible machine that decides whether a unary input
is even, complementing each symbol it reads. Its RE circuit starts when a particle enters
"Begin" and ends when the particle leaves by "Accept" or "Reject". Morita's companion
report shows one full run of this circuit in 4,406 figures.[^15]

## Entities & Concepts

- [[reversible-logic-element-with-memory](pages/reversible-logic-element-with-memory.md)]
- [[reversible-turing-machine](pages/reversible-turing-machine.md)]
- [[billiard-ball-model](pages/billiard-ball-model.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]

## Relation to Other Wiki Pages

Kari reports that reversible Turing machines can be universal (Bennett 1973), and that
Morita and Harao (1989) simulated them in 1D reversible CA
([[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]). This chapter
builds such machines from a different primitive, a single logic element with one bit of
memory. The billiard-ball model is also what Margolus's 2D reversible CA simulates
([[margolus-neighbourhood](pages/margolus-neighbourhood.md)]). An RE circuit realized in
billiard balls could therefore in principle run inside that CA (own reasoning; the
chapter does not mention Margolus). The universality count for RLEMs is another exact
frontier, like the ones in
[[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)].

[^1]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.127 — "Reversible computing is a paradigm of computation that is closely related to reversibility in physics. ... The function of a reversible logic element is described by a one-to-one mapping. Thus, the behavior of a reversible logic circuit can be traced backward uniquely with respect to the time axis. There are two types of reversible logic elements: one without memory, which is commonly called a reversible logic gate [5, 19, 20], and one with memory [10, 16]."
[^2]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.127-128 — "in the case of reversible computing, logic elements with memory are also useful. The main reason is that if we use an appropriate reversible logic element with memory, we can construct various reversible computing models easily."
[^3]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.128 [synthesis] — "A rotary element (RE) is an instance of 2-state 4-symbol RLEM that was first introduced in [10]"; M_RE = ({H, V}, {n, e, s, w}, {n′, e′, s′, w′}, δ_RE), Table 6.1
[^4]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.128 [synthesis] — "In this survey, we describe how RLEMs are defined, how they are related to physical reversibility, and how reversible Turing machines (RTMs) can be built by them. In particular, here we give a simpler construction method of RTMs by REs than the one given in [10]"; [10] = Morita, MCU 2001
[^5]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.137 — "if we further implement each RE by a mechanism in the billiard ball model (BBM) as in Figure 6.4, then the whole system of the RTM can be realized in the space of BBM."
[^6]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.128-129 — "The direction of the bar can be either horizontal or vertical, and they represent the states H and V ... When no particle is coming, nothing happens on the RE. If a particle comes from the direction parallel to the bar, then it goes out from the output line of the opposite side without affecting the direction of the bar ... If a particle comes from the direction orthogonal to the bar, then it makes a right turn, and rotates the bar by 90 degrees counterclockwise"
[^7]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.129 — "It is shown that any RSM can be built using only REs [11], and that any reversible Turing machine is realized as an infinite circuit composed only of REs [10]. Hence, in such a sense RE is universal."
[^8]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.129 [synthesis] — (2k)! kinds of 2-state k-symbol RLEMs, 24, 720, 40,320; equivalence classes 8, 24, 82; non-degenerate 4, 14, 55; "As discussed in [9] by Margenstern, it is important to know the frontier between universality and non-universality"; every non-degenerate 2-state k-symbol RLEM with k > 2 simulates RE; of the four non-degenerate 2-symbol ones "three of them has been proved to be non-universal [18], but it is left open for the remaining one"
[^9]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.130-131 [synthesis] — building RE from gates "is not a good method" because many gates and "exact synchronization of two or more moving balls is necessary"; direct realization with one stationary state ball and reflectors; "the signal ball can be given to an input line at any moment and at any speed ... Only the time interval between the first and the second collisions in Figure 6.4(c) should be adjusted exactly"
[^10]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.133-134 [synthesis] — a write also performs a read, "Otherwise, reversibility of the memory cell does not hold"; reading is done by W0 and then rewriting; the construction in [10] separated read and write, used "write complementary symbol" and "inverse-read instructions", "eight kinds of instruction and response symbols", while here "only four kinds of symbols W0, W1, R0, and R1 are used"
[^11]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.133 (Table 6.2) [synthesis] — memory cell state set {(h, s) | h, s ∈ {0, 1}}; ten input symbols W0, W1, R0, R1, SL, SLI, SLc, SR, SRI, SRc, each with a corresponding output symbol
[^12]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.133-134 [synthesis] — δ_C: a cell with h = 0 passes every symbol except SLI and SRI; head cell answers W0/W1 with R0/R1 by the old symbol, sent to the left neighbour; on SL the head cell sets h = 0 and sends SLI left, whose receiver sets h = 1 and sends SLc; SR, SRI, SRc similar
[^13]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.134 — "Connecting an infinite number of copies of this circuit to the right, we have a tape unit for a 2-symbol RTM."
[^14]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.134-135 [synthesis] — "each quintuple of an RTM is executed by producing read, write, and shift instructions consecutively"; W0 to read, then W0 or W1, then SL or SR; REs laid in 4 rows: the 4th row per state sends W0, the 3rd row writes and changes state, the 1st or 2nd rows shift the head
[^15]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.132, 135-136 [synthesis] — Example 1: T_parity with states q0, q1, q2, q_acc, q_rej checks whether a unary number is even, and complements every symbol read; Fig. 6.8 caption: "An example of its whole computing process is shown in 4406 figures in [13]"; the particle enters "Begin" and exits "Accept" or "Reject"
