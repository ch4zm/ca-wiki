---
title: Universal Turing Machine
category: Concepts
summary: Turing's finite automaton with an unbounded tape that can simulate any other Turing machine — the logical model von Neumann generalized from computation to construction
tags: [concept, turing, universality, computation]
sources: [tsra-editors-introduction, tsra-lecture-2, tsra-part2-ch4, tsra-part2-ch5, statistical-mechanics-of-cellular-automata, universality-and-complexity-in-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Universal Turing Machine

## Description

A Turing machine is a finite automaton with an indefinitely expandable tape. Turing
proved that there is a universal machine *U* with this property: for any Turing machine
*M* there is a finite program *π* such that *U*, directed by *π*, computes the same
results as *M*.[^1]

In von Neumann's
[[theory-of-automata](pages/theory-of-automata.md)], Turing machines make up part of the
theory's "strict" (logical) half. Through Gödel and Turing, recursive functions are
exactly those computable by Turing machines, so mathematical logic can be treated from
the point of view of automata.[^2] Von Neumann calls Turing's the *integral* approach: it
axiomatizes what the whole automaton does, without saying what its parts are, in contrast
to the synthetic McCulloch–Pitts approach.[^3]

**Universality and its threshold.** A universal automaton can imitate any automaton,
even a more complicated one. A lack of complexity in the machine is made up for by more
complex instructions. This works only once the machine has reached a definite minimum
level of complexity; below it, no instructions are enough.[^4] Von Neumann regarded this
as the first appearance of "the attribute of universality," and noted that it involves
no vicious circle, because the extra complexity comes in through the instructions.[^5]

**Doing vs. predicting.** Universality has a matching limit: "you can build an organ
which can do anything that can be done, but you cannot build an organ which tells you
whether it can be done" (the halting problem).[^6] This underlies the
[[description-vs-object-complexity](pages/description-vs-object-complexity.md)] conjecture.

The Part II TOC of
[[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]
shows that von Neumann takes up Turing machines directly in his account of
[[self-reproduction](pages/self-reproduction.md)]: Ch. 1 has a section on "The Richard
paradox and Turing machines". Ch. 5 closes with "Logical universality of the cellular
structure" and "The Universal Constructor".[^7]

**Embedded in a cellular automaton.** Von Neumann builds a Turing machine inside his
29-state CA. A finite-state controller plus a [[cellular-tape](pages/cellular-tape.md)] (a row of cells reached by an
extendible wire loop) behaves exactly like finite control plus tape. The head moves ±1
cell per step, because a finite control cannot store an unbounded address.[^8] Burks completes the construction in Ch. 5. Any finite automaton is built as one state organ per state, joined by a coded channel. Adding the tape gives an [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] that performs a universal Turing machine's computations, so the rule is logically universal. The embedded machine gets the same results, only much more slowly.[^9] The universal constructor has the same shape, a finite automaton plus a tape unit. Its output is a construction rather than a computation.[^10]

**Universality in other cellular automata.** Wolfram treats any cellular automaton as a
computer. The initial configuration is the program and data, and the evolution is the
computation. Unlike a Turing machine's single head, every cell is updated at every
step.[^11] He lists the known universal cases as of 1983. The simplest universal Turing
machine then known had 7 states and 4 symbols. Smith (1971) showed that an 18-state
one-dimensional cellular automaton with three-cell neighbourhoods can simulate it.
Otherwise universality is shown by building "wires", NAND gates and memories out of
cellular structures. The [[game-of-life](pages/game-of-life.md)] does this with glider
streams. Banks (1971) gave a 3-state type-I (five-cell) 2D universal rule, and Toffoli
(1977) a 2-state one that needs an infinite nonzero background. There were early signs of
a 5-state one-dimensional universal rule (all cited via Wolfram and not read).[^12]
Wolfram judged the elementary two-state rules too simple to be universal.[^13] He adds an
idea that goes beyond computation. A universal cellular automaton can simulate any other
cellular automaton through an encoding, and if the encoding is simple, the simulated rule
should inherit the simulator's *statistical* behaviour
([[self-organization](pages/self-organization.md)]).[^14]

**Universality as a class of behaviour.** Wolfram (1984) turns universality into a
conjecture about a whole class of rules. Class 4 of the
[[wolfram-classes](pages/wolfram-classes.md)] is conjectured to be exactly the rules capable
of universal computation.[^15] If a rule is universal, no general finite algorithm can say
whether a given start will die out or leave persistent structures, just as no algorithm
solves the halting problem. Its behaviour cannot be found by any shortcut much simpler
than running it.[^16] For code 20 Wolfram measures a "halting probability", the fraction
of small random starts that die out, of about 0.93.[^17] Whether a given rule is universal
is itself undecidable in general, because the structures needed may be arbitrarily large.
Only infinite cellular automata can be universal. A finite one has finitely many states
and can compute only the "space-bounded" functions.[^18] He also connects the idea to
*algorithmic probability* (Chaitin), the chance that a universal computer given random
input produces a given output, and defines an *evolutionary probability* for a structure
to appear after t steps (cited via Wolfram and not read).[^19]

## Appearances in Sources

- [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] - class 4 conjectured universal; undecidability of dying out and of universality itself; halting probability of code 20
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — universality across cellular automata: Smith's 18-state 1D rule, Life, Banks, and simulation by encoding
- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] — an initially quiescent universal Turing machine in the 29-state CA
- [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] — a Turing machine realized in the 29-state CA
- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — definition of the universal machine, and its role in the logic of automata
- [[tsra-lecture-2](pages/tsra-lecture-2.md)] — integral method, universality threshold, doing vs. predicting

## Related Concepts

- [[wolfram-classes](pages/wolfram-classes.md)] - class 4 conjectured to be the universal rules
- [[game-of-life](pages/game-of-life.md)] — universal through glider-stream circuits
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] — judged in 1983 too simple for universality
- [[cellular-tape](pages/cellular-tape.md)] — the cellular realization of the tape
- [[descriptions-vs-originals](pages/descriptions-vs-originals.md)] — the halting problem and Richard's paradox motivate passive self-description
- [[universal-constructor](pages/universal-constructor.md)] — the construction analogue: builds any automaton from its description

