---
title: Universal Turing Machine
category: Concepts
summary: Turing's finite automaton with an unbounded tape that can simulate any other Turing machine — the logical model von Neumann generalized from computation to construction
tags: [concept, turing, universality, computation]
sources: [tsra-editors-introduction]
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
the point of view of automata.[^2] The Part II TOC of
[[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]
shows that von Neumann takes up Turing machines directly in his account of
[[self-reproduction](pages/self-reproduction.md)]: Ch. 1 has a section on "The Richard
paradox and Turing machines". Ch. 5 closes with "Logical universality of the cellular
structure" and "The Universal Constructor".[^3]

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — definition of the universal machine, and its role in the logic of automata

## Related Concepts

- [[self-reproduction](pages/self-reproduction.md)] — von Neumann's construction-universality analogue
- [[theory-of-automata](pages/theory-of-automata.md)] — Turing machines belong to its strict part
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — the finite-automaton building block

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.14 — "A Turing machine is a finite automaton with an indefinitely expandable tape. ... Turing's universal computer U has this property: for any Turing machine M there is a finite program P such that machine U, operating under the direction of P, will compute the same results as M."
[^2]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] pp.25, 27 [synthesis] — "Recursive functions are those functions which can be computed on Turing machines, and so mathematical logic may be treated from the point of view of automata"; the strict part "includes mathematical logic as extended to cover finite automata and Turing machines"
[^3]: raw/von-neumann-theory-of-self-reproducing-automata.pdf pp.vii, ix (Contents) [synthesis] — §1.6.3.2 "The Richard paradox and Turing machines"; §5.1.3 "Logical universality of the cellular structure"; §5.2 "The Universal Constructor CU + (MC + L)"
