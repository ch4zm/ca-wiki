---
title: Universal Turing Machine
category: Concepts
summary: Turing's finite automaton with an unbounded tape that can simulate any other Turing machine — the logical model von Neumann generalized from computation to construction
tags: [concept, turing, universality, computation]
sources: [tsra-editors-introduction, tsra-lecture-2, tsra-part2-ch4]
created: 2026-09-24
updated: 2026-09-24
---

# Universal Turing Machine

## Description

A Turing machine is a finite automaton with an indefinitely expandable tape. Turing
proved that there is a universal machine *U* with this property: for any Turing machine
*M* there is a finite program *P* such that *U*, directed by *P*, computes the same
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
cell per step, because a finite control cannot store an unbounded address.[^8]

## Appearances in Sources

- [[tsra-part2-ch4](pages/tsra-part2-ch4.md)] — a Turing machine realized in the 29-state CA
- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — definition of the universal machine, and its role in the logic of automata
- [[tsra-lecture-2](pages/tsra-lecture-2.md)] — integral method, universality threshold, doing vs. predicting

## Related Concepts

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