- [[self-reproduction](pages/self-reproduction.md)] — von Neumann's construction-universality analogue
- [[theory-of-automata](pages/theory-of-automata.md)] — Turing machines belong to its strict part
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — the finite-automaton building block
- [[description-vs-object-complexity](pages/description-vs-object-complexity.md)] — follows from the impossibility of predicting behavior

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.14 — "A Turing machine is a finite automaton with an indefinitely expandable tape. ... Turing's universal computer U has this property: for any Turing machine M there is a finite program P such that machine U, operating under the direction of P, will compute the same results as M."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.25, 27 [synthesis] — "Recursive functions are those functions which can be computed on Turing machines, and so mathematical logic may be treated from the point of view of automata"; the strict part "includes mathematical logic as extended to cover finite automata and Turing machines"
[^3]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.43 — "Turing started by axiomatically describing what the whole automaton is supposed to do, without telling what its elements are, just by describing how it's supposed to function."
[^4]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.50 — "... Thus a lesser degree of complexity in an automaton can be compensated for by an appropriate increase of complexity of the instructions. ... This is only true if A is sufficiently complicated, if it has reached a certain minimum level of complexity."
[^5]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.50 — "here, for the first time, one deals with something which has the attribute of universality, which has the ability to do anything that anybody can do. You also see that there is no vicious circle in it, because of the manner in which the extra complexity is brought in (by giving more elaborate instructions)."
[^6]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.51 — "you can build an organ which can do anything that can be done, but you cannot build an organ which tells you whether it can be done."
[^7]: raw/von-neumann-theory-of-self-reproducing-automata.pdf pp.vii, ix (Contents) [synthesis] — §1.6.3.2 "The Richard paradox and Turing machines"; §5.1.3 "Logical universality of the cellular structure"; §5.2 "The Universal Constructor"
[^8]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.204-206 [synthesis] — relative addressing by ±1 steps following Turing; the constructing unit specified as a finite automaton with next-state, write, and move functions operating the tape
[^9]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.267-270 [synthesis] — FA embedded as state organs interconnected by a coded channel; an initially quiescent universal Turing machine can be embedded, so the structure is logically universal; embedded devices operate slowly relative to the cellular time frame
[^10]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.285-286 [synthesis] — both M_u and M_c are a finite automaton plus MC + L; the output of M_u is a computation, of M_c a construction
[^11]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.629 [synthesis] — the initial configuration represents a "program" and "initial data", processed by evolution into the "output"; analogous to a Turing machine's tape, but "instead of considering a single 'head' ... the cellular automaton evolution simultaneously affects all sites at each time step"
[^12]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] — simplest universal Turing machine has seven internal states and four symbols; Smith (1971): an eighteen-state one-dimensional three-site-neighbourhood cellular automaton simulates it; wires, NAND gates and memories; Life via glider streams; Banks (1971) three-state type-I 2D; two states with an infinite background (Toffoli 1977a); "preliminary indications" of a five-state 1D universal rule
[^13]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.630 — "the elementary cellular automata considered here and in Secs. II and III are not of sufficient complexity to be capable of universal computation."
[^14]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.629-630 [synthesis] — universal cellular automata may simulate any other cellular automaton; the interpreter is an encoding of configurations; "so long as the encoding defined by the interpreter is sufficiently simple, the statistical characteristics of the evolution of configurations in the universal cellular automaton will be shared by the cellular automaton being simulated"
[^15]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.31 - "These analogies lead to the speculation that class 4 cellular automata are characterized by the capability for universal computation."
[^16]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.32 [synthesis] - "no general finite algorithm can predict whether a particular initial configuration in a computationally universal cellular automaton will evolve to the null configuration after a finite time", analogous to "the insolubility of the halting problem for universal Turing machines"; the value cannot be determined "by any 'short-cut' procedure much simpler than explicit simulation"
[^17]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.32-33 [synthesis] - Fig. 14: "the fraction of configurations which generate no persistent structures (essentially the 'halting probability') is approximately 0.93"
[^18]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.32-33 [synthesis] - "Only infinite cellular automata may be capable of universal computation; finite cellular automata ... may therefore evaluate only a subset of all computable functions (the 'space-bounded' ones)"; "it is impossible to determine in general whether a particular cellular automaton is capable of universal computation"
[^19]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.34 [synthesis] - "algorithmic probability" [24] (Chaitin) of a structure generated by a universal computer from random input, invariant up to constant factors; "evolutionary probability" p_E(t); "logical depth" [25] (Bennett)
