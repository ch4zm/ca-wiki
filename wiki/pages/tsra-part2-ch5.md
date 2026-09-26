---
title: "Theory of Self-Reproducing Automata — Part II, Ch. 5: Automata Self-Reproduction"
category: Sources
summary: Burks's completion of von Neumann's design — the memory control finished and its interference problem solved (including a crossing organ), an initially quiescent universal Turing machine, the two-path constructing arm and constructing unit, and the self-reproducing automaton itself
tags: [von-neumann, burks, 29-state, self-reproduction, universal-constructor, turing-machine, engineering]
sources: [tsra-part2-ch5]
created: 2026-09-24
updated: 2026-09-26
---

# Theory of Self-Reproducing Automata — Part II, Ch. 5: Automata Self-Reproduction

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 251–296 (PDF pp. 266–311)
**Date ingested:** 2026-09-24
**Type:** book chapter (entirely editorial: Burks's completion of the unfinished manuscript)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

> The whole chapter is in Burks's brackets. Burks's letters are mapped onto the wiki's
> notation (see [[universal-constructor](pages/universal-constructor.md)]): his D(M) is
> φ(M); his universal constructor M_c is the constructor A; his modified constructor
> M_c*, which also copies the tape, is A + B + C in one unit; his universal Turing
> machine M_u, when attached, plays the payload P. Full crosswalk: [[notation-map](pages/notation-map.md)].

## Summary

Von Neumann's manuscript stops partway through the memory control of the
[[cellular-tape](pages/cellular-tape.md)]. In Ch. 5 Burks finishes the design and then
carries it through, one step at a time, to a self-reproducing automaton in
[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)].[^1]

The chapter works through the program's questions in order:[^2]

| Step | Result |
|---|---|
| §5.1.1–5.1.2 | the memory control is finished and made to work; a tape unit with unlimited memory can be embedded as an **initially quiescent** automaton |
| §5.1.3 | any finite automaton can be embedded too, so an initially quiescent **universal Turing machine** exists in the rule: the rule is logically universal |
| §5.2 | the constructing arm and constructing unit are designed, so a **universal constructor** exists: construction-universal |
| §5.3 | the constructor is modified to copy its tape, giving **self-reproduction**, also with a universal Turing machine as payload |

Burks's closing claim: "In this cellular structure, self-reproduction is a special case of
construction, and construction and computation are similar activities."[^3]

## Finishing the memory control (§5.1.1)

Six more sections of the manuscript survive and then break off. They are mostly delay
calculations, and most of them are wrong because of von Neumann's Ch. 3
([[tsra-part2-ch3](pages/tsra-part2-ch3.md)]) sizing errors.
Burks summarizes them instead of reproducing them.[^1] The finished memory control is
87 cells wide and 547 high. It has a read-write-erase unit (320 × 31), that unit's control
(545 × 22), and a [[coded-channel](pages/coded-channel.md)]. The channel codes are 9-bit
sequences that start with a one and contain exactly three more ones, which gives 56
codes.[^4]

**Delays.** Each control organ needs a precisely timed delay. For example, a periodic
pulser has to run for about 6n steps, but the stop signal takes a fixed ~1200-step path
through the memory control and back. So each start signal must be held back by roughly 2000
extra steps, and the amount varies by up to about 100 from one control organ to
another.[^5] Von Neumann planned the shared part of this delay as four winding paths of
1972 cells each. His error in the height of one channel section leaves room for paths only
45 cells high, which is too short. Burks's fixes give more than one step of delay per cell:
alternate confluent and ordinary cells (1½ steps per cell), or use two repeaters of
relatively prime periods 41 and 47 whose outputs coincide after 1927 steps. Alternatively,
run all the delays through a single path.[^6] With the fixes the channel needs 39 distinct
codes, so the 56 available are enough.[^7]

**Speed.** One lengthening step of the tape takes about 36n + 13,000 time units and one
shortening step about 48n + 20,000, where n is the position of the cell being scanned.[^7]

## The interference problem (§5.1.2)

