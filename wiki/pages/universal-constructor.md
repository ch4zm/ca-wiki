---
title: Universal Constructor
category: Concepts
summary: Von Neumann's automaton that builds any automaton from its description; combined with a description copier and a controller it yields self-reproduction via A + B + C + φ(A + B + C)
tags: [concept, universal-constructor, self-reproduction, von-neumann]
sources: [tsra-lecture-5, tsra-part2-ch1, tsra-part2-ch2]
created: 2026-09-24
updated: 2026-09-24
---

# Universal Constructor

## Description

> **Notation used throughout this wiki.** **A** = universal constructor, **B** = description
> copier, **C** = controller, **P** = optional payload (an extra product), **φ(X)** = the
> description of X (a tape of cells in the cellular model). A self-reproducer is
> (A + B + C) + φ(A + B + C), or (A + B + C + P) + φ(A + B + C + P) with a payload. The
> source uses different and inconsistent letters; the wiki does not follow them.

A universal constructor is an automaton A with this property: given a description φ(X) of
any automaton X, it builds X, using up the description in the process. It is the
construction analogue of the [[universal-turing-machine](pages/universal-turing-machine.md)].
Where Turing's machine reads a description and *computes* what the described machine
would compute, the constructor reads a description and *builds* the described machine.[^1]

**Why build from a description.** Copying an existing automaton directly is hard. Its parts
are joined in every direction, and inspecting them risks disturbing them. Copying a linear
string is easy. Von Neumann therefore builds from a coded description rather than from
the object.[^2] In his kinematic model the description is a chain of rigid elements that
encodes binary digits.[^3]

**The self-reproducing scheme.** Three components:

| Component | Given φ(X), it... |
|---|---|
| **A** — universal constructor | builds X, consuming φ(X) |
| **B** — copier | produces two copies of φ(X) |
| **C** — controller | directs B to copy, A to build from one copy, attaches the other copy to the new X, and cuts X + φ(X) loose |

Neither A nor B is of "higher order" than its product. A's description is as complex as
what it builds, and B only duplicates. Now take X = A + B + C. Supplied with
φ(A + B + C), the aggregate produces (A + B + C) + φ(A + B + C), which is a copy of
itself.[^4]

**No vicious circle.** A, B, and C are defined for an arbitrary X before X is set to
A + B + C, so the self-reference is harmless. The same structure is why Turing's universal
machine involves no vicious circle.[^5]

**Two uses of the description.** The description φ is used twice: once *interpreted*,
when A reads it as instructions, and once *copied* as uninterpreted data, when B duplicates
it. That separation is what lets the scheme escape the paradox that a builder must contain
a complete description of its own product.[^4]

**Extensions.** Adding an arbitrary payload P gives (A + B + C + P) + φ(A + B + C + P),
which reproduces itself and also builds P as a by-product. A mutation in the P part of the
description is inherited by later generations. This is how the scheme models heredity (see
[[self-reproduction](pages/self-reproduction.md)]).[^6]

Von Neumann first presented the scheme in the
[[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] model. Part II of
[[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]
carries it out in a cellular structure (Ch. 5 §5.2).[^7]

**In the cellular model.** Inside a [[cellular-automaton](pages/cellular-automaton.md)], the description φ is a linear tape of cells
outside the automaton. It lists the bounding rectangle of the target and the state of every
cell in it, as base-k digits separated by commas and ending in a period. Any automaton fits
this format, so a single constructor that reads the tape is construction-universal. The same
tape also supplies the unbounded memory needed for logical universality.[^8] Offspring are
built in a quiescent state, so that partly built parts do not react, and are then activated
by a single starting stimulus. Successive offspring are placed at shifted coordinates so
that descendants never collide.[^9] Why the copier copies the description rather than the
original is explained in [[descriptions-vs-originals](pages/descriptions-vs-originals.md)].
The constructor places cells with a [[construction-arm](pages/construction-arm.md)]: extend a path, write a cell, retract. A fixed
device can build any finite pattern this way from two stimulus strings, but it is always
larger than what it builds. This is exactly why self-reproduction needs a constructor that
reads an external description, rather than one that stores its own construction program.[^10] The rule itself is [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)].

## Appearances in Sources

- [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] — the rule and the construct-and-retract technique it uses
- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — the cellular version: description tape, universal plan, and activation
- [[tsra-lecture-5](pages/tsra-lecture-5.md)] — the A + B + C scheme in the kinematic model

## Related Concepts

- [[construction-arm](pages/construction-arm.md)] — the mechanism by which it places cells
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] — the rule it is designed in
- [[descriptions-vs-originals](pages/descriptions-vs-originals.md)] — why the copier copies the description
- [[cellular-automaton](pages/cellular-automaton.md)] — the medium of the cellular version
- [[self-reproduction](pages/self-reproduction.md)] — what the scheme achieves
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the computational model it generalizes
- [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] — the setting of the first version
- [[complexity-threshold](pages/complexity-threshold.md)] — the constructor exists only above the threshold

[^1]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.83-84 [synthesis] — the approach is modeled on Turing's universal automata; given a description chain φ(X), the constructing automaton consumes it and builds X from free parts
[^2]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.83-84 [synthesis] — building from a logical description is simpler than copying an object; an existing automaton's parts connect in all directions, while a linear chain is easy to copy
[^3]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.83 [synthesis] — binary tape of rigid elements: a side element at a node is 1, its absence 0 (Fig. 2)
[^4]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.84-85 [synthesis] — A and B individually are not of higher order than their products; control C sequences copying, building, attaching, and cutting loose; with X = A + B + C the system reproduces itself
[^5]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.85 [synthesis] — A, B, and C are defined for arbitrary X before X is chosen, so "the process is not circular"
[^6]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.86-87 [synthesis] — adding a payload yields a by-product; mutations in the payload part are inherited
[^7]: raw/von-neumann-theory-of-self-reproducing-automata.pdf p.ix (Contents) — §5.2 "The Universal Constructor"
[^8]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.113-118 [synthesis] — description tape with digit, comma, and period states; the universal plan (bounding rectangle plus every cell's state) encoded on it gives construction-universality; the tape also closes the gap to logical universality
[^9]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.126-129 [synthesis] — secondaries are built quasi-quiescent and started by a single stimulus; successive descendants are shifted so they don't interfere
[^10]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.155-156 [synthesis] — editor: construct-and-retract builds any finite quiescent array from two binary sequences; the constructing array is always larger, circumvented by a universal constructor with attached self-description
