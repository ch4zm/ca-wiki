---
title: "Theory of Self-Reproducing Automata — Part I, Lecture 2: Rigorous Theories of Control and Information"
category: Sources
summary: Von Neumann's second Illinois lecture (1949) — McCulloch–Pitts nets and Turing machines as synthetic vs. integral theories of automata, universality and its complexity threshold, and the conjecture that complex automata are simpler than their descriptions
tags: [von-neumann, mcculloch-pitts, turing, universality, complexity, logic]
sources: [tsra-lecture-2]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Part I, Lecture 2: Rigorous Theories of Control and Information

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 42–56 (PDF pp. 58–72)
**Date ingested:** 2026-09-24
**Type:** book section (reconstructed lecture, December 1949, with editorial commentary)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

> Bracketed text is the editor's paraphrase or commentary, and the unbracketed lecture
> text is heavily edited. pp. 51–56 are mostly editorial: commentary on Turing machines
> and correspondence with Gödel.

## Summary

This lecture covers the *rigorous* (strict) half of information theory, which von
Neumann treats as another way of doing formal logic.[^1] He presents two theories of
automata that each turned out to be "exactly co-extensive with formal logics": McCulloch
and Pitts's neural networks and Turing's machines.[^2] He contrasts their methods. The
McCulloch–Pitts approach is *synthetic*: it axiomatizes only very simple elements and
lets complexity come from combining them. Turing's approach is *integral*: it
axiomatizes what the whole automaton does, without saying what its parts are.[^3]

The McCulloch–Pitts result says that any behavior you can specify rigorously in finitely
many words can be realized by a network of idealized
[[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]s, so "the generality of
neural systems is exactly the same as the generality of logics."[^4] Turing's result
supplies the [[universal-turing-machine](pages/universal-turing-machine.md)]: an automaton
that, given suitable instructions, imitates any other automaton. It works only above a
definite minimum level of complexity.[^5] Its counterpart is a limit: no automaton can
predict the behavior of an arbitrary automaton.[^6]

Both results feed into a claim about complexity. For simple automata, it is easier to
describe or predict the behavior than to build the object. At high complication, von
Neumann suggests, this reverses, and the object becomes simpler than any description of
what it does ([[description-vs-object-complexity](pages/description-vs-object-complexity.md)]).[^7]

## Key Takeaways

- **Synthetic vs. integral.** An automaton can be specified from its elements up
  (McCulloch–Pitts) or by its overall behavior (Turing). Both methods reach exactly the
  power of formal logic.[^2][^3]
- **Nets equal logic.** Any rigorously and finitely stated behavior can be realized by a
  McCulloch–Pitts network. This shows what is logically possible, not how nature does it.[^4][^8]
- **Universality has a threshold.** Below a certain complexity, no instructions are
  enough. Above it, one automaton can do anything any automaton can do, with the missing
  complexity supplied by the instructions.[^5] Von Neumann: "here, for the first time,
  one deals with something which has the attribute of universality."[^9]
- **Doing vs. predicting.** "You can build an organ which can do anything that can be
  done, but you cannot build an organ which tells you whether it can be done."[^6]
- **Description vs. object.** At high complexity the automaton may be simpler than its
  description. Gödel, asked about it, reads this as a matter of logical type rather than
  length.[^7][^10]

## Entities & Concepts

- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[description-vs-object-complexity](pages/description-vs-object-complexity.md)]
- [[complexity-threshold](pages/complexity-threshold.md)]
- [[theory-of-automata](pages/theory-of-automata.md)]

## Relation to Other Wiki Pages

This lecture is the primary source for claims that
[[tsra-editors-introduction](pages/tsra-editors-introduction.md)] reports second-hand: the
description-vs-object reversal, and the grounding of the logical theory of automata in
McCulloch–Pitts and Turing. Its threshold for universality is the computational
counterpart of the [[complexity-threshold](pages/complexity-threshold.md)] for
self-reproduction.

[^1]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.42 — "Von Neumann said that there are two parts to information theory: the rigorous and the probabilistic. ... the rigorous part of information theory is just a different way of dealing with formal logics."
[^2]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.43 — "Both of them showed that their fictitious mechanisms are exactly co-extensive with formal logics; in other words, that what their automata can do can be described in logical terms and, conversely, that anything which can be described rigorously in logical terms can also be done by automata."
[^3]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.43 — "the synthetic way, and the integral way. McCulloch and Pitts described structures which are built up from very simple elements, so that all you have to define axiomatically are the elements, and then their combination can be extremely complex. Turing started by axiomatically describing what the whole automaton is supposed to do, without telling what its elements are"
[^4]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.45 — "No matter how you formulate your conditions, you can always put a neural network in the box which will realize these conditions, which means that the generality of neural systems is exactly the same as the generality of logics."
[^5]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.50 — "... Thus a lesser degree of complexity in an automaton can be compensated for by an appropriate increase of complexity of the instructions. ... This is only true if A is sufficiently complicated, if it has reached a certain minimum level of complexity. In other words, a simpler thing will never perform certain operations, no matter what instructions you give it; but there is a very definite finite point where an automaton of this complexity can, when given suitable instructions, do anything that can be done by automata at all."
[^6]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.51 — "So, you can construct an automaton which can do anything any automaton can do, but you cannot construct an automaton which will predict the behavior of any arbitrary automaton. In other words, you can build an organ which can do anything that can be done, but you cannot build an organ which tells you whether it can be done."
[^7]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.47 — "There is a good deal in formal logics to indicate that the description of the functions of an automaton is simpler than the automaton itself, as long as the automaton is not very complicated, but that when you get to high complications, the actual object is simpler than the literary description."
[^8]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.46 — "What is not demonstrated by the McCulloch and Pitts result is equally important. It does not prove that any circuit you are designing in this manner really occurs in nature."
[^9]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.50 — "here, for the first time, one deals with something which has the attribute of universality, which has the ability to do anything that anybody can do. You also see that there is no vicious circle in it, because of the manner in which the extra complexity is brought in (by giving more elaborate instructions)."
[^10]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] pp.55-56 — Gödel: "this theorem certainly shows that the description of what a mechanism is doing in certain cases is more involved than the description of the mechanism, in the sense that it requires new and more abstract primitive terms, namely higher types. However, this implies nothing as to the number of symbols necessary, where the relationship may very well be in the opposite direction"