When n is about 200, the coded sequence that starts a periodic pulser arrives in the main
channel at the same moment as the one that should stop it. The two overlap into a third
code and trigger the wrong decoder, so von Neumann's memory control fails for certain loop
lengths.[^8] Burks gives two solutions:

1. **Avoid those lengths.** Never use tape cells below x₂₅₀. This widens the memory control
   by 250 cells, to 337 wide and 547 high, and about 99% of the added area is blank. It works but is
   inelegant.[^9]
2. **Cross the wires.** The interference comes from serial design. Von Neumann's machine
   does one thing at a time, like his EDVAC, and does not use the medium's capacity for
   parallel processing. The trouble would disappear if signal paths could cross.[^10] A
   crossing primitive would add states. Instead, J. E. Gorman designed a **crossing organ**
   built from existing states (Fig. 42). Four such organs let stop signals go directly from
   the counters and cut out most of the delay circuitry.[^11]

Crossing organs contain active cells, which breaks a design constraint. Burks names the
constraint here: an **initially quiescent automaton** is a finite area whose cells are all
in one of the 10 quiescent states (U, the eight quiescent transmission states, or the
quiescent confluent C₀₀). It is started by a stimulus at its edge. Everything a
constructor builds is of this kind.[^12] So the crossing organs are built passive, with
their active cells replaced by the quiescent versions. The machine's starting stimulus
first sends a code that makes four small constructing devices start each organ's clocks,
and only then does the memory control run.[^13] Burks considers neither solution ideal, but
says elegance does not matter here: von Neumann wanted an existence proof.[^14]

## Logical universality (§5.1.3)

A finite automaton is given by three functions of its state and the bit just read: the next
state, the bit to write, and the direction (±1) to move. Burks embeds it as one copy of a
**state organ** (Fig. 43) per state, joined by a coded channel. Each state organ routes
control to its successor according to those functions, and eight channels connect it to
the memory control. Initial quiescence is kept by having the starting stimulus inject the
first state's codes.[^15] Adding the tape gives Burks's result: "We have shown how to embed
in von Neumann's 29-state cellular structure an initially quiescent automaton which
performs the computations of a universal Turing machine. Hence this cellular structure is
logically universal."[^16]

The embedded machines are slow. Each machine step takes many time units of the cellular
automaton, and more as the loops grow. They compute the same results as the machines they
simulate, but not in real time.[^17]

## The universal constructor (§5.2)

**The constructing arm (§5.2.1).** The secondary (constructed) automaton occupies an
α × β rectangle whose lower-left corner is at (x₁, y₁) in the first quadrant, and the state
of each cell (i, j) is given by λᵢⱼ, one of the 10 quiescent states.[^18] Von Neumann's
tape design used a *single-path* method, in which the whole path is converted between
ordinary and special transmission whenever the tip needs the other kind. Each conversion
costs a sequence proportional to the path length.[^19] His rough notes contain something
better: a *two-path* [[construction-arm](pages/construction-arm.md)]. It has an ordinary
path and a special path side by side, joined at a head. Both kinds of stimulus are always
available at the tip, so no path ever needs converting.[^20]

The arm has five operations: horizontal advance, vertical advance, horizontal retreat,
vertical retreat, and injecting a starting stimulus. Each retreat leaves the two vacated
cells in chosen quiescent states γ and δ. Every operation is a fixed pulse sequence of at
most 47 pulses, whatever the arm's length.[^21]

**The construction algorithm** (Fig. 50, assuming β is even):[^22]

1. Extend the arm to the upper-left corner of the target area: x₁ + 2 horizontal advances,
   then y₁ + β vertical advances.
2. Repeat β/2 times: advance α − 2 cells horizontally, then retreat α − 2 cells horizontally
   laying down two rows of the target, then retreat twice vertically.
3. Inject the starting stimulus from below into the cell at (x₁ + ½, y₁ + ½).
4. Withdraw: y₁ vertical and x₁ + 2 horizontal retreats, leaving U behind.

Other quadrants need only extra head designs. Construction also assumes the target area is
blank, a wide enough blank path leads to it, and nothing else interferes.[^23]

