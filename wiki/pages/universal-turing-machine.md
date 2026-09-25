---
title: Universal Turing Machine
category: Concepts
summary: Turing's finite automaton with an unbounded tape that can simulate any other Turing machine - the logical model von Neumann generalized from computation to construction
tags: [concept, turing, universality, computation]
sources: [tsra-editors-introduction, tsra-lecture-2, tsra-part2-ch4, tsra-part2-ch5, statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-25
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
Langton (1990) proposes a dynamical analogue, the *freezing problem*: will a cellular
automaton near the order-chaos transition eventually freeze into short-period behaviour?
He calls it "quite likely" undecidable, and conjectures that the halting problem is a
special case of it ([[edge-of-chaos](pages/edge-of-chaos.md)]).[^7]

The Part II TOC of
[[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]
shows that von Neumann takes up Turing machines directly in his account of
[[self-reproduction](pages/self-reproduction.md)]: Ch. 1 has a section on "The Richard
paradox and Turing machines". Ch. 5 closes with "Logical universality of the cellular
structure" and "The Universal Constructor".[^8]

**Embedded in a cellular automaton.** Von Neumann builds a Turing machine inside his
29-state CA. A finite-state controller plus a [[cellular-tape](pages/cellular-tape.md)] (a row of cells reached by an
extendible wire loop) behaves exactly like finite control plus tape. The head moves ±1
cell per step, because a finite control cannot store an unbounded address.[^9] Burks completes the construction in Ch. 5. Any finite automaton is built as one state organ per state, joined by a coded channel. Adding the tape gives an [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] that performs a universal Turing machine's computations, so the rule is logically universal. The embedded machine gets the same results, only much more slowly.[^10] The universal constructor has the same shape, a finite automaton plus a tape unit. Its output is a construction rather than a computation.[^11]

**Universality in other cellular automata.** Wolfram treats any cellular automaton as a
computer. The initial configuration is the program and data, and the evolution is the
computation. Unlike a Turing machine's single head, every cell is updated at every
step.[^12] He lists the known universal cases as of 1983. The simplest universal Turing
machine then known had 7 states and 4 symbols. Smith (1971) showed that an 18-state
one-dimensional cellular automaton with three-cell neighbourhoods can simulate it.
Otherwise universality is shown by building "wires", NAND gates and memories out of
cellular structures. The [[game-of-life](pages/game-of-life.md)] does this with glider
streams. Banks (1971) gave a 3-state type-I (five-cell) 2D universal rule, and Toffoli
(1977) a 2-state one that needs an infinite nonzero background. There were early signs of
a 5-state one-dimensional universal rule (all cited via Wolfram and not read).[^13]
Wolfram judged the elementary two-state rules too simple to be universal.[^14] He adds an
idea that goes beyond computation. A universal cellular automaton can simulate any other
cellular automaton through an encoding, and if the encoding is simple, the simulated rule
should inherit the simulator's *statistical* behaviour
([[self-organization](pages/self-organization.md)]).[^15]

**Later universality results (Kari 2005).** Kari reports two universality theorems
built on Turing-machine simulation. The [[game-of-life](pages/game-of-life.md)] is
universal, and whether a finite Life pattern dies is undecidable (Berlekamp, Conway and
Guy). [[rule-110](pages/rule-110.md)], a two-state nearest-neighbour rule, is universal: Wolfram
conjectured this in the 1980s and later proved it with Cook, overturning the 1983 judgement
above for the elementary family.[^16] Reversible rules can be universal too. Toffoli (1977) simulated any
d-dimensional CA in a (d + 1)-dimensional reversible one. Morita and Harao (1989)
simulated [[reversible-turing-machine](pages/reversible-turing-machine.md)]s, which can be universal (Bennett 1973), in 1D
reversible CA ([[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]).[^17]
Kari separates this Turing-machine universality from
[[intrinsic-universality](pages/intrinsic-universality.md)], the ability to simulate
every CA on infinite configurations.[^18]

## Appearances in Sources

- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - the freezing problem; class IV and universal computation at the phase transition
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - universality of Life and rule 110; universal reversible CA; Turing vs intrinsic universality
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — universality across cellular automata: Smith's 18-state 1D rule, Life, Banks, and simulation by encoding
- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] — an initially quiescent universal Turing machine in the 29-state CA
- [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] — a Turing machine realized in the 29-state CA
- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — definition of the universal machine, and its role in the logic of automata
- [[tsra-lecture-2](pages/tsra-lecture-2.md)] — integral method, universality threshold, doing vs. predicting

## Related Concepts

- [[edge-of-chaos](pages/edge-of-chaos.md)] - the freezing problem, a dynamical analogue of halting
- [[game-of-life](pages/game-of-life.md)] — universal through glider-stream circuits
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] — judged in 1983 too simple for universality
- [[cellular-tape](pages/cellular-tape.md)] — the cellular realization of the tape
- [[descriptions-vs-originals](pages/descriptions-vs-originals.md)] — the halting problem and Richard's paradox motivate passive self-description
- [[universal-constructor](pages/universal-constructor.md)] — the construction analogue: builds any automaton from its description

- [[self-reproduction](pages/self-reproduction.md)] — von Neumann's construction-universality analogue
- [[theory-of-automata](pages/theory-of-automata.md)] — Turing machines belong to its strict part
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — the finite-automaton building block
- [[description-vs-object-complexity](pages/description-vs-object-complexity.md)] — follows from the impossibility of predicting behavior
- [[rule-110](pages/rule-110.md)] - a universal elementary rule
- [[intrinsic-universality](pages/intrinsic-universality.md)] - the CA-native, stronger notion
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - universal reversible rules
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - halting-problem reductions give undecidable CA questions
- [[reversible-turing-machine](pages/reversible-turing-machine.md)] - the reversible special case, also universal

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.14 — "A Turing machine is a finite automaton with an indefinitely expandable tape. ... Turing's universal computer U has this property: for any Turing machine M there is a finite program P such that machine U, operating under the direction of P, will compute the same results as M."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.25, 27 [synthesis] — "Recursive functions are those functions which can be computed on Turing machines, and so mathematical logic may be treated from the point of view of automata"; the strict part "includes mathematical logic as extended to cover finite automata and Turing machines"
[^3]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.43 — "Turing started by axiomatically describing what the whole automaton is supposed to do, without telling what its elements are, just by describing how it's supposed to function."
[^4]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.50 — "... Thus a lesser degree of complexity in an automaton can be compensated for by an appropriate increase of complexity of the instructions. ... This is only true if A is sufficiently complicated, if it has reached a certain minimum level of complexity."
[^5]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.50 — "here, for the first time, one deals with something which has the attribute of universality, which has the ability to do anything that anybody can do. You also see that there is no vicious circle in it, because of the manner in which the extra complexity is brought in (by giving more elaborate instructions)."
[^6]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.51 — "you can build an organ which can do anything that can be done, but you cannot build an organ which tells you whether it can be done."
[^7]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.33-34 [synthesis] - Sec. 7.3: "a natural analog of Turing's Halting problem in what we call the Freezing problem"; "It is quite likely that the freezing problem is undecidable"; Sec. 8.1: "the halting problem can be seen as a specific instance of the more general freezing problem for dynamical systems"
[^8]: raw/von-neumann-theory-of-self-reproducing-automata.pdf pp.vii, ix (Contents) [synthesis] — §1.6.3.2 "The Richard paradox and Turing machines"; §5.1.3 "Logical universality of the cellular structure"; §5.2 "The Universal Constructor"
[^9]: [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] pp.204-206 [synthesis] — relative addressing by ±1 steps following Turing; the constructing unit specified as a finite automaton with next-state, write, and move functions operating the tape
[^10]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.267-270 [synthesis] — FA embedded as state organs interconnected by a coded channel; an initially quiescent universal Turing machine can be embedded, so the structure is logically universal; embedded devices operate slowly relative to the cellular time frame
[^11]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.285-286 [synthesis] — both M_u and M_c are a finite automaton plus MC + L; the output of M_u is a computation, of M_c a construction
[^12]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.629 [synthesis] — the initial configuration represents a "program" and "initial data", processed by evolution into the "output"; analogous to a Turing machine's tape, but "instead of considering a single 'head' ... the cellular automaton evolution simultaneously affects all sites at each time step"
[^13]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] — simplest universal Turing machine has seven internal states and four symbols; Smith (1971): an eighteen-state one-dimensional three-site-neighbourhood cellular automaton simulates it; wires, NAND gates and memories; Life via glider streams; Banks (1971) three-state type-I 2D; two states with an infinite background (Toffoli 1977a); "preliminary indications" of a five-state 1D universal rule
[^14]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.630 — "the elementary cellular automata considered here and in Secs. II and III are not of sufficient complexity to be capable of universal computation."
[^15]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.629-630 [synthesis] — universal cellular automata may simulate any other cellular automaton; the interpreter is an encoding of configurations; "so long as the encoding defined by the interpreter is sufficiently simple, the statistical characteristics of the evolution of configurations in the universal cellular automaton will be shared by the cellular automaton being simulated"
[^16]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 [synthesis] - Theorem 1 (Berlekamp et al.): Life universal, death of a finite configuration undecidable; Wolfram's 1980s conjecture [74] and its proof by "him and Cook [76]"; Theorem 2: rule 110 universal
[^17]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 [synthesis] - Toffoli [65]: any d-dimensional CA simulated by a (d + 1)-dimensional reversible CA; Morita and Harao [54]; "reversible Turing machines can be computationally universal [4]"; Theorem 8
[^18]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.23 [synthesis] - "The universality of GOL and rule 110 is based on performing Turing machine simulations in the CA. But also a stronger form of universality exists that is inherent to CA"