**Redesigning the memory control (§5.2.2).** The two-path arm can also run the tape (Fig.
51). Reading still uses 10101. The four tape operations (lengthen or shorten, and leave a 0
or a 1) each become a fixed sequence independent of n. That removes all the 6n delay
machinery, and the memory control shrinks to a simplified read-write-erase unit and a coded
channel.[^24] Burks thinks von Neumann saw this. The design had grown much more complex
than von Neumann expected (his 1952 letter planned Ch. 2 at about twice Ch. 1's length).
Once he had the two-path arm, he would have wanted to redo Ch. 3 and start Ch. 4 afresh,
and he never found the time. Even so, the old design was the first proof that a tape unit
with unlimited memory can be embedded in the rule.[^25]

**The constructing unit (§5.2.3).** A full design is in Thatcher. Burks sketches enough to
show that one exists.[^26] The tape holds a period; then x₁, y₁, α, β, each followed by a
comma; then every λᵢⱼ; then a closing period. The numbers are written in tally form: a
number k is k + 1 copies of the "one" character. That makes 14 characters in all (zero,
one, comma, period, and the ten λ values). Each is 4 bits, never 0000, plus a fifth marker
bit, stored in five cells.[^27]

The tape delivers bits at irregular times, but the arm needs each code at exact successive
times. Burks gives two ways to turn one into the other. One is a tree of 30 state organs
that selects a fixed sequence. The other, which needs less apparatus, is a
**static-dynamic converter** (Fig. 53): four periodic pulsers hold the bits, and four
delayed decoders release them in phase.[^28] The constructing unit then runs the algorithm,
counting tallies with the marker bits.[^29] The constructing unit together with the tape is
the universal constructor: "for each initially quiescent automaton M, there is a coded
description D(M) of M such that, when D(M) is placed on a tape L attached to M_c, M_c will
construct M."[^30]

**Computing vs. constructing.** The universal Turing machine and the universal constructor
have the same shape: a finite automaton plus a tape unit. The Turing machine's output is a
computation and the constructor's output is a construction, and both produce it by sending
signals into constructing arms.[^31]

## Self-reproduction (§5.3)

**The questions, restated (§5.3.1).** Burks recasts von Neumann's five questions for the
29-state rule: (A) logical universality, (B) constructibility, (C) construction
universality, (D) self-reproduction, alone and with a universal Turing machine attached,
and (E) evolution. Von Neumann never came back to evolution.[^32] Constructibility is
answered from Ch. 2: every initially quiescent automaton can be built by some active
automaton.[^33] Not every configuration can be built, though. Burks's simple example is a
3 × 3 block of the sensitized state S₀ surrounded by C₀₀ cells. He relates this to Moore's
[[garden-of-eden](pages/garden-of-eden.md)] configurations.[^34]

**The construction (§5.3.2).** A + φ(A) alone builds another A with no tape, so the
offspring cannot reproduce. Burks therefore modifies the constructor. The tape now holds a
period, φ(M), a period, the tape contents M should receive, and a period. The modified
constructor does three things:[^35]

1. builds M from φ(M);
2. gives M a tape with the specified contents, or, if no contents are specified, a copy of
   φ(M) itself;
3. sends M its starting stimulus.

Step 2 is a plain tape copy that the arm can do. With the modified constructor as
A + B + C, (A + B + C) + φ(A + B + C) builds (A + B + C) + φ(A + B + C): "Hence, a
self-reproducing automaton can be embedded in von Neumann's 29-state cellular
structure."[^36] With a universal Turing machine attached as the payload P,
(A + B + C + P) + φ(A + B + C + P) reproduces itself and can also compute.[^37]

## Key Takeaways

- **Every one of von Neumann's questions except evolution is answered yes.** The 29-state
  rule is computation-universal, construction-universal, and self-reproductive.[^3]
- **Initial quiescence is the governing constraint.** A constructor can only build
  quiescent patterns, so everything, including crossing organs and the constructor itself,
  has to start quiescent and be switched on.[^12]
- **Constant-cost arm operations.** The two-path arm makes every construction step a fixed
  sequence of at most 47 pulses, and applied to the tape it would have removed most of the
  memory control's complexity.[^21][^24]
- **Serial design causes the bugs.** The interference problem comes from building a serial,
  EDVAC-like machine in a medium that allows parallel processing.[^10]
- **Construction and computation are the same kind of process** in this medium.[^31]

## Entities & Concepts

- [[universal-constructor](pages/universal-constructor.md)]
- [[self-reproduction](pages/self-reproduction.md)]
- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)]
- [[crossing-organ](pages/crossing-organ.md)]
- [[garden-of-eden](pages/garden-of-eden.md)]
- [[construction-arm](pages/construction-arm.md)]
- [[cellular-tape](pages/cellular-tape.md)]
- [[coded-channel](pages/coded-channel.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]
- [[signal-coding-organs](pages/signal-coding-organs.md)]

## Relation to Other Wiki Pages

The chapter completes what [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] leaves unfinished
and carries out the scheme that [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] and
[[tsra-lecture-5](pages/tsra-lecture-5.md)] outline. It also points ahead to later work:
Thatcher's and Codd's designs, and Moore ([[edward-f-moore](pages/edward-f-moore.md)]) and Myhill ([[john-myhill](pages/john-myhill.md)]) on Garden-of-Eden configurations
(Moore's paper is [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)], Myhill's
[[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)]; see [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]).

[^1]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.251 [synthesis] — the manuscript continues for six further sections and abruptly terminates; mainly delay calculations, most wrong owing to Ch. 3 errors; summarized, not reproduced
[^2]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.265-266, 270-271, 286, 293-296 [synthesis] — the tape-unit, logical-universality, universal-constructor, and self-reproduction results stated in italics at the end of each stage
[^3]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.296 — "His 29-state cellular structure is computation-universal, construction-universal, and self-reproductive. In this cellular structure, self-reproduction is a special case of construction, and construction and computation are similar activities."
[^4]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.251-252 [synthesis] — RWE 320 × 31, RWEC 545 × 22; each coded sequence begins with a one, contains exactly three other ones, length 9 or less, giving 56; MC 547 × 87
[^5]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.254-256 [synthesis] — the upper periodic pulser must run about 6n; delay Δ₃ about 1200; extra delay needed in D, Z, and W about 2000; variation between control organs no more than about 100
[^6]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.257-258 [synthesis] — W₁–W₄ planned at height 68, width 29, area 1972; the CC₁ error limits them to height 45; confluent/ordinary alternation gives 1½ units per cell; repeaters of periods 41 and 47 coincide after 1927; alternative single path through W
[^7]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.258-259 [synthesis] — MC needs 39 coded sequences, confirming 56 is adequate; lengthening about 36nˢ + 13,000, shortening about 48nˢ + 20,000
[^8]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.259-260 [synthesis] — for nˢ about 200 the start sequence for a periodic pulser overlaps the stop sequence from CC₁; corruption by interference in the main channel
[^9]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.260-261 [synthesis] — never use cells x₀ … x₂₄₉; MC extended 250 cells, 337 wide and 547 high; all but about 1% of the added area unexcitable; "most inelegant"
[^10]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.261 [synthesis] — the structure allows parallel data processing but the design does one thing at a time, like the EDVAC; the interference problem would not arise if wires could cross
[^11]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.261-264 [synthesis] — a crossing primitive would add states; crossing organ of Fig. 42 designed by J. E. Gorman; four crossing organs greatly reduce the delay circuitry
[^12]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.264 [synthesis] — "we define an *initially quiescent automaton* to be a finite area of von Neumann's 29-state cellular structure every cell of which is in 1 of the 10 quiescent states U, T_uα0, and C₀₀"; the secondary is started by a stimulus on its periphery
[^13]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.264-265 [synthesis] — crossing organs built with passive states; each gets a constructing device and decoder; the starting stimulus sends a code that starts the clocks via constructing arms
[^14]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.265 [synthesis] — neither solution ideal; inelegance not relevant to von Neumann's purpose, an existence proof
[^15]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.267-269 [synthesis] — FA defined by functions A, X, E; one state organ SO per state interconnected by a coded channel; eight channels to MC; the starting stimulus injects γⱼ and γₖ
[^16]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.270 — "We have shown how to embed in von Neumann's 29-state cellular structure an initially quiescent automaton which performs the computations of a universal Turing machine. Hence this cellular structure is logically universal."
[^17]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.270 [synthesis] — each step s takes several time units t, longer as the loops grow; the embedded automata compute the same results but not at the same rate
[^18]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.271 [synthesis] — secondary of width α and height β with lower-left cell at (x₁, y₁), first quadrant; each λᵢⱼ one of the quiescent states
[^19]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.272-273 [synthesis] — single path construction procedure: the whole path is changed between ordinary and special; each change needs a sequence proportional to the path length
[^20]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.273-274 [synthesis] — four pages of rough notes; the constructing arm is two adjacent parallel paths, one ordinary and one special, terminating at a head; never necessary to change a whole path
[^21]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.275-277 [synthesis] — five operations: horizontal advance, vertical advance, horizontal and vertical retreat with γ-δ, injection of the starting stimulus; the longest sequence has length 47, independent of the arm's length
[^22]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.275-276 [synthesis] — the algorithm for constructing and starting a secondary on the plan of Fig. 50, presupposing β even
[^23]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.276 [synthesis] — other quadrants need redesigned heads; presupposes an unexcitable target area, a wide enough unexcitable path, and no interfering automaton
[^24]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.277-279 [synthesis] — Fig. 51; read by 10101 as before; operations L0, L1, S0, S1 with lengths independent of n; the 6n delay machinery unnecessary; MC reduces to a simplified RWE and a coded channel
[^25]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.279 [synthesis] — the design turned out much more complex than anticipated (letter to Muntyan, 1952); von Neumann would have revised Ch. 3 and started Ch. 4 afresh; the old MC is the first proof that an unlimited tape unit can be embedded
[^26]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.280 [synthesis] — a complete design for a constructing unit is in Thatcher's "Universality in the von Neumann Cellular Model"; enough is shown to establish that a workable CU exists
[^27]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.280-281 [synthesis] — tape layout period, x₁, y₁, α, β with commas, the λᵢⱼ, a period; 14 characters; four bits avoiding 0000 plus a marker bit, five cells per character; x₁ as x₁ + 1 "one" characters
[^28]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.281-283 [synthesis] — freely timed vs. rigidly timed sequences; first method 30 state organs; second method the static-dynamic converter of Fig. 53, requiring less apparatus
[^29]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.283-285 [synthesis] — the revised algorithm, with CU counting tallies and marking characters
[^30]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.286 — "there can be embedded in von Neumann's 29-state cellular structure a universal constructor M_c with this property: for each initially quiescent automaton M, there is a coded description D(M) of M such that, when D(M) is placed on a tape L attached to M_c, M_c will construct M."
[^31]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.285-286, 294 [synthesis] — M_u and M_c both a finite automaton plus MC + L; the output of M_u is a computation, of M_c a construction, both accomplished by sending signals into constructing arms
[^32]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.286-287, 292 [synthesis] — questions (A)–(E) with sub-questions, reformulated for the 29-state structure; evolution remarked on in §§1.7-1.8 but never returned to
[^33]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.292 [synthesis] — for each initially quiescent automaton there are two binary sequences which, fed into Fig. 14, construct it
[^34]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 [synthesis] — not all automata specifiable at time zero can be constructed; a simple example is the 3 × 3 configuration of the sensitized state S₀ surrounded by C₀₀; footnote 12 on Moore's Garden-of-Eden configurations
[^35]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.294-295 [synthesis] — M_c + D(M_c) is not self-reproduction since the constructed M_c lacks a tape; tape layout period, D(M), period, T(M), period; M_c* constructs M, gives it a tape with T(M) or a copy of D(M), and starts it
[^36]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.295 — "Hence, a self-reproducing automaton can be embedded in von Neumann's 29-state cellular structure."
[^37]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.295-296 [synthesis] — (M_u + M_c*) + D(M_u + M_c*) constructs a copy of itself and can carry out a computation; answers (D2)
